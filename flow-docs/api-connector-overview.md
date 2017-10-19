---
title: "Introducción a los conectores de API  | Microsoft Docs"
description: Los propietarios de los servicios ISV y SaaS pueden compilar conectores y que Microsoft los certifique.
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 62f8f8d0af72292a61324d75bd46f53d559b46a3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="api-connector-overview-microsoft-flow"></a>Introducción sobre conectores de API (Microsoft Flow)
Un **conector de API** es un contenedor basado en OpenAPI (Swagger) en torno a una API de REST que permite al servicio subyacente comunicarse con [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com) y [Logic Apps](https://docs.microsoft.com/azure/logic-apps/). Proporciona un medio para que los usuarios se conecten a sus cuentas y le saquen partido a un conjunto de **desencadenadores** y **acciones** previamente generados para compilar sus aplicaciones y flujos de trabajo.

Como **fabricante de software independiente (ISV)** o **propietario del servicio SaaS**, puede compilar conectores para habilitar una amplia gama de escenarios empresariales y de productividad para los usuarios. Un conector le ayudará a ir más allá de un conjunto definido de integraciones y a aumentar el alcance, la detectabilidad y el uso del servicio.

## <a name="requirements"></a>Requisitos
Para compilar y enviar un conector, el servicio debe cumplir los siguientes requisitos:

* Escenario de usuario empresarial que se adapte bien a Microsoft Flow, PowerApps y Logic Apps
* Servicio disponible públicamente con API de REST estables

## <a name="build-your-connector"></a>Compilación del conector
El primer paso para compilar un conector de API es compilar un conector personalizado completamente funcional. Un conector personalizado funciona exactamente igual que un conector de API, pero su disponibilidad se limita a su autor y a usuarios específicos dentro de los inquilinos del autor.

El proceso para compilar un conector conlleva varios pasos:

![Pasos para la creación de un conector de API](./media/api-connectors-overview/authoring-steps.png)

[Más información](api-connector-dev.md) sobre cómo desarrollar un conector de API.

## <a name="submit-for-certification"></a>Envío para certificación
Una vez compilado un conector, debe enviarlo para su certificación. Como parte de nuestro proceso de certificación de terceros, Microsoft revisa el conector antes de la publicación.

Este proceso valida la funcionalidad del conector en Microsoft Flow y PowerApps y comprueba el cumplimiento técnico y de contenido.

[Obtenga más información](api-connector-submission.md) sobre el proceso de envío del conector para su certificación y publicación.

## <a name="get-support"></a>Obtención de soporte técnico
Para obtener soporte técnico de incorporación y desarrollo, envíe un correo electrónico a [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com). Esta cuenta se supervisa y se administra activamente. Las consultas e incidencias de los desarrolladores se envían rápidamente al equipo adecuado.

