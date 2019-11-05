---
title: Integración de Microsoft Flow con sitios web y aplicaciones | Microsoft Docs
description: Inserte las experiencias de Microsoft Flow en su sitio web o aplicación.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547705"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integración de Microsoft Flow con sitios web y aplicaciones
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Inserte Microsoft Flow en la aplicación o el sitio web mediante *widgets de Flow* para ofrecer a los usuarios una forma sencilla de automatizar sus tareas profesionales o personales.

Los widgets de flujo son iframes ubicados en un documento host. Este documento apunta a una página en el diseñador de Microsoft Flow. Estos widgets integran la funcionalidad de Microsoft Flow específica en la aplicación de terceros.

Los widgets pueden ser sencillos. Por ejemplo, un widget que representa una lista de plantillas sin comunicación entre el host y el iframe. Los widgets también pueden ser complejos. Por ejemplo, un widget que aprovisiona un flujo a partir de una plantilla y, a continuación, desencadena el flujo a través de una comunicación bidireccional entre el host y el widget.

## <a name="prerequisites"></a>Requisitos previos

- Una **cuenta Microsoft** o
- Una cuenta profesional o educativa

## <a name="use-the-unauthenticated-widget"></a>Usar el widget no autenticado
Para usar el widget plantillas no autenticadas, insértelo directamente en la aplicación host mediante un iframe. No necesita el SDK de JS o un token de acceso. 

### <a name="show-templates-for-your-scenarios"></a>Mostrar plantillas para los escenarios
Para empezar, agregue este código para mostrar las plantillas de Microsoft Flow en el sitio web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Parámetro | Denominación |
| --- | --- |
| configuración regional |Código de idioma y región de cuatro letras para la vista de plantilla. Por ejemplo, `en-us` representa el Inglés de Estados Unidos y `de-de` representa el alemán. |
| término de búsqueda |El término de búsqueda de las plantillas que desea mostrar en la vista. Por ejemplo, busque `wunderlist` para mostrar las plantillas de Wunderlist. |
| número de plantillas |El número de plantillas que desea mostrar en la vista. |
| Destino |La página que se abre cuando los usuarios seleccionan la plantilla. Escriba `details` para mostrar los detalles de la plantilla o escriba `new` para abrir el diseñador de Microsoft Flow. |
| Categoría |Filtra a la categoría de plantilla especificada. | 
| los. Name |Contexto adicional que se va a pasar al flujo. |


Si el parámetro de destino es `new`, el diseñador de Microsoft Flow se abre cuando los usuarios seleccionan una plantilla. Después, los usuarios pueden crear un flujo en el diseñador. Vea la sección siguiente si desea tener toda la experiencia del widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Pasar parámetros adicionales a la plantilla de flujo

Si el usuario está en un contexto específico en el sitio web o la aplicación, es posible que desee pasar ese contexto al flujo. Por ejemplo, un usuario puede abrir una plantilla para *Notificarme cuando se agrega un elemento a una lista mientras se* examina una lista determinada en Wunderlist. Siga estos pasos para pasar el ID. de lista como un *parámetro* al flujo:

1. Defina el parámetro en la plantilla de flujo antes de publicarlo. Un parámetro tiene el siguiente aspecto `@{parameters('parameter_name')}`.
1. Pase el parámetro en la cadena de consulta del elemento src de iframe. Por ejemplo, agregue `&parameters.listName={the name of the list}` si tiene un parámetro denominado **listName**.

### <a name="full-sample"></a>Ejemplo completo

Para mostrar las cuatro principales plantillas de Wunderlist en alemán e iniciar el usuario con **myCoolList**, use este código:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Uso de los widgets de flujo autenticados

En la tabla siguiente se muestra la lista de widgets Microsoft Flow que admiten la experiencia completa en el widget mediante el token de acceso de autenticación de usuario. Tendrá que usar el kit de desarrollo de software (SDK) de JavaScript de Microsoft Flow para insertar los widgets y proporcionar el token de acceso de usuario necesario.

