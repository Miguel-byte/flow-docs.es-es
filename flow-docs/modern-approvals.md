---
title: Automatice fácilmente los flujos de trabajo de aprobación. | Microsoft Docs
description: Automatice los flujos de trabajo de aprobación que se integran con SharePoint, Dynamics CRM, Salesforce, OneDrive para la empresa, zendesk o WordPress.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548694"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Crear y probar un flujo de trabajo de aprobación con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Con Microsoft Flow, puede administrar la aprobación de documentos o procesos en varios servicios, entre los que se incluyen SharePoint, Dynamics 365, Salesforce, OneDrive para la empresa, zendesk o WordPress.

Para crear un flujo de trabajo de aprobación, agregue la acción **aprobaciones-iniciar una aprobación** a cualquier flujo. Después de agregar esta acción, el flujo puede administrar la aprobación de documentos o procesos. Por ejemplo, puede crear flujos de aprobación de documentos que aprueben facturas, pedidos de trabajo o presupuestos de ventas. También puede crear flujos de aprobación de proceso que aprueben solicitudes de vacaciones, trabajo de horas extras o planes de viajes.

Los aprobadores pueden responder a las solicitudes de su bandeja de entrada de correo electrónico, [el centro de aprobaciones](https://flow.microsoft.com/manage/approvals/received/) del sitio web de Microsoft Flow o la aplicación Microsoft Flow.

## <a name="create-an-approval-flow"></a>Crear un flujo de aprobación
Aquí se muestra información general sobre el flujo que crearemos y probaremos:

   ![Información general de Flow](./media/modern-approvals/create-flow-overview.png)

El flujo realiza los pasos siguientes:

1. Se inicia cuando alguien crea una solicitud de vacaciones en una lista de SharePoint Online.
2. Agrega la solicitud de vacaciones al centro de aprobación y, a continuación, envía un correo electrónico al aprobador.
3. Envía un correo electrónico con la decisión del aprobador a la persona que solicitó las vacaciones.
4. Actualiza la lista de SharePoint Online con los comentarios de decisión del aprobador.

## <a name="prerequisites"></a>Requisitos previos
Para completar este tutorial, debe tener acceso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Cree estas columnas en la lista de SharePoint Online:

   ![Columnas de la lista de SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Anote el nombre y la dirección URL de la lista de SharePoint Online. Los necesitará más adelante cuando configure el desencadenador **SharePoint-cuando se crea un elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Crear el flujo a partir de la plantilla en blanco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Agregar un desencadenador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

La **dirección del sitio** y el nombre de la **lista** son los elementos que anotó anteriormente en este tutorial.

![Información de SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Agregar una acción de perfil

1. Seleccione **nuevo paso**y, a continuación, seleccione **Agregar una acción**.
   
    ![Nuevo paso](./media/modern-approvals/select-sharepoint-add-action.png)
2. Escriba **perfil** en el cuadro de búsqueda **elegir una acción** .
   
    ![buscar perfil](./media/modern-approvals/search-for-profile.png)
3. Busque y, a continuación, seleccione la acción **usuarios de Office 365-obtener mi perfil** .
   
    ![Seleccionar usuarios de Office](./media/modern-approvals/select-my-profile.png)
4. Proporcione un nombre para el flujo y, a continuación, seleccione **Crear flujo** para guardar el trabajo que hemos hecho hasta ahora.
   
    ![guardar flujo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Agregar una acción de aprobación

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Esta acción envía la solicitud de aprobación a la dirección de correo electrónico en el cuadro de **asignado a** .
>
>

## <a name="add-a-condition"></a>Agregar una condición

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Agregar una acción de correo electrónico para aprobaciones

Siga estos pasos para enviar un correo electrónico si se aprueba la solicitud de vacaciones:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico aprobada](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Agregar una acción de actualización para las solicitudes aprobadas

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Se requieren la **dirección del sitio**, **el nombre**de la lista, el **identificador**y el **título** .
>
>

![Actualizar configuración de elemento](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Agregar una acción de correo electrónico para rechazos

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuración de solicitudes rechazadas](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Agregar acción de actualización para las solicitudes rechazadas

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Se requieren la **dirección del sitio**, **el nombre**de la lista, el **identificador**y el **título** .
   >
   >

![actualizar tarjeta de elemento](./media/modern-approvals/configure-update-item-no.png)

1. Seleccione **Actualizar flujo** para guardar el trabajo que hemos hecho.
   
    ![Seleccionar acción de actualización](./media/modern-approvals/update.png)

Si ha seguido estos pasos, el flujo debe ser similar al de esta captura de pantalla:

![Información general de Flow](./media/modern-approvals/completed-flow.png)

Ahora que hemos creado el flujo, es el momento de probarlo.

## <a name="request-an-approval"></a>Solicitar una aprobación

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Crear aprobaciones de ejecución prolongada

Si es probable que el flujo se ejecute durante más de 30 días, considere la posibilidad de almacenar las aprobaciones en Common Data Service. Esto permite crear flujos que actúan sobre las respuestas a las solicitudes de aprobación, incluso después de que se agote el tiempo de espera de la ejecución del flujo original. Para ello, use dos flujos, uno para enviar una solicitud de aprobación y el otro para ejecutar la lógica de negocios en las respuestas a la solicitud de aprobación, en función de la acción **crear una aprobación (V2)** . Más información sobre las [aprobaciones de ejecución prolongada](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Si usa clientes de correo electrónico modernos, no tiene que preguntarse si todavía se requiere una solicitud porque Microsoft Flow actualiza automáticamente el correo electrónico para indicar que se ha completado la aprobación.

## <a name="cancel-an-approval-requests"></a>Cancelar solicitudes de aprobación

En ocasiones, es posible que desee cancelar una solicitud de aprobación que haya enviado. Es posible que haya cometido un error en la solicitud o que ya no sea relevante. En cualquier caso, la persona que envió la solicitud puede cancelarla siguiendo estos pasos:

1. Seleccionar la aprobación
1. Seleccione **Cancelar aprobación** en el panel lateral.

>[!TIP]
>Siempre puede seleccionar la pestaña **historial** para ver las solicitudes de aprobación que ha cancelado.

>[!NOTE]
> La característica cancelar es compatible con la acción **crear una aprobación (V2)** .

## <a name="request-approvals-from-guest-users"></a>Solicitar aprobaciones de usuarios invitados

Puede enviar solicitudes de aprobación a personas ajenas a la organización. Para ello, use usuarios invitados de Azure Active Directory (Azure AD) [invitando a usuarios de otros inquilinos como invitados](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Cuando se asigna un rol a un invitado, se proporciona al invitado el permiso necesario para participar en el proceso de aprobación.

Ahora que ha creado y probado el flujo, asegúrese de que otros usuarios sepan cómo usarlo.

## <a name="learn-more"></a>Aprende más

* Ver y administrar [las solicitudes de aprobación pendientes](approve-reject-requests.md)
* Cree [flujos de aprobación secuenciales.](sequential-modern-approvals.md)
* Cree [flujos de aprobación en paralelo.](parallel-modern-approvals.md)
* Instale la aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
