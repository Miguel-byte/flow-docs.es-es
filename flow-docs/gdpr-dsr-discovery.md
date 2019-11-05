---
title: Microsoft Flow RGPD Data Subject requests Discovery | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a solicitudes de detección de asunto de datos RGPD.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548125"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Responder a solicitudes de detección de asunto de datos de RGPD para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El primer paso para responder a un DSR es encontrar datos personales que son el asunto de la solicitud. Este primer paso le ayuda a determinar si un DSR cumple los requisitos de su organización para respetar o rechazar una solicitud de DSR. Por ejemplo, después de buscar y revisar los datos personales en cuestión, puede determinar que la solicitud no cumple los requisitos de su organización, ya que esto puede afectar negativamente a los derechos y libertades de otras personas.

A continuación se muestra un resumen de los tipos de Microsoft Flow recursos que contienen datos personales para un usuario específico.

|**Recursos que contienen datos personales**|**Función**|
|-----|-----|
|Registros generados por el sistema|Telemetría que captura eventos del sistema e historial.|
|Historial de ejecución|El historial de cada ejecución de flujo durante los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada y salida del flujo. [Aprende más](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Fuente de actividades| Proporciona un resumen de las actividades de flujo, incluidos el estado de ejecución, los errores y las notificaciones.|
|Trabajos de usuario|No se encuentra al usuario, trabajos del sistema que se ejecutan en nombre de un usuario para que se ejecuten los flujos.|
|Fluyen|La lógica de flujo de trabajo que existe para un flujo. [Aprende más](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permisos de Flow|Los flujos se pueden compartir y volver a asignar a otros usuarios. Existen listas de permisos para todos los flujos. [Aprende más](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalles del usuario|Detalles, que no son visibles por el usuario, que admiten la ejecución de flujo.|
|Conexiones|Lo usan los conectores y permiten la conectividad con las API, los sistemas, las bases de datos, etc. [Aprende más](https://docs.microsoft.com/flow/add-manage-connections)|
|Permisos de conexión|Permisos para una conexión específica. [Aprende más](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Conectores personalizados que un usuario ha creado y publicado y que permite la conectividad con sistemas personalizados o de terceros. [Aprende más](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permisos del conector personalizado|Listas de permisos para conectores personalizados. [Aprende más](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Puerta|Las puertas de enlace son servicios de datos locales que un usuario puede instalar para transferir datos de forma rápida y segura entre Microsoft Flow y un origen de datos que no está en la nube. [Aprende más](https://docs.microsoft.com/flow/gateway-manage)|
|Permisos de puerta de enlace|Las puertas de enlace se pueden compartir con los usuarios de una organización. [Aprende más](https://go.microsoft.com/fwlink/?linkid=872249)|
