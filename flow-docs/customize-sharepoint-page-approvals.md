---
title: Administrar aprobaciones de la página de SharePoint con Microsoft Flow | Microsoft Docs
description: Obtenga información sobre cómo administrar aprobaciones de la página de SharePoint con Microsoft Flow...
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
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061351"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Administrar aprobaciones de la página de SharePoint con Microsoft Flow

Los administradores de sitio de SharePoint pueden usar Microsoft Flow para requieren las páginas de sitio nuevo o actualizado para ser aprobado antes de que se está publicando.

En este artículo, obtendrá información sobre cómo configurar el sitio de SharePoint para usar un flujo para solicitar cambios en el sitio que se aprueben antes de que entren en vivo.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurar SharePoint para aprobaciones de página

### <a name="prerequisites"></a>Requisitos previos 

Debe ser un administrador de sitio de SharePoint para realizar las actividades en este artículo.

1. Inicie sesión en SharePoint como un administrador del sitio.
1. Seleccione **páginas** desde la barra de navegación.

    ![Seleccione el flujo de aprobación de la página](media/customize-sharepoint-page-approvals/pages.png)

1. Seleccione **flujo** y, a continuación, seleccione **configurar el flujo de aprobación de la página**.
    
    ![Seleccione el flujo de aprobación de la página](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Proporcionar un **nombre flujo**, al menos un nombre en el **aprobadores** cuadro y, a continuación, seleccione **crear**.
    
    ![Seleccione el flujo de aprobación de la página](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

¡Eso es todo! Ahora, cada vez que una página se agrega o modifica, pasa de una solicitud de aprobación a la **aprobadores** aparece en el flujo.

El flujo de aprobación de la página es igual que cualquier otro flujo, por lo que se incluye en el **Mis flujos** ficha.

![Seleccione el flujo de aprobación de la página](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Enviar una página de aprobación

Ahora que ha creado un flujo de aprobación de la página, cualquier persona que agrega o cambia una página deberá hacer lo siguiente:

 - Realice un cambio en el sitio (agregar una nueva página, por ejemplo) y, a continuación, guarde el cambio.

     ![Enviar la página para su aprobación](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Espere a que alguien aprobar el cambio.
    
    ![Enviar la página para su aprobación](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprobar una página

Los aprobadores reciben un correo electrónico cada vez que hay una solicitud de aprobación de la página. Puede aprobar las solicitudes directamente en el correo electrónico (si su cliente de correo electrónico admite mensajes accionables) o abra la página desde el correo electrónico para revisar y aprobar, a continuación, la página de SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizar flujos de aprobación de la página

Dado que las aprobaciones de página usan Microsoft Flow en segundo plano, el flujo de aprobación de la página está disponible para los propietarios de sitios modificar y agregar cualquier lógica de negocios personalizada en el flujo. Para modificar el flujo, puede seleccionar el propietario del sitio **flujos** y, a continuación, seleccione **vea sus flujos** en la biblioteca de páginas para encontrar el flujo de aprobación de la página.

## <a name="learn-more"></a>Más información

- [Flujo de aprobación de la página](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurar la aprobación de la página](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
