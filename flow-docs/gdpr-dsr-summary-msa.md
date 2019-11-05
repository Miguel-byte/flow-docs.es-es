---
title: Resumen de solicitudes de asunto de datos de RGPD para las cuentas de Microsoft (MSA) | Microsoft Docs
description: Obtenga información acerca de cómo responder a las solicitudes de RGPD de los datos para Microsoft Flow.
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
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548172"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Responder a solicitudes de RGPD Data Ject Rights (DSRS Against)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se describe el Reglamento general de protección de datos de la Unión Europea (RGPD) y se proporcionan los pasos que puede seguir para admitir el cumplimiento de RGPD para los usuarios de Microsoft Flow que se autentican con las cuentas de Microsoft (MSA).

## <a name="prerequisites"></a>Requisitos previos

Necesita una MSA con una [licencia gratuita Microsoft Flow](https://flow.microsoft.com/pricing/) para realizar los pasos de este artículo.

>[!TIP]
> La información de cumplimiento de RGPD también está disponible para los usuarios que se autentican con [cuentas de Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Responder a DSRs Against para los datos de clientes de Microsoft Flow

La solicitud formal de un sujeto de datos a un controlador para realizar una acción en sus datos personales se denomina solicitud de derechos de asunto de datos (DSR). RGPD define los datos personales como **cualquier dato relacionado con una persona física identificada o identificable**. El RGPD ofrece derechos de usuarios (conocidos como asuntos de datos) para administrar los datos personales recopilados por una empresa, agencia u organización (conocido como el controlador de datos o el controlador). Estos derechos incluyen:

* Obtener copias de los datos personales.
* Solicitando correcciones a los datos personales.
* Restringir el procesamiento de datos personales.
* Eliminación de datos personales.
* Recibir datos personales en formato electrónico para que pueda moverse a otro controlador.

Microsoft ofrece productos, servicios y herramientas para ayudar a los controladores a buscar y actuar en los datos personales cuando responden a solicitudes de DSRs Against de datos que residen en la nube.

Esta es una introducción a los procesos descritos en esta guía:

1. **Detectar**: Use las herramientas de búsqueda y detección para encontrar fácilmente los datos de los clientes que puedan ser objeto de una solicitud de DSR. Si determina que los documentos que recopila cumplen las directrices de controlador para llevar a cabo una acción, puede realizar una o varias de las acciones de DSR descritas en los pasos siguientes. Obtenga más información en la [documentación de detección de Microsoft Flow DSR para cuentas Microsoft](gdpr-dsr-discovery-msa.md). Como alternativa, puede determinar que la solicitud no cumple las directrices del controlador para responder a las solicitudes de DSR.

1. **Acceso**: recupere los datos personales que residen en la nube de Microsoft y, si se solicita, realice una copia del mismo para que pueda estar disponible para el sujeto de datos.

1. **Rectificar**: realice los cambios o implemente otras acciones solicitadas en los datos personales, si procede.

1. **Restringir**: restrinja el procesamiento de datos personales, ya sea quitando las licencias para varios servicios en línea o desactivando los servicios deseados siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de forma local o en otra ubicación.

1. **Eliminar**: Quite permanentemente los datos personales que residen en la nube de Microsoft. Obtenga más información sobre cómo [eliminar datos personales para cuentas Microsoft](gdpr-dsr-delete-msa.md). Más información sobre [el cierre de una cuenta de Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exportar**: proporcione una copia electrónica (en formato legible por máquina) de datos personales. [Obtenga más información sobre cómo exportar datos personales para cuentas Microsoft](gdpr-dsr-export-msa.md).
