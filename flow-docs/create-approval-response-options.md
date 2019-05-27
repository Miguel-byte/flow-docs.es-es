---
title: Crear flujos de aprobación con respuestas personalizadas | Microsoft Docs
description: Crear flujos de aprobación con respuestas personalizadas.
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
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061719"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Crear opciones de respuesta personalizada para flujos de aprobación

Supongamos que desea enviar una solicitud de aprobación cada vez que un empleado carga un informe de gastos en SharePoint y, a continuación, permitirá que el aprobador responda con una de las tres opciones: Aceptar, ¿necesita más información o rechazar.


## <a name="prerequisites"></a>Requisitos previos

- Una cuenta de Microsoft Flow con una licencia del Plan 2 (Plan 2 es necesario usar las características premium. Aprobaciones es una característica premium).
- Una lista de SharePoint para los empleados que escriba sus informes de gastos.

## <a name="create-approval-flow"></a>Crear un flujo de aprobación
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione **Mis flujos** desde la barra de navegación izquierdo.
1. Seleccione **New** > **crear desde cero**.

    ![Crear a partir de una opción en blanco](media/create-approval-response-options/create-approval-response-options.png)

1. En la pantalla que se abre, seleccione **crear desde cero**. 

    ![Seleccione crear desde cero](media/create-approval-response-options/create-from-blank.png)

1. Busque **sharepoint** y, a continuación, seleccione **cuando se crea un elemento** en la lista de desencadenadores. 

1. Proporcione el SharePoint **dirección del sitio** y **lista nombre**. 

1. Seleccione **nuevo paso**, busque **aprobación**y, a continuación, seleccione **inicial y esperar una aprobación (V2)**.

1. En el **inicial y esperar una aprobación (V2)** tarjeta, seleccione el **tipo de aprobación** lista.

    ![Tipo de aprobación](media/create-approval-response-options/select-approval-type.png)

1. Seleccione **respuestas personalizadas: esperar una respuesta (Premium)**.

    ![Respuestas personalizadas](media/create-approval-response-options/select-custom-responses.png)

    A continuación, creará las respuestas personalizadas que los aprobadores va a usar al responder a una solicitud de aprobación de gastos de un empleado.


1. En el **respuesta opciones elemento - 1** , escriba **Accept** y, a continuación, seleccione **Agregar nuevo elemento**. 

    ![Respuesta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. En el **elemento - 2 opciones de respuesta** , escriba **rechazar** y, a continuación, seleccione **Agregar nuevo elemento**.

    ![Respuesta personalizada 2](media/create-approval-response-options/enter-response-2.png)

1. En el **elemento - 3 opciones de respuesta** , escriba **necesita más información**.

    ![Respuesta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Escriba un **título**, **asignado a** (correo electrónico del aprobador), y **detalles** (los detalles que debe incluirse en la solicitud de aprobación).

    Este es un ejemplo de lo que podría incluir para su organización.

    ![Detalles de las respuestas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Ahora que ha creado sus respuestas personalizadas, es posible que desee realizar diferentes acciones en el flujo, dependiendo de la respuesta del aprobador.


## <a name="use-approval-responses"></a>Usar las respuestas de aprobación 

Si la respuesta a la solicitud es **Accept**, es posible que desee enviar un correo electrónico al departamento de contabilidad, le pide que reembolsar el empleado por el gasto. 

Si la respuesta es **rechazar**, desea enviar un correo electrónico al empleado, que les informará de que se ha rechazado la solicitud.

Y por último, si es la respuesta del aprobador **necesita más información**, es posible que desee enviar un correo electrónico al empleado, que solicita el empleado para proporcionar más información.

Para realizar cualquiera de estas opciones en el flujo, agregue un [ **condición** ](add-condition.md) o un **conmutador** acción al flujo y, a continuación, seleccione el **resultado** campo de la aprobación solicitar desde el selector de contenido dinámico. Asegúrese de confirmar si el valor es Accept, ¿necesita más información o rechazar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Responder a solicitudes de aprobación con una respuesta personalizada

Los aprobadores reciben las solicitudes de aprobación en correo electrónico. También se muestran las solicitudes en el centro de aprobación en Microsoft Flow. 

![Correo electrónico de solicitud de aprobación](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Más información
- Crear [único flujos de aprobador](modern-approvals.md)
- Crear [flujos secuenciales de aprobador](sequential-modern-approvals.md)
