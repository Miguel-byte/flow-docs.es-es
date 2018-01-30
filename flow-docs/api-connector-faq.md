---
title: "Preguntas más frecuentes sobre los conectores de API | Microsoft Docs"
description: "Encuentre respuestas a preguntas acerca de requisitos, desencadenadores y otras áreas."
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
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="api-connector-faq-microsoft-flow"></a>Preguntas más frecuentes sobre conectores de API (Microsoft Flow)
## <a name="requirements"></a>Requisitos
**P:**  ¿Puedo compilar un conector sin las API de REST? </br>
**R:** No, para compilar un conector, es preciso disponer de compatibilidad con las API de REST de HTTP del servicio. 

**P:** ¿Qué herramientas se pueden usar para crear un conector? </br>
**R:** Azure tiene funcionalidades y servicios que se pueden utilizar para exponer cualquier servicio como una API, como Azure App Service para hospedar, API Management, etc.

**P:**  ¿Qué tipos de autenticación se admiten? </br>
**R:** Se pueden usar estos estándares de autenticación compatibles:

* [OAuth 2.0](https://oauth.net/2/), que incluye [Azure Active Directory](https://azure.microsoft.com/develop/identity/) o servicios específicos, como Dropbox, GitHub y SalesForce
* OAuth 2.0 genérica.
* [Autenticación básica](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [Clave de API](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Desencadenadores
**P:**  ¿Puedo compilar desencadenadores sin webhooks? </br>
**R:** No, los conectores personalizados para Azure Logic Apps y Microsoft Flow solo admiten desencadenadores basados en webhook. Si desea solicitar otros patrones para la implementación, póngase en contacto con [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) y proporcione más detalles acerca de la API.

## <a name="certification"></a>Certificación
**P**: No soy partner de Microsoft ni fabricante de software independiente (ISV). ¿Puedo crear conectores? </br>
**R**: Sí, puede registrar estos conectores para su uso interno en la organización, pero si desea certificar y liberar públicamente un conector, debe poseer el servicio subyacente o presentar derechos explícitos para usar la API.

## <a name="other"></a>Otros
**P:**  Mis API usan un host dinámico. ¿Cómo se implementa con OpenAPI? </br>
**R:** Los conectores personalizados no admiten hosts dinámicos. En su lugar, use un host estático para desarrollo y pruebas. Si desea certificar el conector, pregunte a su contacto de Microsoft acerca de la implementación dinámica.

**P:**  ¿Es compatible con Postman Collection V2? </br>
**R:** No, actualmente solo se admite Postman Collection V1.

**P:**  ¿Es compatible con OpenAPI 3.0? </br>
**R:** No, actualmente solo se admite OpenAPI 2.0.