| Tipo de widget    | Característica admitida                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Fluyen          | Muestra una lista de flujos en una pestaña para los flujos personales y compartidos. Edite un flujo existente o cree un nuevo flujo a partir de una plantilla o en blanco. | 
| flowCreation   | Crea un flujo a partir de un identificador de plantilla que proporciona la aplicación host.                                                                | 
| Runtime        | Desencadena un flujo de desencadenador manual o híbrido que proporciona la aplicación host.                                                        | 
| approvalCenter | Inserta solicitudes de aprobación y aprobaciones enviadas.                                                                                        | 
| Templa      | Muestra una lista de plantillas. El usuario elige una para crear un nuevo flujo.                                                                         | 

Use el SDK de flujo autenticado para permitir a los usuarios crear y administrar flujos directamente desde su sitio web o aplicación (en lugar de navegar a Microsoft Flow). Deberá iniciar sesión con su cuenta de Microsoft o Azure Active Directory para usar el SDK autenticado.

> [!NOTE]
> No hay ninguna manera de ocultar la personalización de marca de Microsoft Flow cuando se usan widgets.

## <a name="widget-architecture"></a>arquitectura de widget

Microsoft Flow widgets funcionan mediante la inserción de un iframe que hace referencia a Microsoft Flow en una aplicación host. El host proporciona el token de acceso que requiere el widget de Microsoft Flow. El SDK de Microsoft Flow JS permite que la aplicación host inicialice y administre el ciclo de vida del widget.

