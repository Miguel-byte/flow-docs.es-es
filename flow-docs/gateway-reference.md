---
title: Puerta de enlace de datos local | Microsoft Docs
description: Este artículo es una introducción a la puerta de enlace de datos local para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544633"
---
# <a name="what-is-an-on-premises-data-gateway"></a>¿Qué es una puerta de enlace de datos local?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La puerta de enlace de datos local actúa como un puente para proporcionar una transferencia de datos rápida y segura entre los datos locales (datos que no están en la nube) y varios servicios en la nube de Microsoft. Estos servicios en la nube incluyen Power BI, PowerApps, Microsoft Flow, Azure Analysis Services y Azure Logic Apps. Mediante el uso de una puerta de enlace, las organizaciones pueden mantener bases de datos y otros orígenes de datos en sus redes locales, pero usar los datos locales de forma segura en los servicios en la nube.

## <a name="how-the-gateway-works"></a>Cómo funciona la puerta de enlace

![Introducción a la puerta de enlace](media/gateway-reference/on-premises-data-gateway.png)

Para obtener más información sobre cómo funciona la puerta de enlace, consulte [arquitectura de puerta de enlace de datos local](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Tipos de puertas de enlace

Hay dos tipos diferentes de puertas de enlace, cada una para un escenario diferente:

- **La puerta de enlace de datos local** permite que varios usuarios se conecten a varios orígenes de datos locales. Puede utilizar una puerta de enlace de datos local con todos los servicios admitidos, con una sola instalación de puerta de enlace. Esta puerta de enlace es idónea para escenarios complejos con varias personas que tienen acceso a varios orígenes de datos.

- **La puerta de enlace de datos local (modo personal)** permite a un usuario conectarse a orígenes y no se puede compartir con otros usuarios. Una puerta de enlace de datos local (modo personal) solo se puede usar con Power BI. Esta puerta de enlace es idónea para escenarios en los que es la única persona que crea informes y no es necesario compartir ningún origen de datos con otros usuarios.

## <a name="use-a-gateway"></a>Uso de una puerta de enlace

Hay cuatro pasos principales para utilizar una puerta de enlace.

1. [Descargar e instalar la puerta de enlace](/data-integration/gateway/service-gateway-install) en un equipo local.
2. [Configurar](/data-integration/gateway/service-gateway-app) la puerta de enlace según el firewall y otros requisitos de red.
3. [Agregar administradores de puerta de enlace](/data-integration/gateway/service-gateway-manage) que también pueden administrar y administrar otros requisitos de red.
4. [Solucione los problemas](/data-integration/gateway/service-gateway-tshoot) de la puerta de enlace en caso de errores.

## <a name="next-steps"></a>Pasos siguientes

- [Instalación de la puerta de enlace de datos local](/data-integration/gateway/service-gateway-install)
