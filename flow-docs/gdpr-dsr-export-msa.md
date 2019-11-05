---
title: Microsoft Flow solicitudes de exportación de asunto de datos de RGPD para las cuentas de Microsoft (MSA) | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a las solicitudes de exportación de los sujetos de datos de RGPD para las cuentas de Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548150"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Responder a solicitudes de exportación de asunto de datos de RGPD para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Como parte de nuestro compromiso de colaborar con usted en su viaje al Reglamento general de protección de datos (RGPD), hemos desarrollado documentación para ayudarle a prepararse. En la documentación no solo se describe lo que estamos haciendo para prepararse para el RGPD, sino también ejemplos de pasos que puede seguir hoy en día con Microsoft para admitir el cumplimiento de RGPD cuando se usa Microsoft Flow.

## <a name="manage-export-requests"></a>Administrar solicitudes de exportación

El *derecho de portabilidad de datos* permite a los interesados solicitar una copia de sus datos personales en formato electrónico (es decir, un "formato estructurado, de uso frecuente, legible por máquina e interoperable") que se puede transmitir a otro controlador de datos.

Use el [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy/)o [Microsoft Flow](https://flow.microsoft.com/) para buscar o exportar datos personales para un usuario específico.

|Datos personales|Cód|
|-----------------|-------------------|
|Actividad de productos y servicios|Panel de privacidad de Microsoft|
|Fluyen|Portal de Microsoft Flow Maker|
|Historial de ejecución|Portal de Microsoft Flow Maker|
|Fuente de actividades|Portal de Microsoft Flow Maker|
|Conexiones|Portal de Microsoft Flow Maker|

## <a name="export-product-and-service-activity"></a>Exportar la actividad de productos y servicios

1. Inicie sesión en el [Panel de privacidad de Microsoft](https://account.microsoft.com/privacy/) con su cuenta de Microsoft (MSA).
1. Seleccione **historial de actividades**.

    ![historial de actividades](./media/gdpr-dsr-export-msa/activityhistory.png) puede examinar el historial de actividades de las distintas aplicaciones y servicios de Microsoft que usa.
1. Para exportar los datos de **actividad de productos y servicios** , seleccione **descargar los datos**y, a continuación, seleccione **crear nuevo archivo**.

    ![Descargar los datos](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Seleccione **App & el uso del servicio**y, después, seleccione **crear archivo**.

    ![Descargar los datos](./media/gdpr-dsr-export-msa/create-archive.png)
1. Se crea un nuevo archivo. Seleccione **download (descargar** ) para obtener los datos exportados de la actividad de los productos y servicios.

    ![Descargar](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exportar un flujo

Un usuario final que tiene acceso a un flujo puede exportar el flujo siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).

1. Seleccione **Mis flujos**y, después, seleccione el flujo que se va a exportar.

1. Seleccione **... Más**y, a continuación, seleccione **exportar**.

    ![Flujo de exportación](./media/gdpr-dsr-export/export-flow.png)

1. Seleccione **paquete (. zip)** .

El flujo estará ahora disponible como paquete comprimido. Para obtener más información, consulte la entrada de blog sobre [Cómo exportar e importar un flujo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar historial de ejecución

El historial de ejecución incluye una lista de todas las ejecuciones de un flujo. Estos datos incluyen el estado del flujo, la hora de inicio, la duración y los datos de entrada y salida para los desencadenadores y las acciones.

Un usuario final que tenga acceso al flujo puede seguir estos pasos para exportar estos datos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).
1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo para el que desea exportar el historial de ejecuciones.
1. En el panel **historial de ejecución** , seleccione **ver todo**.

    ![Historial de ejecución](./media/gdpr-dsr-export/run-history.png)

1. Seleccione **Descargar CSV**.

    ![Descargar CSV](./media/gdpr-dsr-export/download-csv.png)

El historial de ejecución se descarga como un archivo. csv para que pueda abrirlo en Microsoft Excel o en un editor de texto para analizar los resultados.

## <a name="export-a-users-activity-feed"></a>Exportar la fuente de actividades de un usuario

En [Microsoft Flow](https://flow.microsoft.com/), la fuente de actividades muestra el historial de las actividades, los errores y las notificaciones de un usuario. Los usuarios pueden ver su fuente de actividades siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione el icono de campana cerca de la esquina superior derecha y, a continuación, seleccione **Mostrar todas las actividades**.

    ![Mostrar fuente de actividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. En la pantalla **actividad** , copie los resultados y, a continuación, péguelos en un editor de texto como Microsoft Word.

    ![Mostrar fuente de actividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar las conexiones de un usuario

Las conexiones permiten a los flujos conectarse a las API, las aplicaciones SaaS y otros sistemas de terceros. Siga estos pasos para ver las conexiones:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione el icono de engranaje cerca de la esquina superior derecha y, a continuación, seleccione **conexiones**.

    ![Mostrar conexiones](./media/gdpr-dsr-export/show-connections.png)
1. Copie los resultados y, a continuación, péguelos en un editor de texto como Microsoft Word.
