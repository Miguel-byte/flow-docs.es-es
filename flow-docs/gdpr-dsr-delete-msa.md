---
title: Microsoft Flow solicitudes de eliminación de asunto de datos de RGPD para las cuentas de Microsoft (MSA) | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a solicitudes de eliminación de asunto de datos de RGPD para las cuentas de Microsoft.
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
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548056"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Responder a solicitudes de eliminación de asunto de datos de RGPD
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

El **derecho a** la eliminación de datos personales es una protección de clave en RGPD. La eliminación de datos personales incluye la eliminación de todos los datos personales excepto la información del registro de auditoría.

Microsoft Flow permite a los usuarios crear flujos de trabajo automatizados. Cuando un usuario decide eliminar sus datos personales de Microsoft Flow, el usuario puede revisar sus datos personales y determinar si desea eliminar algunos o todos ellos.

En la tabla siguiente se muestran los datos personales que se eliminan automáticamente y los datos que requieren un usuario de la cuenta de Microsoft (MSA) para revisarlos y eliminarlos.

|Requiere que el usuario de MSA Revise y elimine|Eliminado automáticamente|
|------|------|
|Actividad de productos y servicios|Historial de ejecución|
|Fluyen|Fuente de actividades|
|Conexiones||

Microsoft Flow ofrece las siguientes experiencias para ayudar a los usuarios a buscar, revisar o cambiar los datos personales y los recursos que no se eliminan automáticamente:

## <a name="manage-delete-requests"></a>Administrar solicitudes de eliminación

En los pasos siguientes se describe cómo autoservicio de solicitudes de eliminación para RGPD.

### <a name="delete-product-and-service-activity"></a>Eliminar actividad de productos y servicios

1. Inicie sesión en el [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy/) con su MSA.
1. Seleccione el vínculo **historial de actividad** .

    ![Historial de actividades](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Puede buscar o examinar el historial de actividades para las diferentes aplicaciones y servicios de Microsoft que usa, incluidos Microsoft Flow. Seleccione **eliminar** para quitar eventos de actividad de producto o servicio específicos.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. En unos instantes, el elemento se elimina y se quita del panel de privacidad.

### <a name="list-and-delete-flows"></a>Lista y eliminación de flujos

Los usuarios pueden enumerar y eliminar sus flujos de [Microsoft Flow](https://flow.microsoft.com) siguientes estos pasos:

1. Inicie sesión en el [Microsoft Flow](https://flow.microsoft.com)y seleccione en **Mis flujos**.

1. Seleccione **...** junto al flujo que va a eliminar y, a continuación, seleccione **eliminar**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Eliminar conexiones

Los conectores usan conexiones para comunicarse con las API y los sistemas SaaS. Las conexiones incluyen referencias al usuario que las crea. El usuario puede eliminar estas referencias en cualquier momento siguientes estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com), seleccione el icono de engranaje y, a continuación, seleccione **conexiones**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Seleccione la conexión que desea eliminar, seleccione **...** y, a continuación, seleccione **eliminar**.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Seleccione el icono **eliminar** en el mensaje de confirmación.

    ![Eliminar evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Si otros flujos usan la conexión, está eliminando, recibirá una notificación de que se necesita una nueva conexión. En caso contrario, seleccione **eliminar** para continuar.
>
>

## <a name="learn-more"></a>Aprende más

* Introducción a [Microsoft Flow](getting-started.md)
* Conozca [las novedades de](release-notes.md) Microsoft Flow
