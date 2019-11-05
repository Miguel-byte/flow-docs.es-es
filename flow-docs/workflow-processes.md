---
title: Flujos de trabajo de Common Data Service clásico | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548335"
---
# <a name="classic-common-data-service-workflows"></a>Flujos de trabajo de Common Data Service clásico 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los flujos de trabajo automatizan los procesos empresariales sin una interfaz de usuario. Normalmente, los usuarios utilizan procesos de flujo de trabajo para iniciar la automatización que no requiere ninguna interacción del usuario.

> [!IMPORTANT]
> Use flujos en lugar de flujos de trabajo clásicos para automatizar los procesos empresariales. Más información: [reemplazo de flujos de trabajo de Common Data Service clásico con flujos](replace-workflows-with-flows.md)  
  
 Cada proceso de flujo de trabajo está asociado a una sola entidad. Al configurar los flujos de trabajo tiene cuatro áreas principales a tener en cuenta:  
  
-   ¿Cuándo iniciarlos?  
  
-   ¿Deben ejecutarse como un flujo de trabajo en tiempo real o un flujo de trabajo en segundo plano?  
  
-   ¿Qué acciones deben realizar?  
  
-   ¿En qué condiciones se deben realizar acciones?  
  
 En este tema se explica cómo buscar procesos de flujo de trabajo y se describe cuándo iniciarlos y si deben ejecutarse en tiempo real o en segundo plano. Para obtener información sobre las acciones que deben realizar y las condiciones, consulte [configuración de procesos de flujo de trabajo](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>¿Dónde se personalizan los procesos de flujo de trabajo?  
 Para ver los flujos de trabajo de la organización, vea el nodo **procesos** de la **solución predeterminada** y filtre por los procesos que tienen el **flujo de trabajo** **categoría** .  
  
 ![Procesos filtrados por flujo de trabajo en Dynamics 365](media/workflow-processes-filtered.PNG "Procesos filtrados por flujo de trabajo en Dynamics 365")  
  
 En función de cómo se cree la aplicación, los usuarios pueden crear o modificar sus flujos de trabajo en la aplicación. 
 
Los desarrolladores pueden crear flujos de trabajo mediante la información de la [Guía para desarrolladores de Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) y las soluciones que compre pueden incluir flujos de trabajo que puede modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propiedades de flujo de trabajo  
 En el explorador de soluciones, seleccione **procesos** y haga clic en **nuevo**.  
  
 Cuando se crea un flujo de trabajo, el cuadro de diálogo **Crear proceso** requiere que se establezcan tres propiedades que tienen todos los procesos:  
  
 ![Creación de un flujo de trabajo en Dynamics 365](media/create-workflow.PNG "Creación de un flujo de trabajo en Dynamics 365")  
  
 **Nombre del proceso**  
 No es necesario que el nombre del proceso de flujo de trabajo sea único, pero si espera que tenga muchos flujos de trabajo, puede que desee usar una Convención de nomenclatura para diferenciar claramente sus procesos. Es posible que desee aplicar prefijos estándar al nombre del flujo de trabajo. El prefijo puede describir la función del flujo de trabajo o el Departamento de la empresa. Esto le ayudará a agrupar elementos similares en la lista de flujos de trabajo.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de flujo de trabajo.  
  
 **ID**  
 Cada proceso de flujo de trabajo debe establecerse en una sola entidad. No se puede cambiar la entidad después de crear el proceso de flujo de trabajo.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta opción aparece al seleccionar flujo de trabajo como categoría. Esta configuración determina si el flujo de trabajo es un flujo de trabajo en tiempo real o en segundo plano. Los flujos de trabajo en tiempo real se ejecutan de forma inmediata y los flujos de trabajo en segundo plano se ejecutan de forma asincrónica. Las opciones de configuración disponibles dependen de la opción que elija para esta opción. Los flujos de trabajo en segundo plano permiten condiciones de espera que no están disponibles para los flujos de trabajo en tiempo real. Siempre y cuando no use esas condiciones de espera, puede convertir los flujos de trabajo en segundo plano en flujos de trabajo en tiempo real y flujos de trabajo en tiempo real en flujos de trabajo en segundo plano. Para obtener más información sobre las condiciones de espera, vea [establecer condiciones para las acciones de flujo de trabajo](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 También tiene la opción **tipo** para especificar si se va a crear un nuevo flujo de trabajo desde cero o se puede iniciar desde una plantilla existente. Al elegir **nuevo proceso desde una plantilla existente (seleccionar de la lista)** puede elegir entre los procesos de flujos de trabajo disponibles que se guardaron previamente como una plantilla de proceso.  
  
 Después de crear el flujo de trabajo o de editar uno existente, tendrá las siguientes propiedades adicionales:  
  
 ![Pestaña General de un flujo de trabajo](media/create-workflow-general-tab.PNG "Pestaña General de un flujo de trabajo")  
  
 **Activar como**  
 Puede elegir **plantilla de proceso** para crear un punto de inicio avanzado para otras plantillas. Si elige esta opción, después de activar el flujo de trabajo, no se aplicará pero, en su lugar, estará disponible para seleccionarlo en el cuadro de diálogo **Crear proceso** si selecciona **tipo**: **nuevo proceso de una plantilla existente (seleccionar de la lista)** .  
  
 Las plantillas de proceso son útiles cuando se tiene una serie de procesos de flujo de trabajo similares y se quieren definirlos sin duplicar la misma lógica.  
  
> [!NOTE]
>  La edición de una plantilla de proceso no cambia los comportamientos de ningún otro proceso de flujo de trabajo creado previamente utilizando como plantilla. Un nuevo flujo de trabajo creado mediante una plantilla es una copia del contenido de la plantilla.  
  
 **Disponible para ejecutarse**  
 Esta sección contiene opciones que describen cómo está disponible el flujo de trabajo para su ejecución.  
  
 **Ejecutar este flujo de trabajo en segundo plano (recomendado)**  
 Esta casilla refleja la opción seleccionada al crear el flujo de trabajo. Esta opción está deshabilitada, pero puede cambiarla desde el menú **acciones** eligiendo **convertir en un flujo de trabajo en tiempo real** o **convertir en un flujo de trabajo en segundo plano**.  
  
 **Como un proceso a petición**  
 Elija esta opción si desea permitir que los usuarios ejecuten este flujo de trabajo desde el comando **Ejecutar flujo de trabajo** .  
  
 **Como proceso secundario**  
 Elija esta opción si desea permitir que el flujo de trabajo esté disponible para iniciarse desde otro flujo de trabajo.  
  
 **Retención de trabajos de flujo de trabajo**  
 Esta sección contiene una opción para eliminar un flujo de trabajo después de que se haya completado la ejecución del flujo de trabajo.  
  
 **Eliminar automáticamente las tareas de flujo de trabajo completadas (para ahorrar espacio en disco)**  
 Elija esta opción si desea que se elimine automáticamente una tarea de flujo de trabajo completada.  
  
> [!NOTE]
>  Las tareas del flujo de trabajo no se eliminan inmediatamente después de la finalización, pero poco después, a través de un proceso por lotes.  
  
 **ID**  
 En el caso de las entidades propiedad del usuario, las opciones son **organización**, **principal: unidades de negocio secundarias**, **unidad de negocio**o **usuario**. En el caso de las entidades propiedad de la organización, la única opción es **organización**.  
  
 Si el ámbito es **organización**, la lógica de flujo de trabajo se puede aplicar a cualquier registro de la organización. De lo contrario, el flujo de trabajo solo se puede aplicar a un subconjunto de registros que se encuentran dentro del ámbito.  
  
> [!NOTE]
>  El valor de ámbito predeterminado es **usuario**. Asegúrese de comprobar que el valor de ámbito es adecuado antes de activar el flujo de trabajo.  
  
 **Iniciar cuando**  
 Utilice las opciones de esta sección para especificar Cuándo debe iniciarse un flujo de trabajo automáticamente. Puede configurar un flujo de trabajo en tiempo real para que se ejecute antes de determinados eventos. Se trata de una funcionalidad muy eficaz porque el flujo de trabajo puede detener la acción antes de que se produzca. Más información: [uso de flujos de trabajo en tiempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Las opciones son:  
  
- **Se crea el registro**  
  
- **Cambios de estado de registro**  
  
- **El registro está asignado**  
  
- **Cambio de campos de registro**  
  
- **El registro se ha eliminado**  
  
> [!NOTE]
>  Tenga en cuenta que las acciones y condiciones que defina para el flujo de trabajo no son conscientes de Cuándo se ejecuta el flujo de trabajo. Por ejemplo, si define un flujo de trabajo para actualizar el registro, esta acción no se puede realizar mediante un flujo de trabajo en tiempo real antes de que se cree el registro. No se puede actualizar un registro que no existe. De forma similar, un flujo de trabajo en segundo plano no puede actualizar un registro que se ha eliminado, aunque podría definir esta acción para el flujo de trabajo. Si configura un flujo de trabajo para realizar una acción que no se puede realizar, se producirá un error y se producirá un error en todo el flujo de trabajo.  
  
 **Ejecutar como**  
 Esta opción solo está disponible si anula la selección de la opción **ejecutar este flujo de trabajo en segundo plano (recomendado)** al crear el flujo de trabajo o si posteriormente convirtió un flujo de trabajo en segundo plano para que sea un flujo de trabajo en tiempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de seguridad de procesos de flujo de trabajo  
 Cuando un flujo de trabajo en segundo plano se configura como un proceso a petición y lo inicia un usuario mediante el comando **Ejecutar flujo** de trabajo, las acciones que puede realizar el flujo de trabajo se limitan a las que el usuario podría realizar en función de los privilegios y los niveles de acceso definidos por los roles de seguridad establecidos para su cuenta de usuario.  
  
 Cuando un flujo de trabajo en segundo plano comienza en función de un evento, el flujo de trabajo funciona en el contexto de la persona que lo posee, normalmente la persona que creó el flujo de trabajo.  
  
 En el caso de los flujos de trabajo en tiempo real, tiene la opción **Execute as** y puede elegir si el flujo de trabajo debe aplicar el contexto de seguridad del propietario del flujo de trabajo o el usuario que realizó los cambios en el registro. Si el flujo de trabajo incluye acciones que todos los usuarios no podrían realizar en función de las restricciones de seguridad, debe elegir que el flujo de trabajo se ejecute como el propietario del flujo de trabajo.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Activación de un flujo de trabajo  
 Los flujos de trabajo solo se pueden editar mientras están desactivados. Antes de que un flujo de trabajo se pueda usar manualmente o se pueda aplicar debido a eventos, debe activarse. Antes de que se pueda activar un flujo de trabajo, debe contener al menos un paso. Para obtener información sobre cómo configurar los pasos, consulte [configuración de procesos de flujo de trabajo](configure-workflow-steps.md)  
  
 Un flujo de trabajo solo puede activarse o desactivarse por parte del propietario del flujo de trabajo o por alguien con la **acción en nombre de otro privilegio de usuario** , como el administrador del sistema.  Esta es la razón por la que un usuario malintencionado podría modificar el flujo de trabajo de alguien sin conocer el cambio. Puede reasignar un flujo de trabajo de su propiedad cambiando el propietario. Este campo está en la pestaña **Administración** . Si no es el administrador del sistema y necesita editar un flujo de trabajo que sea propiedad de otro usuario, debe desactivarlo y asignarlo a usted. Una vez que termine de editar el flujo de trabajo, puede volver a asignarlo para que pueda activarlo.  
  
 Los flujos de trabajo en tiempo real requieren que el usuario tenga el privilegio **activar procesos en tiempo real** . Dado que los flujos de trabajo en tiempo real tienen un mayor riesgo de afectar al rendimiento del sistema, solo se debe conceder este privilegio a las personas que pueden evaluar el riesgo potencial.  
  
 Los flujos de trabajo se guardan cuando se activan, por lo que no es necesario guardarlos antes de activarlos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Configuración de procesos de flujo de trabajo](configure-workflow-steps.md)  <br/>
[Agregar un flujo de trabajo a petición a un flujo de procesos empresariales](bpf-add-on-demand-workflow.md) 

