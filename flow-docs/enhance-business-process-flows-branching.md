---
title: Mejora de los flujos de proceso de negocio con ramas con PowerApps | Microsoft Docs
description: Obtenga información sobre cómo usar las ramas en un flujo de proceso de negocio
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8911c828b216d8f65210b4c54603fd8838e848b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054100"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: Mejora de los flujos de proceso de negocio con ramas

Los flujos de proceso de negocio le guían por las distintas fases de ventas, marketing o procesos de servicio hacia su finalización. En los casos más sencillos, un flujo de proceso de negocio lineal es una buena opción. Pero en escenarios más complejos, un flujo de proceso de negocio se puede mejorar con la creación de ramas. Si tiene los permisos de creación en los flujos de proceso de negocio, podrá crear el flujo con varias ramas mediante la lógica `If-Else`. La condición de ramas puede estar formada por varias expresiones lógicas en las que se usa una combinación de operadores `AND` u `OR`. La selección de la rama se realiza de forma automática, en tiempo real, en función de las reglas definidas durante la definición del proceso. Por ejemplo, para vender automóviles, puede configurar un solo flujo de proceso de negocio, que después de una fase de calificación común se divida en dos ramas independientes en función de una regla (si el cliente prefiere un automóvil nuevo o uno de segunda mano, si su presupuesto es mayor o inferior de 20 000 EUR, y así sucesivamente. ), una rama para la venta de automóviles nuevos y otra para los de segunda mano. Para obtener más información sobre los flujos de proceso de negocio, vea [Información general sobre flujos de proceso de negocio](business-process-flows-overview.md).  
  
 En el diagrama siguiente se muestra un flujo de proceso de negocio con ramas.  
  
 ![Diagrama de flujo en el que se muestran los pasos del proceso de venta de automóviles](media/example-car-sales-flow-chart.png "Flowchart showing the steps in the car sales process")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Qué necesita saber para diseñar flujos de proceso de negocio con ramas  
 Tenga en cuenta la información siguiente cuando diseñe el flujo de proceso de negocio con ramas:  
  
-   Un proceso puede abarcar un máximo de 5 entidades únicas.  
  
-   Puede usar un máximo de 30 fases por proceso y un máximo de 30 pasos por fase.  
  
-   Cada rama no puede tener más de 5 niveles de profundidad.  
  
-   La regla de creación de ramas se debe basar en los pasos de la fase que la precede.  
  
-   Se pueden combinar varias condiciones en una regla mediante el operador `AND` o el operador `OR`, pero no los dos.  
  
-   Al definir un flujo de proceso, también se puede seleccionar una relación entre entidades. Esta relación debe ser una relación entre entidades 1:N (Uno a varios).  
  
-   Se puede ejecutar simultáneamente más de un proceso activo en el mismo registro de datos.  
  
-   Los iconos (Fases, Pasos, Condiciones etc.) se pueden arrastrar y colocar para reorganizarlos en el flujo del proceso.  
  
-   Al combinar las ramas, todas las ramas del mismo nivel se deben combinar en una sola fase. Todas las ramas del mismo nivel se deben combinar en una sola fase, o bien cada rama del mismo nivel debe terminar el proceso. Una rama del mismo nivel no se puede combinar con otras ramas y terminar el proceso al mismo tiempo.  
  
> [!NOTE]
> - Una entidad que se use en el proceso se puede revisitar varias veces (varios bucles de entidad cerrados).  
> - Un proceso puede volver a la fase anterior con independencia del tipo de la entidad. Por ejemplo, si la fase activa es **Entregar oferta** en un registro de oferta, los usuarios del proceso pueden cambiar la fase activa a la fase **Proponer** en un registro de oportunidad.  
>   
>   En otro ejemplo, supongamos que un proceso está actualmente en el **propuesta presente** fase en el flujo del proceso: **Calificar cliente potencial** > **identificar necesidades** > **Crear propuesta** > **presentar propuesta**  >  **Cerrar**. Si la propuesta que se presenta al cliente requiere más investigaciones para identificar las necesidades del cliente, los usuarios pueden seleccionar simplemente la fase **Identificar las necesidades** del proceso y elegir **Establecer como activa**.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Ejemplo de involucración de los clientes de Dynamics 365: Flujo del proceso con dos bifurcaciones de venta del automóvil
 
Veamos el ejemplo del flujo de proceso de negocio con dos ramas, para la venta de automóviles nuevos y usados.  
  
 En primer lugar, se creará un proceso denominado **Proceso de venta de automóviles**.  
  
