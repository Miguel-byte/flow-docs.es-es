---
title: Información para editar flujos de IU de escritorio | Microsoft Docs
description: Aprenda a editar flujos de IU de escritorio.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589811"
---
# <a name="edit-desktop-ui-flows"></a>Editar flujos de IU de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Los flujos de interfaz de usuario de escritorio automatizan las aplicaciones de escritorio de Windows. Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) para obtener más información sobre los problemas con los que puede encontrarse, soluciones alternativas para estos problemas y escenarios que no se admiten en esta versión preliminar.

## <a name="prerequisites"></a>Requisitos previos
Flujo de la interfaz de usuario del escritorio. [Cree un flujo de IU de escritorio ahora](create-desktop.md#create-and-test-desktop-ui-flows) si no tiene uno para editar.

## <a name="edit-actions"></a>Editar acciones

![Editar acciones](../media/edit-desktop/edit-actions.png "Editar acciones")

Puede editar la grabación para:

-   Modifique el valor para las acciones que lo admiten.
-   Elimine un paso.
-   Elimine toda la grabación.
-   Cambiar el orden de las acciones con arrastrar y colocar. Tenga cuidado con esto, ya que puede interrumpir la coherencia de la grabación.

Los parámetros avanzados permiten cambiar:

-  Retraso después de realizar la acción. Por ejemplo, puede Agregar un retraso de un segundo si cambia PT0S a PT1S. Esto puede ser útil cuando la aplicación de destino tiene un tiempo de respuesta lento que no se completa antes del siguiente paso del flujo de la interfaz de usuario.
-   El [selector](edit-desktop.md#set-the-selector) para el elemento de la interfaz de usuario de destino.

## <a name="add-a-recording"></a>Agregar una grabación

Es posible que desee grabar el flujo de la interfaz de usuario en varias sesiones. Una vez completada la primera grabación, puede continuar de la siguiente manera:

1. Inicie sesión en [Power Automatic](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **flujos de interfaz de usuario (vista previa)** .
1. Seleccione el flujo de la interfaz de usuario que desea editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Seleccione **Editar**. 
1. Seleccione **nuevo paso**.

   ![Nuevo paso](../media/edit-desktop/new-step.png "Nuevo paso")

1. Seleccione **grabar aplicación** en la lista de acciones.

   ![Grabar aplicación](../media/edit-desktop/select-record-ui-actions.png "Grabar aplicación")

1. Seleccione **iniciar la grabadora**.

   ![Seleccionar la grabadora de Launch](../media/create-windows-ui-flow/select-launch-recorder.png "Seleccionar la grabadora de Launch")

   El control de la grabadora se muestra en la parte superior de la pantalla.

   ![El control de la grabadora](../media/create-windows-ui-flow/recorder-control.png "El control de la grabadora")

1. Inicie la aplicación que desea grabar.

     >[!TIP]
     >Al mantener el mouse sobre los controles de la aplicación, observará que un contorno azul resalta cada control. Espere siempre el resaltado azul antes de seleccionar un control.
     >
     >Si el resaltado azul no aparece alrededor del elemento, es posible que no se grabe correctamente.

1. Seleccione **registro** en el control de la grabadora.

1. Siga los pasos de la interfaz de usuario de la aplicación que va a grabar y seleccione **listo** en el control de la grabadora.
1. Seleccione **Guardar**y, a continuación, pruebe el flujo de la interfaz de usuario.

## <a name="add-a-manual-action"></a>Agregar una acción manual

Una vez que haya grabado una aplicación con al menos una acción, puede Agregar manualmente cualquiera de las siguientes acciones para esa aplicación.

| **Actuar**          | **Comentario**                                                       |
|---------------------|-------------------------------------------------------------------|
| Cerrar aplicación   |                                                                   |
| Clic con el botón derecho         |                                                                   |
| Enviar claves           | Envíe claves y combinaciones de teclas, como CTRL + C.                             |
| Clic con el botón primario          |                                                                   |
| Obtener texto            | Lea el texto de un elemento de la interfaz de usuario y úselo como salida. |
| Escribir texto          |                                                                   |
| Obtener elemento habilitado | Comprueba si un elemento de la interfaz de usuario está habilitado o deshabilitado.         |
| Clear (elemento)       | Borre el valor de un elemento de la interfaz de usuario editable.             |
| Esperar segundos    | Espere antes de continuar con el paso siguiente.                           |

Siga estos pasos para agregar una acción manual:

1. Inicie sesión en [Power Automatic](https://flow.microsoft.com).
1. Seleccione **Mis flujos** > **flujos de interfaz de usuario (vista previa)** .
1. Seleccione el flujo de la interfaz de usuario que desea editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Seleccione **Editar**. 
1. Seleccione la tarjeta de grabación que contiene los pasos a los que desea agregar un nuevo paso.
   La tarjeta se expande y muestra los pasos grabados.

   ![Seleccionar tarjeta de grabación](../media/edit-desktop/manual-select-recording-card.png)

1. Seleccione **Agregar una acción** en la tarjeta de grabación, justo debajo del último paso grabado.
   Verá la lista de acciones manuales mencionadas anteriormente en el tutorial. 

1. Seleccione la acción que desea agregar. Aquí, he seleccionado **obtener elemento habilitado**, pero puede seleccionar cualquier acción que tenga sentido para su escenario.

   ![Seleccione la acción que desea agregar. png](../media/edit-desktop/select-action-to-add.png)

Una vez agregada la acción, tendrá que establecer el **selector** en las opciones avanzadas de la acción.

![Opciones avanzadas de acción](../media/edit-desktop/action-advanced-options.png "Opciones avanzadas de acción")

### <a name="set-the-selector"></a>Establecer el selector

El selector identifica el elemento de la interfaz de usuario en el que se realiza la acción durante la reproducción. Se recomienda copiar y pegar esta información desde un paso independiente que tenga como destino el mismo elemento de la interfaz de usuario, si es posible.

El formato del selector es:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Debe proporcionar los datos para los campos **elemementStack** y **elementXPath** del elemento selector.

Este es un ejemplo del aspecto que podría tener el **elemementStack** .

![Pila de elementos](../media/edit-desktop/elementstack.png "Pila de elementos")

Puede capturar el **elementXPath** con la [grabadora de IU de WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Herramienta WAD](../media/edit-desktop/wad-tool.png "Herramienta WAD")

Quite el primer elemento (todo antes de/Window) antes de usar el resultado en **elementXPath** del selector.

Pruebe el flujo de la interfaz de usuario para confirmar que el selector funciona correctamente.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [ejecutar el flujo de la interfaz de usuario](run-ui-flow.md) que acaba de editar.

- Si desea hacer más cosas con los flujos de la interfaz de usuario, también puede probar flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md) .

