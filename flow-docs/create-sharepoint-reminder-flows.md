---
title: Crear un flujo de recordatorio para elementos de SharePoint | Microsoft Docs
description: Cree flujos que le recuerden las fechas de vencimiento de los elementos de SharePoint.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547563"
---
# <a name="sharepoint-remind-me"></a>Recordatorio de SharePoint
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Las listas y bibliotecas de SharePoint permiten definir columnas de metadatos personalizados para realizar el seguimiento de fechas. Con la integración de Microsoft Flow con SharePoint, puede crear fácilmente flujos de recordatorios basados en columnas de fecha y hora en SharePoint. Con los flujos de recordatorios, recibirá una alerta de correo electrónico personal con un número predeterminado de días antes de una fecha en cualquier documento o elemento de SharePoint.

## <a name="prerequisites"></a>Requisitos previos
- Acceso a Microsoft SharePoint Online.
- Una lista de SharePoint o una biblioteca con una columna de fecha y hora.
- Acceso a Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Crear un flujo de recordatorio

 1. Cree una [lista de SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) con al menos una columna de fecha y hora en la vista actual. 
 1. Seleccione **Flow** > **establecer un aviso** > **fecha de desactivación** (esta es la columna con el valor DateTime del recordatorio).

     ![Seleccionar el flujo de recordatorio](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Proporcione un **nombre de flujo** y el número de días antes de la entrada de la columna de fecha y hora cuando desee recibir la alerta de aviso en la tarjeta **establecer un recordatorio** .

    ![Establecer detalles de flujo de recordatorio](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Seleccione **crear** en la tarjeta **establecer una recordatorio** .

1. Recibirá el mensaje siguiente, que indica que se ha creado el flujo:

    ![Flujo de recordatorio creado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmar recordatorios recibidos

Recibirá un recordatorio por correo electrónico, en función de la entrada **Recordármelo este número de días de antemano** realizado en el conjunto de **un flujo de recordatorio** que creó anteriormente. 

## <a name="edit-your-flow"></a>Editar el flujo

El flujo de recordatorio es como cualquier otro flujo, por lo que puede tener acceso a él y editarlo a través de [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Aprende más

- Introducción a [Microsoft Flow](https://flow.microsoft.com).
- Establezca un [flujo de recordatorio](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) en SharePoint.