1.  [Abra el Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y, después, en el panel de navegación de la izquierda, haga clic en **Procesos**.  
  
2.  Haga clic en **Nuevo** para crear un proceso.  
  
3.  Especifique la **Categoría** como **Flujo de proceso de negocio** y, para la **Entidad** principal, elija **Cliente potencial**.  
  
4.  Agregue la primera fase al proceso denominada **Aprobar** y los pasos **Período de tiempo de compra** y **Preferencia de automóvil**.  
  
5.  Después de la fase **Aprobar** común, el proceso se divide en dos ramas independientes, mediante el icono **Condición**.  
  
    1.  Configure el icono de condición con reglas que cumplan sus requisitos empresariales.  
  
    2.  Para agregar la primera rama a una fase, agregue un icono de fase en la ruta "Sí" del icono de condición.  
  
    3.  Para agregar la segunda rama que se ejecuta cuando no se cumple la condición, agregue otro icono de fase en la ruta "No" del icono de condición  
  
> [!TIP]
>  Puede agregar otra condición a la ruta de acceso "no" de un icono de condición existente para crear ramas más complejas.  
  
 ![Imagen en la que se muestra la fase Aprobar creada](media/example-car-sales-qualify-stage.JPG "Image showing the created Qualify stage")  
  
 Si la **Preferencia de automóvil** = **Nuevo**, el proceso se bifurca a la fase **Venta de automóviles nuevos**; en caso contrario, salta a la fase **Venta de automóviles usados**, en la segunda rama, como se muestra a continuación.  
  
 ![Imagen en la que se muestra la fase de venta de automóviles nuevos](media/example-car-sales-new-stage-1.JPG "Image showing the New Car Sale stage")  
  
 ![Fase de venta de automóviles usados](media/example-car-sales-pre-owned-stage.JPG "Pre-owned car sales stage")  
  
 Después de completar todos los pasos de las fases **Venta de automóviles nuevos** o **Venta de automóviles usados**, el proceso regresa al flujo principal, con la fase **Entregar oferta**.  
  
 ![Fase Entregar oferta](media/example-car-sales-deliver-quote-stage.JPG "Deliver Quote stage")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Evitar la divulgación de información  
 Considere la posibilidad de un flujo de proceso de negocio con ramas para el procesamiento de una solicitud de préstamo de un banco, como se muestra a continuación. Las entidades personalizadas que se usan en las fases se muestran entre paréntesis.  
  
 ![Diagrama de flujo en el que se muestran los pasos en un proceso de ejemplo para evitar la divulgación de información](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Flow chart showing the steps in an example process to prevent information disclosure")  
  
 En este escenario, el Gestor de préstamos bank necesita tener acceso al registro de solicitud, pero el Gestor de préstamos no debería tener ninguna visibilidad en la investigación de la solicitud. A primera vista, parece que se puede hacer fácilmente mediante la asignación de un rol de seguridad al gestor de préstamos en el que se especifique que no tiene acceso a la entidad de investigación. Pero veamos el ejemplo con más detalle para comprobar si es lo que realmente ocurre.  
  
 Supongamos que un cliente solicita al banco un préstamo de 60 000 EUR. El gestor de préstamos revisa la solicitud en la primera fase. Si se cumple la regla de creación de ramas que comprueba si la cantidad adeudada al banco superará los 50 000 EUR, la siguiente fase del proceso consiste en investigar si la solicitud es fraudulenta. Si se determina que realmente se trata de un caso de fraude, el proceso pasa emprender acciones legales contra el solicitante. El Gestor de préstamos no debería tener visibilidad en las dos fases de investigación porque el officer no tiene acceso a la entidad de investigación.  
  
 Sin embargo, si el Gestor de préstamos, abre el registro de solicitud, todas estarían capaz de ver todo el proceso de extremo a otro. No sólo el Gestor de préstamos será capaz de ver el escenario de investigación de fraude, sino también podrá identificar el resultado de la investigación por haber estado capaz de ver el escenario de acciones legales en el proceso. Además, el officer será capaz de mostrar en vista previa de los pasos en las fases de investigación eligiendo la fase. Mientras que el Gestor de préstamos no podrá ver los datos o el estado de finalización del paso, ella podrá identificar las posibles acciones que se realizaron en el remitente de la solicitud durante la investigación y fases de acciones legales.  
  
 En este flujo de proceso, el gestor de préstamos podrá ver las fases Investigación de fraude y Acción legal, lo que constituye una divulgación de información incorrecta. Se recomienda prestar especial atención a la información que se pueda revelar debido a la creación de ramas. En nuestro ejemplo, el proceso se divide en dos procesos independientes, uno para el procesamiento de la solicitud y otro para la investigación de fraude, para evitar la divulgación de información. El proceso para el gestor de préstamos tendrá este aspecto:  
  
 ![Diagrama de flujo en el que se muestran pasos adiciones del proceso para evitar la divulgación de información](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Flow chart showing additional steps in the process to prevent information disclosure")  
  
 El proceso para la investigación será independiente e incluirá las fases siguientes:  
  
 ![Diagrama de flujo en el que se muestran los pasos de un proceso de investigación para casos de divulgación de información](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Flow chart showing steps for an investigation process for information disclosure cases")  
  
 Tendrá que proporcionar un flujo de trabajo para sincronizar la decisión de aprobar o denegar desde el registro Investigación al registro Solicitud.  
  
### <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de proceso de negocio](create-business-process-flow.md)   
 [Creación de lógica de negocios personalizada mediante procesos](guide-staff-through-common-tasks-processes.md)   
 
