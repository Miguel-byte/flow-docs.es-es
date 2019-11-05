---
title: Obtenga información sobre cómo crear flujos compatibles con soluciones | Microsoft Docs
description: Aprenda a crear flujos que reconocen soluciones.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546465"
---
# <a name="create-a-flow-in-a-solution"></a>Creación de un flujo en una solución
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los flujos que se crean en una solución se conocen como flujos *con reconocimiento de la solución* . Siga estos pasos para crear un flujo compatible con soluciones.

## <a name="prerequisites"></a>Requisitos previos

Debe tener al menos una solución antes de poder crear un flujo compatible con soluciones.

## <a name="create-the-flow"></a>Creación del flujo 

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione **soluciones** en la barra de navegación.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Seleccione la solución en la que va a crear el flujo.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Seleccione **+ nuevo**y, a continuación, seleccione **flujo**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Se abre Microsoft Flow.

1. Use los conectores y desencadenadores disponibles para compilar el flujo.

   En este ejemplo, crearemos un flujo sencillo que enviará una notificación cuando llegue un correo electrónico a la bandeja de entrada.
1. Busque y, a continuación, seleccione **Office 365 Outlook**.
1. Seleccione el desencadenador **cuando llega un nuevo correo electrónico** .
1. Seleccione **+ nuevo paso**.
1. Seleccione la acción **enviarme una notificación de Mobile** .
1. Agregue el token dinámico de **asunto** al campo de **texto** del cuadro **enviarme una notificación de Mobile** .
1. Asigne un nombre al flujo y, a continuación, guarde el flujo.

   El flujo debe ser similar al siguiente:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Seleccione **soluciones** para ver el flujo en la solución:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Aprende más

* [Crear una solución](./overview-solution-flows.md)
* [Exportar una solución](./export-flow-solution.md)
* [Importar una solución](./import-flow-solution.md)
* [Editar un flujo compatible con soluciones](./edit-solution-aware-flow.md)
* [Quitar un flujo compatible con soluciones](./remove-solution-aware-flow.md)
