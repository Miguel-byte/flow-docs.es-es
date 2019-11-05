---
title: Crear un flujo de procesos empresariales en PowerApps | MicrosoftDocs
description: Aprenda a crear un flujo de procesos empresariales
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546531"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: creación de un flujo de procesos empresariales para estandarizar procesos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este tutorial se muestra cómo crear un flujo de procesos empresariales con PowerApps. Para más información sobre por qué usar los flujos de procesos empresariales, consulte [información general sobre flujos de procesos empresariales](business-process-flows-overview.md). Para obtener información sobre cómo crear un flujo de tareas móviles, consulte [crear un flujo de tareas móviles](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Cuando un usuario inicia un flujo de procesos empresariales, las fases y los pasos del proceso se muestran en la barra de proceso en la parte superior de un formulario:  
  
 ![Proceso empresarial con fases](media/business-process-stages.png "Proceso empresarial con fases")  
  
 > [!TIP]
 >  Después de crear una definición de flujo de proceso empresarial, puede proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia de flujo de proceso empresarial. Por ejemplo, para los procesos relacionados con el servicio, puede proporcionar acceso completo para que los representantes del servicio de atención al cliente cambien la instancia de flujo del proceso de negocio, pero proporcionan acceso de solo lectura a la instancia de los representantes de ventas para que puedan supervisar las actividades posteriores a la venta de su compradores. Para establecer la seguridad de una definición de flujo de proceso empresarial que cree, seleccione **Habilitar roles de seguridad** en la barra de acciones.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Requisitos previos

