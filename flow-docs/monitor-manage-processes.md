---
title: Supervisión y administración de procesos de flujo de trabajo con PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549008"
---
# <a name="monitor-and-manage-workflow-processes"></a>Supervisión y administración de procesos de flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Para supervisar y administrar procesos, debe buscar el proceso, evaluar el estado y realizar las acciones necesarias para solucionar los problemas.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Supervisión de flujos de trabajo en segundo plano  
 Los flujos de trabajo en segundo plano generan registros de trabajos del sistema para realizar el seguimiento de su estado. Puede tener acceso a información acerca de estos trabajos del sistema en varios lugares de la aplicación:  
  
 **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > trabajos del sistema**  
 Esto incluirá todos los tipos de trabajos del sistema. Tendrá que filtrar los registros para aquellos en los que el **tipo de trabajo del sistema** es **flujo**de trabajo.  
  
 **Desde el proceso de flujo de trabajo**  
 Abra la definición de flujo de trabajo en segundo plano y vaya a la pestaña **sesión de proceso** . Esto mostrará solo los trabajos del sistema para este flujo de trabajo en segundo plano.  
  
 **Desde el registro**  
 Puede editar el formulario de la entidad para que la navegación incluya la relación de los **procesos en segundo plano** . Esto mostrará todos los trabajos del sistema que se han iniciado en el contexto del registro.  
  
> [!NOTE]
>  Si se produce un error en un trabajo del sistema asincrónico (flujo de trabajo) varias veces consecutivas, el sistema empieza a posponer la ejecución de ese trabajo durante intervalos de tiempo mayores y más largos para que el administrador o el creador de la aplicación pueda investigar y resolver el problema. Una vez que el trabajo se vuelva a ejecutar correctamente, se reanudará la ejecución con normalidad.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Acciones en ejecutar flujos de trabajo en segundo plano  
 Mientras se ejecuta un flujo de trabajo en segundo plano, tiene opciones para **Cancelar**, **pausar**o **posponer** el flujo de trabajo. Si previamente ha pausado un flujo de trabajo, puede **reanudarlo** .  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Supervisión de acciones y flujos de trabajo en tiempo real  
 Los flujos de trabajo en tiempo real y las acciones no usan registros de trabajos del sistema porque se producen inmediatamente. Los errores que se produzcan se mostrarán al usuario en la aplicación con el encabezado **error de proceso empresarial**.  
  
 No hay ningún registro para las operaciones correctas. Puede habilitar el registro de errores si activa la opción **mantener registros para trabajos de flujo de trabajo que han encontrado errores** en el área de **retención registro de flujo de trabajo** en la parte inferior de la pestaña **Administración** del proceso.  
  
 Para ver el registro de errores de un proceso específico, abra el flujo de trabajo en tiempo real o la definición de la acción y vaya a la pestaña **sesión del proceso** . Esto solo mostrará los errores registrados en este proceso.  
  
 Si desea ver una vista de todos los errores de cualquier proceso, vaya a **búsqueda avanzada** y cree una vista que muestre errores en la entidad sesión de proceso.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Estado de los procesos de flujo de trabajo  
 Cuando se ve una lista de procesos de flujo de trabajo, cualquier proceso individual puede tener uno de los siguientes valores de **razón** **de estado y** estado:  
  
|State|Motivo del estado|  
|-----------|-------------------|  
|Párese|Esperando recursos|  
|Suspend|Que|  
|Cerrado|En curso<br /><br /> Pausar<br /><br /> Cancelar|  
|Cubiertos|Completa<br /><br /> Erróneo<br /><br /> Cancelado|  

## <a name="deleting-process-log-records"></a>Eliminar entradas de registro de proceso

Si su organización usa flujos de trabajo en segundo plano o flujos de procesos empresariales que se ejecutan con frecuencia, la cantidad de entradas de registro de proceso puede ser lo suficientemente grande como para causar problemas de rendimiento, así como consumir cantidades significativas de almacenamiento. Para eliminar las entradas de registro de proceso que no se han quitado de forma suficiente en uno de los trabajos de eliminación de registros en masa estándar, puede utilizar la característica de trabajos del sistema de eliminación masiva para crear un trabajo de eliminación de registros en masa personalizado.

1. Vaya a **configuración** > **Administración de datos** > **eliminación de registros en bloque**.
2. En el área **eliminación de registros en masa** , seleccione **nuevo**. 
3. En la página de inicio del **Asistente para eliminación masiva** , seleccione **siguiente**.
4. En la lista **Buscar** , seleccione **trabajos del sistema**.
5. Las condiciones siguientes se usan para crear un trabajo de eliminación de registros en masa para eliminar las entradas del registro del proceso. 
 - El **tipo de trabajo del sistema es igual a Workflow**. Esto tiene como destino registros de flujo de trabajo. 
 - El **Estado es igual a completado**. Solo los flujos de trabajo completados son válidos para ejecutar el trabajo.
 - **Razón del estado es igual a correcto**. Eliminar trabajos correctos, cancelados y con errores.
 - **Completado en más de X días 30**. Use el campo completado en para eliminar solo las entradas de registro del proceso de flujo de trabajo que tengan más de 30 días.
 ![Custom-bulk-record-Deletion. png](media/custom-bulk-record-deletion.png)
6. Haga clic en **siguiente**.
7. Establezca la frecuencia con la que se ejecutará el trabajo de eliminación masiva. Puede programar el trabajo para que se ejecute a intervalos establecidos o crear un trabajo de eliminación masiva único [mediante la opción inmediatamente](#using-the-immediately-option). En este ejemplo, se establece un trabajo periódico que se ejecuta el 21 de mayo de 2018 y cada 30 días a partir de entonces. 
![opciones de eliminación de registros en masa](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Usar la opción inmediatamente

Tenga en cuenta que tiene la opción de realizar una eliminación en masa sincrónica inmediata de los registros seleccionando la opción **inmediatamente** . Esta eliminación se realiza con la ejecución directa SQL Server en lugar de pasar cada registro a través de la canalización de eventos de eliminación, lo que puede reducir el impacto en el rendimiento del sistema. Esta es una buena opción si desea limpiar rápidamente los registros de flujo de trabajo adicionales en lugar del trabajo de eliminación en masa que espera en la cola asincrónica para su procesamiento. 

La opción **inmediatamente** está habilitada cuando se cumplen las condiciones siguientes: 
- El trabajo de eliminación masiva es para la entidad trabajos del sistema.
- Los criterios de búsqueda tienen el tipo de trabajo del sistema de condiciones es igual a flujo de trabajo. 
- El usuario que crea el trabajo de eliminación masiva tiene una profundidad global para el privilegio de eliminación en la entidad AsyncOperation. El rol de seguridad Administrador del sistema tiene este privilegio.  

La eliminación sincrónica en masa solo eliminará los registros AsyncOperation en el estado completado. Se procesa un máximo de 1 millón registros para cada invocación. Tendrá que ejecutar el trabajo varias veces si el entorno tiene más de 1 millón registros para quitar.  
  
## <a name="next-steps"></a>Pasos siguientes   
 [Prácticas recomendadas para los procesos de flujo de trabajo](best-practices-workflow-processes.md) <br />

