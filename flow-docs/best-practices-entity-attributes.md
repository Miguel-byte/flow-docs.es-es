---
title: Procedimientos recomendados para el uso de atributos de entidad de flujo de proceso de negocio | Microsoft docs
description: Conozca los procedimientos recomendados para el uso de atributos de entidad de flujo de proceso de negocio.
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
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "64472981"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Prácticas recomendadas de uso de atributos de flujo de proceso de negocio


Atributos heredados relacionados con el proceso de entidades está en desuso. Estos son algunos procedimientos recomendados para usar el *fase Active* atributo (activestageid) en la entidad de flujo de proceso empresarial. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Informes en el escenario activo de un flujo de procesos empresariales

Vamos a decir que le gustaría obtener una vista de la canalización de ventas mediante la creación de informes sobre el activo que almacenar provisionalmente la **conducir al proceso de ventas de oportunidad** está activado.

Anteriormente, para informar sobre los procesos de negocio en la fase, uno podría definir una vista en cada entidad relacionada del flujo de procesos empresariales y, a continuación, informar sobre el *fase Active* campo (activestageid).

Con la degradación de la *fase Active* campo (activestageid) en las entidades relacionadas, hay dos maneras para informar sobre los flujos de procesos empresariales.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opción 1: Las vistas y gráficos en los negocios procesan entidad flujo **(recomendado)**

En las versiones 9.0 y versiones posteriores, cada flujo de procesos empresariales crea su propia entidad de Common Data Service, normalmente con el mismo nombre que el flujo de procesos empresariales. Para informar sobre el flujo de procesos empresariales, seleccione la entidad para el que desea informar sobre el flujo del proceso empresarial y, a continuación, crear vistas y gráficos, tal como hacía antes.

En nuestro ejemplo, siga estos pasos para ir a la **conducir al proceso de ventas de oportunidad** entidad:
1. Vaya a https://web.powerapps.com.
1. Seleccione el **datos**.
1. Seleccione el **entidades**.
1. Establezca el filtro en **todas**.
1. Busque y, a continuación, seleccione el **conducir al proceso de ventas de oportunidad** entidad.

   ![dar lugar a la entidad de proceso de ventas de oportunidad](media/best-practices-entity-attributes/lead-opportunity-process.png)

En este caso, puede definir las vistas y gráficos al igual que en cualquier otra entidad.

![detalles de entidad del proceso de traducción](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Una ventaja de este enfoque es que puede usar una vista única o un gráfico al informe en los flujos de procesos empresariales que abarcan varias entidades.

Además, como la entidad de flujo de proceso empresarial no es diferente de cualquier otra entidad personalizada en Common Data Service, puede agregar campos personalizados a la entidad que se va a realizar un seguimiento de cualquier información adicional que necesita.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opción 2: copiar fase activa para una entidad relacionada

Como alternativa, para continuar informar de la entidad relacionada, cree un flujo para copiar el *fase Active* campo (activestageid) de la entidad de flujo de proceso empresarial en un campo personalizado en las entidades relacionadas de Common Data Service.

Estos son algunos aspectos que debe tener en cuenta al usar este enfoque:

1.  Es posible tener más de un flujo de procesos empresariales que se ejecutan en una sola entidad. Con este enfoque, es mejor tener un campo personalizado que almacena la fase activa para cada flujo de procesos empresariales que se ejecuta en la entidad. Este enfoque garantiza la integridad de los informes.

1.  Como reporting está dirigida a partir de la entidad relacionada, no es posible crear una vista única que informa sobre los flujos de procesos empresariales que abarcan varias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Uso de la fase de active para ejecutar lógica

Estos son algunos casos en los que desea ejecutar la lógica que se basa en la fase de active:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Uso de la fase de active para ejecutar lógica de cliente

Si usa el proceso de negocio, hay muchas cosas que puede desear hacer automáticamente. Por ejemplo:

-   Cambiar el flujo del proceso empresarial activa según la información disponible recientemente en el flujo del proceso empresarial o de formulario.

-   Mueva la fase activa a la fase siguiente o anterior, según los valores especificados de los usuarios para los pasos o campos de formulario.

-   Ocultar o mostrar pestañas del formulario y los campos según el escenario seleccionado.

-   Mostrar mensajes informativos y ejecute calulations basándose en los flujos del proceso empresarial activa, el escenario activo o seleccionado o eventos tales como mover la fase activa.

> [!TIP]
> Para escenarios como estos, use el conjunto admitido de [las API de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) para flujos de procesos empresariales.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Utilización del escenario activo para ejecutar la lógica del lado servidor

Puede haber casos donde automatización basada en las necesidades de flujo de proceso de negocio para realizarse en el servidor. Por ejemplo:

-   Enviar un correo electrónico a un usuario si el **calificar** la fase de la **proceso de ventas de oportunidad** está activo durante más de 15 días.

-   Crear automáticamente un conjunto de actividades relevantes para la fase activa de la **proceso de ventas de oportunidad** cada vez que los cambios.

-   Finalizar automáticamente las **proceso de ventas de oportunidad** cuando se completa la actividad de llamada de teléfono para el cierre.

> [!TIP]
> Usar flujos de trabajo de Common Data Service clásicos o flujos que se define en la entidad para el flujo de procesos empresariales.
> 

Para crear un flujo de trabajo de Common Data Service clásico que crean actividades para las revisiones de la solución interna y hacer un seguimiento con el cliente en el **proponer** fase de la **proceso de ventas de oportunidad**:

1. Creación en el **oportunidad de proceso de ventas** entidad y establecer que se ejecute cada vez que el **fase activa** campo de los cambios de entidad. 
1. Definir una condición para comprobar si el **fase Active** campo equals **proponer**. 
1. Cree un registro de la cita y llamada de teléfono para la revisión interno de la solución y la llamada de cliente para revisar la solución, respectivamente.

   ![seguimiento de la fase de cierre](media/best-practices-entity-attributes/close-stage-followup.png)
