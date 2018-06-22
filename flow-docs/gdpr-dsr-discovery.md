---
title: Detección de solicitudes del titular de los datos de acuerdo con el RGPD en Microsoft Flow | Microsoft Docs
description: Obtenga información acerca de cómo usar Microsoft Flow para responder a solicitudes de detección del titular de los datos de acuerdo con el RGPD.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 9f950da1b62eac66b35a667f307917f704eb9133
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
ms.locfileid: "31823201"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Respuesta a solicitudes de detección del titular de los datos de acuerdo con el RGPD para Microsoft Flow

El primer paso para responder a un derecho de los titulares de datos es buscar los datos personales a los que se refiere la solicitud. Este primer paso le ayudará a determinar si un derecho de los titulares de datos cumple los requisitos de su organización para tener en cuenta o rechazar una solicitud de este tipo. Por ejemplo, después de buscar y revisar los datos personales en cuestión, puede determinar que la solicitud no cumple los requisitos de su organización porque si se atiende podría afectar negativamente a los derechos y libertades de terceros.

A continuación se muestra un resumen de los tipos de recursos de Microsoft Flow que contienen datos personales para un usuario específico.

|**Recursos que contienen datos personales**|**Propósito**|
|-----|-----|
|Registros generados por el sistema|Telemetría que captura el historial y los eventos del sistema.|
|Historial de ejecución|El historial de cada ejecución de flujo de los últimos 28 días. Estos datos incluyen la hora de inicio, la hora de finalización, el estado y toda la información de entrada/salida para el flujo. [Más información](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Fuente de actividades| Proporciona un resumen de las actividades de flujo, como el estado de ejecución, los errores y las notificaciones.|
|Trabajos de usuario|No visibles para el usuario, los trabajos del sistema que se ejecutan en nombre del usuario para que se ejecuten los flujos.|
|Flujos|La lógica de flujo de trabajo que existe para un flujo. [Más información](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permisos de flujo|Los flujos pueden compartirse y volverse a asignar a otros usuarios. Existen listas de permisos para todos los flujos. [Más información](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalles del usuario|Detalles, no percibidos por el usuario, que respaldan la ejecución del flujo.|
|Conexiones|Utilizadas por los conectores, permiten la conectividad a las API, los sistemas, las bases de datos, etc. [Más información](https://docs.microsoft.com/flow/add-manage-connections)|
|Permisos de conexión|Permisos para una conexión específica. [Más información](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados.|Conectores personalizados que ha creado y publicado un usuario que permiten la conectividad con sistemas de otros fabricantes o personalizados. [Más información](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permisos de conector personalizado|Listas de permisos para los conectores personalizados. [Más información](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Puerta de enlace|Las puertas de enlace son servicios de datos locales que pueden instalarse por un usuario para transferir datos de forma rápida y segura entre Microsoft Flow y un origen de datos que no se encuentra en la nube. [Más información](https://docs.microsoft.com/flow/gateway-manage)|
|Permisos de puerta de enlace|Las puertas de enlace se pueden compartir con los usuarios dentro de una organización. [Más información](https://go.microsoft.com/fwlink/?linkid=872249)|
