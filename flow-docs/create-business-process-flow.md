---
title: Creación de un flujo de proceso de negocio en PowerApps | Microsoft Docs
description: Aprenda a crear un flujo de proceso de negocio
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 258fedabea816b9a20a8f768632e797dec576365
ms.sourcegitcommit: d3243c9f82c5e058919c5cb85d36d45f1f034411
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2018
ms.locfileid: "43774309"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: Crear un flujo de proceso de negocio para estandarizar procesos

En este tutorial se explica cómo crear un flujo de proceso de negocio con PowerApps. Para saber más sobre por qué se usan flujos de proceso de negocio, vea [Información general sobre flujos de proceso de negocio](business-process-flows-overview.md). Para más información sobre cómo crear un flujo de tareas móviles, vea [Crear un flujo de tareas móviles](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Cuando un usuario inicia un flujo de proceso de negocio, las fases y los pasos del proceso se muestran en la barra de proceso en la parte superior de un formulario:  
  
 ![Proceso de negocio con fases](media/business-process-stages.png "Proceso de negocio con fases")  
  
 > [!TIP]
 >  Después de crear una definición de flujo de proceso de negocio, puede proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia del flujo de proceso de negocio. Por ejemplo, para los procesos relacionados con el servicio, podría proporcionar acceso completo a los representantes de servicio al cliente para que cambien la instancia del flujo de proceso de negocio, pero proporcionar acceso de solo lectura a la instancia para los representantes de ventas, de modo que puedan supervisar las actividades posventa de sus clientes. Para establecer la seguridad de una definición de flujo de proceso de negocio que ha creado, seleccione **Habilitar roles de seguridad** en la barra de acciones.  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## <a name="create-a-business-process-flow"></a>Crear un flujo de proceso de negocio  
  
1. Abra el [explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. En el panel de navegación izquierdo, seleccione **Procesos**. 
  
3.  En la barra de herramientas **Acciones**, seleccione **Nuevo**.  
  
4.  En el cuadro de diálogo **Crear proceso**, rellene los campos obligatorios:  
  
    -   Escriba un nombre de proceso. El nombre de proceso no tiene que ser único, pero debe ser significativo para las personas que deben elegir un proceso. Puede cambiarlo más adelante.  
  
    -   En la lista **Categoría**, seleccione **Flujo de proceso de negocio**.  
  
         No se puede cambiar la categoría después de crear el proceso.  
  
    -   En la lista **Entidad**, seleccione la entidad en la que quiere basar el proceso.  
  
         La entidad seleccionada afectará a los campos disponibles para los pasos que se pueden agregar a la primera fase del flujo de proceso. Si no encuentra la entidad que quiere, asegúrese de que la entidad tiene la opción Business process flows (fields will be created) [Flujos de proceso de negocio (se crearán los campos)] establecida en la definición de entidad. No se puede cambiar esto después de guardar el proceso.  
  
5. Haga clic en **Aceptar**.  
  
     Se crea el nuevo proceso y se abre el diseñador de flujo de proceso de negocio con una sola fase creada automáticamente.  
  
 ![Ventana de flujo de proceso de negocio que muestra los elementos principales](media/business-process-flow-window-showing-main-elements.png "Ventana de flujo de proceso de negocio que muestra los elementos principales")  
  
6. **Agregue las fases.** Si los usuarios van a avanzar de una fase de negocio a otra en el proceso:  
  
    1.  Arrastre un componente **Fase** desde la pestaña **Componentes** y suéltelo en un signo + en el diseñador.  
  
        ![Arrastrar una fase del proceso de negocio](media/drag-business-process-stage.png "Arrastrar una fase del proceso de negocio")  
  
    2.  Para establecer las propiedades de una fase, seleccione la fase y establezca las propiedades en la pestaña **Propiedades** en la parte derecha de la pantalla:  
  
        -   Escriba un nombre para mostrar.  
  
        -   Si quiere, puede seleccionar una categoría para la fase.  La categoría (como **Calificar** o **Desarrollar**) aparece como un botón de contenido adicional en la barra de proceso.  
  
            ![Botón de contenido adicional en la barra de proceso de negocio](media/business-process-bar-chevron.png "Botón de contenido adicional en la barra de proceso de negocio")  
  
        -   Cuando haya terminado de cambiar las propiedades, haga clic en **Aplicar**.  
  
7. **Agregue pasos a una fase.** Para ver los pasos de una fase, seleccione **Detalles** en la esquina inferior derecha de la fase. Para agregar más pasos:  
  
    1.  Arrastre el componente **Paso** a la fase de la pestaña **Componentes**.  
  
        ![Agregar paso a una fase en un proceso de negocio](media/add-step-stage-business-process.png "Agregar paso a una fase en un proceso de negocio")  
  
    2.  Seleccione el paso y establezca las propiedades en la pestaña **Propiedades**:  
  
        1.  Debe especificar un nombre para mostrar para el paso.  
  
        2.  Si quiere que los usuarios escriban datos para completar un paso, seleccione el campo correspondiente en la lista desplegable.  
  
        3.  Seleccione **Obligatorio** si los usuarios deben rellenar el campo para completar el paso antes de pasar a la siguiente fase del proceso.  
  
        4.  Seleccione **Aplicar** cuando haya terminado.  
  
8. **Agregue una rama (condición) al proceso.** Para agregar una condición de rama:  
  
    1.  Arrastre el componente **Condición** desde la pestaña **Componentes** hasta un signo + entre dos fases.  
  
        ![Agregar una condición a un flujo de proceso de negocio](media/add-condition-business-process-flow.png "Agregar una condición a un flujo de proceso de negocio")  
  
    2.  Seleccione la condición y establezca las propiedades en la pestaña **Propiedades**. Para más información sobre las propiedades de creación de ramas, vea [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas). Cuando haya terminado de establecer las propiedades para la condición, seleccione **Aplicar**.  
  
9. **Agregue un flujo de trabajo.** Para invocar un flujo de trabajo:  
  
    1.  Arrastre un componente **Flujo de trabajo** desde la pestaña **Componentes** hasta una fase, o vaya al elemento **Flujo de trabajo global** en el diseñador.   Decidir cuál debe agregar dependerá de lo siguiente:  
  
       - **Arrástrelo a una fase** cuando quiera desencadenar el flujo de trabajo al entrar o salir de la fase. El componente de flujo de trabajo debe basarse en la misma entidad principal que la fase.  
  
       - **Arrástrelo hasta el elemento Flujo de trabajo global** cuando quiera desencadenar el flujo de trabajo cuando se active el proceso o cuando se archive el proceso (cuando el estado cambia a **Completado** o **Abandonado**). El componente de flujo de trabajo debe basarse en la misma entidad principal que el proceso.  
  
    2.  Seleccione el flujo de trabajo y establezca las propiedades en la pestaña **Propiedades**:  
  
       1.  Escriba un nombre para mostrar.  
  
       2.  Seleccione cuándo debe activarse el flujo de trabajo.  
  
       3.  Busque un flujo de trabajo activo a petición que coincida con la entidad de la fase o cree un nuevo flujo de trabajo mediante **Nuevo**.  
  
       4.  Seleccione **Aplicar** cuando haya terminado.  
  
       Para más información sobre flujos de trabajo, vea [Procesos de flujo de trabajo](../common-data-service/workflow-processes.md).  
  
10. Para validar el flujo de proceso de negocio, seleccione **Validar** en la barra de acciones.  
  
11. Para guardar el proceso como un borrador mientras sigue trabajando en él, seleccione **Guardar** en la barra de acciones.  
  
    > [!IMPORTANT]
    >  Mientras un proceso sea un borrador, los demás no podrán usarlo.  
  
12. Para activar el proceso y que esté disponible para el resto del equipo, seleccione **Activar** en la barra de acciones.  

13. Para proporcionar control sobre quién puede crear, leer, actualizar o eliminar la instancia del flujo de proceso de negocio, seleccione **Editar roles de seguridad** en la barra de comandos del diseñador. Por ejemplo, para los procesos relacionados con el servicio, podría proporcionar acceso completo a los representantes de servicio al cliente para que cambien la instancia del flujo de proceso de negocio, pero proporcionar acceso de solo lectura a la instancia para los representantes de ventas, de modo que puedan supervisar las actividades posventa de sus clientes.

  En la pantalla **Roles de seguridad**, seleccione el nombre de un rol para abrir la página de información del rol de seguridad. Seleccione la pestaña Flujos de proceso de negocio y, después, asigne los privilegios adecuados en el flujo de proceso de negocio para un rol de seguridad.

  > [!NOTE]
  > Los roles de seguridad Administrador del sistema y Personalizador del sistema tienen acceso a nuevos flujos de procesos de negocio de forma predeterminada.

   ![Asignar privilegios a un flujo de proceso de negocio](media/bpf-assign-privileges.png)

  Para especificar los privilegios, seleccione los botones de radio correspondientes y haga clic en Guardar. Para más información sobre privilegios, vea [Business process flow privileges](business-process-flows-overview.md#BKMK_MultipleBPF) (Privilegios de flujos de proceso de negocio).

  Después, no olvide asignar el rol de seguridad a los usuarios adecuados de la organización.

> [!TIP] 
>  Estas son algunas sugerencias que debe tener en cuenta cuando trabaje con el flujo de tareas en la ventana del diseñador:  
>   
> - Realice una instantánea de todo en la ventana del flujo de proceso de negocio. Para ello, seleccione **Instantánea** en la barra de acciones. Esto resulta útil, por ejemplo, si quiere compartir el proceso con un miembro del equipo y recibir comentarios de él.  
> - Use el minimapa para desplazarse rápidamente a diferentes partes del proceso. Esto es útil cuando tiene un proceso complicado que se desplaza fuera de la pantalla.  
> - Para agregar una descripción al proceso de negocio, seleccione **Detalles** bajo el nombre de proceso en la esquina izquierda de la ventana del flujo de proceso de negocio. Puede usar hasta 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar un flujo de proceso de negocio  
 Para editar flujos de procesos de negocio, abra el explorador de soluciones, seleccione **Procesos** y, después, seleccione el **Flujo de proceso de negocio** en la lista de procesos que quiere editar.  
  
 Cuando selecciona el nombre del flujo de proceso de negocio que quiere editar en la lista de procesos, este se abre en el diseñador, donde puede realizar las actualizaciones que quiera. Expanda **Detalles** bajo el nombre de proceso para cambiar su nombre o agregue una descripción y vea información adicional.  
  
 ![Sección de detalles ampliada de un flujo de proceso de negocio](media/business-process-flow-details.png "Sección de detalles ampliada de un flujo de proceso de negocio")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Otros aspectos que debe conocer sobre flujos de procesos de negocio
 **Editar fases**  
Los flujos de procesos de negocio pueden tener hasta 30 fases.    
  
Puede agregar o cambiar las siguientes propiedades de una fase:  
  
- **Nombre de fase**  
  
- **Entidad**. Puede cambiar la entidad de cualquier fase, excepto la primera.  
  
- **Categoría de fases**. Una categoría permite agrupar las fases por un tipo de acción. Es útil para los informes que agrupan los registros según la fase en la que se encuentran. Las opciones para la categoría de fases proceden del conjunto de opciones globales Categoría de fase. Puede agregar opciones adicionales a este conjunto de opciones globales y cambiar las etiquetas de las opciones existentes, si lo prefiere. También puede eliminar estas opciones si quiere, pero se recomienda que mantenga las opciones existentes. No podrá volver a agregar exactamente la misma opción si la elimina. Si no quiere que la usen, cambie la etiqueta a "No usar".  
  
- **Relación**. Indique una relación cuando la fase anterior del proceso esté basada en una entidad diferente. Para la fase que se está definiendo actualmente, elija **Seleccionar relaciones** para señalar que se use una relación al cambiar entre dos fases. Se recomienda que seleccione una relación por estos buenos motivos:  
  
    -   A menudo, las relaciones tienen asignaciones de atributos definidas que transmiten automáticamente datos entre los registros, lo que reduce la entrada de datos.  
  
    -   Al seleccionar **Siguiente fase** en la barra de proceso para un registro, se mostrará cualquier registro que use la relación en el flujo de proceso, con lo que se promueve la reutilización de registros en el proceso. Además, puede usar flujos de trabajo para automatizar la creación de registros para que el usuario solo tenga que seleccionarlo en lugar de crear uno para optimizar aún más el proceso.  
  
**Editar pasos**  
 Cada fase puede tener hasta 30 pasos.    
  
**Agregar rama**  
Para saber más sobre cómo agregar una rama a una fase, vea [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas).  
  
Para hacer que un flujo de proceso de negocio esté disponible para que lo usen otros usuarios, debe ordenar el flujo de proceso, habilitar los roles de seguridad y activarlo.  
  
**Establecer el orden del flujo de proceso**  
 Cuando tenga más de un flujo de proceso de negocio para una entidad (tipo de registro), tendrá que establecer qué proceso se asigna automáticamente a los nuevos registros. En la barra de comandos, seleccione **Ordenar flujo de proceso**. Para los nuevos registros o los registros que aún no tienen un flujo de proceso asociado a ellos, se usará el primer flujo de proceso de negocio al que acceda un usuario.  
  
**Habilitar roles de seguridad**  
Los usuarios tienen acceso a un flujo de proceso de negocio según el privilegio definido en el flujo de proceso de negocio en el rol de seguridad asignado al usuario. 

De manera predeterminada, los roles de seguridad **Administrador del sistema** y **Personalizador del sistema** son los únicos que pueden ver un nuevo flujo de proceso de negocio. 

Para especificar los privilegios en un flujo de proceso de negocio, abra el flujo del proceso de negocio para su edición y seleccione **Editar roles de seguridad** en la barra de comandos del diseñador de flujo de proceso de negocio. Vea el paso 13 en [Crear un flujo de proceso de negocio](#create-a-business-process-flow) mencionado antes en este tema.
  
**Activar**  
Antes de que los demás puedan usar el flujo de proceso de negocio, primero debe activarlo. En la barra de comandos, seleccione **Activar**. Después de confirmar la activación, el flujo de proceso de negocio estará listo para usarse. Si un flujo de proceso de negocio tiene errores, no podrá activarlo hasta que se corrijan los errores.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Agregar una acción a petición a un flujo de proceso de negocio
La actualización de Dynamics 365 (en línea), versión 9.0 introduce una característica de flujo de proceso de negocio: la automatización de flujos de procesos de negocio con los pasos de acción. Puede agregar un botón a un flujo de proceso de negocio que desencadenará una acción o un flujo de trabajo.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Agregar flujos de trabajo a petición o acciones mediante un paso de acción
Supongamos que, como parte del proceso de calificación de oportunidades, la organización Contoso exige que un revisor designado se encargue de revisar todas las oportunidades. Por este motivo, la organización Contoso creó una acción que: 

- Crea un registro de tarea que está asignado al revisor de oportunidades. 
- Anexa "Listo para revisión" al tema de oportunidad. 

Además, Contoso necesita poder ejecutar estas acciones a petición. Para integrar estas tareas en el proceso de calificación de oportunidades, las acciones deben aparecer en el flujo del proceso de negocio de la oportunidad. Para habilitar esta función, seleccione **As a Business Process Flow action step** (Paso de acción como flujo de proceso de negocio).
![Disponible para ejecutarse como un flujo de proceso de negocio.](media/action-available-to-run.png)

Después, se agrega el paso de acción al flujo de proceso de negocio de la oportunidad de Contoso. Luego se valida y se actualiza el flujo del proceso.

![Acción que se agrega al flujo de proceso de negocio de la oportunidad.](media/add-action-to-bpf.png)

Ahora, los empleados de Contoso pueden iniciar la acción desde el paso de proceso de negocio **Calificar oportunidad**, a petición, con solo seleccionar **Ejecutar**.

![Ejecutar acción.](media/action-execute.png)

> [!IMPORTANT]
> - Para poder ejecutar una acción o un flujo de trabajo a petición, el flujo de proceso de negocio debe incluir un paso de acción. Si el paso de acción ejecuta un flujo de trabajo, el flujo de trabajo debe configurarse para ejecutarse a petición.
> - La entidad asociada con la acción o el flujo de trabajo debe ser la misma que la entidad asociada con el flujo de proceso de negocio.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitación del uso de los pasos de acción en un flujo de proceso de negocio

- Las acciones no están disponibles como pasos de acción si los parámetros de entrada o de salida son los tipos Entity, EntityCollection u OptionSet (Picklist). Las acciones con más de un parámetro de salida EntityReference o cualquier número de parámetros de entrada EntityReference no están disponibles como pasos de acción. Las acciones que no están asociadas con una entidad principal (acción global) no están disponibles como pasos de acción.

  
## <a name="next-steps"></a>Pasos siguientes  
 [Business process flows overview](business-process-flows-overview.md) (Introducción a los flujos de procesos de negocio) </br>   
 [Enhance business process flows with branching](enhance-business-process-flows-branching.md) (Mejorar los flujos de proceso de negocio con creación de ramas).

