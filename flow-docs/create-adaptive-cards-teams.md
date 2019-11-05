---
title: Aprenda a crear flujos que publiquen tarjetas adaptables en Microsoft Teams | Microsoft Docs
description: Aprenda a crear flujos que publiquen contenido con formato enriquecido con tarjetas adaptables en Microsoft Teams.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546497"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usar tarjetas adaptables en Microsoft Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Puede crear un flujo que publique [tarjetas adaptables](https://adaptivecards.io) en un canal de Microsoft Teams. Con las tarjetas adaptables, puede usar el formato enriquecido para que sus publicaciones sean más claras, interactivas y atractivas. Las tarjetas adaptables pueden contener componentes como imágenes, gráficos, texto con formato enriquecido, etc.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Crear un flujo que envíe tarjetas adaptables a un equipo

Siga estos pasos para crear un flujo que envíe una tarjeta adaptable al canal general en el equipo de estrategia y planeamiento. El flujo que creamos usa la **tarjeta publicar su propia tarjeta adaptativa como el bot de flujo a una acción de canal (versión preliminar)** para publicar el contenido de la tarjeta adaptable en el canal semanal del equipo.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el icono **equipos** en la barra de navegación de la izquierda y, a continuación, seleccione el equipo de **estrategia y planeamiento** .

    ![Seleccionar equipos](media/create-adaptive-cards-teams/select-teams-team.png)

1. Seleccione la pestaña **Flow (flujo** ) en la parte superior de la pantalla.
1. Seleccione el icono de **+** (crear desde cero).
1. Busque **periodicidad**y, a continuación, seleccione el desencadenador de **periodicidad** .

    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/select-recurrence.png)

1. Establezca la programación como se indica a continuación para repetir cada semana, a una hora y zona horaria de su elección:
    
    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Seleccione **nuevo paso**.
1. Busque **Adaptive**, seleccione **Microsoft Teams**y, después, seleccione la acción **publicar su propia tarjeta adaptativa como bot de flujo en una acción de canal (versión preliminar)** .

   ![Tarjeta adaptable](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Proporcione un **equipo**, un **canal**y un **mensaje** en la tarjeta **publicar su propia tarjeta adaptativa como bot de flujo a una tarjeta de canal (versión preliminar)** para indicar el equipo y el canal en el que se publicará el **mensaje** de la tarjeta adaptable.

   ![Tarjeta adaptable](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Puede usar este contenido JSON de ejemplo para el **mensaje**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Asigne un nombre al flujo y guárdelo.


## <a name="run-the-flow"></a>Ejecución del flujo

Observe que, una vez transcurrido el tiempo de periodicidad, el flujo envía el contenido de la tarjeta adaptable al canal del equipo que ha definido.

![Ejecución del flujo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Aprende más

- Introducción a los [ejemplos de tarjetas adaptables](https://adaptivecards.io/samples/).
- Cree [contenido de tarjeta adaptable](https://adaptivecards.io) de la forma más sencilla.



