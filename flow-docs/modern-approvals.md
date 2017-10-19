---
title: "Automatice fácilmente los flujos de trabajo de aprobación. | Microsoft Docs"
description: "Automatice los flujos de trabajo de aprobación que se integran con SharePoint, Dynamics CRM, Salesforce, One Drive para la Empresa, Zendesk o WordPress."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: fe05ce536b61887f52ea4e297457c71ead3e8bfd
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Creación y prueba de un flujo de trabajo de aprobación con Microsoft Flow
Con Microsoft Flow se puede administrar la aprobación de documentos o procesos en varios servicios, entre los que se incluyen SharePoint, Dynamics CRM, Salesforce, OneDrive para la Empresa, Zendesk o WordPress.

Para crear un flujo de trabajo de aprobación, agregue la acción **Approvals - Start an approval** (Aprobaciones - Iniciar una aprobación) a cualquier flujo. Después de agregar esta acción, el flujo puede administrar la aprobación de documentos o procesos. Por ejemplo, puede crear flujos de aprobación de documentos que aprueben facturas, pedidos de trabajo o presupuestos de ventas. También puede crear flujos de aprobación de proceso que aprueben solicitudes de vacaciones, horas extras o planes de viajes.

Los aprobadores pueden administrar las solicitudes desde la bandeja de entrada del correo electrónico, [el centro de aprobaciones](https://flow.microsoft.com/manage/approvals/received/) del sitio web de Microsoft Flow o desde la aplicación Microsoft Flow.

## <a name="create-an-approval-flow"></a>Creación de un flujo de aprobación
Esta es una visión general del flujo de que vamos a crear y probar:

   ![información general del flujo](./media/modern-approvals/create-flow-overview.png)

El flujo realiza los pasos siguientes:

1. Se inicia cuando alguien crea una solicitud de vacaciones en una lista de SharePoint Online.
2. Agrega la solicitud de vacaciones en el centro de aprobaciones y, después, la envía por correo electrónico al aprobador.
3. Envía un correo electrónico con la decisión del aprobador a la persona que solicita las vacaciones.
4. Actualiza la lista de SharePoint Online con la decisión y los comentarios del aprobador.

## <a name="prerequisites"></a>Requisitos previos
Para completar este tutorial, debe tener acceso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Cree estas columnas en la lista de SharePoint Online:

   ![Columnas de lista de SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Tome nota del nombre y la dirección URL de la lista de SharePoint Online. Necesitará estos elementos después al configurar el desencadenador **SharePoint - Cuando se crea un elemento**.

## <a name="create-your-flow-from-the-blank-template"></a>Creación del flujo en la plantilla en blanco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adición de un desencadenador
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

La **dirección del sitio** y el **nombre de la lista** son los elementos que anotó anteriormente en este tutorial.

![Información de SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Adición de una acción de perfil
1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![nuevo paso](./media/modern-approvals/select-sharepoint-add-action.png)
2. Escriba **perfil** en el cuadro de búsqueda **Elegir una acción**.
   
    ![buscar perfil](./media/modern-approvals/search-for-profile.png)
3. Busque y, después, seleccione la acción **Usuarios de Office 365 - Obtener mi perfil**.
   
    ![seleccionar usuarios de office](./media/modern-approvals/select-my-profile.png)
4. Proporcione un nombre para el flujo y, después, seleccione **Crear flujo** para guardar el trabajo que hemos hecho hasta ahora.
   
    ![guardar flujo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Adición de una acción de aprobación
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: Esta acción envía la solicitud de aprobación a la dirección de correo electrónico en el cuadro **Asignado a**.

## <a name="add-a-condition"></a>Adición de una condición
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Adición de una acción de correo electrónico para aprobaciones
Siga estos pasos para enviar un correo electrónico si se aprueba la solicitud de vacaciones:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico aprobado](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Adición de una acción de actualización para las solicitudes aprobadas
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

Nota: Los campos **Dirección del sitio**, **Nombre de la lista**, **Identificador** y **Título** son necesarios.

![actualizar configuración de elemento](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Adición de una acción de correo electrónico para rechazos
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuración de solicitudes rechazadas](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Adición de acción de actualización para las solicitudes rechazadas
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   Nota: Los campos **Dirección del sitio**, **Nombre de la lista**, **Identificador** y **Título** son necesarios.

![tarjeta actualizar elemento](./media/modern-approvals/configure-update-item-no.png)

1. Seleccione **Actualizar flujo** para guardar el trabajo que hemos hecho.
   
    ![seleccionar actualizar acción](./media/modern-approvals/update.png)

Si ha seguido estos pasos, el flujo debe ser similar al de esta captura de pantalla:

![información general del flujo](./media/modern-approvals/completed-flow.png)

Ahora que hemos creado el flujo, es el momento de probarlo.

## <a name="request-an-approval"></a>Solicitud de una aprobación
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Ahora que ha creado y probado el flujo, asegúrese de que los demás sepan cómo usarlo.

## <a name="learn-more"></a>Más información
* Vea y administre [solicitudes de aprobación pendientes](approve-reject-requests.md)
* Cree [flujos de aprobación secuenciales.](sequential-modern-approvals.md)
* Cree [flujos de aprobación en paralelo.](parallel-modern-approvals.md)
* Instale la aplicación móvil de Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows).

