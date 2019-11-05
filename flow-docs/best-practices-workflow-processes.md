---
title: Prácticas recomendadas para la administración de procesos de flujo de trabajo | MicrosoftDocs
description: Comprender las maneras recomendadas de usar flujos de trabajo
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546015"
---
# <a name="best-practices-for-workflow-processes"></a>Prácticas recomendadas para los procesos de flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tema contiene los procedimientos recomendados para crear y administrar procesos de flujo de trabajo.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitar bucles infinitos  
 Es posible crear lógica en un flujo de trabajo que inicia un bucle infinito, que consume recursos del servidor y afecta al rendimiento. La situación típica en la que podría producirse un bucle infinito es si tiene un flujo de trabajo configurado para iniciarse cuando se actualiza un atributo y, a continuación, actualiza ese atributo en la lógica del flujo de trabajo. La acción de actualización desencadena el mismo flujo de trabajo que actualiza el registro y vuelve a desencadenar el flujo de trabajo.  
  
 Los flujos de trabajo que se crean incluyen lógica para detectar y detener bucles infinitos. Si un proceso de flujo de trabajo se ejecuta más de un número determinado de veces en un registro específico en un breve período de tiempo, el proceso genera el siguiente error: **se canceló la tarea del flujo de trabajo porque el flujo de trabajo que la inició incluía un bucle infinito. Corrija la lógica del flujo de trabajo e inténtelo de nuevo**. El límite de veces es 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Uso de plantillas de flujo de trabajo  
 Si tiene flujos de trabajo similares y prevé crear más flujos de trabajo que siguen el mismo patrón, guarde el flujo de trabajo como una plantilla de flujo de trabajo. De este modo, la próxima vez que necesite crear un flujo de trabajo similar, cree el flujo de trabajo mediante la plantilla y evite especificar todas las condiciones y acciones desde el principio.  
  
 En el cuadro de diálogo **Crear proceso** , elija **nuevo proceso a partir de una plantilla existente (seleccionar de la lista)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Usar flujos de trabajo secundarios  
 Si aplica la misma lógica en distintos flujos de trabajo o en ramas condicionales, defina esa lógica como un flujo de trabajo secundario para que no tenga que replicar esa lógica manualmente en cada flujo de trabajo o rama condicional. Esto ayuda a facilitar el mantenimiento de los flujos de trabajo. En lugar de examinar muchos flujos de trabajo que pueden aplicar la misma lógica, solo puede actualizar un flujo de trabajo.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Eliminar automáticamente las tareas de flujo de trabajo completadas
En el caso de los flujos de trabajo de segundo plano (asincrónico), se recomienda seleccionar la opción **eliminar automáticamente las tareas de flujo de trabajo completadas (para ahorrar espacio en disco)** en la definición de flujo de trabajo. Activar esta casilla permite que el sistema elimine los registros de flujo de trabajo para las ejecuciones correctas para ahorrar espacio. Tenga en cuenta que los registros de las ejecuciones de flujo de trabajo con errores siempre se guardarán para solucionar problemas.  

![Retención de trabajos de flujo de trabajo](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Conservar los registros de las tareas del flujo de trabajo que encontraron errores  
En el caso de los flujos de trabajo que no se ejecutan en segundo plano (sincrónicos), se recomienda seleccionar la opción **mantener registros para trabajos del flujo de trabajo que detecten errores** en la definición de flujo de trabajo. Al seleccionar esta opción se pueden guardar los registros de las ejecuciones de flujo de trabajo con errores para solucionar problemas. Los registros de las ejecuciones de flujo de trabajo sincrónicas correctas se eliminarán siempre para ahorrar espacio.   

![Opción mantener registros para flujos de trabajo con errores](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limitar el número de flujos de trabajo que actualizan la misma entidad
La ejecución de más de un flujo de trabajo que actualiza la misma entidad puede producir problemas de bloqueo de recursos. Imagine varios flujos de trabajo que se ejecutan, donde cada actualización de oportunidad desencadena una actualización de la cuenta asociada. Varias instancias de estos flujos de trabajo que se ejecutan y que intentan actualizar el mismo registro de cuenta al mismo tiempo pueden producir problemas de bloqueo de recursos. Se producen errores en el flujo de trabajo y se registra un mensaje de error, como **SQL timeout: no se puede obtener el bloqueo en _el nombre del recurso_de recursos**. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Usar notas para realizar un seguimiento de los cambios  
 Al editar flujos de trabajo, debe usar la pestaña notas y escribir lo que hizo y por qué lo hizo. Esto permite a otra persona comprender los cambios realizados.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Información general de procesos de flujo de trabajo](workflow-processes.md)   
 [Configurar procesos de flujo de trabajo](configure-workflow-steps.md)   
 [Supervisión y administración de procesos de flujo de trabajo](monitor-manage-processes.md)
   
