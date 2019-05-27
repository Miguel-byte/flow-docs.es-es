---
title: Aprenda a crear y administrar flujos en Microsoft Teams | Microsoft Docs
description: Crear y administrar flujos para registrar los mensajes y a petición, @mention a los usuarios y los canales, tarjetas de entrada con las opciones de respuesta y más.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061857"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow en los equipos

### <a name="prerequisites"></a>Requisitos previos

1. Acceso a Microsoft Teams.
1. Acceso a Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Instalar la aplicación Microsoft Flow en los equipos

Siga estos pasos para instalar la aplicación Microsoft Flow en Microsoft Teams.

1. Inicie sesión en Microsoft Teams.

1. Pulse el **aplicaciones** situado en la esquina inferior izquierda de la barra de navegación de los equipos.

    ![Seleccionar aplicaciones](media/flows-teams/apps.png)

1. Seleccione el **flujo** app. Es posible que deba buscar **flujo** si no lo ve.

    ![Seleccione la aplicación flow](media/flows-teams/select-flow-app.png)

1. Haga clic en **Instalar**.

    ![Botón instalar](media/flows-teams/select-install.png)

1. Microsoft Flow ya está instalado.

    ![Instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Creación de un flujo en Teams

1. Inicie sesión en Microsoft Teams.

1. Seleccione el **agregan más aplicaciones** vínculo (...) en la barra de navegación y, a continuación, seleccione el **flujo** app.

    ![Icono aplicaciones agregadas](media/flows-teams/added-apps-icon.png)

1. Si no lo ha hecho antes, es posible que deba iniciar sesión y conceder permisos.

    ![Inicio de sesión](media/flows-teams/grant-permissions-sign-in.png)


    Tenga en cuenta las siguientes pestañas:

    ![Página de inicio del flujo](media/flows-teams/flow-landing-page.png)

    Nombre|Propósito
    ----|-----|
    conversación|Interactuar con el bot de flujo.
    Flujos|Crear y administrar flujos.
    Aprobaciones|Listas reciben y envían solicitudes de aprobación.
    acerca de|Muestra la versión y otra información sobre Microsoft Flow.


    Ahora verá todos los flujos que se ha creado desde el Diseñador de Microsoft Flow (si existe). 

    También puede crear flujos desde una plantilla personalizada o desde una plantilla en blanco, igual que haría desde el Diseñador de Microsoft Flow. 

## <a name="manage-approvals"></a>Administrar aprobaciones

Puede administrar [aprobaciones](modern-approvals.md) en Microsoft Teams, tal como lo haría en Microsoft Flow. Siga estos pasos para administrar las aprobaciones:

1. Inicie sesión en Microsoft Teams.
1. Seleccione la pestaña **Aprobaciones**.

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab.png)

    Observará el subfichas siguientes:

    Pestaña|Propósito
    ----|-----|
    Recibido|Muestra las solicitudes de aprobación le ha enviado y que está pendientes de acción del usuario.
    Enviado|Muestra las solicitudes de aprobación que ha enviado y está pendiente de acción de otras personas.
    Historial|Listas reciben y envían solicitudes de aprobación.
    Crear un flujo de aprobación|Crear flujos de aprobación.

1. Seleccione el **recibidos**, **enviados**, o **historial** pestañas para obtener más información.

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab-2.png)

1. Seleccione **Crear flujo de aprobación** para crear un flujo de aprobación.

    ![Pestaña aprobaciones](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usar el bot con flujos

### <a name="list-and-launch-flows-with-the-bot"></a>Lista e iniciar flujos con el bot

> [!TIP]
> El bot se enumera y ejecuta los flujos que se desencadena mediante una programación o desencadene manualmente sin intervención del usuario.

1. Inicie sesión en Microsoft Teams.
1. Seleccione el **agregan más aplicaciones** vínculo (...) en la barra de navegación y, a continuación, seleccione el **flujo** app.

    ![Icono aplicaciones agregadas](media/flows-teams/added-apps-icon.png)
    
1. Seleccione el **conversación** ficha.

    ![Pestaña de conversación](media/flows-teams/conversations-tab.png)

En el **conversación** ficha, puede enviar comandos al bot, que responde mediante la realización de las acciones de comando que se ejecute. Por ejemplo, para enumerar los flujos y ejecutar el flujo con el índice 1, ejecute los siguientes comandos:

- ```List flows``` -El bot muestra una lista de los flujos, precedida por un número de índice.
- ```Run flow 1``` -Ejecuciones de flujo de número 1. En este caso, *1* es el número de índice del flujo que desea ejecutar.

   ![Comandos de bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obtener la descripción de flujos

Para obtener la descripción para el flujo con el índice 1 en la lista de flujos, ejecute ```describe flow 1```. La respuesta de bot será similar a esta imagen:

   ![Describir flujos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obtiene la lista de comandos para el bot

Para obtener la lista de comandos de los identificadores de bot, pedirle con este comando: ```learn more``` 

La respuesta de bot será similar a esta imagen:

![Describir flujos](media/flows-teams/bot-learn-more.png) 
