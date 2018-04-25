---
title: Creación de conectores personalizados e inserción de flujos | Microsoft Docs
description: Cree un conector personalizado, compártalo e inserte un flujo, entre otras operaciones.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: a3f1e21cfbf00749a0ef09c0363da162f0419f42
ms.sourcegitcommit: aee927ab32b5e28ee9b1880b4a292f9c15025f88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="start-to-build-with-microsoft-flow"></a>Inicio de la compilación con Microsoft Flow

Estos son algunos métodos mediante los que puede ampliar su aplicación con Microsoft Flow:

* Crear un conector personalizado y conectarse a él.
* Compartir el conector personalizado con todos los usuarios de Microsoft Flow.
* Insertar la experiencia del flujo en una aplicación.
* Resaltar todos los conectores personalizados para que los usuarios puedan interactuar con Microsoft Flow de la mejor manera posible para ellos.

## <a name="prerequisites"></a>Requisitos previos

* Cuenta de [Microsoft Flow](https://flow.microsoft.com).

## <a name="create-a-custom-connector"></a>Creación de un conector personalizado

Si dispone de un servicio web al que quiera conectarse desde Microsoft Flow, primero será necesario crear un conector personalizado. Al registrar un conector personalizado, enseña a Microsoft Flow las características de su servicio web, incluido el tipo de autenticación que requiere, los desencadenadores y las acciones que admite, y los parámetros y las salidas de cada una de dichas acciones.

Siga este tutorial para obtener información sobre cómo [registrar y usar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Después de registrar el conector personalizado, puede compartirlo en su organización para realizar pruebas.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Uso compartido de un conector personalizado con todos los usuarios de Microsoft Flow

Después de probar por completo el conector personalizado, inicie el [proceso de revisión](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que Microsoft apruebe que lo comparta con todos los demás usuarios de Microsoft Flow.

Esto es lo que necesitará para el proceso de revisión:

* Archivo OpenAPI que represente la API y la información de autenticación.
* Icono para el conector.
* Descripción del conector.
* Aproximadamente diez ideas sobre cómo puede beneficiar el conector a otros usuarios a través de plantillas.

Después de enviar esta información, Microsoft empezará a evaluar la funcionalidad de la API en Microsoft Flow y Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Inserción de la experiencia de flujo en un sitio web o una aplicación

Puede [insertar](embed-flow-dev.md) Microsoft Flow en su aplicación para habilitar la integración profunda y en contexto entre la aplicación y el resto de servicios que admite Microsoft Flow. Por ejemplo, puede:

* Examinar todas las plantillas relacionadas con el servicio y que permiten que el usuario seleccione una plantilla.
* Administrar los flujos que los usuarios han relacionado con su aplicación.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre cómo [insertar](embed-flow-dev.md) Microsoft Flow en su aplicación.
