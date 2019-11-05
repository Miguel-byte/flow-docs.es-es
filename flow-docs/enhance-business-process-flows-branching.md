---
title: Mejorar los flujos de procesos empresariales con la bifurcación con PowerApps | MicrosoftDocs
description: Aprenda a usar la bifurcación en un flujo de procesos empresariales
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544778"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: mejorar los flujos de procesos empresariales con bifurcación
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los flujos de procesos empresariales le guían a través de varias fases de los procesos de ventas, marketing o servicios hasta su finalización. En casos sencillos, un flujo de procesos empresariales lineal es una buena opción. Sin embargo, en escenarios más complejos, puede mejorar un flujo de procesos empresariales con ramificación. Si tiene los permisos create en los flujos de procesos empresariales, podrá crear un flujo de procesos empresariales con varias bifurcaciones mediante el `If-Else` lógica. La condición de bifurcación se puede formar de varias expresiones lógicas que usan una combinación de operadores `AND` o `OR`. La selección de la bifurcación se realiza automáticamente, en tiempo real, en función de las reglas definidas durante la definición del proceso. Por ejemplo, en el caso de los automóviles, puede configurar un flujo de procesos empresariales, que, una vez que una fase de calificación común se divide en dos bifurcaciones independientes en función de una regla (el cliente prefiere un automóvil nuevo o un coche que ya existe, es su presupuesto por encima o por debajo de $20.000 , etc. ), una rama, para vender nuevos automóviles y otra rama, para vender coches de propiedad previa. Para obtener más información sobre los flujos de procesos empresariales, vea [Introducción a los flujos de procesos empresariales](business-process-flows-overview.md).  
  
 En el diagrama siguiente se muestra un flujo de procesos empresariales con bifurcaciones.  
  
 ![Diagrama de flujo que muestra los pasos del proceso de ventas del automóvil](media/example-car-sales-flow-chart.png "Diagrama de flujo que muestra los pasos del proceso de ventas del automóvil")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Lo que necesita saber al diseñar flujos de procesos empresariales con ramas  
 Tenga en cuenta la siguiente información al diseñar el flujo de procesos empresariales con las ramas:  
  
-   Un proceso puede abarcar un máximo de 5 entidades únicas.  
  
-   Puede usar un máximo de 30 fases por proceso y un máximo de 30 pasos por fase.  
  
-   Cada rama no puede tener más de 5 niveles de profundidad.  
  
-   La regla de bifurcación debe basarse en los pasos de la fase que la preceden inmediatamente.  
  
-   Puede combinar varias condiciones en una regla mediante el operador `AND` o el operador `OR`, pero no ambos operadores.  
  
-   Al definir un flujo de proceso, puede seleccionar una relación de entidad de forma opcional. Esta relación debe ser una relación de entidad 1: N (uno a varios).  
  
-   Se puede ejecutar más de un proceso activo simultáneamente en el mismo registro de datos.  
  
-   Puede reorganizar los mosaicos (fases, pasos, condiciones, etc.) en el flujo del proceso mediante arrastrar y colocar.  
  
-   Al combinar ramas, todas las bifurcaciones del mismo nivel deben combinarse en una sola fase. Las bifurcaciones del mismo nivel deben fusionar mediante combinación en una sola fase o cada rama del mismo nivel debe finalizar el proceso. Una bifurcación del mismo nivel no puede fusionar mediante combinación con otras bifurcaciones y al mismo tiempo finalizar el proceso.  
  
> [!NOTE]
> - Una entidad utilizada en el proceso se puede volver a visitar varias veces (varios bucles de entidad cerrados).  
> - Un proceso puede volver a la fase anterior, independientemente de un tipo de entidad. Por ejemplo, si la etapa activa es **entrega de presupuesto** en un registro de oferta, los usuarios del proceso pueden volver a la fase de **propuesta** en un registro de oportunidad.  
>   
>   En otro ejemplo, supongamos que un proceso está actualmente en la fase de la **propuesta actual** en el flujo de proceso: **calificar a clientes potenciales** > **identificar las necesidades** > **crear propuesta** > **propuesta de presentación** >  **Cierre**. Si la propuesta presentada al cliente requiere más investigación para identificar las necesidades de los clientes, los usuarios pueden simplemente seleccionar la etapa **identificar necesidades** del proceso y elegir **establecer activo**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Ejemplo: flujo de proceso de venta de automóviles con dos ramas
 
Echemos un vistazo al ejemplo del flujo de procesos empresariales con dos bifurcaciones, para vender coches nuevos y predeterminados.  
  
 En primer lugar, vamos a crear un nuevo proceso denominado **Car Sales Process**.  
  
