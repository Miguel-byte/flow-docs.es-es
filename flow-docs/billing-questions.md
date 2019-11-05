---
title: Preguntas sobre facturación y medición | Microsoft Docs
description: Respuestas a las preguntas más frecuentes sobre la facturación y la medición en Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546197"
---
# <a name="billing-and-metering-questions"></a>Preguntas sobre facturación y medición
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se responden las preguntas más frecuentes sobre la facturación y la medición en Microsoft Flow.

>[!NOTE]
> PowerApps y Microsoft Flow usarán un [nuevo modelo de licencias](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) a partir del 1 de octubre de 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>¿Dónde puedo averiguar qué planes de precios están disponibles?

Vea la [Página de precios](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>¿Dónde puedo averiguar cuál es mi plan?

Vea la [Página de precios](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Cómo cambiar planes?

En el menú de navegación superior, seleccione **aprender** > **precios**y, a continuación, seleccione el plan al que desea cambiar.

![Obtener información sobre los precios de >](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>¿Cómo sabe cuánto he usado?

Si tiene un plan gratuito o un plan de evaluación, haga clic o pulse en el icono de engranaje de la barra de navegación superior para mostrar su uso actual en el plan. 

![Botón configuración](./media/billing-questions/settings.png)

Si se encuentra en un plan de pago, las ejecuciones se agrupan en todos los usuarios de la organización. Estamos trabajando en características para exponer la cuota y el uso disponibles en una organización.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>¿Qué ocurre si mi uso supera los límites?

Microsoft Flow limita las ejecuciones de flujo.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>¿Dónde puedo encontrar más información sobre los límites de uso?

En la [Página de precios](https://flow.microsoft.com/pricing/), consulte la sección de **preguntas más frecuentes** .

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>¿Qué ocurre si intento ejecutar ejecuciones con demasiada frecuencia?

El Plan determina la frecuencia con que se ejecutan los flujos. Por ejemplo, los flujos pueden ejecutarse cada 15 minutos si está en el plan gratis. Si un flujo se desencadena menos de 15 minutos después de su última ejecución, se pone en cola hasta que hayan transcurrido 15 minutos.

## <a name="what-counts-as-a-run"></a>¿Qué cuenta como una ejecución?

Cada vez que se desencadena un flujo, ya sea por un desencadenador automático o por su inicio manual, se considera una ejecución. Las comprobaciones de datos nuevos no se cuentan como ejecuciones.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>¿Existen diferencias entre las cuentas de Microsoft y las cuentas profesionales o educativas para la facturación?

?. Si inicia sesión con una cuenta de Microsoft (por ejemplo, una cuenta que termina con @outlook.com o @gmail.com), solo puede usar el plan gratuito. Para aprovechar las ventajas de las características del plan de pago, inicie sesión con una dirección de correo electrónico profesional o educativa.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Estoy intentando actualizar, pero me he indicado que mi cuenta no es válida.

Para actualizar, use una cuenta profesional o educativa o cree una [cuenta de prueba de Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>¿Por qué me he quedado sin ejecuciones cuando el flujo solo se ejecutó varias veces?

Algunos flujos pueden ejecutarse con más frecuencia de lo esperado. Por ejemplo, puede crear un flujo que le envíe una notificación de envío cada vez que el administrador le envíe un correo electrónico. Ese flujo debe ejecutarse cada vez que reciba un correo electrónico (de cualquier persona) porque el flujo debe comprobar si el correo electrónico procede de su jefe. Esta acción cuenta como una ejecución.

Puede solucionar este problema colocando todo el filtrado que necesita en el desencadenador. En el ejemplo de notificación de extracción, expanda el menú **Opciones avanzadas** y, a continuación, proporcione la dirección de correo electrónico del administrador en el campo **de** .

## <a name="other-limits-and-caveats"></a>Otros límites y advertencias

* Cada cuenta puede tener tantos como:
  * flujos de 250.
  * 15 conectores personalizados.
  * 20 conexiones por API y 100 conexiones en total.
* Solo puede instalar una puerta de enlace en el entorno predeterminado.
* Algunos conectores externos, como Twitter, implementan la limitación de la conexión para controlar la calidad del servicio. Los flujos producen un error cuando la limitación está en vigor. Si se producen errores en los flujos, revise los detalles de la ejecución en la que se produjo el error en el historial de ejecución del flujo.
