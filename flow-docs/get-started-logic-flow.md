---
title: Automatización de tareas mediante la creación de un flujo | Microsoft Docs
description: Cree un flujo que realice automáticamente una o varias acciones, como enviar correo electrónico, cuando se produzcan eventos como alguien que agrega una fila a una lista de SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548306"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Creación de un flujo en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Cree un flujo que realice una o varias tareas automáticamente una vez desencadenada por un evento. Por ejemplo, cree un flujo que le envíe una notificación por correo electrónico cuando alguien envíe un Tweet que contenga una palabra clave que especifique. En este ejemplo, el envío de un tweet es el evento y el envío de correo es la acción.

## <a name="prerequisites"></a>Requisitos previos

* Una cuenta en [Flow.Microsoft.com](https://flow.microsoft.com)
* Una cuenta de Twitter
* Credenciales de Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especificar un evento para iniciar el flujo

En primer lugar, debe seleccionar qué evento, o *desencadenador*, inicia el flujo.

1. En [Flow.Microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior y, después, seleccione **crear desde**cero.

    ![Opción flujos en la barra de navegación izquierda](./media/get-started-logic-flow/create-logic-flow.png)
1. Active la casilla **Buscar cientos de conectores y desencadenadores** en la parte inferior de la pantalla, escriba **Twitter** en el cuadro que dice **Buscar todos los conectores y desencadenadores**y, a continuación, seleccione **Twitter-cuando se publica un nuevo Tweet**.

    ![Evento de Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Si aún no ha conectado su cuenta de Twitter a Microsoft Flow, seleccione **iniciar sesión en Twitter**y proporcione sus credenciales.

1. En el cuadro de **texto buscar** , escriba la palabra clave que desea buscar.

    ![Palabra clave de Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificar una acción

1. Seleccione **nuevo paso**y, a continuación, seleccione **Agregar una acción**.

    ![Agregar acción](./media/get-started-logic-flow/add-action-icon.png)

1. En el cuadro que muestra **Buscar todos los conectores y acciones**, escriba o pegue **Enviar correo electrónico**y, a continuación, seleccione **Office 365 Outlook-enviar un correo electrónico**.

    ![Lista de acciones](./media/get-started-logic-flow/send-email.png)

1. Si se le solicita, seleccione el botón de inicio de sesión y proporcione sus credenciales.

1. En el formulario que aparece, escriba o pegue la dirección de correo electrónico en el cuadro **para** y, a continuación, seleccione su nombre en la lista de contactos que aparece.

    ![Mensaje de correo electrónico en blanco](./media/get-started-logic-flow/blank-email.png)
1. En el cuadro **asunto** , escriba o pegue **nuevo tweet de:** y, a continuación, escriba un espacio.

    ![Línea de asunto con marcador de posición](./media/get-started-logic-flow/message-token.png)
1. En la lista de tokens, seleccione el token con **Tweet** para agregar un marcador de posición para él.

    ![Agregar parámetro](./media/get-started-logic-flow/add-parameter.png)
1. Seleccione el cuadro **cuerpo** y, a continuación, seleccione el token de **texto del Tweet** para agregar un marcador de posición.
1. opta Agregue más tokens, otro contenido o ambos al cuerpo del correo electrónico.
1. Cerca de la parte superior de la pantalla, asigne un nombre al flujo y seleccione **Crear flujo**.

    ![Seleccione el botón Crear flujo](./media/get-started-logic-flow/create-button.png)
1. Seleccione **listo** para actualizar la lista de flujos.

     ![Seleccione el botón listo](./media/get-started-logic-flow/done-button.png)
1. Envíe un tweet con la palabra clave que ha indicado o espere a que otra persona publique este Tweet.

     En un minuto después de que se publique el tweet, un mensaje de correo electrónico le notificará el nuevo Tweet.

> [!TIP]
> Use la acción **Enviar correo electrónico (V2)** para dar formato al correo electrónico en el que se personaliza la fuente, usar negrita, cursiva o subrayado, personalizar el color y resaltar, y crear listas o vínculos, etc.

![Correo electrónico de edición enriquecida](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Administrar un flujo

1. En [Flow.Microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.
1. En la lista de flujos, realice una de las acciones siguientes:

   * Para pausar un flujo, establezca su alternancia en **OFF**.

       ![Pausar flujo](./media/get-started-logic-flow/pause-flow.png)
   * Para reanudar un flujo, establezca el control de alternancia en **activado**.

       ![Reanudar flujo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar un flujo, seleccione el icono de lápiz que corresponde al flujo que desea editar.

       ![Seleccionar flujo](./media/get-started-logic-flow/select-flow.png)
   * Para eliminar un flujo, seleccione el icono **...** , seleccione **eliminar**y, a continuación, seleccione **eliminar** en el cuadro de mensaje que aparece.

       ![Eliminar icono](./media/get-started-logic-flow/delete-icon.png)
   * Para ver el historial de ejecución de un flujo, seleccione el flujo en la página **Mis flujos** y, a continuación, vea el historial en la sección **historial de ejecución** de la página que se abre.

       ![Historial de ejecución](./media/get-started-logic-flow/run-history.png)

     Seleccione una ejecución de flujo en la lista de ejecuciones para ver las entradas y salidas de cada paso.

> [!NOTE]
> Puede tener hasta 600 flujos en su cuenta. Si ya tiene 600 flujos, elimine uno antes de crear otro flujo.
>
>

## <a name="next-steps"></a>Pasos siguientes

* [Agregue pasos](multi-step-logic-flow.md), como diferentes maneras de recibir notificaciones, al flujo.
* [Ejecutar tareas según una programación](run-scheduled-tasks.md), cuando desee que una acción se realice a diario, en una fecha determinada o después de un número determinado de minutos.
* [Agregue un flujo a una aplicación](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para permitir que la aplicación inicie la lógica en la nube.
* Comience a [trabajar con los flujos de equipo](create-team-flows.md) e invite a otros usuarios a colaborar con usted para diseñar flujos.
