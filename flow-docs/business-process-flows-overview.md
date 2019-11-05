---
title: Información general sobre flujos de procesos empresariales | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545517"
---
# <a name="business-process-flows-overview"></a>Introducción a los flujos de procesos empresariales
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Puede ayudar a garantizar que las personas escriban datos de forma coherente y sigan los mismos pasos cada vez que trabajen con un cliente mediante la creación de un flujo de procesos empresariales. Por ejemplo, puede que desee crear un flujo de proceso de negocio para que todos los usuarios controlen las solicitudes del servicio de atención al cliente de la misma manera, o para requerir que las personas obtengan la aprobación de una factura antes de enviar un pedido. Los flujos de procesos empresariales usan la misma tecnología subyacente que otros procesos, pero las capacidades que proporcionan son muy diferentes de las demás características que utilizan procesos. Para obtener información sobre cómo crear o editar un flujo de procesos empresariales, consulte [crear un flujo de procesos empresariales](create-business-process-flow.md).  
  
 [Vea un breve vídeo (4:49) sobre los flujos de procesos empresariales.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>¿Por qué usar flujos de procesos empresariales?  
Los flujos de procesos empresariales proporcionan una guía para que las personas realicen el trabajo. Proporcionan una experiencia de usuario simplificada que dirige a los usuarios a través de los procesos que su organización ha definido para las interacciones que deben ser avanzadas para una conclusión de algún tipo. Esta experiencia del usuario se puede personalizar para que las personas con roles de seguridad diferentes puedan tener una experiencia que se adapte mejor al trabajo que realizan.  
  
 Use flujos de proceso de negocio para definir un conjunto de pasos que los usuarios deben seguir para llevarlos a un resultado deseado. Estos pasos proporcionan un indicador visual que indica a los usuarios dónde se encuentran en el proceso empresarial. Los flujos de procesos empresariales reducen la necesidad de entrenamiento porque no es necesario que los nuevos usuarios se centren en la entidad que deben usar. Pueden dejar que el proceso los guíe. Puede configurar los flujos de procesos empresariales para que admitan metodologías de ventas comunes que puedan ayudar a los grupos de ventas a conseguir mejores resultados. En el caso de los grupos de servicios, los flujos de procesos empresariales pueden ayudar a los nuevos empleados a acelerar la velocidad y evitar errores que podrían dar lugar a clientes insatisfechos.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>¿Qué pueden hacer los flujos de procesos empresariales?  
 Con los flujos de procesos empresariales, se define un conjunto de *fases* y *pasos* que se muestran a continuación en un control en la parte superior del formulario.  
  
 ![Proceso empresarial con fases](media/business-process-stages.png "Proceso empresarial con fases")  
  
 Cada fase contiene un grupo de pasos. Cada paso representa un campo donde se pueden escribir los datos. Los usuarios avanzan a la fase siguiente mediante el botón **fase siguiente** . Puede realizar un paso necesario para que los usuarios deban escribir datos para el campo correspondiente antes de poder continuar con la siguiente fase. Esto se conoce normalmente como "acceso a la fase".  
  
 Los flujos de procesos empresariales aparecen relativamente sencillos en comparación con otros tipos de procesos, ya que no proporcionan ninguna lógica de negocios condicional ni automatización más allá de proporcionar la experiencia simplificada para la entrada de datos y el control de entradas en fases. Sin embargo, cuando se combinan con otros procesos y personalizaciones, pueden desempeñar un papel importante al ahorrar tiempo, reducir los costos de aprendizaje y aumentar la adopción del usuario.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flujos de procesos empresariales integrados con otras personalizaciones  
 Cuando usted o el usuario escribe datos mediante flujos de procesos empresariales, los cambios en los datos también se aplican a los campos de formulario para que cualquier automatización que proporcionen las reglas de negocios o los scripts de formulario se pueda aplicar inmediatamente. Se pueden agregar pasos que establezcan valores para los campos que no están presentes en el formulario y que estos campos se agregarán al modelo de objetos de `Xrm.Page` que se usa para los scripts de formulario. Los flujos de trabajo que se inician mediante cambios en los campos incluidos en un flujo de proceso empresarial se aplicarán cuando se guarden los datos en el formulario. Si la automatización se aplica mediante un flujo de trabajo en tiempo real, los cambios serán visibles inmediatamente para el usuario cuando se actualicen los datos del formulario una vez guardado el registro.  
  
 Aunque el control de flujo del proceso empresarial en el formulario no proporciona ninguna programación directa del lado cliente, los cambios aplicados por las reglas de negocios o los scripts de formulario se aplican automáticamente a los controles de flujo del proceso empresarial. Si oculta un campo en un formulario, ese campo también se ocultará en el control de flujo del proceso empresarial. Si establece un valor mediante reglas de negocios o scripts de formulario, ese valor se establecerá en el flujo del proceso empresarial.  
  
### <a name="concurrent-process-flows"></a>Flujos de procesos simultáneos  
 Los flujos de procesos empresariales simultáneos permiten a los personalización configurar varios procesos empresariales y asociarlos con el mismo registro inicial. Los usuarios pueden cambiar entre varios procesos empresariales que se ejecutan simultáneamente y reanudan su trabajo en la fase del proceso en el que se encontraban.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flujos de procesos empresariales del sistema  
 Se incluyen los siguientes flujos de procesos empresariales. Para comprender cómo funcionan los flujos de procesos empresariales, revise estos flujos de procesos empresariales del sistema:  
  
-   Proceso de ventas de oportunidades  
  
-   Proceso de ventas de oportunidades  
  
-   Proceso de teléfono a caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Varias entidades en flujos de procesos empresariales  
 Puede usar un flujo de procesos empresariales para una sola entidad o abarcar varias entidades. Por ejemplo, puede tener un proceso que comience con una oportunidad y, a continuación, continúe en una oferta, un pedido y, a continuación, una factura, antes de volver a cerrar la oportunidad.  
  
 Puede diseñar flujos de procesos empresariales que unen los registros de hasta cinco entidades diferentes en un único proceso para que los usuarios que usen la aplicación puedan centrarse en el flujo de su proceso en lugar de en qué entidad están trabajando. Pueden navegar más fácilmente entre los registros de entidad relacionados.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Hay varios flujos de procesos empresariales disponibles por entidad  
 No todos los usuarios de una organización pueden seguir el mismo proceso y diferentes condiciones pueden requerir que se aplique un proceso diferente. Puede tener hasta 10 flujos de procesos empresariales activos por entidad para proporcionar los procesos adecuados para diferentes situaciones.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controlar qué flujo de procesos empresariales se aplicará  
 Puede asociar flujos de procesos empresariales a roles de seguridad para que solo los usuarios con esos roles de seguridad puedan verlos o usarlos. También puede establecer el orden de los flujos de procesos empresariales para que pueda controlar qué flujo de procesos empresariales se establecerá de forma predeterminada. Esto funciona de la misma manera que se definen varios formularios para una entidad.  
  
 Cuando alguien crea un nuevo registro de entidad, la lista de definición de procesos empresariales activos disponibles se filtra por el rol de seguridad del usuario. La primera definición de procesos empresariales activada disponible para el rol de seguridad del usuario de acuerdo con la lista de pedidos de proceso es la que se aplica de forma predeterminada. Si hay más de una definición de proceso empresarial activo disponible, los usuarios pueden cargar otra desde el cuadro de diálogo cambiar proceso. Cada vez que se cambia el proceso, el que se representa actualmente se dirige al fondo y se reemplaza por el seleccionado, pero mantiene su estado y se puede volver a cambiar. Cada registro puede tener varias instancias de proceso asociadas (cada una de ellas para una definición de flujo de proceso empresarial diferente, hasta un total de 10). Al cargar el formulario, solo se representa un flujo de procesos empresariales. Cuando un usuario aplica un proceso diferente, es posible que ese proceso solo se cargue de forma predeterminada para ese usuario determinado.  
  
 Para asegurarse de que un proceso empresarial se carga de forma predeterminada para todos los usuarios (comportamiento equivalente a "anclar" el proceso), se puede Agregar un script de API de cliente personalizado (recurso Web) a la carga de formulario que carga específicamente una instancia de proceso empresarial existente en función de la empresa. IDENTIFICADOR de definición de proceso. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Consideraciones sobre el flujo de procesos empresariales  
 Solo puede definir flujos de procesos empresariales para las entidades que los admitan. También debe tener en cuenta los límites del número de procesos, fases y pasos que se pueden agregar.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flujos de procesos empresariales que llaman a un flujo de trabajo  
 Puede llamar a flujos de trabajo a petición desde dentro de un flujo de procesos empresariales. Puede configurarlo desde el nuevo diseñador de flujo de procesos empresariales arrastrando un componente de flujo de trabajo a una fase de proceso o a la sección flujos de trabajo globales. Para obtener más información sobre el uso de flujos de trabajo en flujos de procesos empresariales, consulte [blog: automatización del flujo de procesos empresariales en Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Cuando se incluye un flujo de trabajo que se desea desencadenar al salir de la fase de una fase en el flujo del proceso empresarial y esa fase es la última fase del flujo, el diseñador da la impresión de que el flujo de trabajo se desencadenará cuando se complete la fase. Sin embargo, el flujo de trabajo no se desencadenará porque no tiene lugar una transición de fase. No recibirá una advertencia o un error que le impedirá incluir el flujo de trabajo en la fase. Cuando un usuario interactúa con el flujo de procesos empresariales, al finalizar o abandonar el proceso no se produce una transición de fase y, por tanto, no se desencadena el flujo de trabajo. Considere los ejemplos siguientes:  
  
-   Cree un flujo de procesos empresariales con dos fases, S1 se conecta a S2, con un flujo de trabajo en la fase S2 y establezca el desencadenador en **fase de salida**.  
  
-   Cree un flujo de procesos empresariales con tres fases, S1 Connect a S2 y, a continuación, S2 ramas a S3. Incluye un flujo de trabajo en S2 y establece el desencadenador en **fase de salida**.  
  
 El flujo de trabajo no se desencadenará en ninguno de los casos. Para solucionar este problema, puede Agregar un flujo de trabajo global y agregar el flujo de trabajo que desea que se desencadene para que el flujo de trabajo se desencadene para el proceso empresarial en lugar de una fase del proceso. Puede establecer el desencadenador de un flujo de trabajo global para procesar abandonado o proceso completado para que el flujo de trabajo se desencadene cuando un usuario abandone o complete el proceso empresarial.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que pueden usar flujos de procesos empresariales  
 Todas las entidades personalizadas pueden usar flujos de procesos empresariales. Las siguientes entidades estándar también pueden usar flujos de procesos empresariales:  
  
-   Código  
-   Agenda  
-   Campañas  
-   Actividad de la campaña  
-   Respuesta de la campaña  
-   Participantes  
-   Póngase  
-   Correo electrónico  
-   Ayuda  
-   Enviar  
-   Y  
-   Facturas  
-   responsabilidad  
-   Mayúscula  
-   Lista de marketing  
-   Posibilidades  
-   Llamada de teléfono  
-   Manuales  
-   Elemento de lista de precios  
-   Cita  
-   Cita periódica  
-   Documentación de ventas  
-   Actividad social  
-   Orden  
-   Usuario  
-   Task  
-   Discusión  
  
 Para habilitar una entidad personalizada para los flujos de procesos empresariales, active la casilla **flujos de proceso de negocio (campos que se crearán)** en la definición de entidad. Tenga en cuenta que no se puede deshacer esta acción.  
  
> [!NOTE]
>  Si navega a la fase de flujo de procesos empresariales que contiene la entidad `Social Activity` y elige el botón **fase siguiente** , verá la opción **crear** . Al elegir **crear**, se carga el formulario de **actividad social** . Sin embargo, dado que `Social Activity` no es válido para `Create` desde la interfaz de usuario de la aplicación, no podrá guardar el formulario y verá el mensaje de error: "error inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Para garantizar un rendimiento aceptable y la facilidad de uso de la interfaz de usuario, hay algunas limitaciones que debe tener en cuenta al planear el uso de flujos de procesos empresariales:  
  
-   No puede haber más de 10 procesos de flujo de procesos empresariales activados por entidad.  
  
-   Cada proceso no puede contener más de 30 fases.  
  
-   Los procesos de varias entidades no pueden contener más de cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Compatibilidad de personalización de entidad de flujo de proceso empresarial 

Introducida en la actualización de Dynamics 365 (en línea), la actualización de la versión 9,0, las entidades de flujo de procesos empresariales pueden aparecer en el sistema para que los datos del registro de la entidad se puedan poner a disposición de las cuadrículas, las vistas, los gráficos y los paneles. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Usar registros de entidad de flujo de procesos empresariales con cuadrículas, vistas, gráficos y paneles

Con los flujos de procesos empresariales disponibles como una entidad, ahora puede usar las búsquedas avanzadas, las vistas, los gráficos y los paneles a partir de los datos de flujo de procesos empresariales para una entidad determinada, como un cliente potencial o una oportunidad. Los administradores y los personalizadores del sistema pueden crear cuadrículas de flujo de procesos empresariales, vistas, gráficos y paneles personalizados similares a los creados con cualquier otra entidad.

Los flujos de procesos empresariales, como el **proceso de ventas de cliente potencial**, aparecen como una entidad personalizable en el explorador de soluciones.

![Explorador de soluciones con la entidad de proceso de liderazgo a oportunidad](media/bpf-lead-solution-explorer.png)

Para obtener acceso a una vista de flujo de proceso de negocio predeterminada, abra el explorador de soluciones, expanda **entidades** > expanda el proceso que desee, como **cliente potencial para el proceso de ventas de oportunidades**, seleccione **vistas**y, a continuación, seleccione la vista que desee.

Hay disponibles varias vistas predeterminadas que puede ver como un gráfico, como la vista del proceso de ventas de la **oportunidad activa** . 

![Vista del proceso de ventas de oportunidad activa](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interacción con la entidad flujo de proceso de negocio desde un flujo de trabajo
También puede interactuar con entidades de flujo de procesos empresariales desde un flujo de trabajo. Por ejemplo, puede crear un flujo de trabajo para que el registro de la entidad flujo de proceso empresarial cambie la fase activa cuando se actualice un campo en el registro de la entidad oportunidad. Para obtener más información sobre cómo hacerlo, vea [automatizar fases de flujo de procesos empresariales mediante flujos de trabajo](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitaciones del uso de entidades de flujo de procesos empresariales

- Actualmente, no se pueden crear formularios personalizados para entidades basadas en un flujo de procesos empresariales.
- Si una solución incluye una entidad de flujo de proceso de negocio, la entidad flujo de proceso empresarial se debe agregar manualmente a la solución antes de exportarla. De lo contrario, la entidad flujo de proceso empresarial no se incluirá en el paquete de la solución. Más información: [agregar componentes](/powerapps/maker/model-driven-apps/create-solution#add-solution-components) de la solución

### <a name="next-steps"></a>Pasos siguientes  
 [Vea un breve vídeo (4:49) sobre los flujos de procesos empresariales](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   
 [Mejorar los flujos de procesos empresariales con bifurcación](enhance-business-process-flows-branching.md) <br/>
 [Notas del producto: habilitación del proceso con Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
