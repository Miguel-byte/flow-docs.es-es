---
title: Configuración de fases y pasos del flujo de trabajo en PowerApps | MicrosoftDocs
description: Más información sobre cómo configurar los pasos del flujo de trabajo
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547070"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurar fases y pasos del flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Al diseñar flujos de trabajo, tiene la opción de incluir la lógica que desea realizar en fases y pasos.  
  
 **Diferentes**  
 Las fases facilitan la lectura de la lógica del flujo de trabajo y explican la lógica del flujo de trabajo. Sin embargo, las fases no afectan a la lógica o el comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso deben estar incluidos en una fase.  
  
 **Pasos**  
 Los pasos son una unidad de lógica de negocios dentro de un flujo de trabajo. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Acciones que pueden realizar los procesos de flujo de trabajo  

 Los procesos de flujo de trabajo pueden realizar las acciones enumeradas en la tabla siguiente.  
  
|Actuar|Denominación|  
|------------|-----------------|  
|**Crear registro**|Crea un nuevo registro para una entidad y asigna los valores que elija a los atributos.|  
|**Actualizar registro**|Puede actualizar el registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de N:1 o cualquier registro creado en pasos anteriores.|  
|**Asignar registro**|Puede asignar el registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de N:1 o cualquier registro creado en los pasos anteriores.|  
|**Enviar correo electrónico**|Envía un correo electrónico. Puede optar por crear un nuevo mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad del registro en el que se está ejecutando el flujo de trabajo o cualquier entidad que tenga una relación de N:1 con la entidad, o bien la entidad para los registros creados en pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Cambia el estado del registro en el que se está ejecutando el proceso, cualquiera de los registros vinculados a ese registro con una relación de N:1 o cualquier registro creado en los pasos anteriores.|  
|**Detener flujo de trabajo**|Detiene el flujo de trabajo actual. Puede establecer un estado de **correcto** o **cancelado** y especificar un mensaje de estado.<br /><br /> Cuando se configuran flujos de trabajo en tiempo real para un evento, detener un flujo de trabajo con un estado cancelado evitará que se complete la acción del evento. Consulte [uso de flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obtener más información.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos de flujo de trabajo personalizados que definan acciones. No hay ningún paso personalizado disponible de forma predeterminada.|  
  
### <a name="setting-record-values"></a>Establecer valores de registro  

 Al crear un registro, puede establecer valores para el registro. Al actualizar un registro, puede establecer, anexar, incrementar, reducir, multiplicar o borrar valores.  
  
 Al seleccionar **establecer propiedades**, se abre un cuadro de diálogo que muestra el formulario predeterminado de la entidad.  
  
 En la parte inferior del cuadro de diálogo puede ver una lista de campos adicionales que no aparecen en el formulario.  
  
 En cualquier campo, puede establecer un valor estático y que se establecerá mediante el flujo de trabajo.  
  
 En el lado derecho del cuadro de diálogo, el **Asistente de formulario** le proporciona la capacidad de establecer o anexar valores dinámicos del contexto del registro actual. Esto incluye los valores de los registros relacionados a los que se puede tener acceso desde las relaciones de N:1 (varios a uno) de la entidad.  
  
 Las opciones disponibles en el **Asistente de formulario** dependen del campo que haya seleccionado en el formulario. Al establecer un valor dinámico, verá un marcador de posición amarillo conocido como ' Slug ' que muestra dónde se incluirán los datos dinámicos. Si desea quitar el valor, solo tiene que seleccionar el campo de indicaciones y eliminarlo. En el caso de los campos de texto, puede utilizar una combinación de datos estáticos y dinámicos.  
  
 Con valores dinámicos no se sabe con certeza que un campo o entidad relacionada tiene el valor que desea establecer. En realidad, puede establecer un número de campos para probar y establecer el valor y ordenarlos en orden mediante las flechas verdes. Si el primer campo no tiene datos, el segundo campo se intentará y así sucesivamente. Si ninguno de los campos tiene datos, puede especificar un valor predeterminado que se usará.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Establecer condiciones para las acciones de flujo de trabajo  

 Las acciones que se aplican a menudo dependen de las condiciones. Los procesos de flujo de trabajo proporcionan varias maneras de establecer condiciones y crear lógica de bifurcación para obtener los resultados deseados. Puede comprobar los valores del registro en el que se está ejecutando el proceso de flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de N:1 o valores dentro del propio proceso.  
  
|Tipo de condición|Denominación|  
|--------------------|-----------------|  
|**Condición de comprobación**|Instrucción lógica "If-\<" > then ".<br /><br /> Puede comprobar los valores actuales del registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de N:1 o cualquier registro creado en los pasos anteriores. Según estos valores, puede definir pasos adicionales cuando la condición sea verdadera.<br /><br /> En la instrucción ' if-\<Condition > then, puede usar los operadores siguientes: **es igual**a, no **es igual**a, **contiene datos**, no **contiene datos**, **en** y **no en**. **Nota:**  **En** y **no en** , son operadores jerárquicos. Solo se pueden usar en las entidades que tienen definida una relación jerárquica. Si está intentando usar estos operadores en las entidades que no tienen definida la relación jerárquica, verá el mensaje de error: "usa un operador jerárquico en una entidad que no tiene definida una relación jerárquica. Haga que la entidad sea jerárquica (marcando una relación como jerárquica) o use un operador diferente ". Para obtener más información sobre las relaciones jerárquicas, vea [definir y consultar datos relacionados jerárquicamente](/powerapps/maker/common-data-service/define-query-hierarchical-data). Una captura de pantalla que sigue a la tabla es un ejemplo de la definición del proceso de flujo de trabajo que usa **en** y **no en** los operadores jerárquicos.|  
|**Rama condicional**|Una instrucción "else-if-then" lógica, el editor usa el texto "de lo contrario, si \<condición >:"<br /><br /> Seleccione una condición de comprobación que haya definido previamente y puede Agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelva false.|  
|**Acción predeterminada**|Instrucción "Else" lógica. el editor usa el texto "otherwise:"<br /><br /> Seleccione una condición de comprobación, una rama condicional, una condición de espera o una rama de espera paralela que haya definido previamente, y puede usar una acción predeterminada para definir los pasos para todos los casos que no coincidan con los criterios definidos en los elementos Condition o Branch.|  
|**Condición de espera**|Permite a un flujo de trabajo en segundo plano pausarse hasta que se cumplan los criterios definidos por la condición. El flujo de trabajo se inicia de nuevo automáticamente cuando se cumplen los criterios de la condición de espera.<br /><br /> Los flujos de trabajo en tiempo real no pueden utilizar condiciones de espera.|  
|**Rama de espera paralela**|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con un conjunto de pasos adicionales correspondiente que se realiza solo cuando se cumple el criterio inicial. Puede usar ramas de espera paralelas para crear límites de tiempo en la lógica del flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere indefinidamente hasta que se cumplan los criterios definidos en una condición de espera.|  
|**Paso personalizado**|Los desarrolladores pueden crear pasos de flujo de trabajo personalizados que definan condiciones. No hay ningún paso personalizado disponible de forma predeterminada.|  
  
 La captura de pantalla siguiente contiene un ejemplo de la definición del proceso de flujo de trabajo con **en** y **no en** operadores jerárquicos. En nuestro ejemplo, se aplican dos descuentos diferentes a dos grupos de cuentas. En **Agregar paso**, seleccionamos la **condición de comprobación** para especificar la condición **if-then** que contiene los operadores **en** o **no en** . La primera condición **if-then** se aplica a todas las cuentas que se encuentran **en** la cuenta Alpine Ski House. Estas cuentas reciben un 10% de descuento en buenos y servicios adquiridos. La segunda condición **if-then** se aplica a todas las cuentas que **no están en** la cuenta Alpine Ski House y reciben un descuento del 5%. Después, seleccionó **Actualizar registro** para definir la acción que se realizará en función de la condición.  
  
 ![Proceso de flujo de&#47;trabajo con operadores no bajos](media/wfp-under-not-under.PNG "Proceso de flujo de trabajo con operadores bajo/no en")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Uso de flujos de trabajo en tiempo real  

 Puede configurar flujos de trabajo en tiempo real, pero debe usarlos con cuidado. Los flujos de trabajo en segundo plano se suelen recomendar porque permiten que el sistema los aplique a medida que los recursos del servidor están disponibles. Esto ayuda a suavizar el trabajo que tiene que hacer el servidor y a mantener el mejor rendimiento para todos los usuarios que usan el sistema. El inconveniente es que las acciones definidas por los flujos de trabajo en segundo plano no son inmediatas. No se puede predecir cuándo se aplicarán, pero por lo general se tardará unos minutos. Para la mayoría de la automatización de los procesos empresariales, esto es correcto porque no es necesario que los usuarios que usan el sistema sepan que el proceso se está ejecutando.  
  
 Use flujos de trabajo en tiempo real cuando un proceso empresarial solicite a alguien que vea inmediatamente los resultados del proceso o si desea poder cancelar una operación. Por ejemplo, puede que desee establecer ciertos valores predeterminados para un registro la primera vez que se guarda o desea asegurarse de que algunos registros no se eliminan.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversión entre flujos de trabajo en tiempo real y en segundo plano  

 Puede cambiar un flujo de trabajo en tiempo real a un flujo de trabajo en segundo plano si elige **convertir en un flujo de trabajo en segundo plano** en la barra de herramientas.  
  
 Puede cambiar un flujo de trabajo en segundo plano en un flujo de trabajo en tiempo real eligiendo **convertir en un flujo de trabajo en tiempo real** en la barra de herramientas. Si el flujo de trabajo en segundo plano usa condiciones de espera, dejará de ser válida y no podrá activarla hasta que quite la condición de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Inicio de flujos de trabajo en tiempo real antes o después de los cambios de estado  

 Cuando se configuran **las opciones de procesos automáticos** para flujos de trabajo en tiempo real, el evento **iniciar cuando** las opciones del estado cambia le permiten seleccionar **después** o **antes** de cuando cambia el estado. La opción predeterminada es **After**.  
  
 Al seleccionar **antes** de indicar que desea que se aplique la lógica en el flujo de trabajo antes de que se guarden los datos que cambian el estado. Esto le proporciona la capacidad de comprobar los valores antes de que se aplique otra lógica después de la operación e impedir que se realice una lógica adicional. Por ejemplo, puede tener lógica adicional en un complemento o una acción de flujo de trabajo personalizada que podría iniciar acciones en otro sistema. Al detener el procesamiento, puede evitar los casos en los que los sistemas externos se ven afectados. Aplicar flujos de trabajo en tiempo real antes de este evento también significa que no es necesario "revertir" otras acciones de flujo de trabajo o de complementos que puedan haber guardado datos cuando se cancela la operación.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Usar la acción detener flujo de trabajo con flujos de trabajo en tiempo real  

 Al aplicar una acción **detener flujo de trabajo** en un flujo de trabajo, tiene la opción de especificar una condición de estado que puede ser **correcta** o **cancelada**. Cuando se establece el estado en cancelado, se impide la operación. Se mostrará al usuario un mensaje de error que contiene el texto del mensaje de estado de la acción de detención con el encabezado **error de proceso empresarial**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Crear lógica de negocios personalizada con procesos](guide-staff-through-common-tasks-processes.md)   
 [Información general de procesos de flujo de trabajo](workflow-processes.md)   
 [Supervisión y administración de procesos de flujo de trabajo](monitor-manage-processes.md)   
 [Prácticas recomendadas para los procesos de flujo de trabajo](best-practices-workflow-processes.md)
