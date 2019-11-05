---
title: Ejecutar flujos de interfaz de usuario desde otros flujos | Microsoft Docs
description: Ejecutar flujos de interfaz de usuario desde otros flujos
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
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589751"
---
# <a name="run-ui-flows"></a>Ejecutar flujos de IU

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Después de crear y probar un flujo de interfaz de usuario, puede ejecutarlo desde un evento, una programación o un botón. Para que esto sea posible, agregue el flujo de la interfaz de usuario a un [flujo automatizado](../get-started-logic-flow.md), un [flujo de botones](../introduction-to-button-flows.md), un [flujo programado](../run-scheduled-tasks.md)o un [flujo de procesos empresariales](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Requisitos previos

- Necesita la [puerta de enlace de datos local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que el dispositivo tenga el flujo de la interfaz de usuario desencadenado por Power Automatic.
   
   La puerta de enlace es una conexión segura de nivel empresarial entre Power Automatic y el dispositivo (donde se ejecuta el flujo de la interfaz de usuario). Power Automatic usa la puerta de enlace para acceder a su dispositivo local para que pueda desencadenar los flujos de la interfaz de usuario a partir de un evento, una programación o un botón.
- Una cuenta profesional o educativa. 

   >[!IMPORTANT]
   >Debe usar la misma cuenta profesional o educativa para configurar la puerta de enlace, iniciar sesión en Power Automatic y iniciar sesión en el dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Ejecutar el flujo de la interfaz de usuario a partir de un flujo de eventos, botones, programaciones o procesos empresariales

En este ejemplo, usaremos un flujo automatizado para desencadenar un flujo de interfaz de usuario cuando llega un nuevo correo electrónico.

1. Vaya a [Power Automatic](https://flow.microsoft.com/).
1. Seleccione **Mis flujos** en la barra de navegación izquierda.
1. Seleccione **nuevo**y, a continuación, seleccione **automatizado-desde en blanco**.

   >[!TIP]
   >Puede elegir cualquier otro tipo de flujo que se ajuste a sus necesidades.

1. Asigne un nombre al flujo en el cuadro **nombre de flujo** .
1. Busque "nuevo correo electrónico" y, a continuación, seleccione **cuando llegue un nuevo correo electrónico (V3)** de la lista de desencadenadores. 
    
   ![Seleccionar un desencadenador](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Seleccionar un desencadenador")

1. Seleccione **crear**y, a continuación, seleccione **nuevo paso**.

1. Busque **flujos de interfaz de usuario**y, a continuación, seleccione **ejecutar un flujo de IU para el escritorio** en la lista de **acciones**. 

   ![Acción de búsqueda](../media/run-ui-flow/search-action.png "Acción de búsqueda")

1. Proporcione la información de puerta de enlace y las credenciales del dispositivo. 

   Tendrá que hacerlo una vez por dispositivo:

    - **Nombre de conexión**: elija un nombre para la conexión del dispositivo a Flow. Puede ser diferente del nombre de la puerta de enlace.
    - **Nombre de usuario**: proporcione la cuenta profesional o educativa de su dispositivo.
    - **Tipo de autenticación**: seleccione Windows.
    - **Contraseña**: la contraseña de la cuenta profesional o educativa.
    - **Puerta de enlace**: seleccione la puerta de enlace que creó durante la instalación.

      ![Configuración de conexión](../media/run-ui-flow/connection-settings.png "Configuración de conexión")

      >[!TIP]
      >Si no ve la puerta de enlace, es posible que tenga que seleccionar una conexión diferente. Para ello, seleccione **...** en la parte superior derecha de la tarjeta **ejecutar un flujo de IU para Desktop (versión preliminar)** y, a continuación, seleccione la conexión que desea usar desde **mis conexiones**.

      ![Seleccionar una nueva conexión](../media/run-ui-flow/select-new-connection.png "Seleccionar una nueva conexión")

1. Seleccione el flujo de la interfaz de usuario que creó anteriormente.

   ![Seleccionar flujo de IU](../media/run-ui-flow/select-ui-flow.png "Seleccionar flujo de IU")

1. Seleccione **Guardar** para guardar el flujo automatizado.

1. Pruebe el flujo mediante el envío de un correo electrónico para desencadenarlo. Verá que el flujo de la interfaz de usuario reproduce los pasos que grabó. 

![Ejecución correcta que llama a un flujo de IU](../media/run-ui-flow/successful-run.png "Ejecución correcta que llama a un flujo de IU")

>[!TIP]
>No interactúe con el dispositivo mientras se ejecuta el flujo.

## <a name="use-inputs-and-outputs"></a>Usar entradas y salidas

Al definir entradas y salidas dentro de un flujo de la interfaz de usuario, puede pasar información de esas entradas y a ellas.

1. Al agregar un flujo de interfaz de usuario a un flujo, puede ver la lista de entradas que se definieron en el flujo de la interfaz de usuario.

   ![Entradas de flujo de IU](../media/run-ui-flow/inputs.png "Entradas de flujo de IU")

1. Puede rellenar cada campo de entrada en el flujo de la interfaz de usuario con los valores de los pasos anteriores del flujo. Para ello, seleccione el campo de entrada y, a continuación, seleccione una entrada del selector de tokens.


1. También puede usar las salidas del flujo de la interfaz de usuario como entradas para las acciones que aparecen más adelante en el flujo. Para ello, seleccione el campo de entrada y, a continuación, seleccione una entrada del selector de tokens.

## <a name="limitations-and-known-issues"></a>Limitaciones y problemas conocidos

- No se admiten clústeres de puerta de enlace.
- Dado que los teclados no estadounidenses (QWERTY) no se admiten en esta Realease, la reproducción de un paso de entrada en el que la secuencia de teclas se grabó a partir de un teclado (QWERTY) que no es de EE. UU. dará como resultado trazos clave en EE. UU. (QWERTY).

## <a name="learn-more"></a>Aprende más

 - Instale la [puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Use la documentación de la aplicación de puerta de enlace de datos local](https://docs.microsoft.com/flow/gateway-manage) .
 - [Solucione los problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace de datos local.
