---
title: Crear flujos desde el panel de inicio de OneDrive para la empresa | Microsoft Docs
description: Crear flujos desde el panel de inicio de OneDrive para la empresa.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548594"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Crear flujos desde el panel de inicio de OneDrive para la empresa
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Al igual que en el [Panel de inicio de Microsoft Flow de SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), puede ejecutar flujos en archivos específicos en OneDrive para la empresa. 

Esta característica permite a la persona que ejecuta el flujo usar sus propias credenciales, lo que es especialmente aplicable a los flujos creados por un departamento de ti. 

Los usuarios también pueden obtener solicitudes de entradas en tiempo de ejecución como el **aprobador** o el **mensaje**, que puede ser de tipo texto, archivo, correo electrónico, booleano o número.

En este tutorial, vamos a crear un flujo sencillo que usa una de las muchas [plantillas de OneDrive para la empresa](https://flow.microsoft.com/search/?q=OneDrive) para solicitar la aprobación de un archivo por parte del administrador del solicitante.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Creación de un flujo que solicite la aprobación del administrador para un archivo en OneDrive para la empresa

1. Inicie sesión en OneDrive para la empresa.
1. Busque y, a continuación, seleccione el archivo en el que desea crear el flujo.
1. Seleccione el vínculo **Mostrar acciones** (tres puntos).
1. Seleccione **flow** > **crear un flujo**.

     ![Crear flujo](./media/onedrive-launch-panel/create-flow.png) 

1. Seleccione una de las plantillas.

    En este ejemplo, seleccione la opción **solicitar la aprobación de mi administrador para la plantilla de archivo seleccionada** .

     >[!TIP]
     >Inicie sesión en los conectores que solicitan que inicie sesión.

1. Seleccione **continuar**.
1. Realice los cambios que desee en la plantilla y, a continuación, guarde el flujo con un nombre que recuerde fácilmente.

## <a name="run-the-flow"></a>Ejecución del flujo

1. Inicie sesión en OneDrive para la empresa.
1. Busque y seleccione el archivo en el que se va a aprobar la aprobación del administrador de solicitudes.
1. Seleccione el vínculo **Mostrar acciones** (tres puntos).
1. Seleccione **Flow (flujo**). Verá el flujo que creó anteriormente.
1. Seleccione el flujo que creó anteriormente.

     ![Ejecutar el flujo](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Aunque en este tutorial se muestra cómo crear un flujo a partir de una plantilla, también puede crear un flujo desde cero para usar cualquiera de los cientos de conectores disponibles en Microsoft Flow.

## <a name="learn-more"></a>Aprende más

- [Introducción a Microsoft Flow](getting-started.md) 
- [Compilación de flujos de varios pasos](multi-step-logic-flow.md)
