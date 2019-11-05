---
title: Aprenda a crear y administrar flujos en Microsoft Teams | Microsoft Docs
description: Cree y administre flujos para publicar mensajes a petición, @mention usuarios y canales, publicar tarjetas con opciones de respuesta, etc.
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
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547991"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow en los equipos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Requisitos previos

1. Acceso a Microsoft Teams.
1. Acceso a Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Instalación de la aplicación Microsoft Flow en Teams

Siga estos pasos para instalar la aplicación Microsoft Flow en Microsoft Teams.

1. Inicie sesión en Microsoft Teams.

1. Puntee en el icono **aplicaciones** en la parte inferior izquierda de la barra de navegación equipos.

    ![Seleccionar aplicaciones](media/flows-teams/apps.png)

1. Seleccione la aplicación **Flow** . Es posible que tenga que buscar **Flow (flujo** ) si no lo ve.

    ![Selección de la aplicación Flow](media/flows-teams/select-flow-app.png)

1. Seleccione **instalar**.

    ![Botón instalar](media/flows-teams/select-install.png)

1. Microsoft Flow ya está instalado.

    ![Instalación](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Crear un flujo en Teams

1. Inicie sesión en Microsoft Teams.

1. Seleccione el vínculo **aplicaciones más agregadas** (...) en la barra de navegación y, a continuación, seleccione la aplicación **Flow** .

    ![Icono de aplicaciones agregadas](media/flows-teams/added-apps-icon.png)

1. Si no lo ha hecho antes, puede que tenga que iniciar sesión y conceder permisos.

    ![Inicia sesión](media/flows-teams/grant-permissions-sign-in.png)


    Tenga en cuenta las siguientes pestañas:

    ![Página de aterrizaje de Flow](media/flows-teams/flow-landing-page.png)

    Name|Función
    ----|-----|
    Voz|Interactúe con el bot de flujo.
    Fluyen|Crear y administrar flujos.
    Aprobaciones|Muestra las solicitudes de aprobación recibidas y enviadas.
    Sobre|Muestra la versión y otra información sobre Microsoft Flow.


    Ahora verá todos los flujos que ha creado a partir del diseñador de Microsoft Flow (si existe). 

    También puede crear flujos a partir de una plantilla personalizada o de una plantilla en blanco, tal como se hace en el diseñador de Microsoft Flow. 

## <a name="manage-approvals"></a>Administrar aprobaciones

Puede administrar [aprobaciones](modern-approvals.md) en Microsoft Teams, al igual que haría en Microsoft Flow. Siga estos pasos para administrar las aprobaciones:

1. Inicie sesión en Microsoft Teams.
1. Seleccione la pestaña **aprobaciones** .

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab.png)

    Observará las siguientes subpestañas:

    Ficha|Función
    ----|-----|
    Recibieron|Muestra las solicitudes de aprobación que ha recibido y que están pendientes de acción.
    Envió|Muestra las solicitudes de aprobación que ha enviado y que están pendientes de acción de otros usuarios.
    Histo|Muestra las solicitudes de aprobación recibidas y enviadas.
    Crear flujo de aprobación|Cree flujos de aprobación.

1. Seleccione las pestañas **recibido**, **enviado**o **historial** para obtener más información.

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab-2.png)

1. Seleccione **Crear flujo de aprobación** para crear un flujo de aprobación.

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usar el bot con flujos

### <a name="list-and-launch-flows-with-the-bot"></a>Enumerar e iniciar flujos con el bot

> [!TIP]
> El bot muestra y ejecuta los flujos desencadenados por una programación o desencadenados manualmente sin intervención del usuario.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el vínculo **aplicaciones más agregadas** (...) en la barra de navegación y, a continuación, seleccione la aplicación **Flow** .

    ![Icono de aplicaciones agregadas](media/flows-teams/added-apps-icon.png)
    
1. Seleccione la pestaña **conversación** .

    ![Pestaña conversación](media/flows-teams/conversations-tab.png)

En la pestaña **conversación** , puede enviar comandos al bot, que responde realizando las acciones que se ejecutan. Por ejemplo, para mostrar los flujos y ejecutar el flujo con el índice 1, ejecute los siguientes comandos:

- ```List flows```: el bot muestra una lista de los flujos, prefijados por un número de índice.
- ```Run flow 1```: ejecuta el flujo número 1. Aquí, *1* es el número de índice del flujo que desea ejecutar.

   ![Comandos de bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obtener la descripción de los flujos

Para obtener la descripción del flujo con el índice 1 de la lista de flujos, ejecute ```describe flow 1```. La respuesta de bot será similar a la de esta imagen:

   ![Describir flujos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obtener la lista de comandos para el bot

Para obtener la lista de comandos que controla el bot, pídale este comando: ```learn more``` 

La respuesta de bot será similar a la de esta imagen:

![Describir flujos](media/flows-teams/bot-learn-more.png) 
