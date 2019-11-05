---
title: Creación de un flujo con Dynamics 365 (en línea) | Microsoft Docs
description: Cree flujos de trabajo útiles mediante una conexión de Dynamics 365 y Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546911"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Creación de un flujo mediante Dynamics 365 (en línea)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Mediante el uso de un conector de Dynamics 365, puede crear flujos que se inician cuando se produce un evento en Dynamics 365, o algún otro servicio, que realiza una acción en Dynamics 365 o algún otro servicio. 

En Microsoft Flow, puede configurar flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, obtener notificaciones, recopilar datos y mucho más. Para obtener más información, consulte Introducción [a Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Para invocar un desencadenador de flujo, la entidad Common Data Service utilizada con el flujo debe tener **Change Tracking** habilitado. Más información: [Habilitar el seguimiento de cambios para controlar la sincronización de datos](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Creación de un flujo a partir de una plantilla
Puede crear un flujo mediante una de las numerosas plantillas disponibles, como estos ejemplos:

* Cuando se crea un objeto en Dynamics 365, se crea un elemento de lista en SharePoint.
* Cree registros de clientes potenciales de Dynamics 365 a partir de una tabla de Excel.
* Copie las cuentas de Dynamics 365 a los clientes en Dynamics 365 para las operaciones.

Para crear un flujo a partir de una plantilla, siga estos pasos.

1. Inicie sesión en el [sitio web de Microsoft Flow](https://flow.microsoft.com/).
2. Pulse o haga clic en **servicios**y, a continuación, haga clic o pulse en **Dynamics 365**.
3. Hay disponibles varias plantillas. Para empezar, seleccione la plantilla que desee.

## <a name="create-a-task-from-a-lead"></a>Crear una tarea a partir de un cliente potencial
Si una plantilla no está disponible para lo que necesita, cree un flujo desde cero. En este tutorial se muestra cómo crear una tarea en Dynamics 365 cada vez que se crea un cliente potencial en Dynamics 365.

1. Inicie sesión en el [sitio web de Microsoft Flow](https://flow.microsoft.com/).
2. Pulse o haga clic en **Mis flujos**y, después, haga clic o pulse en **crear en blanco**.
3. En la lista de desencadenadores de flujo, pulse o haga clic en **Dynamics 365-cuando se crea un registro**.
4. Si se le solicita, inicie sesión en Dynamics 365.
5. En **nombre**de la organización, seleccione la instancia de Dynamics 365 donde quiere que el flujo escuche.
6. En **nombre de entidad**, seleccione la entidad que desea escuchar, que actuará como desencadenador que inicia el flujo.
   
     Para este tutorial, seleccione **leads**.
   
    ![Detalles de flujo](./media/connection-dynamics365/flow-details.png)
    > AÚN Para que el flujo se desencadene en la entidad Dynamics 365, la definición de la entidad debe tener **Change Tracking** habilitado. Vea [Habilitar el seguimiento de cambios para controlar la sincronización de datos](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Pulse o haga clic en **nuevo paso**y, a continuación, haga clic o pulse en **Agregar una acción**.
8. Pulse o haga clic en **Dynamics 365: crear un nuevo registro**.
9. En **nombre**de la organización, seleccione la instancia de Dynamics 365 en la que desea que el flujo cree el registro. Tenga en cuenta que no tiene que ser la misma instancia desde la que se desencadena el evento.
10. En **nombre de entidad**, seleccione la entidad que creará un registro cuando se produzca el evento.
    
     Para este tutorial, seleccione **tareas**.
11. Aparece un cuadro **asunto** . Al hacer clic o pulsar en él, aparece un panel de contenido dinámico donde puede seleccionar cualquiera de estos campos.
    
    * **Apellido**. Si selecciona este campo, el apellido del cliente potencial se insertará en el campo **asunto** de la tarea cuando se cree.
    * **Tema**. Si selecciona este campo, el campo **tema** del cliente potencial se insertará en el campo **asunto** de la tarea cuando se cree.
    
    Para este tutorial, seleccione **tema**.
    
    ![Tema de adición de Flow](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Sugerencia:** En el panel de contenido dinámico, haga clic o pulse en **Ver más** para mostrar más campos asociados a la entidad. Por ejemplo, también puede rellenar el campo **asunto** de la tarea con el campo **nombre**de la compañía, **cliente**, **Descripción**o **correo electrónico** del cliente potencial.
    > 
    > 
12. Pulse o haga clic en **Crear flujo**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Creación de una tarea de Wunderlist desde una tarea de Dynamics 365
En este tutorial se muestra cómo crear una tarea en [Wunderlist](https://www.wunderlist.com) cada vez que se crea una tarea en Dynamics 365. Wunderlist es un servicio basado en Internet que puede usar para crear listas de tareas pendientes, agregar recordatorios o realizar un seguimiento de los recados.

1. Inicie sesión en el [sitio web de Microsoft Flow](https://flow.microsoft.com/).
2. Pulse o haga clic en **Mis flujos**y, después, haga clic o pulse en **crear en blanco**.
3. En la lista de desencadenadores de flujo, pulse o haga clic en **Dynamics 365-cuando se crea un registro**.
4. En **nombre**de la organización, seleccione la instancia de Dynamics 365 donde quiere que el flujo escuche.
5. En **nombre de entidad**, seleccione la entidad que desea escuchar, que actuará como desencadenador para iniciar el flujo.
   
    Para este tutorial, seleccione **tareas**.
6. Pulse o haga clic en **nuevo paso**y, a continuación, haga clic o pulse en **Agregar una acción**.
7. Escriba *crear una tarea*y, luego, pulse o haga clic en **Wunderlist: crear una tarea**.
8. En **ID**. de lista, seleccione **bandeja de entrada**.
9. En **título**, seleccione **asunto** en el panel de contenido dinámico.
10. Pulse o haga clic en **Crear flujo**.  

## <a name="trigger-based-logic"></a>Lógica basada en desencadenador
Desencadenadores como **cuando se crea un registro**, **cuando se actualiza un registro**y **cuando se elimina un registro** , inicie el flujo en unos minutos después de que se produzca el evento.  En raras ocasiones, el flujo puede tardar hasta 2 horas en desencadenarse.

Cuando se produce el desencadenador, el flujo recibe una notificación, pero el flujo se ejecuta en los datos existentes en el momento en que se ejecuta la acción.  Por ejemplo, si el flujo se desencadena cuando se crea un nuevo registro y actualiza el registro dos veces antes de que se ejecute el flujo, el flujo solo se ejecuta una vez con los datos más recientes.

## <a name="specify-advanced-options"></a>Especificar opciones avanzadas
Al agregar un paso a un flujo, puede pulsar o hacer clic en **Mostrar opciones avanzadas** para agregar un filtro o un orden por consulta que controla cómo se filtran los datos en el flujo.

Por ejemplo, puede usar una consulta de filtro para recuperar solo los contactos activos y puede ordenarlos por Apellido. Para ello, escriba la consulta de filtro OData **StatusCode EQ 1** y seleccione **Last Name (apellidos** ) en el panel de contenido dinámico. Para obtener más información acerca de las consultas de filtro y de ordenación, vea [MSDN: $Filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) y [MSDN: $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Consulta OrderBy de flujo](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Prácticas recomendadas al usar opciones avanzadas
Al agregar un valor a un campo, debe coincidir con el tipo de campo si escribe un valor o selecciona uno en el panel de contenido dinámico.

| Tipo de campo | Cómo usar | Dónde encontrar | Name | Tipo de datos |
| --- | --- | --- | --- | --- |
| Campos de texto |Los campos de texto requieren una sola línea de texto o contenido dinámico que sea un campo de tipo texto. Entre los ejemplos se incluyen los campos **categoría** y **Subcategoría** . |**Configuración** > **personalizaciones** > **personalizar las** **entidades** > del sistema > **campos** > de **tareas** |**Categoría** |**Línea de texto única** |
| Campos de entero |Algunos campos requieren un entero o contenido dinámico que sea un campo de tipo entero. Entre los ejemplos se incluyen **porcentaje completado** y **duración**. |**Configuración** > **personalizaciones** > **personalizar las** **entidades** > del sistema > **campos** > de **tareas** |**PercentComplete** |**Número entero** |
| Campos de fecha |Algunos campos requieren una fecha escrita en formato mm/dd/aaaa o contenido dinámico que sea un campo de tipo de fecha. Entre los ejemplos se incluyen **creado en**, **fecha de inicio**, **Inicio real**, **último tiempo de espera**, **finalización real**y **fecha de vencimiento**. |**Configuración** > **personalizaciones** > **personalizar las** **entidades** > del sistema > **campos** > de **tareas** |**CreatedOn** |**Fecha y hora** |
| Campos que requieren un identificador de registro y un tipo de búsqueda |Algunos campos que hacen referencia a otro registro de entidad requieren el ID. de registro y el tipo de búsqueda. |**Configuración** > **personalizaciones** > **personalizar las** **entidades** > del sistema > **campos** > de **cuenta** |**accountID** |**Clave principal** |
|Conjunto de opciones|Los campos de conjuntos de opciones requieren que se pase un valor entero conocido a este tipo de campo.  En el área de personalización de Dynamics 365, puede ver la opción establecer el campo de número entero de respaldo junto con su etiqueta correspondiente.|Configuración > Personalización > personalizar las entidades > del sistema > campos > de cuenta | Método de contacto preferido| Número entero|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Más ejemplos de campos que requieren un identificador de registro y un tipo de búsqueda
A partir de la tabla anterior, a continuación se muestran más ejemplos de campos que no funcionan con valores seleccionados de la lista de contenido dinámico. En su lugar, estos campos requieren un identificador de registro y un tipo de búsqueda introducidos en los campos de PowerApps.

* **Propietario** y **tipo de propietario**.
  
  * El campo **propietario** debe ser un identificador de registro de equipo o usuario válido.
  * El **tipo de propietario** debe ser **systemusers** o **Teams**.
* **Cliente** y **tipo de cliente**.
  
  * El campo **Customer** debe ser un identificador de registro de contacto o cuenta válido.
  * El **tipo de cliente** debe ser **accounts** o **Contacts**.
* **Con respecto** al **tipo**.
  
  * El campo **referente** a debe ser un identificador de registro válido, como una cuenta o un identificador de registro de contacto.
  * El **tipo referente** a debe ser el tipo de búsqueda para el registro, como **cuentas** o **contactos**.

En este ejemplo se agrega un registro de cuenta que corresponde al identificador de registro y se agrega al campo **referente** a de la tarea.

  ![Flujo de la cuenta de tipo recordId y tipo](./media/connection-dynamics365/flow-recordid-account.png)

En este ejemplo también se asigna la tarea a un usuario específico en función del identificador de registro del usuario.

  ![Tipo recordId y tipo de usuario](./media/connection-dynamics365/flow-recordid-user.png)

Para buscar el identificador de un registro, consulte [Buscar el ID](#find-the-records-id) . de registro más adelante en este tema.

> **Importante:** Los campos no deben contener un valor si tienen una descripción de "solo para uso interno". Estos campos incluyen la **ruta de acceso recorrida**, **parámetros adicionales**y **el número de versión de la regla de zona horaria.**
> 
> 

## <a name="find-the-records-id"></a>Buscar el identificador del registro
1. En la aplicación web Dynamics 365, abra un registro, como un registro de cuenta.
2. En la barra de herramientas acciones, haga clic o **Pulse en extraer
   ![** registro emergente](./media/connection-dynamics365/popout.png) (o pulse o haga clic en **Enviar un vínculo por correo electrónico** para copiar la dirección URL completa en el programa de correo electrónico predeterminado).
   
    En la barra de direcciones del explorador Web, la dirección URL contiene el ID. de registro entre los caracteres de codificación% 7B y% 7D.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Temas relacionados
[Solución de problemas de un flujo](fix-flow-failures.md)

[El flujo de la organización Q & A](organization-q-and-a.md)

[Preguntas más frecuentes](frequently-asked-questions.md)

