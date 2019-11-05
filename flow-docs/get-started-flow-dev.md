---
title: Crear conectores personalizados e insertar flujos | Microsoft Docs
description: Cree un conector personalizado, compártalo, inserte un flujo y haga mucho más.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548268"
---
# <a name="start-to-build-with-microsoft-flow"></a>Empezar a compilar con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Estas son algunas de las maneras en que puede ampliar su aplicación con Microsoft Flow:

* Cree y conéctese a un conector personalizado.
* Comparta el conector personalizado con todos los usuarios Microsoft Flow.
* Inserción de la experiencia de flujo en una aplicación.
* Resalte todos los conectores personalizados para que los usuarios puedan interactuar con Microsoft Flow de la mejor manera para ellos.

## <a name="prerequisites"></a>Requisitos previos

* Una cuenta de [Microsoft Flow](https://flow.microsoft.com) .

## <a name="create-a-custom-connector"></a>Creación de un conector personalizado

Si tiene un servicio Web al que desea conectarse desde Microsoft Flow, primero debe crear un conector personalizado. Al registrar un conector personalizado, enseña Microsoft Flow acerca de las características del servicio Web, incluida la autenticación que requiere, los desencadenadores y las acciones que admite, y los parámetros y salidas de cada una de esas acciones.

Siga este tutorial para aprender a [registrar y usar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Después de registrar el conector personalizado, puede compartirlo en su organización para realizar pruebas.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Compartir un conector personalizado con todos los usuarios Microsoft Flow

Después de probar completamente el conector personalizado, inicie el [proceso de revisión](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que Microsoft lo apruebe para compartir con el resto de usuarios Microsoft Flow.

Esto es lo que necesitará para el proceso de revisión:

* Un archivo OpenAPI que representa la API y la información de autenticación.
* Un icono para el conector.
* Una descripción del conector.
* Aproximadamente 10 ideas sobre cómo el conector podría beneficiar a otros usuarios a través de plantillas.

Después de enviar esta información, Microsoft empieza a evaluar la funcionalidad de la API en Microsoft Flow y Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Inserción de la experiencia de flujo en el sitio web o la aplicación

Puede [insertar](developer/embed-flow-dev.md) Microsoft Flow en la aplicación para habilitar la integración profunda y en contexto entre la aplicación y todos los demás servicios que Microsoft Flow admite. Por ejemplo, puede:

* Examine todas las plantillas relacionadas con el servicio y deje que los usuarios seleccionen una plantilla.
* Administrar los flujos que los usuarios han relacionado con su aplicación.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre cómo [insertar](developer/embed-flow-dev.md) Microsoft Flow en la aplicación.
