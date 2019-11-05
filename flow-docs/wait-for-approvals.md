---
title: Esperar aprobación en un flujo | Microsoft Docs
description: Los flujos pueden esperar a que se produzca un evento externo, como que un usuario apruebe o rechace un cambio, antes de realizar una acción, como el envío de una notificación de la decisión.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea6be2d1deae080df58afd94c1f1e8d0c13c9fcd
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548349"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Esperar aprobación en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Cree un flujo que, si crea un elemento en SharePoint, envía un correo electrónico de aprobación y le notifica si el elemento se ha aprobado o rechazado. Para seguir este tutorial exactamente, cree una lista de SharePoint simple como una acción de desencadenador, pero puede usar otro origen de datos, como Dropbox o OneDrive.

**Requisitos previos**

* Cree una lista de SharePoint simple denominada **Project Tracker**, agregue una columna denominada **title**y, a continuación, agregue una columna Person o Group denominada **asignado a**.

   ![Imagen de la lista de SPO del seguimiento de proyectos](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Agregar un evento para desencadenar el flujo

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior y, después, seleccione **crear desde**cero.

1. Seleccione el cuadro **Buscar cientos de conectores y desencadenadores** , escriba **nuevo elemento**y, a continuación, vaya a **SharePoint: cuando se crea un elemento**.

1. Si se le solicita, inicie sesión en SharePoint.
1. En **dirección del sitio**, escriba la dirección URL del sitio de SharePoint que contiene la lista.

1. En **nombre de lista**, seleccione la lista que creó anteriormente. Si está siguiendo, el nombre es **Project Tracker**.

    ![Imagen de nombre de lista de SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Agregar la acción resultante

1. Seleccione el botón **nuevo paso** y, a continuación, seleccione **Agregar una acción.**

1. En el cuadro **Buscar todos los conectores y acciones** , escriba o pegue **Enviar correo electrónico**y, a continuación, seleccione **Office 365 Outlook-enviar correo electrónico con opciones**.

1. Si se le solicita, inicie sesión en Office 365 Outlook.

1. Seleccione el campo **para** y, a continuación, seleccione el token **asignado a correo electrónico** .

    El usuario de la columna **asignado a** recibe el correo electrónico para aprobar o rechazar elementos. Cuando cree un elemento para probar el flujo, especifíquelo en este campo. De este modo, no solo aprobará o rechazará el elemento, sino que también recibirá el correo electrónico de notificación.

    > [!NOTE]
    > Puede personalizar los campos **asunto** y **Opciones de usuario** para que se ajusten a sus necesidades.

    ![Imagen del campo enviar correo electrónico de aprobación a](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Agregar una condición

1. Seleccione el botón **nuevo paso** y, a continuación, seleccione **Agregar una condición**.

    ![Imagen de agregar una condición](./media/wait-for-approvals/add-a-condition.png)
1. Seleccione el primer cuadro y, a continuación, seleccione el token **SelectedOption** .
1. Seleccione el último cuadro y, a continuación, escriba **aprobar**.

    ![Imagen de la tarjeta de condición](./media/wait-for-approvals/condition-card-2.png)

1. En el área **si es así** , seleccione **Agregar una acción**.

1. En el cuadro **Buscar todos los conectores y acciones** , escriba o pegue **Enviar correo electrónico**y, a continuación, seleccione **Office 365 Outlook-enviar un correo electrónico**.

1. En el campo **para** , escriba un destinatario como **creado por correo electrónico**.

1. En el cuadro **asunto** , especifique un asunto.

    Por ejemplo, seleccione **asignado a DisplayName**, el tipo **ha aprobado** con un espacio en cada lado y, a continuación, seleccione **título**.

1. En el cuadro **cuerpo** , especifique un cuerpo de correo electrónico como **listo para continuar con la siguiente fase del proyecto.**

    > [!NOTE]
    > Se notificará a la persona que creó el elemento en la lista de SharePoint si el proyecto se ha aprobado o rechazado.

    ![Imagen de sí-enviar-correo electrónico](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. En el área **si no** , repita los cinco últimos pasos, excepto cambiar el **asunto** y el **cuerpo** para reflejar que el proyecto se ha rechazado.

     ![Imagen de no-Send-email](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Finalizar y probar el flujo

1. Asigne un nombre al flujo y seleccione **Crear flujo**.

     ![Imagen del flujo de creación](./media/wait-for-approvals/create-flow.png)
1. Cree un elemento en la lista de SharePoint.

    Se envía un correo electrónico de aprobación al destinatario especificado. Cuando el destinatario selecciona **aprobar** o **rechazar** en ese correo electrónico, recibirá un correo electrónico que indica la respuesta.

## <a name="learn-more"></a>Aprende más

* [Tutorial de aprobaciones modernas de aprobador único](modern-approvals.md)
* Crear [aprobaciones secuenciales](sequential-modern-approvals.md)
* Crear [aprobaciones en paralelo](parallel-modern-approvals.md)
* Aprobar [solicitudes sobre la marcha](mobile-approvals.md)
