---
title: Creación de un flujo de trabajo de aprobación moderno con varios aprobadores | Microsoft Docs
description: 'Creación de un flujo de trabajo de aprobación moderno con varios aprobadores '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 269239bd3fbb07c78bf316f9e58003690c63d878
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548972"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Administrar aprobaciones secuenciales con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Algunos flujos de trabajo requieren una aprobación previa antes de que se requiera al aprobador final que cierre la sesión. Por ejemplo, una empresa puede tener una directiva de aprobación secuencial que requiera la aprobación previa de las facturas de más de $1000,00 antes de que las apruebe el Departamento de finanzas.

En este tutorial, se crea un flujo de aprobación secuencial que administra las solicitudes de vacaciones de los empleados.

> [!NOTE]
> SharePoint solo se usa aquí como ejemplo: no es necesario crear flujos de aprobación. Puede usar cualquiera de los servicios más de 200 con los que Microsoft Flow se integra para impulsar los flujos.


## <a name="detailed-steps-in-the-flow"></a>Pasos detallados del flujo
El flujo:

1. Se inicia cuando un empleado crea una solicitud de vacaciones en una [lista de SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Agrega la solicitud de vacaciones al centro de aprobación y, después, envía por correo electrónico la solicitud al aprobador previo.
3. Envía por correo electrónico la decisión de aprobación previa al empleado.
4. Actualiza la lista de SharePoint Online con la decisión y los comentarios del aprobador previo.
   
   Nota: Si la solicitud se ha aprobado previamente, el flujo continuará con estos pasos:
5. Envía la solicitud al aprobador final.
6. Envía por correo electrónico la decisión final al empleado.
7. Actualiza la lista de SharePoint con la decisión final.

En esta imagen se resumen los pasos anteriores:

   ![diagrama de Visio del flujo](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Requisitos previos
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Para los fines de este tutorial, la lista de SharePoint Online que cree debe incluir las columnas siguientes:

   ![Columnas de lista de SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Anote el nombre y la dirección URL de la lista de SharePoint Online. Estos elementos se usan más adelante al configurar el desencadenador **SharePoint-cuando se crea un nuevo elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Crear el flujo a partir de la plantilla en blanco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Agregar un desencadenador
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![información de SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtener el administrador de la persona que creó la solicitud de vacaciones
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Proporcione un nombre para el flujo y, a continuación, seleccione **Crear flujo** para guardar el trabajo que hemos hecho hasta ahora.
   
    ![guardar flujo](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Seleccione **Actualizar flujo** en la parte superior de la pantalla periódicamente para guardar los cambios en el flujo.
   > 
   > 
   
    ![Seleccionar acción de actualización](./media/sequential-modern-approvals/update.png)

Después de cada operación de guardar, seleccione **Editar flujo** en la parte superior de la pantalla y, a continuación, siga realizando cambios.

## <a name="add-an-approval-action-for-pre-approvals"></a>Agregar una acción de aprobación para aprobaciones previas
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Nota: esta acción envía la solicitud de aprobación previa a la dirección de correo electrónico en el cuadro de **asignado a** .

## <a name="add-a-condition"></a>Agregar una condición
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Esta condición comprueba la respuesta de la acción **iniciar una aprobación** .
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Agregar una acción de correo electrónico para aprobaciones previas
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico aprobada previamente](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Agregar una acción de actualización para las solicitudes aprobadas previamente
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Actualizar configuración de elemento](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Obtener el administrador del aprobador previo
1. Use los pasos de [obtención del administrador para la persona que creó las solicitudes de vacaciones](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) que hicimos anteriormente para agregar y, a continuación, configure otra acción **obtener administrador** . Esta vez se obtiene el administrador del aprobador previo.
2. Cuando haya terminado, la tarjeta **obtener administrador 2** debe ser similar a esta imagen. Asegúrese de usar el token de **correo electrónico** de la categoría **obtener administrador** en la tarjeta **agregar contenido dinámico de las aplicaciones y los servicios que se usan en este flujo** .
   
   ![obtener el administrador del aprobador previo](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Agregar la acción de aprobación final
1. Use el paso [Agregar una acción de aprobación para las aprobaciones](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) anteriores para agregar y, a continuación, configure otra acción **iniciar una aprobación** . Esta acción envía una solicitud de correo electrónico para la aprobación final.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
    ![configurar la aprobación](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Adición de la condición de aprobación final
1. Repita los pasos de [Agregar una condición](sequential-modern-approvals.md#add-a-condition) para agregar y, a continuación, configure una **condición** que Compruebe la decisión del aprobador final.

## <a name="send-email-with-final-approval"></a>Enviar correo electrónico con la aprobación final
1. Siga los pasos de [Agregar una acción de correo electrónico para las aprobaciones previas](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) a agregar y, a continuación, configure una acción que envíe un correo electrónico cuando se aprueben las solicitudes de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
   ![plantilla de correo electrónico de aprobación final](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Actualizar SharePoint con aprobación
1. Siga los pasos de [Agregar una acción de actualización para las solicitudes aprobadas previamente](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) para agregar y, a continuación, configurar una acción que actualice SharePoint cuando se apruebe la solicitud de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
    ![Actualizar configuración de elemento](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Enviar correo electrónico con el rechazo de la aprobación previa
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuración de solicitudes rechazadas](./media/sequential-modern-approvals/configure-rejected-email.png)

Nota: esta acción debe agregarse a la rama **If no, no hacer nada** debajo de la tarjeta **condición** .

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Actualización de SharePoint con el rechazo de la aprobación previa
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![actualizar SharePoint para solicitudes rechazadas](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Enviar correo electrónico con el rechazo final
1. Siga los pasos de [Enviar correo electrónico con rechazo de aprobación previa](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) para agregar y configurar una acción que envíe un correo electrónico cuando el aprobador final rechace la solicitud de vacaciones.
   
    Nota: esta acción debe agregarse a la rama **If no, no hacer nada** debajo de la tarjeta de la **condición 2** .
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
   ![configuración de solicitudes rechazadas](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Actualización de SharePoint con el rechazo final
1. Siga los pasos de [actualización de SharePoint con el rechazo de la aprobación previa](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) para agregar y, a continuación, configure una acción que actualice SharePoint si el aprobador final rechaza la solicitud de vacaciones.
2. Cuando haya terminado, la tarjeta debe ser similar a esta imagen:
   
   ![actualizar tarjeta de elemento](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Seleccione **Actualizar flujo** para guardar el trabajo que hemos hecho.
   
   ![Seleccionar acción de actualización](./media/sequential-modern-approvals/update.png)

Si ha seguido estos pasos, el flujo debe ser similar a esta imagen:

![Información general de Flow](./media/sequential-modern-approvals/completed-flow.png)

Ahora que hemos creado el flujo, vamos a verlo en acción.

## <a name="request-an-approval"></a>Solicitar una aprobación
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

La solicitud debe ser similar a esta imagen:

![solicitud de vacaciones](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Ver solicitudes de aprobación pendientes
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Aprobación previa de una solicitud
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Aprobación de la solicitud
Los pasos para aprobar una solicitud son idénticos a los pasos para [aprobar previamente una solicitud](sequential-modern-approvals.md#pre-approve-a-request) .

Nota: el aprobador final obtiene la solicitud de vacaciones solo después de que la solicitud se haya aprobado previamente.

## <a name="reject-a-request"></a>Rechazar una solicitud
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Más información
[Tutorial de aprobaciones modernas de aprobador único](modern-approvals.md)

