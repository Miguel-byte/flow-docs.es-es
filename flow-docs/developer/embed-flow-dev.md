---
title: Integración de Microsoft Flow con sitios web y aplicaciones | Microsoft Docs
description: Inserte las experiencias de Microsoft Flow en su aplicación o sitio web
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 738e566a9b064231a3bc2fe8bf7317df2bafbfef
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462818"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integre Microsoft Flow con sitios web y aplicaciones
Inserte Microsoft Flow en su aplicación o sitio web para proporcionar a los usuarios una manera sencilla de automatizar sus tareas profesionales o personales.

Para crear flujos, los usuarios necesitarán **cuenta Microsoft** o una cuenta profesional o educativa en **Azure Active Directory**. Microsoft Flow no admite, por ejemplo, una solución «de marca blanca» que admita cualquier identidad que use el sistema (a menos que ya utilice cuentas Microsoft o AAD).

## <a name="prerequisites"></a>Requisitos previos
* [Compilar un conector personalizado](register-custom-api.md) que conecte el servicio a Microsoft Flow.
* [Crear y publicar una o varias plantillas](../publish-a-template.md) que utilicen la API.

## <a name="show-templates-for-your-scenarios"></a>Presentación de plantillas para sus escenarios
Para empezar, agregue este código para mostrar las plantillas de flujo directamente en su sitio web:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Nota**: Hemos agregado un salto de línea para que el código aparezca mejor en la página.

| Parámetro | Descripción |
| --- | --- |
| locale |El código de región e idioma de cuatro letras para la vista de la plantilla. Por ejemplo, `en-us` representa el inglés de Estados Unidos, mientras que `de-de` representa el alemán. |
| search term |El término de búsqueda para las plantillas que desea mostrar en la vista. Por ejemplo, busque `wunderlist` para mostrar las plantillas de Wunderlist. |
| number of templates |El número de plantillas que desea mostrar en la vista. |
| destination |La página que se abre cuando los usuarios hacen clic en la plantilla. Especifique `details` para mostrar los detalles de la plantilla o especifique `new` para abrir el diseñador de Microsoft Flow. |
| parameters.{name} |Contexto adicional que se pasa en el flujo. |

Si el parámetro de destino es `new`, Microsoft Flow se abre cuando los usuarios hacen clic en una plantilla y pueden crear un flujo en el diseñador. Si desea tener la experiencia completa de trabajar desde dentro de la aplicación, consulte la sección siguiente.

### <a name="passing-additional-parameters-to-the-flow"></a>Paso de parámetros adicionales al flujo
Si el usuario está en un contexto determinado en su sitio web o aplicación, dicho contexto se puede pasar al flujo. Por ejemplo, un usuario puede abrir una plantilla para *Notify me when an item is added to a list* (Notificarme cuando se agrega un elemento a una lista) mientras ve una lista concreta en Wunderlist. Si sigue estos pasos, podrá pasar el identificador de la lista como *parámetro* al flujo:

1. Defina el parámetro de la plantilla de flujo antes de publicarlo. Así es un parámetro, `@{parameters('parameter_name')}`.
2. Pase el parámetro en iframe src. Por ejemplo, agregue `&parameters.listName={the name of the list}` si tiene un parámetro denominado **listName**.

### <a name="full-sample"></a>Ejemplo completo
Para mostrar las cuatro plantillas principales sobre Wunderlist en alemán e iniciar el usuario con **myCoolList**:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Inserción de la administración de flujos
Use el SDK de Flow autenticado para permitir a los usuarios crear y administrar flujos de directamente desde el sitio web o la aplicación (en lugar de navegar hasta el Portal de Microsoft Flow). Para usar el SDK autenticado, es preciso que el usuario inicie sesión en la cuenta de Microsoft o en Azure Active Directory.

> [!NOTE]
> Todos los usuarios que usan Microsoft Flow en la aplicación serán usuarios de Microsoft Flow. No hay forma alguna de ocultar la personalización de marca de Microsoft Flow.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>Inclusión de JavaScript en el SDK autenticado
Para incluir el SDK en el código HTML, siga este ejemplo. También puede descargar, minimizar e incluir el SDK con su producto.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Creación de un contenedor para la vista
Agregue una etiqueta div de HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Se recomienda aplicar cierto estilo a este contenedor para que aparezca con las dimensiones adecuadas:

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

Tenga en cuenta que el IFrame no se representará correctamente por debajo de los 320 píxeles de ancho y no llenará el contenido por encima de 1200 píxeles de ancho. Debería valor cualquier altura.

### <a name="authentication-against-the-sdk"></a>Autenticación con el SDK
Tanto para enumerar los flujos que el usuario ya ha creado como para crear flujos a partir de plantillas, especifique un authToken desde AAD.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https://flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv',
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

Puede encontrar `environmentId` mediante la siguiente llamada de API que devuelve la lista de los entornos a los que el usuario tiene acceso:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

Esto devuelve una respuesta JSON con la lista de entornos y, en esta, puede seleccionar cualquier entorno. También puede buscar el entorno de usuario predeterminado comprobando la propiedad `properties.isDefault=true`.

En este ejemplo, `requestParam` se define como:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Además, `widgetDoneCallback` es una función de devolución de llamada a la que se debe llamar una vez que el host tiene el token. Esto se hace porque la adquisición del token es probablemente un proceso asincrónico. Los parámetros que deben pasarse al llamar a esta función son `(errorResult: any, successResult: any)`. El parámetro successResult dependerá del tipo de devolución de llamada. Para `GetAccessToken` el tipo es:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
