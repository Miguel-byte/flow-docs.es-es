---
title: Administrar aprobaciones de páginas de SharePoint con Microsoft Flow | Microsoft Docs
description: Obtenga información sobre cómo administrar aprobaciones de páginas de SharePoint con Microsoft Flow.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547651"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Administrar aprobaciones de páginas de SharePoint con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los administradores de sitios de SharePoint pueden usar Microsoft Flow para requerir la aprobación de páginas de sitio nuevas o actualizadas antes de publicarse.

En este artículo, aprenderá a configurar el sitio de SharePoint para que use un flujo para requerir que se aprueben los cambios en el sitio antes de que se realicen.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurar SharePoint para aprobaciones de páginas

### <a name="prerequisites"></a>Requisitos previos 

Debe ser administrador del sitio de SharePoint para realizar las actividades de este artículo.

1. Inicie sesión en SharePoint como administrador del sitio.
1. Seleccione **páginas** en la barra de navegación.

    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/pages.png)

1. Seleccione **Flow** y, a continuación, seleccione **configurar flujo de aprobación de páginas**.
    
    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Proporcione un **nombre de flujo**, al menos un nombre en el cuadro **aprobadores** y, a continuación, seleccione **crear**.
    
    ![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

¡ Eso es todo! Ahora, cada vez que se agrega o se modifica una página, se envía una solicitud de aprobación a los **aprobadores** que se enumeran en el flujo.

El flujo de aprobación de la página es igual que cualquier otro flujo, por lo que aparece en la pestaña **Mis flujos** .

![Seleccionar flujo de aprobación de páginas](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Enviar una página para su aprobación

Ahora que ha creado un flujo de aprobación de páginas, cualquier persona que agregue o cambie una página deberá hacer lo siguiente:

 - Realice un cambio en el sitio (agregue una nueva página, por ejemplo) y, a continuación, guarde el cambio.

     ![Página de envío para aprobación](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Espere a que alguien apruebe el cambio.
    
    ![Página de envío para aprobación](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprobar una página

Los aprobadores reciben un correo electrónico cada vez que hay una solicitud de aprobación de página. Pueden aprobar las solicitudes directamente en el correo electrónico (si su cliente de correo electrónico admite mensajes accionables) o abrir la página del correo electrónico para revisarla y, a continuación, aprobar la página en SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizar los flujos de aprobación de páginas

Dado que las aprobaciones de página usan Microsoft Flow en segundo plano, el flujo de aprobación de la página está disponible para que los propietarios del sitio modifiquen y agreguen cualquier lógica de negocios personalizada en el flujo. Para modificar el flujo, el propietario del sitio puede seleccionar **flujos** y, a continuación, seleccionar **ver los flujos** en la biblioteca de páginas para buscar el flujo de aprobación de la página.

## <a name="learn-more"></a>Aprende más

- [Flujo de aprobación de páginas](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurar la aprobación de páginas](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
