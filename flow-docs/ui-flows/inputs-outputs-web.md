---
title: Usar entradas y salidas en flujos de interfaz de usuario Web | Microsoft Docs
description: Usar entradas y salidas en flujos de interfaz de usuario Web.
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
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549355"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Uso de entradas y salidas en flujos de interfaz de usuario Web

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definir entradas para un flujo de interfaz de usuario Web

Las entradas de un flujo de IU permiten pasar información de un origen externo, como una base de datos u otro flujo de la interfaz de usuario al software heredado de destino que se automatizará.

Cualquier variable que se use (lectura) antes de la inicialización (normalmente realizada a través de comandos de **almacenamiento** ) se tratará automáticamente como una variable de entrada y se mostrará en la tarjeta de acción **ejecutar un flujo de interfaz de usuario para web** .

Puede usar variables mediante la interpolación de cadenas; por ejemplo, cambie el campo de destino del comando click a "ID =\${elementId}". O bien, cambie el campo de valor del comando Type a "\${inputText}".

El comando, **establecer el tamaño** de la ventana y el **tipo** de comando en las siguientes capturas de pantalla usan variables sin inicializar \${width}, \${height} y \${Search}. Estas variables se convertirán en valores de entrada.

![Establecer el tamaño y el tipo de la ventana](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Establecer el tamaño y el tipo de la ventana")

Puede usar variables directamente en algunos comandos; por ejemplo, los campos de destino o valor del comando forEach son variables, no es necesario que lo incluyan con "\${}".

Consulte la referencia de los [comandos de Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para determinar qué comandos toman el nombre de variable directamente.

## <a name="define-outputs-for-a-web-ui-flow"></a>Definir salidas para un flujo de interfaz de usuario Web

Cualquier variable definida en el script Selenium se convierte automáticamente en un valor de salida. Use los siguientes comandos para declarar variables:

[Restaura](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Almacenar atributo](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Almacenar JSON](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Título del almacén](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[valor de almacén](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Identificador de la ventana de almacenamiento](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Almacenar número de XPath](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Ejecutar script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(agregue la sintaxis ' Return ' para devolver el objeto que desea almacenar al final del script)

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [crear flujos de interfaz de usuario Web](create-web.md).
- Aprenda a [desencadenar flujos de interfaz de usuario](run-ui-flow.md).

