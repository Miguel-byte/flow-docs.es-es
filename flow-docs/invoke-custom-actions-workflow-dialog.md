---
title: Invocar acciones personalizadas desde un flujo de trabajo | MicrosoftDocs
description: Obtener información sobre cómo invocar una acción personalizada desde un flujo de trabajo
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547409"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar acciones personalizadas desde un flujo de trabajo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los flujos de trabajo tienen numerosas funcionalidades que admiten escenarios empresariales. La llamada a acciones de operación de datos básicas para un registro, como crear, actualizar y eliminar, desde dentro de un flujo de trabajo resuelve bastantes escenarios empresariales. Sin embargo, si se acoplan las capacidades de los flujos de trabajo con la eficacia de las acciones personalizadas invocadas directamente desde dentro de un flujo de trabajo, se agrega una nueva gama completa de escenarios empresariales a la aplicación sin necesidad de escribir código.  
  
 Echemos un vistazo al escenario en el que se invoca una acción personalizada desde un flujo de trabajo. Invocaremos una acción personalizada para solicitar la aprobación del administrador cuando un descuento para una oportunidad determinada supera el 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Ejemplo: crear una acción personalizada mediante la entidad oportunidad
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , seleccione **procesos**.  
  
2.  En la barra de navegación, elija **nuevo**. Asigne un nombre al proceso y elija la categoría de **acción** .  
  
 Para solicitar una aprobación del descuento, usamos una acción personalizada denominada **proceso de aprobación**. Hemos agregado un parámetro de entrada, **SpecialNotes**y un paso **Enviar correo electrónico** para crear un nuevo mensaje y enviar una solicitud de aprobación del administrador, como se muestra aquí.  
  
 ![Agregar un paso &#45; enviar correo electrónico](media/enable-custom-action-approval-proces-sadd-email.png "Adición de un correo electrónico de envío por pasos")  
  
 Para configurar el mensaje de correo electrónico, elija **establecer propiedades**. Cuando se abra el formulario, use el **Asistente de formulario** para agregar notas especiales y otra información al correo electrónico, como se resalta en la captura de pantalla. Para agregar las notas especiales, coloque el cursor donde desee que aparezcan en el mensaje y, a continuación, en el **Asistente para formularios**, en **Buscar**, elija **argumentos** en la primera lista desplegable y elija **SpecialNotes** en el segundo. y, después, elija **Aceptar**.  
  
 ![Configurar correo electrónico](media/enable-custom-action-approval-process-setup-email.png "Configurar correo electrónico")  
  
 Antes de poder invocar la acción desde un flujo de trabajo, tiene que activarla. Después de haber activado la acción, puede ver sus propiedades eligiendo **Ver propiedades**.  
  
 ![Activar proceso de &#45; aprobación de acciones personalizadas](media/enable-custom-action-approval-process-activate-action.png "Activar proceso de aprobación de acciones personalizadas")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocar una acción personalizada desde un flujo de trabajo  
  
1. En el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , seleccione **procesos**.   
  
2.  En la barra de navegación, elija **nuevo**. Asigne un nombre al proceso y elija la categoría **flujo de trabajo** .  
  
 Hemos creado un flujo de trabajo que invoca la acción personalizada del **proceso de aprobación** cada vez que se requiere la aprobación del administrador para un descuento superior al 20% para una oportunidad.  
  
 ![Establecer propiedades de acción desde el flujo de trabajo](media/enable-custom-action-from-workflow.png "Establecer propiedades de acción desde el flujo de trabajo")  
  
 Puede establecer las propiedades de entrada de la acción seleccionando **establecer propiedades**. Hemos agregado un nombre de la cuenta relacionada con la oportunidad en las notas especiales. En el **Asistente de formulario**, en **Buscar**, elija **cuenta** en la primera lista desplegable, elija **nombre de cuenta** en la segunda lista desplegable y, a continuación, elija **Aceptar**. La propiedad de **destino** es obligatoria y está rellenada por el sistema. **{Oportunidad (oportunidad)}** en la propiedad de **destino** es la misma oportunidad en la que se está ejecutando el flujo de trabajo que realiza la llamada. Como alternativa, puede elegir una oportunidad específica para la propiedad de destino mediante la búsqueda.  
  
 ![Establecer parámetros de entrada para la acción ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Establecer parámetros de entrada para la acción ApprovalProcess")  
  



