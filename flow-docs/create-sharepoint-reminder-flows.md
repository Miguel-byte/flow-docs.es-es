---
title: Crear un flujo de aviso para los elementos de SharePoint | Microsoft Docs
description: Crear flujos que recuerde a pagar las fechas de los elementos de SharePoint.
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
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061121"
---
# <a name="sharepoint-remind-me"></a>Recordármelo de SharePoint

Las listas de SharePoint y las bibliotecas permiten definir columnas de metadatos personalizados para realizar un seguimiento de las fechas. Con la integración de Microsoft Flow con SharePoint, puede crear fácilmente flujos de aviso, según las columnas de fecha y hora en SharePoint. Con los flujos de recordatorio, recibirá una alerta de correo electrónico personal un número predeterminado de días de antelación una fecha en cualquier documento o elemento en SharePoint.

## <a name="prerequisites"></a>Requisitos previos
- Acceso a Microsoft SharePoint Online.
- Una lista de SharePoint, o una biblioteca con una columna de fecha y hora.
- Acceso a Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Crear un flujo de recordatorio

 1. Crear un [lista de SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) con al menos una columna de fecha y hora en la vista actual. 
 1. Seleccione **flujo** > **establecer un aviso** > **fecha desactivado** (esta es la columna con la fecha y hora para el aviso).

     ![Seleccione el flujo de recordatorio](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Proporcione un **nombre de flujo de** y el número de días antes de la entrada de la columna de fecha y hora cuando desea recibir el aviso en el **establecer un aviso** tarjeta.

    ![Establece los detalles del flujo de recordatorio](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Seleccione **crear** en el **establecer un aviso** tarjeta.

1. Recibirá el siguiente mensaje, que indica que se creó el flujo:

    ![Flujo de recordatorio creado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirme los avisos recibidos

Recibirá un aviso por correo electrónico, según la **Recordármelo esto muchos días de antemano** entrada realizada en el **establecer un aviso** flujo que creó anteriormente. 

## <a name="edit-your-flow"></a>Editar el flujo

El flujo de aviso es como cualquier otro flujo, por lo que puede acceder y editar a través [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Más información

- Introducción a [Microsoft Flow](https://flow.microsoft.com).
- Establecer un [flujo recordatorio](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) en SharePoint.


