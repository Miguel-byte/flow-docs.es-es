---
title: Microsoft Flow solicitudes de detección de asunto de datos de RGPD para las cuentas de Microsoft (MSA) | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a solicitudes de detección de asunto de datos de RGPD para las cuentas de Microsoft.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548110"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Responder a solicitudes de detección de asunto de datos de RGPD 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El primer paso para responder a una solicitud DSR es encontrar los datos personales que son el asunto de la solicitud.
A continuación se muestra un resumen de los Microsoft Flow recursos que contienen datos personales de un usuario que se autentica con su cuenta de Microsoft (MSA).

|Recurso|Función|
|-----|-----|
|Historial de ejecución|Proporciona el historial de la ejecución de cada flujo durante los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada/salida para cada ejecución de flujo. Más información sobre el [historial de ejecución de Flow](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Fuente de actividades| Proporciona un resumen de las actividades de cada flujo, incluidos el estado de ejecución, los errores y las notificaciones.|
|Fluyen|La lógica de flujo de trabajo para un [flujo](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Conexiones|Lo usan los conectores y permiten la conectividad con las API, los sistemas, las bases de datos y mucho más. Más información acerca de [las conexiones](add-manage-connections.md).|

