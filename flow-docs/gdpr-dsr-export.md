---
title: Solicitudes de exportación del titular de los datos de acuerdo con el RGPD en Microsoft Flow | Microsoft Docs
description: Obtenga información acerca de cómo usar Microsoft Flow para responder a solicitudes de exportación del titular de los datos de acuerdo con el RGPD.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 1e1fe346ba6ffb264985da0115714246a621ef5a
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Respuesta a solicitudes de exportación del titular de los datos de acuerdo con el RGPD para Microsoft Flow

Como parte de nuestro compromiso de acompañarle en su viaje de adaptación al Reglamento general de protección de datos (RGPD), hemos elaborado una documentación que le ayudará a prepararse. En esta documentación no solo se describe lo que estamos haciendo para prepararnos para el RGPD, sino que también se incluyen ejemplos de medidas que puede adoptar ya para cumplir con el RGPD al usar Microsoft Flow.

## <a name="manage-export-requests"></a>Administración de la exportación de solicitudes

El *derecho de portabilidad de datos* permite a un titular de dato solicitar una copia de sus datos personales en un formato electrónico (es decir, en un "formato estructurado, de uso frecuente, legible por máquinas e interoperable") que se pueda transmitir a otro controlador de datos.

Microsoft Flow ofrece las experiencias siguientes para buscar o exportar datos personales para un usuario específico:

* **Acceso a sitio web:** inicie sesión en el [centro de administración de PowerApps](https://admin.powerapps.com/) o el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/).

* **Acceso a PowerShell:** [cdmlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Datos de cliente**|**Acceso al sitio web**|**Acceso a PowerShell**|
|-----------------|------------------|-------------------|
|Registros generados por el sistema|[Portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/)|
|Historial de ejecución|Portal de creador de Microsoft Flow||
|Trabajos de usuario|| |
|Flujos|Portal de creador de Microsoft Flow||
|Permisos de flujo| Portal de creador de Microsoft Flow y centro de administración de Microsoft Flow||
|Detalles del usuario|| |
|Conexiones|Portal de creador de Microsoft Flow| |
|Permisos de conexión|Portal de creador de Microsoft Flow| |
|Conectores personalizados.|Portal de creador de Microsoft Flow| |
|Permisos de conector personalizado|Portal de creador de Microsoft Flow| |
|Puerta de enlace|Portal de creador de Microsoft Flow|Cmdlets de PowerShell de puerta de enlace local|
|Permisos de puerta de enlace|Portal de creador de Microsoft Flow|

## <a name="export-a-flow"></a>Exportación de un flujo

Un usuario final o un administrador al que se haya concedido acceso al flujo puede exportarlo siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).

1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo para exportar.

1. Seleccione **... Más** y, a continuación, seleccione **Exportar**.

    ![Exportación de flujo](./media/gdpr-dsr-export/export-flow.png)

1. Seleccione **Paquete (.zip)**.

El flujo estará ahora disponible como un paquete comprimido. Para obtener más información, consulte la entrada de blog sobre [cómo exportar e importar un flujo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportación de historial de ejecuciones

El historial de ejecuciones incluye una lista de todas las ejecuciones que se han producido para un flujo. Estos datos incluyen el estado del flujo, la hora de inicio, la duración y los datos de entrada/salida para los desencadenadores y las acciones.

Un usuario final o un administrador al que se haya concedido acceso al flujo a través del centro de administración de Microsoft Flow puede exportar los datos siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).
1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo cuyo historial de ejecución desea exportar.
1. En el panel **HISTORIAL DE EJECUCIÓN**, seleccione **Ver todo**.

    ![Historial de ejecución](./media/gdpr-dsr-export/run-history.png)

1. Seleccione **Descargar CSV**.

    ![Descargar CSV](./media/gdpr-dsr-export/download-csv.png)

El historial de ejecución se descarga como un archivo .csv para que pueda abrirlo en Microsoft Excel o un editor de texto y analizar los resultados en mayor profundidad.

## <a name="export-a-users-activity-feed"></a>Exportación de la fuente de actividad de un usuario

En [Microsoft Flow](https://flow.microsoft.com/), la fuente de actividad muestra el historial de actividades, errores y notificaciones de un usuario. Cualquier usuario puede ver su fuente de actividad siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](http://flow.microsoft.com/), seleccione el icono de campana cerca de la esquina superior derecha y, a continuación, seleccione **Mostrar todas las actividades**.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. En la pantalla **Actividad**, copie los resultados y, a continuación, péguelos en un editor de documentos, como Microsoft Word.

    ![Muestra de la fuente de actividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportación de las conexiones de un usuario

Las conexiones permiten a los flujos conectarse a las API, las aplicaciones de SaaS y otros sistemas de terceros. Siga estos pasos para ver las conexiones:

1. Inicie sesión en [Microsoft Flow](http://flow.microsoft.com/), seleccione el icono de engranaje cerca de la esquina superior derecha y, a continuación, seleccione **Conexiones**.

    ![Muestra de conexiones](./media/gdpr-dsr-export/show-connections.png)
1. Copie los resultados y, a continuación, péguelos en un editor de documentos, como Microsoft Word.

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportación de una lista de permisos de conexión de un usuario

Un usuario puede exportar las asignaciones de roles de conexión para todas las conexiones a las que tiene acceso a través de la función Get-ConnectionRoleAssignment en los [cdmlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).
![Exportación de permisos de conexión](./media/gdpr-dsr-export/export-connection-permissions.png)

## <a name="export-a-users-custom-connectors"></a>Exportación de los conectores personalizados de un usuario

Los conectores personalizados complementan los conectores incluidos y permiten la conectividad con otras API y sistemas SaaS y de desarrollo personalizado. Puede transferir la propiedad de un conector personalizado o eliminarlo.

Siga estos pasos para exportar una lista de conectores de cliente:

1. Vaya a [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione el icono de **engranaje** de la configuración.
1. Seleccione **Conectores personalizados**-
1. Copie y pegue la lista de conectores personalizados en un editor de texto, como Microsoft Word.

    ![Exportación de conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Además de la experiencia proporcionada en Microsoft Flow, puede usar la función Get-Connector de los [cmdlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos los conectores personalizados.

![Exportación de PowerShell de conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors-powershell.png)

## <a name="export-a-users-custom-connector-permissions"></a>Exportación de los permisos de conector personalizado de un usuario

Un usuario puede exportar todos los permisos de conector personalizado que haya creado a través de la función Get-ConnectorRoleAssignment en los [cdmlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

![Exportación de PowerShell de permisos de conector personalizado](./media/gdpr-dsr-export/export-connector-permissions.png)

## <a name="export-approval-history"></a>Exportación del historial de aprobaciones

El historial de aprobaciones de Microsoft Flow captura un registro histórico de las aprobaciones que se han recibido o enviado para un usuario. Cualquier usuario puede ver su historial de aprobación siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](http://flow.microsoft.com/), seleccione **Aprobaciones** y, a continuación, seleccione **Historial**.

    ![Visualización del historial de aprobaciones](./media/gdpr-dsr-export/view-approval-history.png)

1. Una lista muestra las aprobaciones que el usuario ha recibido. Los usuarios pueden mostrar las aprobaciones que enviaron seleccionando la flecha abajo junto a **Recibidas** y, a continuación, seleccionando **Enviadas**.

    ![Visualización de aprobaciones recibidas](./media/gdpr-dsr-export/view-received-approvals.png)
