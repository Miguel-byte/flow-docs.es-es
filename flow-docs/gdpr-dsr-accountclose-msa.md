---
title: Microsoft Flow solicitudes de cierre de cuentas de asunto de datos de RGPD para las cuentas de Microsoft (MSA) | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a las solicitudes de cierre de cuentas de asunto de datos de RGPD para las cuentas de Microsoft.
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
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 8665148baf4d752f1f384670b296a66bbfca6163
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548020"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Responder a las solicitudes de cierre de la cuenta de asunto de datos de RGPD para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El **derecho a la eliminación** de datos personales es una protección de clave en RGPD. Este derecho incluye la eliminación de todos los datos personales excepto la información del registro de auditoría. Cuando los usuarios deciden cerrar su cuenta de Microsoft (MSA), también se eliminan los datos subyacentes del usuario.

Estos recursos contienen datos personales que se eliminan automáticamente cuando un usuario cierra una MSA:

|Recursos que contienen datos personales|
|------|
|Actividad de productos y servicios|
|Historial de ejecución|
|Fluyen|
|Fuente de actividades|
|Detalles del usuario|
|Conexiones|

## <a name="account-close-requests"></a>Solicitudes de cierre de cuenta

En estos pasos se describe cómo autoservicio de solicitudes de cierre de cuenta para RGPD.

1. Inicie sesión en el portal de cierre de la [cuenta de Microsoft](https://go.microsoft.com/fwlink/?LinkId=523898) con su cuenta de Microsoft y, después, seleccione **siguiente**.

    > [!NOTE]
    > Se le recordará que cancele las suscripciones existentes o que exporte los datos de los servicios existentes a los que puede suscribirse.
    >
    >

    ![Cancelar suscripciones](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirme que entiende el impacto del cierre de MSA y, a continuación, seleccione **marcar cuenta para el cierre**.

    Aparece una notificación que indica que la cuenta se cerrará en 30 días. Puede volver a abrir esta cuenta en cualquier momento durante este período de 30 días.

    ![Cuenta cerrada](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Al final de esta ventana de 30 días, comienza el proceso para eliminar todos los Microsoft Flow recursos de esta MSA.

## <a name="learn-more"></a>Aprende más

* Introducción a [Microsoft Flow](getting-started.md)
* Conozca [las novedades de](release-notes.md) Microsoft Flow
