---
title: Aprobar solicitudes en un dispositivo móvil | Microsoft Docs
description: Use un dispositivo móvil para aprobar las solicitudes creadas en Microsoft Flow.
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
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548667"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Aprobar solicitudes en el dispositivo móvil mediante el uso de Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Si un flujo lo identifica como aprobador y ha instalado la aplicación móvil para Microsoft Flow, recibirá una notificación de envío cada vez que se solicite su aprobación.

Este artículo le guía a través de algunos escenarios comunes que es probable que encuentre mientras administra las solicitudes de aprobación en la aplicación móvil para Microsoft Flow.

> [!NOTE]
> Las imágenes de este tema proceden de un dispositivo Android. sin embargo, la experiencia en iOS es similar.
> 
> 

## <a name="prerequisites"></a>Requisitos previos
Para completar este tutorial, necesitará lo siguiente:

* Un dispositivo [Android](https://aka.ms/flowmobiledocsandroid) o [iOS](https://aka.ms/flowmobiledocsios) que ejecuta la aplicación móvil para Microsoft Flow.
* Se debe designar como aprobador en un flujo de aprobación.
* Solicitudes pendientes de aprobación.

## <a name="view-pending-requests"></a>Ver solicitudes pendientes
1. Abra la aplicación móvil para Microsoft Flow.
   
    ![Inicio de la aplicación móvil](./media/mobile-approvals/open-app.png)
2. Seleccione **aprobaciones** en la esquina superior derecha.
   
    ![seleccionar aprobaciones](./media/mobile-approvals/select-approvals.png)
3. Ver todas las aprobaciones pendientes:
   
    ![Consulte las solicitudes de aprobación pendientes](./media/mobile-approvals/show-pending-approval-requests.png)

Si no tiene ninguna solicitud de aprobación pendiente, cree un [flujo de aprobación](modern-approvals.md), establézcalo como aprobador y, a continuación, desencadene el flujo. Las solicitudes de aprobación aparecen en el centro de aprobación unos segundos después de que el flujo se desencadena y envía una solicitud de aprobación.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aprobar solicitudes y dejar un comentario opcional
1. Si no lo ha hecho, siga los pasos anteriores para [ver las solicitudes pendientes](mobile-approvals.md#view-pending-requests).
2. Seleccione **aprobar** en la solicitud que desea aprobar.
   
    ![seleccionar aprobar](./media/mobile-approvals/select-approve.png)
3. (Opcional) Seleccione **Agregar Comentario (opcional)** .
   
    ![seleccionar agregar un comentario](./media/mobile-approvals/select-add-comment.png)
   
    Escriba un Comentario en la pantalla **Agregar comentario** .
   
    ![Escriba su comentario](./media/mobile-approvals/enter-comment-for-approval.png)
4. Seleccione **confirmar** en la esquina superior derecha.
   
    ![confirmar que ha finalizado](./media/mobile-approvals/tap-confirm-button.png)
   
    La pantalla de éxito se muestra después de que el flujo registre su decisión.
   
    ![pantalla de éxito](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rechazar solicitudes y dejar un comentario opcional
Siga los [pasos para aprobar una solicitud](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), pero seleccione **rechazar** en el segundo paso.

## <a name="learn-more"></a>Aprende más
[Cree flujos de aprobación modernos](modern-approvals.md).

