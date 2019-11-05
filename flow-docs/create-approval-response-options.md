---
title: Crear flujos de aprobación con respuestas personalizadas | Microsoft Docs
description: Cree flujos de aprobación con respuestas personalizadas.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547223"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Crear opciones de respuesta personalizadas para flujos de aprobación
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Supongamos que desea enviar una solicitud de aprobación cada vez que un empleado carga un informe de gastos en SharePoint y, a continuación, permitir que el aprobador responda con una de estas tres opciones: aceptar, necesitar más información o rechazar.


## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Microsoft Flow.
- Una lista de SharePoint para que los empleados escriban sus informes de gastos.

## <a name="create-approval-flow"></a>Crear flujo de aprobación
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione **Mis flujos** en la barra de navegación izquierda.
1. Seleccione **nuevo** > **crear desde**cero.

    ![Opción crear desde el espacio en blanco](media/create-approval-response-options/create-approval-response-options.png)

1. En la pantalla que se abre, seleccione **crear desde**cero. 

    ![Seleccione crear desde cero.](media/create-approval-response-options/create-from-blank.png)

1. Busque **SharePoint** y, a continuación, seleccione **cuando se cree un elemento** en la lista de desencadenadores. 

1. Proporcione la **dirección del sitio** de SharePoint y el **nombre de lista**. 

1. Seleccione **nuevo paso**, busque **aprobación**y, después, seleccione **iniciar y espere a que se apruebe (V2)** .

1. En la tarjeta **iniciar y esperar una aprobación (V2)** , seleccione la lista **tipo de aprobación** .

    ![Tipo de aprobación](media/create-approval-response-options/select-approval-type.png)

1. Seleccione **respuestas personalizadas: esperar una respuesta (Premium)** .

    ![Respuestas personalizadas](media/create-approval-response-options/select-custom-responses.png)

    A continuación, creará las respuestas personalizadas que los aprobadores usarán cuando respondan a una solicitud de aprobación para un gasto de empleado.


1. En el cuadro **elemento de opciones de respuesta-1** , escriba **Aceptar** y, a continuación, seleccione **Agregar nuevo elemento**. 

    ![Respuesta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. En el cuadro **elemento de opciones de respuesta-2** , escriba **rechazar** y, a continuación, seleccione **Agregar nuevo elemento**.

    ![Respuesta personalizada 2](media/create-approval-response-options/enter-response-2.png)

1. En el cuadro **elemento de opciones de respuesta-3** , escriba **necesito más información**.

    ![Respuesta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Escriba un **título**, **asignado a** (correo electrónico para el aprobador) y **detalles** (los detalles que se incluirán en la solicitud de aprobación).

    Este es un ejemplo de lo que podría incluir para su organización.

    ![Detalles de las respuestas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Ahora que ha creado las respuestas personalizadas, es posible que desee realizar diferentes acciones en el flujo, en función de la respuesta del aprobador.


## <a name="use-approval-responses"></a>Usar respuestas de aprobación 

Si la respuesta a la solicitud es **aceptada**, es posible que desee enviar un correo electrónico al Departamento de contabilidad, pidiéndoles que reembolsan el gasto al empleado. 

Si la respuesta es **rechazar**, es posible que desee enviar un correo electrónico al empleado, lo que les informa de que la solicitud se ha rechazado.

Y, por último, si la respuesta del aprobador es **necesaria más información**, puede que desee enviar un correo electrónico al empleado, solicitando al empleado que proporcione más información.

Para realizar cualquiera de estas acciones en el flujo, agregue una [**condición**](add-condition.md) o una acción de **cambio** al flujo y, a continuación, seleccione el campo de **resultados** de la solicitud de aprobación en el selector de contenido dinámico. Asegúrese de confirmar si el valor es aceptar, necesita más información o rechazar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Responder a las solicitudes de aprobación con una respuesta personalizada

Los aprobadores reciben solicitudes de aprobación por correo electrónico. Las solicitudes también se muestran en el centro de aprobación en Microsoft Flow. 

![Correo electrónico de solicitud de aprobación](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Aprende más
- Crear [flujos de aprobador único](modern-approvals.md)
- Creación de [flujos de aprobador secuencial](sequential-modern-approvals.md)
