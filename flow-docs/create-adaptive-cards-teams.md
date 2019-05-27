---
title: Aprenda a crear flujos que registre las tarjetas adaptables a Microsoft Teams | Microsoft Docs
description: Aprenda a crear flujos que permite publicar contenido con formato enriquecido con las tarjetas adaptables a Microsoft Teams.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061581"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usar las tarjetas adaptables en Microsoft Teams

Puede crear un flujo que envía [las tarjetas adaptables](https://adaptivecards.io) a un canal Microsoft Teams. Con las tarjetas adaptables, puede usar el formato enriquecido para realizar sus publicaciones más claras, interactivas y atractivas. Las tarjetas adaptables pueden contener componentes, como imágenes, gráficos, texto con formato enriquecido y mucho más.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Crear un flujo que registra las tarjetas adaptables a un equipo

Siga estos pasos para crear un flujo que envía una tarjeta adaptable para el canal general en el equipo de estrategia y planeación. El flujo se crea usa el **publicar su propia tarjeta adaptable con el bot de flujo a un canal (versión preliminar)** acción para publicar contenido de la tarjeta adaptable al canal del equipo cada semana.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el **equipos** icono en el panel de navegación de la barra de la izquierda y, a continuación, seleccione el **planeación y la estrategia** team.

    ![Seleccione los equipos](media/create-adaptive-cards-teams/select-teams-team.png)

1. Seleccione el **flujo** ficha en la parte superior de la pantalla.
1. Seleccione el **+** icono (crear desde cero).
1. Busque **periodicidad**y, a continuación, seleccione el **periodicidad** desencadenador.

    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/select-recurrence.png)

1. Configure la programación como se indica a continuación para repetir cada semana, a una hora y zona horaria de su elección:
    
    ![Tarjeta de periodicidad](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Seleccione **Nuevo paso**.
1. Busque **adaptable**, seleccione **Microsoft Teams**y, a continuación, seleccione el **publicar su propia tarjeta adaptable con el bot de flujo a un canal (versión preliminar)** acción.

   ![Tarjeta adaptable](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Proporcione un **equipo**, **canal**, y **mensaje** en el **publicar su propia tarjeta adaptable con el bot de flujo a un canal (versión preliminar)** tarjeta para indicar el equipo y el canal al que la tarjeta adaptable **mensaje** se publicará.

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

Observe que, después de que transcurra el tiempo de periodicidad, el flujo publica contenido de la tarjeta adaptable para el canal de equipo que ha definido.

![Ejecución del flujo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Más información

- Introducción a [ejemplos tarjeta adaptable](https://adaptivecards.io/samples/).
- Crear [contenido de la tarjeta adaptable](https://adaptivecards.io) de manera sencilla.



