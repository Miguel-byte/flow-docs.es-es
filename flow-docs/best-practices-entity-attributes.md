---
title: Prácticas recomendadas para el uso de atributos de entidad de flujo de procesos empresariales | MicrosoftDocs
description: Conozca los procedimientos recomendados para usar los atributos de entidad de flujo de procesos empresariales.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545284"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Prácticas recomendadas para el uso de atributos de flujo de procesos empresariales
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Los atributos relacionados con los procesos heredados de las entidades están desusados. Estos son algunos procedimientos recomendados para usar el atributo *Active Stage* (activestageid) en la entidad flujo de proceso empresarial. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Informes en la fase activa de un flujo de procesos empresariales

Supongamos que quiere obtener una vista de su canalización de ventas mediante la generación de informes sobre la fase activa en la que está el **proceso de ventas de clientes potenciales** .

Anteriormente, para informar sobre los procesos empresariales por fase, uno podría definir una vista en cada entidad relacionada del flujo de procesos empresariales y, a continuación, generar un informe en el campo *Active Stage* (activestageid).

Con el desuso del campo *Active Stage* (activestageid) en las entidades relacionadas, hay dos maneras de informar sobre los flujos de procesos empresariales.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opción 1: vistas y gráficos en la entidad flujo de proceso empresarial **(recomendado)**

En las versiones 9,0 y posteriores, cada flujo de procesos empresariales crea su propia entidad Common Data Service, normalmente con el mismo nombre que el flujo del proceso empresarial. Para informar sobre el flujo de procesos empresariales, seleccione la entidad para el flujo de proceso empresarial en el que desea crear un informe y, a continuación, cree vistas y gráficos, tal como hizo antes.

En nuestro ejemplo, siga estos pasos para ir a la entidad **lead to oportunidad sales Process** :
1. Vaya a https://web.powerapps.com.
1. Seleccione los **datos**.
1. Seleccione las **entidades**.
1. Establezca el filtro en **todos**.
1. Busque y, a continuación, seleccione la entidad **lead to oportunidad sales Process** .

   ![entidad de proceso de ventas de oportunidades](media/best-practices-entity-attributes/lead-opportunity-process.png)

Aquí, puede definir vistas y gráficos del mismo modo que en cualquier otra entidad.

![detalles de la entidad del proceso de traducción](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Una ventaja de este enfoque es que puede usar una vista o un gráfico únicos para informar sobre los flujos de procesos empresariales que abarcan varias entidades.

Además, como la entidad flujo de proceso empresarial no es diferente de ninguna otra entidad personalizada en Common Data Service, puede agregar campos personalizados a la entidad para realizar el seguimiento de la información adicional que necesite.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opción 2: copiar la fase activa en una entidad relacionada

Como alternativa, para continuar informando de la entidad relacionada, cree un flujo para copiar el campo *Active Stage* (activestageid) de la entidad flujo de proceso empresarial en un campo personalizado en las entidades Common Data Service relacionadas.

Estos son algunos aspectos que hay que tener en cuenta al usar este enfoque:

1.  Es posible tener más de un flujo de proceso empresarial en ejecución en una sola entidad. Con este enfoque, es mejor tener un campo personalizado que almacene la fase activa para cada flujo de proceso empresarial que se ejecute en la entidad. Este enfoque garantiza la integridad de los informes.

1.  A medida que la generación de informes se basa en la entidad relacionada, no es posible crear una vista única que informe sobre los flujos de procesos empresariales que abarquen varias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Usar la fase activa para ejecutar la lógica

Estos son algunos casos en los que puede que desee ejecutar la lógica basada en la fase activa:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Usar la fase activa para ejecutar la lógica del lado cliente

A medida que se utiliza el proceso empresarial, hay muchas cosas que es posible que desee hacer automáticamente. Por ejemplo:

-   Cambiar el flujo del proceso de negocio activo en función de la información recién disponible en el flujo de proceso de negocio o formulario.

-   Mueve la fase activa a la fase siguiente o anterior, en función de los valores que los usuarios especificaron para los pasos o los campos de formulario.

-   Ocultar o mostrar pestañas y campos de formulario en función de la fase seleccionada.

-   Mostrar mensajes informativos y ejecutar calulations en función de los flujos de procesos empresariales activos, la fase activa o seleccionada, o eventos como mover la fase activa.

> [!TIP]
> En escenarios como estos, use el conjunto compatible de [API de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) para flujos de procesos empresariales.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Usar la fase activa para ejecutar la lógica del lado servidor

Puede haber casos en los que la automatización basada en el flujo del proceso empresarial se deba realizar en el lado del servidor. Por ejemplo:

-   Envíe un correo electrónico a un usuario si la fase **calificada** del **proceso de ventas** de la oportunidad está activa durante más de 15 días.

-   Cree automáticamente un conjunto de actividades relevantes para la fase activa del **proceso de ventas de oportunidades** cada vez que cambie.

-   Finalizar automáticamente el **proceso de ventas de oportunidades** cuando se complete la actividad de llamada de teléfono para el cierre.

> [!TIP]
> Use flujos de trabajo de Common Data Service clásico o flujos que defina en la entidad para el flujo de procesos empresariales.
> 

Para compilar un flujo de trabajo de Common Data Service clásico que crea actividades para revisiones de soluciones internas y para realizar un seguimiento del cliente en la fase de **propuesta** del **proceso de ventas de oportunidades**:

1. Créelo en la entidad **proceso de ventas de oportunidades** y establézcalo para que se ejecute cada vez que cambie el campo de **fase activa** de la entidad. 
1. Defina una condición para comprobar si el campo de la **fase activa** es **propuesto**. 
1. Cree una cita y un registro de llamada de teléfono para la revisión interna de la solución y la llamada del cliente para revisar la solución, respectivamente.

   ![cerrar seguimiento de la fase](media/best-practices-entity-attributes/close-stage-followup.png)
