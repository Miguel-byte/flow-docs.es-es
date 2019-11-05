---
title: Diseño de flujos con Microsoft Visio | Microsoft Docs
description: Aproveche la experiencia de Visio de su organización para compilar modelos comunes como punto de partida para crear flujos.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0ffe9fbf8c29682bbcb941dbb48f9986f3c7144d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548780"
---
# <a name="design-flows-in-microsoft-visio"></a>Flujos de diseño en Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El diseñador de Microsoft Flow es una herramienta enriquecida en la que puede configurar todos los detalles de la lógica. Sin embargo, a veces es posible que desee simplemente esbozar la lógica de flujo antes de empezar a crear el flujo. Para ello, utilice Microsoft Visio directamente desde Microsoft Flow.

>[!TIP]
> Muchos procesos comparten un modelo común pero tienen pequeñas variaciones en toda la organización. Puede ahorrar tiempo dentro de la organización con Visio para crear un modelo de flujo de trabajo principal que otros usuarios ajustarán con parámetros especializados.

## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Microsoft Flow.
- La aplicación de escritorio de Microsoft Visio (versión en inglés).
- Experiencia en el uso de Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Diseñar un flujo de trabajo en Visio

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione **plantillas** en el panel de la izquierda.

     ![Seleccionar plantillas en el panel izquierdo](./media/visio-flows/templates-from-left-panel.png)

1. Seleccione **Visio** en la lista.

     ![Filtrar por plantillas de Visio](./media/visio-flows/select-visio.png) 

1. Seleccione la plantilla de **Diagrama de BPMN de flujo básico** en la lista de plantillas de **Visio** que se muestra.

     ![Seleccionar una plantilla de Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio le advierte de que los archivos de Internet podrían dañar el dispositivo. Si está familiarizado, seleccione **sí** en el mensaje de advertencia.

     ![Advertencia sobre archivos de Internet](./media/visio-flows/visio-warning.png)

1. Se inicia Visio Designer.

     ![Vista de Visio Designer](./media/visio-flows/visio-designer.png)


1. Use las formas básicas de BPMN para [diseñar el flujo de trabajo](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Formas básicas de BPMN](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-microsoft-flow"></a>Preparación para exportar el flujo de trabajo a Microsoft Flow

Siga estos pasos para preparar el flujo de trabajo de modo que pueda exportarlo a Microsoft Flow.

1. Seleccione la pestaña **proceso** .
1. Seleccione **preparar para exportar** desde el **Microsoft Flow** grupo de iconos.

   ![Seleccione el icono preparar para exportar](./media/visio-flows/prepare-export-icon.png)
   
   Se abre el grupo **preparar para exportar** .

   ![Preparar grupo de exportación](./media/visio-flows/prepare-export-group.png)

1. En la pestaña **asignación de flujo** del grupo **preparar para exportar** , asigne el diagrama de BPMN a Microsoft Flow controles. 

1. En la pestaña **desencadenadores y acciones** del grupo **preparar para exportar** , asigne el diagrama de BPMN para Microsoft Flow desencadenadores y acciones. para ello, seleccione cada forma y, a continuación, seleccione un desencadenador o una acción para representar esa forma en Microsoft Flow.

El flujo de trabajo está listo para ser exportado cuando no quedan problemas en el control **preparar para exportar** .

![Sin problemas](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Exportar el flujo de trabajo
1. Seleccione el botón **exportar a flujo** para exportar el diagrama de flujo de trabajo a Microsoft Flow.
1. Asigne un nombre al flujo y, a continuación, seleccione el botón **Crear flujo** .
   
   ![Creación del flujo](./media/visio-flows/export-create-flow.png)

1. Debería ver un informe de éxito similar a este.

    ![Realizado](./media/visio-flows/export-create-flow-success.png)

Ahora puede ejecutar o realizar modificaciones en el flujo desde el diseñador de Microsoft Flow, al igual que cualquier otro flujo.

>[!TIP]
> Use las capacidades de uso compartido y comentarios de Visio para colaborar con varias partes interesadas y crear rápidamente un flujo de trabajo completo.

## <a name="learn-more"></a>Aprende más

- [Introducción a Microsoft Flow](getting-started.md) 
- [Compilación de flujos de varios pasos](multi-step-logic-flow.md)
- [Diseño de un flujo con Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
