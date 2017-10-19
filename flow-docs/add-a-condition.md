---
title: "Adición de una condición a un flujo | Microsoft Docs"
description: "Especifique que un flujo realice una o varias tareas solo si el valor de una condición concreta es true."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>Adición de una condición a un flujo
Especifique que un flujo realice una o varias tareas solo si el valor de una condición concreta es true. Por ejemplo, especifique que recibirá un correo electrónico solo si se retwittea al menos diez veces un tweet que contenga una palabra clave.

**Requisitos previos**

* [Creación de un flujo de](get-started-logic-template.md) desde una plantilla: en este tutorial se [utilizará esta plantilla](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) a modo de ejemplo

## <a name="add-a-condition"></a>Adición de una condición
1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.
2. En la lista de flujos, seleccione alguno que haya creado. Este tutorial usa un ejemplo con un desencadenador de Twitter y una acción de SharePoint.
3. En la última acción, haga clic en el botón **Nuevo paso**.
4. Seleccione **Agregar una condición**.
   
    ![Botón de condición](./media/add-a-condition/add-condition.png)
5. Seleccione un área vacía en **Nombre de objeto** y, después, seleccione **Agregar contenido dinámico** para abrir el menú de contenido dinámico.
6. Seleccione el parámetro **Retweet count** para agregarlo al cuadro.
7. En el cuadro **Relación**, seleccione **es mayor o igual que**.
8. En el cuadro **Valor**, escriba **10**.
   
    ![El cuadro Nombre de objeto con un parámetro](./media/add-a-condition/specify-condition.png)
9. Haga clic en el encabezado de la acción que desee dentro de la condición (como **Crear elemento**) y arrástrelo debajo del texto **EN CASO POSITIVO**. Cuando suelte el cursor, la acción se debería mover a ese cuadro.
   
    ![Acción Arrastrar](./media/add-a-condition/drag-action.png)
10. Guarde el flujo.

## <a name="edit-in-advanced-mode"></a>Editar en modo avanzado
También puede seleccionar el vínculo **Editar en modo avanzado** para escribir condiciones más avanzadas. Aquí puede usar cualquier expresión del *Lenguaje de definición de flujo de trabajo*. [Más información acerca de](https://msdn.microsoft.com/library/azure/mt643789.aspx) las funciones disponibles.

