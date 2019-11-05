---
title: Aprenda a editar flujos de interfaz de usuario Web | Microsoft Docs
description: Aprenda a editar flujos de interfaz de usuario Web.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549585"
---
# <a name="edit-web-ui-flows"></a>Editar flujos de interfaz de usuario Web

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Los flujos de interfaz de usuario Web automatizan los sitios web que se ejecutan en la [próxima versión de Microsoft Edge](https://www.microsoftedgeinsider.com/) o Google Chrome. Después de [crear un flujo de interfaz de usuario Web](create-web.md), puede que tenga que editarlo. Siga los pasos de este documento para obtener información sobre cómo editar los flujos de la interfaz de usuario Web.

## <a name="edit-in-selenium-ide"></a>Editar en el IDE de Selenium

Use el IDE de Selenium para editar los flujos de la interfaz de usuario Web.

>[!NOTE]
>La edición en el IDE de Selenium está dirigida a usuarios avanzados y desarrolladores.

Puede hacer referencia a los [comandos de Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para aprender a editar el script.

El IDE de Selenium sugiere distintos selectores y uno predeterminado cuando el destino es un elemento de la interfaz de usuario. También puede definir un nuevo selector si ninguno de los selectores propuestos es adecuado. Esto suele ocurrir cuando la estructura HTML del sitio web es muy dinámica.

Este es un ejemplo de los posibles selectores que identificó el IDE de Selenium:

![Posibles selectores](../media/edit-web/possible-selectors.png "Posibles selectores")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Obtener acceso a una propiedad de una variable de objeto o elemento de una variable de matriz * *

Esta funcionalidad avanzada le permite usar una sintaxis como \${foo. bar} para tener acceso a la propiedad de barra del objeto foo. También puede escribir en la propiedad de barra de Foo mediante foo. bar como la propiedad Value en un comando de almacén. También puede usar una sintaxis como \${foo [0]} para tener acceso al elemento en el índice 0 de la matriz foo.

## <a name="next-steps"></a>Pasos siguientes

- [Crear flujos de interfaz de usuario Web](create-web.md)
- [Ejecutar flujos de IU](run-ui-flow.md)
