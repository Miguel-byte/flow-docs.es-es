---
title: Ejecutar flujos según una programación | Microsoft Docs
description: Automatizar tareas periódicas mediante la ejecución de flujos según una programación, como cada día o cada hora.
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
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548850"
---
# <a name="run-flows-on-a-schedule"></a>Ejecutar flujos según una programación
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cree un flujo que realice una o varias tareas (por ejemplo, enviar un informe por correo electrónico):

* una vez al día, una hora o un minuto
* en una fecha que especifique
* después de un número de días, horas o minutos que especifique

## <a name="create-a-recurring-flow"></a>Creación de un flujo recurrente
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com)y, a continuación, seleccione **Mis flujos** en la barra de navegación superior.
   
    ![Opción Mis flujos](./media/run-scheduled-tasks/create-flow.png)
2. Seleccione **crear desde**cero.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-from-blank.png)
3. En el cuadro **Buscar todos los conectores y desencadenadores** , escriba **periodicidad**y, a continuación, seleccione **programación-periodicidad**.
   
    ![Buscar desencadenador de periodicidad](./media/run-scheduled-tasks/select-recurrence.png)
4. En el cuadro de diálogo **periodicidad** , especifique la frecuencia con la que desea que se ejecute el flujo.
   
    Por ejemplo, especifique **2** en **intervalo** y **semana** en **frecuencia** si desea que el flujo se ejecute cada dos semanas.
   
    ![Especificar periodicidad](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Especificar opciones avanzadas
1. Siga los pasos de la sección anterior y, a continuación, seleccione **Mostrar opciones avanzadas**.
   
    **Nota**: estas opciones cambian en función de los valores en los que se establecen el **intervalo** y la **frecuencia** . Si la pantalla no coincide con el gráfico siguiente, asegúrese de que el **intervalo** y la **frecuencia** se establecen en los mismos valores que el gráfico.
2. Seleccione una **zona horaria** para especificar si la **hora de inicio** refleja una zona horaria local, la hora universal coordinada (UTC), etc.
3. Especifique una **hora de inicio** en este formato:
   <br>AAAA-MM-DDTHH: MM: SSZ
4. Si especificó **día** en **frecuencia**, especifique la hora del día en que se debe ejecutar el flujo.
5. Si especificó **semana** en **frecuencia**, especifique el día o los días de la semana en los que se debe ejecutar el flujo y la hora o las horas del día en que se debe ejecutar el flujo.
   
    Por ejemplo, configure las opciones tal como se muestra para iniciar un flujo no antes del mediodía (hora del Pacífico) el lunes, el 1 de enero de 2018 y ejecutarlo cada dos semanas los martes a las 5:30P (hora del Pacífico).
   
    ![Especificar opciones avanzadas](./media/run-scheduled-tasks/advanced-options.png)
6. Agregue la acción o acciones que desea que realice el flujo, como se describe [en crear un flujo desde cero](get-started-logic-flow.md) .

## <a name="delay-a-flow"></a>Retrasar un flujo
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com)y, a continuación, seleccione **Mis flujos** en la barra de navegación superior.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-flow.png)
2. Seleccione **crear desde**cero.
   
    ![Crear un flujo desde cero](./media/run-scheduled-tasks/create-from-blank.png)
3. Especifique un evento como se describe [en crear un flujo desde cero](get-started-logic-flow.md) .
4. Seleccione **nuevo paso**y, a continuación, seleccione **Agregar una acción**.
   
    ![Opción para agregar una acción a un flujo](./media/run-scheduled-tasks/add-action.png)
5. En la lista de acciones, realice una de las acciones siguientes:
   
   * Seleccione **retraso**, especifique un **recuento**y especifique una **unidad** de tiempo como segundo, minuto u hora.
   * Seleccione **retraso hasta**y, a continuación, especifique una fecha en este formato.<br>AAAA-MM-DDTHH: MM: SSZ
     
     ![agregar un retardo](./media/run-scheduled-tasks/add-delay.png)
     ![especificar el retraso en unidades de tiempo](./media/run-scheduled-tasks/delay.png)
     ![especificar el retraso hasta](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Aprende más

Obtenga más información sobre las [Opciones avanzadas](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) y cómo configurarlas.