Necesita el [plan de flujo 2](https://preview.flow.microsoft.com/pricing/) para crear flujos de procesos empresariales. Algunos planes de licencias de Dynamics 365 incluyen el plan de flujo 2.

## <a name="create-a-business-process-flow"></a>Crear un flujo de procesos empresariales  
  
1. Abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. En el panel de navegación izquierdo, seleccione **procesos**. 
  
3.  En la barra de herramientas **acciones** , seleccione **nuevo**.  
  
4.  En el cuadro de diálogo **Crear proceso** , complete los campos obligatorios:  
  
    -   Escriba un nombre de proceso. No es necesario que el nombre del proceso sea único, pero debe ser significativo para las personas que necesitan elegir un proceso. Puede cambiarlo más adelante.  
  
    -   En la lista **categoría** , seleccione **flujo de procesos empresariales**.  
  
         No se puede cambiar la categoría después de crear el proceso.  
  
    -   En la lista **entidad** , seleccione la entidad en la que desea basar el proceso.  
  
         La entidad que seleccione afectará a los campos disponibles para los pasos que se pueden agregar a la primera fase del flujo de proceso. Si no encuentra la entidad que desea, asegúrese de que la entidad tiene la opción flujos de procesos empresariales (se crearán campos) establecida en la definición de la entidad. No se puede cambiar después de guardar el proceso.  
  
5. Seleccione **Aceptar**.  
  
     Se crea el nuevo proceso y se abre el diseñador de flujo de procesos empresariales con una sola fase ya creada.  
  
 ![Ventana flujo de proceso empresarial que muestra los elementos principales](media/business-process-flow-window-showing-main-elements.png "Ventana flujo de proceso empresarial que muestra los elementos principales")  
  
6. **Agregar fases.** Si los usuarios van a progresar de una etapa de negocio a otra en el proceso:  
  
    1.  Arrastre un componente de **fase** de la pestaña **componentes** y colóquelo en un signo + en el diseñador.  
  
        ![Arrastrar una fase de proceso empresarial](media/drag-business-process-stage.png "Arrastrar una fase de proceso empresarial")  
  
    2.  Para establecer las propiedades de una fase, seleccione la fase y, a continuación, establezca las propiedades en la pestaña **propiedades** en el lado derecho de la pantalla:  
  
        -   Escriba un nombre para mostrar.  
  
        -   Si lo desea, seleccione una categoría para la fase.  La categoría (como **calificar** o **desarrollar**) aparece como un botón de contenido adicional en la barra de proceso.  
  
            ![Botón de contenido de barra de proceso empresarial](media/business-process-bar-chevron.png "Botón de contenido de barra de proceso empresarial")  
  
        -   Cuando haya terminado de cambiar las propiedades, seleccione el botón **aplicar** .  
  
7. **Agregue pasos a una fase.** Para ver los pasos de una fase, seleccione **detalles** en la esquina inferior derecha de la fase. Para agregar más pasos:  
  
    1.  Arrastre el componente **Step** hasta la fase de la pestaña **componentes** .  
  
        ![Agregar paso a una fase en un proceso empresarial](media/add-step-stage-business-process.png "Agregar paso a una fase en un proceso empresarial")  
  
    2.  Seleccione el paso y, a continuación, establezca propiedades en la pestaña **propiedades** :  
  
        1.  Escriba un nombre para mostrar para el paso.  
  
        2.  Si desea que los usuarios escriban datos para completar un paso, seleccione el campo adecuado en la lista desplegable.  
  
        3.  Seleccione **requerido** si los usuarios deben rellenar el campo para completar el paso antes de pasar a la siguiente fase del proceso.  
  
        4.  Seleccione **aplicar** cuando haya terminado.  
  
8. **Agregue una rama (condición) al proceso.** Para agregar una condición de bifurcación:  
  
    1.  Arrastre el componente **condición** de la pestaña **componentes** a un signo + entre dos fases.  
  
        ![Agregar una condición a un flujo de procesos empresariales](media/add-condition-business-process-flow.png "Agregar una condición a un flujo de procesos empresariales")  
  
    2.  Seleccione la condición y, a continuación, establezca propiedades en la pestaña **propiedades** . Para obtener más información sobre las propiedades de bifurcación, vea [mejorar los flujos de procesos empresariales con bifurcación](enhance-business-process-flows-branching.md). Cuando haya terminado de establecer las propiedades de la condición, seleccione **aplicar**.  
  
9. **Agregue un flujo de trabajo.** Para invocar un flujo de trabajo:  
  
    1.  Arrastre un componente de **flujo de trabajo** desde la pestaña **componentes** a una fase o hasta el elemento **flujo de trabajo global** en el diseñador.   La que se agrega a depende de lo siguiente:  
  
       - **Arrástrelo hasta una fase** en la que desee desencadenar el flujo de trabajo en la entrada o salida de la fase. El componente de flujo de trabajo debe basarse en la misma entidad principal que la fase.  
  
       - **Arrástrelo hasta el elemento de flujo de trabajo global** cuando quiera desencadenar el flujo de trabajo cuando se active el proceso o cuando el proceso se Archive (cuando el estado cambie a **completado** o **abandonado**). El componente de flujo de trabajo debe basarse en la misma entidad principal que el proceso.  
  
    2.  Seleccione el flujo de trabajo y, a continuación, establezca propiedades en la pestaña **propiedades** :  
  
       1.  Escriba un nombre para mostrar.  
  
       2.  Seleccione Cuándo se debe desencadenar el flujo de trabajo.  
  
       3.  Busque un flujo de trabajo activo a petición existente que coincida con la entidad de fase o cree un nuevo flujo de trabajo seleccionando **nuevo**.  
  
       4.  Seleccione **aplicar** cuando haya terminado.  
  
       Para obtener más información sobre los flujos de trabajo, vea [procesos de flujo de trabajo](../common-data-service/workflow-processes.md).  
  
10. Para validar el flujo de procesos empresariales, seleccione **validar** en la barra de acciones.  
  
11. Para guardar el proceso como borrador mientras sigue trabajando en él, seleccione **Guardar** en la barra de acciones.  
  
    > [!IMPORTANT]
    >  Siempre que un proceso sea un borrador, los usuarios no podrán usarlo.  
  
12. Para activar el proceso y ponerlo a disposición de su equipo, seleccione **Activar** en la barra de acciones.  

13. Para proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia de flujo de proceso empresarial, seleccione **Editar roles de seguridad** en la barra de comandos del diseñador. Por ejemplo, para los procesos relacionados con el servicio, puede proporcionar acceso completo para que los representantes del servicio de atención al cliente cambien la instancia de flujo del proceso de negocio, pero proporcionan acceso de solo lectura a la instancia de los representantes de ventas para que puedan supervisar las actividades posteriores a la venta de su compradores.

  En la pantalla **roles de seguridad** , seleccione el nombre de un rol para abrir la página información de rol de seguridad. Seleccione la pestaña flujos de procesos empresariales y, a continuación, asigne los privilegios adecuados en el flujo de procesos empresariales para un rol de seguridad.

  > [!NOTE]
  > Los roles de seguridad de administrador del sistema y de Personalizador del sistema tienen acceso de forma predeterminada a los nuevos flujos de procesos empresariales.

   ![Asignar privilegios a un flujo de procesos empresariales](media/bpf-assign-privileges.png)

  Especifique los privilegios seleccionando los botones de radio adecuados y haga clic en guardar. Para obtener más información acerca de los privilegios, vea [privilegios de flujo de procesos empresariales](business-process-flows-overview.md#BKMK_MultipleBPF).

  Después, no olvide asignar el rol de seguridad a los usuarios adecuados de su organización.

> [!TIP] 
>  Estas son algunas sugerencias que hay que tener en cuenta al trabajar en el flujo de tareas en la ventana del diseñador:  
>   
> - Para tomar una instantánea de todo en la ventana flujo de proceso empresarial, seleccione **instantánea** en la barra de acciones. Esto resulta útil, por ejemplo, si desea compartir y obtener comentarios sobre el proceso de un miembro del equipo.  
> - Use la asignación mínima para navegar rápidamente a diferentes partes del proceso. Esto resulta útil cuando se tiene un proceso complicado que se desplaza fuera de la pantalla.  
> - Para agregar una descripción para el proceso empresarial, seleccione **detalles** en el nombre del proceso en la esquina izquierda de la ventana flujo de proceso empresarial. Puede usar hasta 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar un flujo de procesos empresariales  
 Para editar flujos de procesos empresariales, abra el explorador de soluciones, seleccione **procesos**y, a continuación, seleccione el **flujo de procesos empresariales** en la lista de procesos que desea editar.  
  
 Al seleccionar el nombre del flujo de proceso empresarial que desea editar en la lista de procesos, se abre en el diseñador, donde puede hacer las actualizaciones que desee. Expanda **detalles** bajo el nombre del proceso para cambiarle el nombre o agregue una descripción y vea información adicional.  
  
 ![Sección de detalles expandida de un flujo de procesos empresariales](media/business-process-flow-details.png "Sección de detalles expandida de un flujo de procesos empresariales")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Otros aspectos que se deben conocer acerca de los flujos de procesos empresariales
 **Editar fases**  
Los flujos de procesos empresariales pueden tener hasta 30 fases.    
  
Puede Agregar o cambiar las siguientes propiedades de una fase:  
  
- **Nombre de la fase**  
  
- **Entidad**. Puede cambiar la entidad para cualquier fase excepto la primera.  
  
- **Categoría de fase**. Una categoría permite agrupar las fases por un tipo de acción. Resulta útil para los informes que agruparán los registros por la fase en la que se encuentran. Las opciones de la categoría fase provienen del conjunto de opciones globales de la categoría de fase. Puede agregar opciones adicionales a este conjunto de opciones global y cambiar las etiquetas de las opciones existentes si lo desea. También puede eliminar estas opciones si lo desea, pero le recomendamos que mantenga las opciones existentes. No podrá volver a agregar exactamente la misma opción si la elimina. Si no quiere que se usen, cambie la etiqueta a "no usar".  
  
- **Relación**. Escriba una relación cuando la fase anterior del proceso se base en otra entidad. En la fase que se está definiendo actualmente, elija **seleccionar relaciones** para identificar una relación que se va a usar al moverse entre las dos fases. Se recomienda seleccionar una relación para las siguientes ventajas:  
  
    -   A menudo, las relaciones tienen asignaciones de atributos definidas que transportan automáticamente los datos entre los registros, lo que minimiza la entrada de datos.  
  
    -   Al seleccionar **fase siguiente** en la barra de proceso de un registro, los registros que usan la relación se enumerarán en el flujo de proceso, con lo que se fomenta la reutilización de los registros en el proceso. Además, puede usar flujos de trabajo para automatizar la creación de registros de modo que el usuario simplemente lo seleccione en lugar de crear uno para optimizar aún más el proceso.  
  
**Editar pasos**  
 Cada fase puede tener hasta 30 pasos.    
  
**Agregar rama**  
Para obtener información sobre cómo agregar una rama a una fase, vea [mejorar los flujos de procesos empresariales con bifurcación](enhance-business-process-flows-branching.md).  
  
Para que un flujo de procesos empresariales esté disponible para que lo usen los usuarios, debe solicitar el flujo de proceso, habilitar los roles de seguridad y activarlo.  
  
**Establecer el orden de flujo de proceso**  
 Si tiene más de un flujo de procesos empresariales para una entidad (tipo de registro), deberá establecer qué proceso se asigna automáticamente a los nuevos registros. En la barra de comandos, seleccione **ordenar flujo de proceso**. En el caso de los registros o registros nuevos que aún no tienen un flujo de proceso asociado, el primer flujo de proceso empresarial al que un usuario tiene acceso es el que se usará.  
  
**Habilitar roles de seguridad**  
Los usuarios tienen acceso a un flujo de procesos empresariales en función del privilegio definido en el flujo de procesos empresariales en el rol de seguridad asignado al usuario. 

De forma predeterminada, solo los roles de seguridad de **Administrador del** sistema y de **Personalizador del sistema** pueden ver un nuevo flujo de procesos empresariales. 

Para especificar los privilegios de un flujo de procesos empresariales, abra el flujo de procesos empresariales para editar y, a continuación, seleccione **Editar roles de seguridad** en la barra de comandos del diseñador de flujo de procesos empresariales. Vea el paso 13 en [crear un flujo de proceso de negocio](#create-a-business-process-flow) que se muestra anteriormente en este tema.
  
**Activación**  
Para que cualquier usuario pueda usar el flujo de procesos empresariales, debe activarlo. En la barra de comandos, seleccione **Activar**. Después de confirmar la activación, el flujo de procesos empresariales está listo para usarse. Si un flujo de procesos empresariales tiene errores, no podrá activarlo hasta que se corrijan los errores.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Agregar una acción a petición a un flujo de procesos empresariales
La actualización de Dynamics 365 (en línea), versión 9,0 presenta una característica de flujo de procesos empresariales: automatización del flujo de procesos empresariales con los pasos de acción. Puede Agregar un botón a un flujo de procesos empresariales que desencadenará una acción o un flujo de trabajo.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Agregar flujos de trabajo a petición o acciones mediante un paso de acción
Supongamos que, como parte del proceso de cualificación de la oportunidad, la organización de Contoso requiere que todas las oportunidades sean revisadas por un revisor designado. Posteriormente, la organización de Contoso creó una acción que: 

- Crea un registro de tarea asignado al revisor de oportunidades. 
- Anexa "Ready for Review" al tema de la oportunidad. 

Además, Contoso debe ser capaz de ejecutar estas acciones a petición. Para integrar estas tareas en el proceso de calificación de oportunidades, las acciones deben aparecer en el flujo de procesos empresariales de la oportunidad. Para habilitar esta funcionalidad, seleccione **como un paso de acción de flujo de procesos empresariales**.
![disponible para ejecutarse como un flujo de procesos empresariales.](media/action-available-to-run.png)

A continuación, el paso de acción se agrega al flujo de procesos empresariales de la oportunidad de contoso. Después, el flujo de proceso se valida y se actualiza.

![Acción agregada al flujo de procesos empresariales de oportunidades.](media/add-action-to-bpf.png)

Ahora, los miembros de Salesforce de Contoso pueden poner en marcha la acción del paso de proceso empresarial de **cualificación de oportunidades** , a petición, seleccionando **Ejecutar**.

![Ejecutar acción.](media/action-execute.png)

> [!IMPORTANT]
> - Para poder ejecutar una acción o flujo de trabajo a petición, el flujo de proceso empresarial debe incluir un paso de acción. Si el paso de acción ejecuta un flujo de trabajo, el flujo de trabajo se debe configurar para ejecutarse a petición.
> - La entidad asociada a la acción o flujo de trabajo debe ser la misma que la entidad asociada al flujo de procesos empresariales.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitación del uso de pasos de acción en un flujo de procesos empresariales

- Las acciones no están disponibles como pasos de acción si los parámetros de entrada o salida son tipos de entidad, EntityCollection o OptionSet (lista desplegable). Las acciones con más de un parámetro de salida de EntityReference o cualquier número de parámetros de entrada de EntityReference no están disponibles como pasos de acción. Las acciones no asociadas a una entidad principal (acción global) no están disponibles como pasos de acción.

## <a name="instant-flows-in-business-process-flows"></a>Flujos instantáneos en flujos de procesos empresariales

Puede ejecutar un **flujo instantáneo** para automatizar tareas repetitivas, generar documentos, realizar un seguimiento de las aprobaciones, etc., desde dentro de una fase en un proceso empresarial.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Agregar un flujo instantáneo como un paso en un proceso empresarial

Supongamos que vende impresoras y usa el **proceso de ventas** de la oportunidad a las oportunidades para cerrar acuerdos. Como parte de este proceso, le gustaría que el responsable de equipo Revise y apruebe las propuestas que el equipo de ventas colocará en una fase anterior del flujo de procesos empresariales antes de compartirla con el cliente.

Para ello, deberá hacer dos cosas:
1. Cree un flujo instantáneo que solicite la revisión y aprobación de la propuesta del equipo.
1. Agregue el flujo instantáneo como un paso en el **proceso de ventas de clientes potenciales a oportunidades**.

> [!TIP]
> Solo los [flujos que reconocen soluciones](https://docs.microsoft.com/flow/overview-solution-flows) se pueden agregar como un paso en un proceso empresarial. 

### <a name="build-an-instant-flow"></a>Creación de un flujo instantáneo

1. En Microsoft Flow, seleccione **soluciones** en el menú de navegación.
1. Seleccione **solución predeterminada** en la lista de soluciones que aparece. 
1. Seleccione el menú **+ nuevo** y, después, seleccione **Flow (flujo** ) en la lista que aparece.
1. Busque y, a continuación, seleccione el conector de **Common Data Service** .
1. Busque y, a continuación, seleccione el desencadenador **cuando se selecciona un registro** en la lista de desencadenadores de **Common Data Service** .
1. Establezca **entorno** en **predeterminado**y, a continuación, establezca **el nombre** de la entidad en **proceso de ventas de oportunidades**.
1. Agregue un campo de entrada de texto para que el usuario escriba el vínculo a la propuesta.

   ![Desencadenador de flujo instantáneo](media/instant-flow-trigger.png "Desencadenador de flujo instantáneo")

   Necesitaremos información de la instancia de flujo de proceso empresarial para ayudar a proporcionar el contexto de la solicitud de aprobación, por lo que debe seguir estos pasos para hacerlo.

1. Agregue la acción de **análisis de JSON** . 
1. Establezca el **contenido** en **entidad** seleccionándolo en la lista de valores dinámicos para el desencadenador **cuando se selecciona un registro** .
1. Pegue el siguiente contenido en el campo **esquema** .

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   Las cosas deben ser similares a las siguientes:

   ![Análisis de JSON](media/instant-flow-json-date.png "Análisis de JSON")

  1. Agregue la acción **obtener registro** del conector de **Common Data Service** .
  1. Establezca **entorno** en **(actual)** , **nombre de entidad** en **proceso de ventas de oportunidades**e **identificador de elemento** en **BPFFlowStageEntityRecordID**.

     ![Agregar un registro](media/instant-flow-add-record.png)

     Ahora que tenemos los datos, defina el proceso de aprobación agregando el **Inicio y la espera de una acción de aprobación (V2)** y, a continuación, rellene la información pertinente. Obtenga más información sobre las [aprobaciones]( sequential-modern-approvals.md) si no está familiarizado con.

     > [!TIP]
     > - Use el selector de contenido dinámico para agregar campos de la acción **obtener registro** para agregar información relevante a la solicitud de aprobación, de modo que los aprobadores puedan saber con facilidad de qué trata la solicitud. 
     > - Para proporcionar más contexto sobre la fase activa en la que se encuentra el proceso empresarial, agregue el campo **BPFActiveStageLocalizedName** de la lista de valores dinámicos.

     El **Inicio y la espera de una tarjeta de aprobación (V2)** pueden tener un aspecto similar al siguiente:

      ![Tarjeta de aprobación](media/instant-flow-add-approval-action.png)

1. Por último, guarde el flujo y enciéndalo.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Agregue este flujo como un paso en el proceso de ventas de clientes potenciales a oportunidades.

Ahora que ha creado el flujo instantáneo, lo único que se necesita es agregarlo al flujo de procesos empresariales. 

1. Abra el **proceso de ventas de clientes potenciales** en el diseñador de flujo de procesos empresariales. 
1. Arrastre y coloque el **paso de flujo (vista previa)** de la lista de **componentes** en la fase de **propuesta** .
1. A continuación, seleccione el icono de búsqueda en el campo **seleccionar un flujo** para mostrar todos los flujos que se pueden agregar a un flujo de procesos empresariales.
1. Seleccione un flujo de la lista y, a continuación, guarde los cambios seleccionando el botón **aplicar** situado en la parte inferior del panel de propiedades.
1. Por último, seleccione el botón **Actualizar** para que este flujo de procesos empresariales con su nuevo paso de flujo instantáneo esté disponible para los usuarios.
  
## <a name="next-steps"></a>Pasos siguientes

 - [Introducción a los flujos de procesos empresariales](business-process-flows-overview.md)  
 - [Mejorar los flujos de procesos empresariales con bifurcación](enhance-business-process-flows-branching.md)
 - [Información general de las aprobaciones](sequential-modern-approvals.md)
 - [Pasos detallados para agregar un flujo instantáneo a un flujo de procesos empresariales](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


