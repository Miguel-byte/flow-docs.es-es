---
title: Microsoft Flow solicitudes de exportación de asunto de datos RGPD | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a solicitudes de exportación de asunto de datos RGPD.
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548197"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Responder a solicitudes de exportación de asunto de datos de RGPD para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Como parte de nuestro compromiso de colaborar con usted en su viaje al Reglamento general de protección de datos (RGPD), hemos desarrollado documentación para ayudarle a prepararse. En la documentación no solo se describe lo que estamos haciendo para prepararse para el RGPD, sino también ejemplos de pasos que puede seguir hoy en día con Microsoft para admitir el cumplimiento de RGPD cuando se usa Microsoft Flow.

## <a name="manage-export-requests"></a>Administrar solicitudes de exportación

El *derecho de portabilidad de datos* permite a los datos solicitar una copia de sus datos personales en formato electrónico (es decir, un "formato estructurado, de uso frecuente, legible por máquina e interoperable") que se puede transmitir a otro controlador de datos.

Microsoft Flow ofrece las siguientes experiencias para buscar o exportar datos personales para un usuario específico:

* **Acceso al sitio web:** inicie sesión en el [centro de administración de PowerApps](https://admin.powerapps.com/)o en el centro de administración de [Microsoft Flow](https://admin.flow.microsoft.com/).

* **Acceso a PowerShell:**  [cdmlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Datos del cliente**|**Acceso al sitio web**|**Acceso a PowerShell**|
|-----------------|------------------|-------------------|
|Registros generados por el sistema|[Portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/)|
|Historial de ejecución|Portal de Microsoft Flow Maker||
|Fluyen|Portal de Microsoft Flow Maker||
|Permisos de Flow| Portal de Microsoft Flow Maker y centro de administración de Microsoft Flow||
|Detalles del usuario||Cmdlets de PowerApps|
|Conexiones|Portal de Microsoft Flow Maker|Cmdlets de PowerApps |
|Permisos de conexión|Portal de Microsoft Flow Maker|Cmdlets de PowerApps |
|Conectores personalizados|Portal de Microsoft Flow Maker|Cmdlets de PowerApps |
|Permisos del conector personalizado|Portal de Microsoft Flow Maker|Cmdlets de PowerApps |
|Puerta|Portal de Microsoft Flow Maker|Cmdlets de PowerShell de puerta de enlace de datos local|
|Permisos de puerta de enlace|Portal de Microsoft Flow Maker|Cmdlets de PowerShell de puerta de enlace de datos local|

## <a name="export-a-flow"></a>Exportar un flujo

Un usuario final o un administrador que haya concedido acceso al flujo puede exportar el flujo siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).

1. Seleccione el vínculo **Mis flujos** y, después, seleccione el flujo que se va a exportar.

1. Seleccione **... Más**y, a continuación, seleccione **exportar**.

    ![Flujo de exportación](./media/gdpr-dsr-export/export-flow.png)

1. Seleccione **paquete (. zip)** .

El flujo estará ahora disponible como paquete comprimido. Para obtener más información, consulte la entrada de blog sobre [Cómo exportar e importar un flujo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar historial de ejecución

El historial de ejecución incluye una lista de todas las ejecuciones que se han producido para un flujo. Estos datos incluyen el estado del flujo, la hora de inicio, la duración y los datos de entrada y salida para los desencadenadores y las acciones.

Ya sea un usuario final o un administrador al que se haya concedido acceso al flujo a través del centro de administración de Microsoft Flow, puede seguir estos pasos para exportar estos datos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/).
1. Seleccione el vínculo **Mis flujos** y, a continuación, seleccione el flujo para el que desea exportar el historial de ejecuciones.
1. En el panel **historial de ejecución** , seleccione **ver todo**.

    ![Historial de ejecución](./media/gdpr-dsr-export/run-history.png)

1. Seleccione **Descargar CSV**.

    ![Descargar CSV](./media/gdpr-dsr-export/download-csv.png)

El historial de ejecución se descarga como un archivo. csv para que pueda abrirlo en Microsoft Excel o en un editor de texto y analizar aún más los resultados.

## <a name="export-a-users-activity-feed"></a>Exportar la fuente de actividades de un usuario

En [Microsoft Flow](https://flow.microsoft.com/), la fuente de actividades muestra el historial de las actividades, los errores y las notificaciones de un usuario. Cualquier usuario puede ver su fuente de actividades siguiendo estos pasos:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione el icono de campana cerca de la esquina superior derecha y, a continuación, seleccione **Mostrar todas las actividades**.

    ![Mostrar fuente de actividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. En la pantalla **actividad** , copie los resultados y, a continuación, péguelos en un editor de documentos como Microsoft Word.

    ![Mostrar fuente de actividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar las conexiones de un usuario

Las conexiones permiten a los flujos conectarse a las API, las aplicaciones SaaS y otros sistemas de terceros. Siga estos pasos para ver las conexiones:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione el icono de engranaje cerca de la esquina superior derecha y, a continuación, seleccione **conexiones**.

    ![Mostrar conexiones](./media/gdpr-dsr-export/show-connections.png)
1. Copie los resultados y, a continuación, péguelos en un editor de documentos como Microsoft Word.

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportar una lista de los permisos de conexión de un usuario

Un usuario puede exportar las asignaciones de roles de conexión para todas las conexiones a las que tienen acceso a través de la función get-ConnectionRoleAssignment en el [cdmlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exportar los conectores personalizados de un usuario

Los conectores personalizados complementan los conectores integrados y permiten la conectividad con otras API, SaaS y sistemas desarrollados de personalización. Puede transferir la propiedad de un conector personalizado o eliminarlo.

Siga estos pasos para exportar una lista de conectores de clientes:

1. Vaya a [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione el icono de **engranaje** configuración.
1. Seleccione **conectores personalizados**.
1. Copie y pegue la lista de conectores personalizados en un editor de texto como Microsoft Word.

    ![Exportación de conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Además de la experiencia proporcionada en Microsoft Flow, puede usar la función get-Connector de los [cmdlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos los conectores personalizados.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exportar los permisos del conector personalizado de un usuario

Un usuario puede exportar todos los permisos de conector personalizados que ha creado a través de la función get-ConnectorRoleAssignment en el [cdmlets de PowerShell de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exportar historial de aprobación

Microsoft Flow historial de aprobaciones captura un registro histórico de las aprobaciones que se han recibido o enviado para un usuario. Cualquier usuario puede ver su historial de aprobación:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione **aprobaciones**y, a continuación, seleccione **historial**.

    ![Ver el historial de aprobación](./media/gdpr-dsr-export/view-approval-history.png)

1. Una lista muestra las aprobaciones recibidas por el usuario. Los usuarios pueden mostrar las aprobaciones que enviaron seleccionando la flecha abajo situada junto a **recibido** y, después, seleccionando **enviado**.

    ![Ver aprobaciones recibidas](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exportar detalles de usuario
Los detalles de usuario proporcionan una vinculación entre un usuario y un inquilino específico. Un administrador puede exportar esta información llamando al cmdlet **Get-AdminFlowUserDetails** y pasando el identificador de objeto del usuario.

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exportar configuración de puerta de enlace
La respuesta a las solicitudes de exportación de sujeto de datos para puertas de enlace de datos locales se puede encontrar [aquí](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