![arquitectura de widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Detalles del SDK de JS

El equipo de Microsoft Flow proporciona el SDK de JS para facilitar la integración de widgets de flujo en aplicaciones de terceros. Flow JS SDK está disponible como vínculo público en el servicio Flow y permite que la aplicación host controle los eventos del widget e interactúe con la aplicación Flow enviando acciones al widget. Los eventos y las acciones de widget son específicos del tipo de widget.

### <a name="widget-initialization"></a>Inicialización del widget

La referencia del SDK de Flow JS debe agregarse a la aplicación host antes de inicializar el widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Cree una instancia de SDK de JS pasando los valores de nombre de host y configuración regional opcionales en un objeto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Name     | Requerido/opcional | Denominación                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Opta          | Microsoft Flow nombre de host, por ejemplo, https://flow.microsoft.com        | 
| `locale`   | Opta          | Configuración regional del cliente para el widget (el valor predeterminado es `en-Us` si no se especifica) | 


Una vez creada la instancia de SDK de JS, puede inicializar e insertar un widget de Microsoft Flow en un elemento primario en la aplicación host. Para ello, agregue un elemento HTML div:

```html
<div id="flowDiv" class="flowContainer"></div>
```

A continuación, inicialice el widget de Microsoft Flow con el método `renderWidget()` SDK de JS. Asegúrese de proporcionar el tipo de widget y la configuración correspondiente.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Este es un ejemplo de estilo para el contenedor que puede modificar para que coincida con las dimensiones de la aplicación host.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Estos son los parámetros de `renderWidget()`: 

| Parámetro        | Requerido/opcional | Denominación                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obligatorio          | Identificador de un elemento DIV en la página host donde se insertará el widget.                   | 
| `environmentId`    | Opta          | Los widgets necesitan un identificador de entorno. Si no proporciona un identificador, se usa un entorno predeterminado. | 
| `flowsSettings`    | Opta          | Objeto de configuración de Microsoft Flow                                                                        | 
| `templateSettings` | Opta          | Objeto de configuración de plantilla                                                                    | 
| `approvalSettings` | Opta          | Objeto de configuración de aprobación                                                                    | 

### <a name="access-tokens"></a>Tokens de acceso

Una vez que se ejecuta el SDK de JS `renderWidget()`, el SDK de JS Inicializa un iframe que apunta a la dirección URL del widget Microsoft Flow. Esta dirección URL contiene toda la configuración de los parámetros de la cadena de consulta. La aplicación host necesita obtener un token de acceso Microsoft Flow para el usuario (Azure Active Directory token de JWT con https://service.flow.microsoft.com) de audiencia antes de inicializar el widget. El widget genera un evento `GET_ACCESS_TOKEN` para solicitar un token de acceso del host. El host debe controlar el evento y pasar el token al widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

La aplicación host es responsable de mantener el token y pasarlo con una fecha de expiración válida al widget cuando se solicite. Si el widget está abierto durante períodos más largos, el host debe comprobar si el token ha expirado y actualizar el token si es necesario antes de pasarlo al widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detectar si el widget está listo

Después de la inicialización correcta, el widget genera un evento para notificar que el widget está listo. El host puede escuchar el evento de `WIDGET_READY` y ejecutar cualquier código de host adicional.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Configuración del widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings se puede usar para personalizar la funcionalidad del widget Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parámetro | Requerido/opcional | Denominación | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obligatorio | Usar el GUID de la plantilla cuando el usuario seleccione el botón **crear desde** cero en el widget de flujo | 
| `flowsFilter` | Opta | El widget Microsoft Flow aplica el filtro proporcionado al enumerar los flujos. Por ejemplo, muestre los flujos que hacen referencia a un sitio de SharePoint específico. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Opta | Tiene como valor predeterminado la pestaña activa para mostrar en el widget Microsoft Flow. <br /> Por ejemplo, <br /> ```tab:'sharedFlows' ``` muestra la pestaña equipo<br /> y ``` tab:'myFlows' ``` muestra la pestaña mis flujos. |   

### <a name="templatessettings"></a>TemplatesSettings 

Esto se aplica a todos los widgets que permiten crear flujos a partir de una plantilla, incluidos los widgets de flujos, FlowCreation y plantillas.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parámetro |Requerido/opcional | Denominación                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Opta          | Parámetros de tiempo de diseño que se usan al crear un flujo a partir de una plantilla, por ejemplo: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Opta          | Los valores válidos son ' New ' o ' details '. Cuando se establece en ' details ', se muestra una página de detalles al crear un flujo a partir de una plantilla.     |
| `pageSize` | Opta          | Número de plantillas que se van a mostrar. Tamaño predeterminado = 6 | 
| `searchTerm` | Opta          | Mostrar plantillas que coincidan con el término de búsqueda proporcionado| 
| `templateCategory` | Opta          | Mostrar plantillas en una categoría específica| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Se aplica a los widgets ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parámetro | Requerido/opcional | Denominación | 
|------------|-------------------|--------------| 
| `hideLink`| Opta | Cuando se establece en `true`, el widget oculta los vínculos de aprobación recibido y enviado | 
| `autoNavigateToDetails`| Opta | Cuando se establece en `true`, el widget abre automáticamente los detalles de aprobación cuando solo existe una aprobación. | 
| `approvalsFilter`| Opta | El widget de aprobación aplicará el filtro de aprobación especificado al enumerar las aprobaciones, por ejemplo: el widget de aprobación aplicará el filtro de aprobación especificado al enumerar las aprobaciones, por ejemplo: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Opta | Pestaña activa predeterminada para mostrar en el widget de flujo. <br/> Valores válidos: ' receivedApprovals ', ' sentApprovals ' | 
| `showSimpleEmptyPage`| Opta | Muestra una página vacía cuando no hay ninguna aprobación | 
| `hideInfoPaneCloseButton` | Opta | Oculta el botón de cierre del panel de información (o el host ya tiene un botón Cerrar) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventos de widget

El widget Microsoft Flow admite eventos que permiten que el host escuche los eventos de ciclo de vida de los widgets. El widget Microsoft Flow admite dos tipos de eventos: eventos de notificación unidireccionales (por ejemplo, widget\_Ready) y eventos generados por el widget para capturar datos del host (get\_Access\_token). El host debe usar el método widget. Listen () para escuchar eventos específicos generados por el widget.

### <a name="usage"></a>Uso

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventos admitidos por tipo de widget

| Evento de widget      | Indicaciones                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget cargado correctamente                                      | 
| `WIDGET_RENDERED`   | Widget cargado y representación de la interfaz de usuario completada                      | 
| `GET_ACCESS_TOKEN`  | Solicitud de widget para insertar token de acceso de usuario                      | 
| `GET_STRINGS`       | Permite que el host invalide un conjunto de cadenas de interfaz de usuario que se muestran en el widget. | 

### <a name="runtime-widget"></a>Widget en tiempo de ejecución

| Evento de widget                    | Indicaciones                                     | Data                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Se desencadena y se ha iniciado la ejecución de flujo      |           | 
| `RUN_FLOW_COMPLETED`              | La ejecución de Flow se desencadenó correctamente             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | El usuario seleccionó el botón listo en la ejecución de flujo       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Botón Cancelar seleccionado por el usuario en la ejecución de flujo     |           | 
| `FLOW_CREATION_SUCCEEDED`         | El flujo se creó correctamente           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Se desencadena cuando el host debe cerrar el widget |       | 

### <a name="flow-creation-widget"></a>Widget de creación de flujo

| Evento de widget             | Indicaciones                                  | Data  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | No se pudo crear el flujo                     |       | 
| `WIDGET_CLOSE`             | Se desencadena cuando el host debe cerrar el widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | No se pudo cargar la plantilla              |       | 
| `FLOW_CREATION_SUCCEEDED`  | El flujo se creó correctamente        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget de aprobación

| Evento de widget                      | Indicaciones                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Estado de aprobación recibido cambiado  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Estado de aprobación enviada cambiado      | 

El evento **GET\_Strings** le permite personalizar el texto de algunos de los elementos de la interfaz de usuario que se muestran en el widget. Se pueden personalizar las siguientes cadenas:

| Clave de cadena                     | Uso en el widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texto que se muestra en el botón Crear flujo en el widget creación de flujo y tiempo de ejecución                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Valor inicial que se va a usar para el nombre de flujo en el widget de creación de flujo. Solo se usa cuando la opción allowCustomFlowName está habilitada. | 
| `FLOW_CREATION_HEADER`           | Encabezado que se va a usar al crear un flujo en el widget creación de flujo y tiempo de ejecución                                                    | 
| `INVOKE_FLOW_HEADER`             | Encabezado que se va a usar al invocar un flujo en el widget en tiempo de ejecución                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texto que se muestra en el botón que se usa para invocar o ejecutar un flujo en el widget en tiempo de ejecución                                                       | 

### <a name="example"></a>Ejemplo

Llame a `widgetDoneCallback` pasando un objeto JSON con pares clave-valor de clave de cadena y texto para reemplazar el valor predeterminado.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Acciones de widget

El host usa acciones de widget para enviar una acción o un mensaje específico al widget. El SDK de widget JS proporciona el método `notify()` para enviar un mensaje o una carga JSON al widget. Cada acción de widget admite una firma de carga específica.

### <a name="usage"></a>Uso

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Ejemplo 

Invocar un flujo enviando el siguiente comando a un widget en tiempo de ejecución 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget en tiempo de ejecución

| Acción del widget                               | Indicaciones                                                      | Interfaz de parámetros  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Desencadena una ejecución de flujo                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Desencadena una ejecución de flujo por plantilla                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtiene el esquema del desencadenador para un flujo                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Cancela cualquier actividad pendiente y genera un evento WIDGET_CLOSE. |                      | 

### <a name="flow-creation-widget"></a>Widget de creación de flujo

| Acción del widget                               | Indicaciones                                                      | Interfaz de parámetros  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crea un flujo para la plantilla seleccionada.                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crea un flujo para la definición de plantilla seleccionada.          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Cancela cualquier actividad pendiente y genera un evento WIDGET_CLOSE. |                      | 

### <a name="approval-widget"></a>Widget de aprobación

| Acción del widget  | Indicaciones                                           | Interfaz de parámetros  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Cierra el panel info (información) que muestra los detalles de aprobación  | N/A                  | 

## <a name="configuring-your-client-application"></a>Configuración de la aplicación cliente

Tendrá que configurar la aplicación cliente con ámbitos de servicio de Flow (permisos delegados). Si la aplicación de Azure Active Directory (AAD) utilizada para la integración del widget usa un flujo de autorización de "concesión de código", la aplicación de AAD debe preconfigurarse con permisos delegados que son compatibles con Microsoft Flow. Esto proporciona permisos delegados que permiten a la aplicación:

-   Administrar aprobaciones
-   Leer aprobaciones
-   Actividades de lectura
-   Administrar flujos
-   Leer flujos

Siga estos pasos para seleccionar uno o varios permisos delegados:

1.  Vaya a https://portal.azure.com 
2.  Seleccione **Azure Active Directory**.
3.  Seleccione **registros de aplicaciones** en **administrar**.
4.  Escriba la aplicación de terceros que se configurará para los ámbitos de servicio de Flow.
5.  Seleccione **configuración**.
      arquitectura de ![widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Seleccione **los permisos necesarios** en **acceso de API**/
7. Seleccione **Agregar**.
8. Elija **seleccionar una API**.
      arquitectura de ![widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Busque **Microsoft Flow servicio** y selecciónelo. Nota: para poder ver Microsoft Flow servicio, el inquilino debe tener al menos un usuario de AAD que haya iniciado sesión en el portal de Flow (<https://flow.microsoft.com>).
10. Elija los ámbitos de flujo necesarios para la aplicación y, a continuación, seleccione **Guardar**.
      arquitectura de ![widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

La aplicación obtendrá ahora un token de servicio de flujo que contiene permisos delegados en la solicitud de \'SCP ' en el token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Widgets de flujo de inserción de aplicaciones de ejemplo 

En la sección de recursos se proporciona una aplicación de una sola página (SPA) de JavaScript de ejemplo para que pueda experimentar con los widgets de flujo de incrustación en una página host. El uso de la aplicación de ejemplo requiere el registro de una aplicación de AAD con el flujo de concesión implícito habilitado.

### <a name="registering-an-aad-app"></a>Registro de una aplicación de AAD

1.  Inicie sesión en el [Azure portal](https://portal.azure.com/).
2.  En el panel de navegación izquierdo, seleccione **Azure Active Directory**y, a continuación, seleccione **registros de aplicaciones** (versión preliminar) \> nuevo registro.
3.  Cuando aparezca la página **registrar una aplicación** , escriba un nombre para la aplicación.
4.  En **tipos de cuenta compatibles**, seleccione **cuentas** en cualquier directorio de la organización.
5.  En la sección **URL de redireccionamiento** , seleccione la plataforma web y establezca el valor en la dirección URL de Application\'s basada en el servidor Web.  Configure este valor en http://localhost:30662/ para ejecutar la aplicación de ejemplo.
6.  Seleccione **registrar**.
7.  En la página **información general** de la aplicación, anote el valor de identificador de la aplicación (cliente).
8.  El ejemplo requiere que esté habilitado el [flujo de concesión implícita](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) . En el panel de navegación izquierdo de la aplicación registrada, seleccione **autenticación**.
9.  En **Configuración avanzada**, bajo **concesión implícita**, active las casillas **token de identificador** y **tokens de acceso** . Los tokens de identificador y los tokens de acceso son necesarios, ya que esta aplicación debe iniciar sesión en los usuarios y llamar a la API de Flow.
10. Seleccione **Guardar**.

### <a name="running-the-sample"></a>Ejecutar el ejemplo
<!-- todo where should I download from? -->
1.  Descargue el ejemplo y cópielo en una carpeta local del dispositivo.
2.  Abra el archivo index. html en la carpeta FlowSDKSample y modifique el `applicationConfig` para actualizar el `clientID` al ID. de la aplicación que registró anteriormente.
    arquitectura de ![widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  La aplicación de ejemplo está configurada para usar los ámbitos de flujo **. Read. All** y **Flow. Manage. All.** Puede configurar ámbitos adicionales actualizando la propiedad **flowScopes** en el objeto **applicationConfig** .
4.  Ejecute estos comandos para instalar la dependencia y ejecutar la aplicación de ejemplo:
    > \> NPM instalar \> node Server. js
5. Abra el explorador y, a continuación, escriba http://localhost:30662
6. Seleccione el botón **iniciar sesión** para autenticarse en AAD y adquirir un token de acceso de flujo.
7. El cuadro de texto **token de acceso** contiene el token de acceso.
    arquitectura de ![widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Seleccione el widget **flujos de carga** o el **Widget cargar plantillas** para insertar los widgets correspondientes.
    arquitectura de ![widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Vínculo de [descarga](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)de la aplicación de ejemplo.

## <a name="resources"></a>Recursos

### <a name="widget-test-pages"></a>Páginas de prueba de widgets

Obtenga más información sobre la integración y configuración de widgets:

- Widget de plantillas: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget en tiempo de ejecución: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widgets del centro de aprobaciones: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget de flujos: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Configuraciones regionales de widget compatibles

Si la configuración regional inicializada no aparece en la lista, Flow usará de forma predeterminada la configuración regional admitida más cercana.

| configuración regional     | módulo                   | 
|------------|----------------------------| 
| BG-BG      | Búlgaro (Bulgaria)       | 
| CA-es      | Catalán (España)            | 
| CS-cz      | Checo (República Checa)     | 
| da-DK      | Danés (Dinamarca)           | 
| de-de      | Alemán (Alemania)           | 
| el-GR      | Griego (Grecia)             | 
| en-US      | Inglés (Estados Unidos)    | 
| es-es      | Español (Castilian)        | 
| ET-EE      | Estonio (Estonia)         | 
| EU-es      | Euskera (España)             | 
| fi-fi      | Finés (Finlandia)          | 
| fr-fr      | Francés (Francia)            | 
| GL-es      | Gallego (España)           | 
| alta-HU      | Húngaro (Hungría)        | 
| HI-in      | Hindi (India)              | 
| hr-HR      | Croata (Croacia)         | 
| identificador ID.      | Indonesio (Indonesia)     | 
| ti      | Italiano (Italia)            | 
| JP-JP      | Japonés (Japón)           | 
| kk-kz      | Kazajo (Kazajistán)        | 
| ko-KR      | Coreano (Corea)             | 
| lt-LT      | Lituano (Lituania)     | 
| LV: LV      | Letón (Letonia)           | 
| MS-My      | Malayo (Malasia)           | 
| NB-no      | Noruego (bokmål)         | 
| NL-nl      | Holandés (Países Bajos)        | 
| PL-PL      | Polaco (Polonia)            | 
| pt-br      | Portugués (Brasil)        | 
| PT-pt      | Portugués (Portugal)      | 
| ro-ro      | Rumano (Rumania)         | 
| RU-ru      | Ruso (Rusia)           | 
| SK-sk      | Eslovaco (Eslovaquia)          | 
| SL-si      | Esloveno (Eslovenia)       | 
| Sr-Cyrl-RS | Serbio (cirílico, Serbia) | 
| Sr-Latn-RS | Serbio (Latino, Serbia)    | 
| SV-se      | Sueco (Suecia)           | 
| TH-th      | Tailandés (Tailandia)            | 
| TR-tr      | Turco (Turquía)           | 
| RU-UA      | Ucraniano (Ucrania)        | 
| vi-vn      | Vietnamita (Vietnam)      |
