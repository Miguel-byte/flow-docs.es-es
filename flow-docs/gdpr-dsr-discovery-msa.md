---
title: Solicitudes de detección del interesado de acuerdo con el RGPD en Microsoft Flow para cuentas de Microsoft (MSA) | Microsoft Docs
description: Obtenga información sobre cómo usar Microsoft Flow para responder a solicitudes de detección del interesado de acuerdo con el RGPD para cuentas de Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: d31e91420f2235b201d3ae974b1950ae5fbc35c9
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563310"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Respuesta a solicitudes de detección del interesado de acuerdo con el RGPD 

El primer paso para responder a una solicitud DSR consiste en encontrar los datos personales objeto de la solicitud.
Este es un resumen de los recursos de Microsoft Flow que contienen datos personales de un usuario que se autentica con su cuenta de Microsoft (MSA).

|Recurso|Propósito|
|-----|-----|
|Historial de ejecución|Proporciona el historial de cada ejecución del flujo de los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada y salida de cada ejecución del flujo. Obtenga más información sobre el [historial de ejecución de flujo](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Fuente de actividades| Proporciona un resumen de las actividades de cada flujo, como el estado de ejecución, los errores y las notificaciones.|
|Flujos|La lógica de flujo de trabajo para un [flujo](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Conexiones|Usadas por los conectores, permiten la conectividad a las API, los sistemas, las bases de datos y mucho más. Obtenga más información sobre las [conexiones](add-manage-connections.md).|

