---
title: "Comienzo de la compilación | Microsoft Docs"
description: "Cree un conector personalizado, compártalo e inserte un flujo, entre otras operaciones."
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Inicio de la compilación con Microsoft Flow
Con Microsoft Flow puede ampliar cualquier aplicación de las siguientes formas, entre otras:

* cree y conéctese a un conector personalizado
* comparta dicha API con todos los usuarios de Microsoft Flow
* inserte la experiencia de flujo desde dentro de una aplicación
* saque provecho de todas las API de desarrollador para que los usuarios puedan interactuar con Microsoft Flow de la mejor manera posible para ellos

## <a name="prerequisites"></a>Requisitos previos
* Una cuenta en [flow.microsoft.com](https://flow.microsoft.com)

## <a name="create-a-custom-connector"></a>Creación de un conector personalizado
Cuando tenga un servicio web que desee poder automatizar con Microsoft Flow, primero tendrá que compilar un conector personalizado. Mediante el registro de un conector personalizado, se enseñan a Microsoft Flow las características de su API de web, incluida la autenticación que requiere, los desencadenadores y las acciones que admite, y los parámetros y salidas de cada una de esas acciones.

Para registrar un conector personalizado, siga [este tutorial](https://powerapps.microsoft.com/tutorials/register-custom-api/). Después de registrarla, puede compartirla en su organización para que otros usuarios pueden ayudarle a probarla.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Uso compartido de un conector personalizado con todos los usuarios de Microsoft Flow
Después de probar completamente el conector personalizado, inicie el proceso de revisión tal como se indica en [esta entrada de blog](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/):

* Un archivo OpenAPI que representa la API y la información de autenticación
* Un icono para el conector
* Una descripción de la API
* Aproximadamente diez ideas sobre cómo puede beneficiar la API a otros usuarios a través de plantillas

Después de enviar esta información, Microsoft empezará a evaluar la función de la API en Microsoft Flow y Microsoft PowerApps.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>Inserción de la experiencia de flujo en un sitio web o una aplicación
Por último, puede insertar Microsoft Flow desde dentro de una aplicación para habilitar la integración profunda en contexto entre la aplicación y los restantes servicios que admite Microsoft Flow. Por ejemplo, puede:

* Examinar todas las plantillas que se relacionan con el servicio y permiten al usuario seleccionar una plantilla
* Administrar los flujos que los usuarios han relacionado con su aplicación

Para más información acerca de cómo insertar Microsoft Flow dentro de una aplicación, siga [este tutorial](embed-flow-dev.md).