1.  [Abra el explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y, a continuación, en el panel de navegación izquierdo, seleccione **procesos**.  
  
2.  Seleccione **nuevo** para crear un nuevo proceso.  
  
3.  Especifique la **categoría** como **flujo de proceso empresarial** y, para la **entidad** principal, elija **cliente potencial**.  
  
4.  Agregue la primera fase al proceso denominado **calificar** y agregar pasos **tiempo de compra** y **preferencia de automóvil**.  
  
5.  Después de la fase de **certificación** común, dividimos el proceso en dos bifurcaciones independientes, mediante el icono **condición** .  
  
    1.  Configurar el icono condición con reglas que cumplan los requisitos empresariales  
  
    2.  Para agregar la primera rama de una fase, agregue un icono de fase a la ruta de acceso "sí" del icono de condición.  
  
    3.  Para agregar la segunda rama que se ejecuta cuando no se cumple la condición, agregue otro icono de fase en la ruta "no" del icono de condición.  
  
> [!TIP]
>  Puede agregar otra condición en la ruta de acceso "no" de un icono de condición existente para crear una bifurcación más compleja.  
  
 ![Imagen que muestra la fase de certificación creada](media/example-car-sales-qualify-stage.JPG "Imagen que muestra la fase de certificación creada")  
  
 Si la **preferencia del coche** = **nuevo**, el proceso se ramifica en la nueva fase de **ventas del automóvil** ; de lo contrario, salta a la fase de ventas del **automóvil** , en la segunda rama, como se muestra a continuación.  
  
 ![Imagen que muestra la nueva fase de venta de coches](media/example-car-sales-new-stage-1.JPG "Imagen que muestra la nueva fase de venta de coches")  
  
 ![Fase&#45;de ventas de coche preexistente](media/example-car-sales-pre-owned-stage.JPG "Fase de ventas de coche preexistente")  
  
 Después de completar todos los pasos de la fase nueva fase de **ventas de automóvil** o de **ventas de coches preexistentes** , el proceso vuelve al flujo principal, con la fase de entrega de la **oferta** .  
  
 ![Fase de entrega de cotización](media/example-car-sales-deliver-quote-stage.JPG "Fase de entrega de cotización")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedir la divulgación de información  
 Considere la posibilidad de un flujo de procesos empresariales con ramas para procesar una solicitud de préstamo en un banco, como se muestra a continuación. Las entidades personalizadas que se usan en las fases se muestran entre paréntesis.  
  
 ![Diagrama de flujo que muestra los pasos de un proceso de ejemplo para impedir la divulgación de información](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Diagrama de flujo que muestra los pasos de un proceso de ejemplo para impedir la divulgación de información")  
  
 En este escenario, el responsable de préstamos bancarias necesita tener acceso al registro de la solicitud, pero el responsable del préstamo no debe tener visibilidad sobre la investigación de la solicitud. A primera vista, parece que se puede hacer fácilmente mediante la asignación de un rol de seguridad al responsable de préstamo que no especifica ningún acceso a la entidad de investigación. Pero echemos un vistazo al ejemplo con más detalle y veamos si esto es realmente cierto.  
  
 Supongamos que un cliente coloca en la solicitud de préstamo de más de $60.000 al Banco. El responsable de préstamos revisa la solicitud en la primera fase. Si se cumple la regla de bifurcación que comprueba si la cantidad adeudada en el Banco superará $50.000, la siguiente fase del proceso es investigar si la solicitud es fraudulenta. Si se determina que esto es, en realidad, un caso de fraude, el proceso pasa a realizar una acción legal en el solicitante. El responsable de préstamos no debe tener visibilidad en las dos fases de investigación, ya que el oficial no tiene acceso a la entidad de investigación.  
  
 Sin embargo, si el agente de préstamo abre el registro de la solicitud, todos podrán ver todo el proceso de un extremo a otro. No solo el responsable del préstamo podrá ver la fase de investigación de fraude, sino que también podrá identificar el resultado de la investigación, ya que podrá ver la fase de acción legal en el proceso. Además, el oficial podrá obtener una vista previa de los pasos de las fases de investigación eligiendo la fase. Aunque el responsable no podrá ver los datos o el estado de finalización del paso, podrá identificar las posibles acciones que se realizaron en relación con el remitente de la solicitud durante las fases de investigación y de acción legal.  
  
 En este flujo de proceso, el responsable del préstamo podrá ver la investigación de fraude y las fases de acción legales, lo que constituye una divulgación inadecuada de la información. Se recomienda prestar especial atención a la información que se puede divulgar debido a la bifurcación. En nuestro ejemplo, divida el proceso en dos procesos independientes, uno para el procesamiento de solicitudes y otro para la investigación de fraude, para evitar la divulgación de información. El proceso del responsable de préstamos tendrá el siguiente aspecto:  
  
 ![Diagrama de flujo que muestra pasos adicionales en el proceso para evitar la divulgación de información](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Diagrama de flujo que muestra pasos adicionales en el proceso para evitar la divulgación de información")  
  
 El proceso de la investigación será independiente e incluirá las siguientes fases:  
  
 ![Diagrama de flujo que muestra los pasos de un proceso de investigación para casos de divulgación de información](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Diagrama de flujo que muestra los pasos de un proceso de investigación para casos de divulgación de información")  
  
 Tendrá que proporcionar un flujo de trabajo para sincronizar la decisión de aprobación o denegación del registro de la investigación en el registro de la solicitud.  
  
### <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   
 [Crear lógica de negocios personalizada con procesos](guide-staff-through-common-tasks-processes.md)   
 
