---
title: Agregar una condición a un flujo | Microsoft Docs
description: Especifique que un flujo realice una o varias tareas solo si una condición es verdadera.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544707"
---
# <a name="add-a-condition-to-a-flow"></a>Agregar una condición a un flujo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Especifique que un flujo realice una o varias tareas solo si una condición es verdadera. Por ejemplo, especifique que recibirá un correo electrónico solo si un Tweet que contiene una palabra clave se retweet al menos 10 veces.

## <a name="prerequisites"></a>Requisitos previos

* [Creación de un flujo](get-started-logic-template.md) a partir de una plantilla: en este tutorial se [usa esta plantilla](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) como ejemplo

## <a name="add-a-condition"></a>Agregar una condición

1. En [Microsoft Flow](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.

    Es posible que tenga que iniciar sesión si aún no ha iniciado sesión.

1. En la lista de flujos, seleccione uno de los flujos que ha creado.

    En este tutorial se usa un ejemplo con un desencadenador de Twitter y una acción de SharePoint.

1. Seleccione **Editar flujo**.

1. En la última acción, seleccione **nuevo paso**.

1. Seleccione **Agregar una condición**.

    ![Botón condición](./media/add-condition/add-condition.png)

1. En la tarjeta **condición** , seleccione un área vacía en el cuadro de la izquierda.

    Se abre la lista de **contenido dinámico** .

1. Seleccione el parámetro **recuento de subtweets** para agregarlo al cuadro.

1. En el cuadro de la parte central de la tarjeta **condición** , seleccione **es mayor o igual que**.

1. En el cuadro de la derecha, escriba **10**.

    ![El cuadro Nombre de objeto con un parámetro en él](./media/add-condition/specify-condition.png)

1. Seleccione el encabezado de la acción que desea usar dentro de la condición (como **crear elemento**) y arrástrela debajo del texto que aparece en **caso afirmativo**.

    Al soltar el cursor, la acción se mueve a ese cuadro.

    ![Acción de arrastrar](./media/add-condition/drag-action.png)

1. Configure la acción según sea necesario.

1. Guarde el flujo.

## <a name="edit-in-advanced-mode"></a>Editar en modo avanzado

También puede seleccionar **Editar en modo avanzado** para escribir condiciones más avanzadas. Puede usar cualquier expresión del lenguaje de *definición de flujo de trabajo* en modo avanzado. Obtenga información sobre todas las [expresiones](https://msdn.microsoft.com/library/azure/mt643789.aspx)disponibles.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre cómo [usar expresiones](use-expressions-in-conditions.md) en condiciones en modo avanzado.
