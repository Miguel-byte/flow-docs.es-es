---
title: "Preguntas acerca de la facturación y las mediciones | Microsoft Docs"
description: "Respuestas a las preguntas más frecuentes sobre la facturación y la medición en Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2016
ms.author: deonhe
ms.openlocfilehash: b627c008e1483360f35b6de579e2c0da32e60c93
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="billing-and-metering-questions"></a>Preguntas acerca de la facturación y la medición
En este artículo se responden las preguntas más frecuentes acerca de la facturación y la medición en Microsoft Flow.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>¿Dónde puedo encontrar los precios planes disponibles?
Consulte la [página de precios](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>¿Dónde puedo encontrar averiguar cuál es mi plan?
Consulte la [página de precios](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>¿Cómo se cambiar de plan?
En el menú de navegación superior, haga clic o pulse **Más información**y, después, **Precios**.

![Más información > Precios](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>¿Cómo sé cuánto he usado?
Para mostrar los registros de las ejecuciones, junto con las notificaciones y los errores, haga clic o pulse **Actividad**.

![Vínculo Actividad](./media/billing-questions/activity-link.png)

Si tiene un plan gratuito o un plan de evaluación, haga clic o pulse el icono del engranaje de la barra de navegación superior para mostrar su uso actual en el plan.   

![Botón Configuración](./media/billing-questions/settings.png)

Si no tiene un plan gratuito o un plan de evaluación, las ejecuciones se agrupan entre todos los usuarios de la organización. Estamos trabajando en características que muestren la cuota disponible y el uso en una organización.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>¿Qué ocurre si mi uso supera los límites?
Microsoft Flow pueden empezar a limitar las ejecuciones.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>¿Dónde puedo encontrar más información acerca de los límites de uso?
En el [página de precios](https://flow.microsoft.com/pricing/), consulte la sección de **preguntas más frecuentes**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>¿Qué sucede si intento realizar ejecuciones con demasiada frecuencia?
El plan determina la frecuencia con que se ejecutan los flujos. Por ejemplo, en los planes gratuitos, los flujos pueden ejecutarse cada 15 minutos. Si un flujo se desencadena menos de 15 minutos después de su última ejecución, se pone en cola hasta que hayan transcurrido los 15 minutos. Las comprobaciones de la existencia de datos nuevos no cuentan como ejecuciones.

## <a name="what-counts-as-a-run"></a>¿Qué se considera una ejecución?
Cada vez que se desencadene un flujo, independientemente de que lo haga un desencadenador automático o se inicie manualmente, se considera una ejecución.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>¿Hay diferencias entre las cuentas Microsoft y las cuentas profesionales o educativo de cara a la facturación?
Sí. Si inicia sesión con una cuenta Microsoft (por ejemplo, una cuenta que termine en @outlook.com o @gmail.com), solo puede utilizar el plan gratuito. Para sacar provecho de las características del plan de pago, inicie sesión con un identificador de correo electrónico profesional o educativo.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Al intentar realizar una actualización, se me indica que mi cuenta no es apta.
Para actualizarla, use una cuenta profesional o educativa, o bien cree una evaluación de Office 365, para lo que debe seguir las instrucciones de este [artículo de Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Mi flujo se ha ejecutado muy pocas veces, ¿por qué me he quedado sin ejecuciones?
Ciertos flujos pueden ejecutarse con mayor frecuencia de la esperada. Por ejemplo, puede crear un flujo que le envíe una notificación push cada vez que su jefe le envíe un correo electrónico. Dicho flujo debe ejecutarse cada vez que reciba un correo electrónico (de cualquier persona), ya que el flujo debe comprobar si el correo electrónico procede de su jefe. Esta acción cuenta como su ejecución.

Para solucionar este problema coloque en el desencadenador todos los filtros que sean necesarios. En el ejemplo anterior, expanda el menú **Opciones avanzadas** y especifique la dirección de correo electrónico de su jefe en el campo **De**.

## <a name="other-limits-and-caveats"></a>Otros límites y advertencias
* Cada cuenta puede tener:
  * 50 flujos
  * 15 Conectores personalizados
  * 20 conexiones por API y un total de 100 conexiones.
* Puede instalar una puerta de enlace solo en el entorno predeterminado.   
* Algunos conectores externos, como Twitter, implementan la limitación de conexiones para controlar la calidad del servicio. Cuando la limitación está en vigor, se producirán errores en los flujos. Para revisar los detalles de esta limitación, vea la ejecución en la que se produjo el error en el historial de ejecuciones del flujo.

