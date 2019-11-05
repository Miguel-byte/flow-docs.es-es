---
title: Información general de regiones para Microsoft Flow | Microsoft Docs
description: Información general con preguntas y respuestas acerca de las regiones de Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548482"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Preguntas más frecuentes sobre regiones en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
En este documento se proporciona una lista de las preguntas más frecuentes sobre Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Cómo averiguar dónde se implementa el flujo
El flujo se implementa en la [región](https://azure.microsoft.com/regions/) que hospeda el [entorno](environments-overview-admin.md). Por ejemplo, si su entorno se crea en la región de Europa, el flujo se implementa en los centros de datos de Europa.

Los administradores pueden identificar la región si inician sesión en el [centro de administración](https://admin.flow.microsoft.com)de Microsoft Flow. La pestaña **entornos** enumera todos los entornos existentes y sus regiones.

![Ver entornos](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>¿Qué regiones están disponibles?
* Estados Unidos
* Centroeuropeo
* Asia
* Australia
* India
* Japón
* Canadá
* Sudamérica
* Reino Unido
* Gobierno de EE. UU. (GCC)
* Francia

## <a name="what-features-are-specific-to-a-given-region"></a>¿Qué características son específicas de una región determinada?
Los entornos se pueden crear en distintas regiones y enlazarse a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se implementa en centros de datos de esa ubicación geográfica. Esto se aplica a cualquier elemento que cree en ese entorno, incluidos Common Data Model, flujos, conexiones, puertas de enlace, aplicaciones y conectores personalizados.

Para obtener un rendimiento óptimo, cree el entorno en la región más cercana a los usuarios. Por ejemplo, si los usuarios están en Europa, cree sus entornos en la región de Europa. Si los usuarios están en el Estados Unidos, cree los entornos en la región de Estados Unidos.

## <a name="gateways"></a>Puertas
Las puertas de enlace son:

* No está disponible en la región de la India.
* Solo se admite en el entorno predeterminado, no en entornos personalizados.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>¿Está Microsoft Flow disponible en las nubes nacionales?
?. [Más información](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>¿Qué direcciones IP de salida se usan en cada región?
Consulte [límites y configuración](limits-and-config.md).

