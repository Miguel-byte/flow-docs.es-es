---
title: Usar entradas y salidas en flujos de interfaz de usuario de escritorio | Microsoft Docs
description: Usar entradas y salidas en flujos de IU de escritorio.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589783"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Usar entradas y salidas en flujos de IU de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definir entradas

Las entradas le permiten pasar información de un origen externo, como una base de datos o cualquier conector compatible al software heredado que automatiza la interfaz de usuario.

Por ejemplo, puede usar la información de clientes de una lista de SharePoint como origen para la entrada en el software de contabilidad heredado.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Definir entradas en el Asistente para flujos de la interfaz de usuario

1. Seleccione "nueva entrada"

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Agregue un nombre, un ejemplo de datos y una descripción a la entrada.

    - Los datos de ejemplo se usan durante la grabación o la prueba.

    - La descripción será útil para diferenciar las entradas que ha creado.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Una vez creadas las entradas, puede hacer clic en siguiente para usarlas en una grabación.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Usar entradas para pasar información a la aplicación

1. Durante la grabación, puede usar una entrada en una aplicación seleccionando **usar entrada**.

1. En la lista, puede elegir entre tres opciones:

    - Seleccione una de las entradas que ha definido en el paso de **configuración de los** flujos de la interfaz de usuario.

    - Usar una salida definida previamente (consulte la sección salidas). Esto resulta útil para pasar información entre diferentes aplicaciones dentro del mismo flujo de la interfaz de usuario.

    - Cree una nueva entrada mientras está grabando. Lo encontrará en flujos de interfaz de usuario paso de **configuración de campos de entrada** .

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Seleccione la ubicación en la que desea usar la entrada. El valor de ejemplo que ha definido se usa automáticamente. En el ejemplo siguiente, "Hello World" es el valor de ejemplo para el nombre de entrada "My INPUT" y se agrega a la página en Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. En potencia automatizar **los pasos de registro y edición**, expanda acciones que usan entradas para ver cuál de ellas está seleccionada.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Al desencadenar el flujo de la interfaz de usuario, puede cambiar el valor de entrada en el. Consulte usar entradas & salidas para obtener más información.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Usar salidas para extraer información de la aplicación

Las salidas permiten pasar información del software heredado que el flujo de interfaz de usuario automatiza a un destino externo, como una base de datos o cualquier [conector compatible](https://flow.microsoft.com/connectors/).

Por ejemplo, puede extraer información del cliente del software de contabilidad heredado y agregarlo a una lista de SharePoint.

Las salidas solo se pueden crear al grabar el flujo de la interfaz de usuario.

1. Durante una grabación, seleccione en el botón "obtener salida".

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Seleccione el botón "Seleccionar texto" (este es el único tipo de salida disponible para ahora)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Haga clic en un elemento de la interfaz de usuario para seleccionar el texto de la salida. El valor se capturará automáticamente.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Defina el nombre y la descripción de la salida.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Seleccione **Guardar.** 

La salida ya está disponible en el área dedicada del asistente.

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Cada salida tiene:

-  Un nombre de salida tal y como se define durante la grabación.
-  Descripción: este campo puede ser muy útil cuando se definen muchas salidas durante una grabación y se desea identificarlas fácilmente.
-  Un nombre de acción: la acción en la que se ha definido la salida en el flujo de la interfaz de usuario

## <a name="delete-an-output-from-a-ui-flow"></a>Eliminar una salida de un flujo de IU

Si ya no necesita una salida, puede eliminarla volviendo a la acción asociada y quitando el nombre de salida en el valor dinámico.

## <a name="test-your-ui-flow"></a>Probar el flujo de la interfaz de usuario

La prueba de flujos de IU le permite validar los cambios y el comportamiento de reproducción adecuado.

1. Opta Escriba el nuevo valor en el campo de entrada. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Haga clic en **probar ahora** para ver el software heredado que se está automatizando. Verá que automatización del flujo de la interfaz de usuario reproduce los pasos registrados. **No interactúe con el dispositivo mientras dure la reproducción.**

1. Una vez completada la reproducción, verá el estado de ejecución del flujo de la interfaz de usuario:

    - Para cada acción, un estado que indica que la prueba ha funcionado bien y las entradas asociadas.

    - Valor de las salidas obtenidas para esta prueba.

    - En caso de que se genere un error, podrá ver qué paso fue problemático con una captura de pantalla del momento en que se produjo el error.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Aprende más

- Aprenda a [desencadenar el flujo de la interfaz de usuario](run-ui-flow.md) que acaba de crear.

- Si desea hacer más cosas con los flujos de la interfaz de usuario, también puede probar flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md) .


