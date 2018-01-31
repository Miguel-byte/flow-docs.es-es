---
title: Desarrollo de un conector de API | Microsoft Docs
description: "Describa la API, especifique el tipo de autenticación, compile desencadenadores y acciones y pruébelos."
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
ms.openlocfilehash: 8731e8a90a62bac4a05068386d23d2449952860b
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="develop-an-api-connector-microsoft-flow"></a>Desarrolle un conector de API (Microsoft Flow)
La compilación de un conector conlleva varios pasos. Para empezar a trabajar en [Microsoft Flow](https://flow.microsoft.com/), haga clic o pulse el botón **Configuración** (el icono de engranaje) en la esquina superior derecha de la página. A continuación, haga clic o pulse en **Conectores personalizados**.

![Buscar conectores de API](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>Descripción de la API
Los conectores de API se describen mediante el [estándar OpenAPI](https://swagger.io/) para definir la interfaz de una API de HTTP. Puede empezar a compilar con un archivo OpenAPI que ya existe o puede importar una [colección Postman](https://www.getpostman.com/docs/collections) que generará automáticamente el archivo OpenAPI en su lugar. 

![Definir el diagrama de API](./media/api-connectors-dev/build-your-api-updated.png)

Si empieza desde cualquiera de estas descripciones de API, los campos de metadatos del asistente se rellenarán automáticamente. Puede editar estos campos en cualquier momento.  

## <a name="build-security"></a>Seguridad
Elija el tipo de autenticación admitido por el servicio y proporcione detalles adicionales para permitir que la identidad fluya adecuadamente entre el servicio y los clientes. 

![Diagrama de seguridad](./media/api-connectors-dev/security.png)

[Obtenga más información](register-custom-api.md) acerca de la seguridad del conector.

## <a name="build-triggers-and-actions"></a>Compilación de desencadenadores y acciones
1. Para compilar los desencadenadores y las acciones del conector, vaya a la pestaña **Definición**. 
   
    ![Diagrama de definición](./media/api-connectors-dev/definition.png)
2. Con el asistente, puede agregar nuevas operaciones o editar el esquema y la respuesta de las que ya existen. Las propiedades **generales** de cada operación le permiten controlar la experiencia del usuario final del conector. Conozca más información sobre los diferentes tipos de operaciones con los vínculos siguientes:
   
   * [Desencadenadores](customapi-webhooks.md) (no visible en PowerApps)
   * [Acciones](register-custom-api.md)
     
     Para implementar una funcionalidad avanzada para Microsoft Flow, consulte [Extensiones de OpenAPI para conectores de API](https://flow.microsoft.com/documentation/customapi-how-to-swagger/). 
3. Por último, haga clic o pulse en **Crear conector** para registrar el conector de API.

Para conocer características adicionales no disponibles en el asistente, póngase en contacto con [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com).

## <a name="test-the-connector"></a>Comprobación del conector
Antes del envío, pruebe el conector de API de una o más maneras: 

* Con el [asistente de pruebas](https://flow.microsoft.com/blog/new-updates-custom-api/) de la API del conector puede llamar a cada operación para comprobar su funcionalidad y el esquema de respuesta.
* En el diseñador de Microsoft Flow, puede compilar visualmente flujos con la API del conector. Este método de pruebas le proporciona visibilidad sobre la funcionalidad de la interfaz de usuario y las características del conector.
* En PowerApps Studio, puede llamar a cada operación mediante la barra de fórmulas y enlazar la respuesta a los controles de la pantalla.

Este tema proporciona información general. Para más información, consulte [Registro y uso de un conector personalizado](register-custom-api.md).

