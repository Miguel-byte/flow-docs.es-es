---
title: Microsoft Flow solicitudes de eliminación de asunto de datos de RGPD | Microsoft Docs
description: Aprenda a usar Microsoft Flow para responder a solicitudes de eliminación de asunto de datos de RGPD.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548070"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Responder a solicitudes de eliminación de asunto de datos de RGPD para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La eliminación de los datos personales de los datos de los clientes de una organización es una protección de clave en RGPD. La eliminación de datos personales incluye la eliminación de todos los datos personales y los registros generados por el sistema, excepto la información del registro de auditoría.

Microsoft Flow permite a los usuarios crear flujos de trabajo de automatización que son una parte fundamental de las operaciones cotidianas de la organización. Cuando un usuario deja la organización, un administrador debe revisar manualmente y determinar si se deben eliminar determinados datos y recursos creados por el usuario. Hay otros datos personales que se eliminan automáticamente cada vez que se elimina la cuenta de usuario de Azure Active Directory.

En la tabla siguiente se muestran los datos personales que se eliminan automáticamente y los datos que necesita un administrador para revisarlos y eliminarlos manualmente:

|Requiere revisión y eliminación manual|Se eliminan automáticamente cuando se elimina el usuario de Azure Active Directory|
|------|------|
|Entorno|Registros generados por el sistema|
|Permisos de entorno * *|Historial de ejecución|
|Fluyen|Fuente de actividades|
|Permisos de Flow|Puerta |
|Detalles del usuario|Permisos de puerta de enlace|
|Conexiones||
|Permisos de conexión||
|Conector personalizado *||
|Permisos del conector personalizado||

\* Cada uno de estos recursos contiene registros "creado por" y "modificado por" que incluyen datos personales. Por motivos de seguridad, estos registros se conservan hasta que se elimina el recurso.

\* * Para entornos que incluyen una base de datos de Common Data Service, los permisos de entorno (por ejemplo, qué usuarios están asignados a los roles de administrador y creador de entorno) se almacenan como registros en la base de datos de Common Data Service. Consulte [ejecución de DSRs Against con Common Data Service datos de clientes](https://go.microsoft.com/fwlink/?linkid=872251)para obtener instrucciones sobre cómo responder a DSRs Against para los usuarios que usan el Common Data Service.

En el caso de los datos y recursos que requieren una revisión manual, Microsoft Flow ofrece las siguientes experiencias para buscar o cambiar los datos personales de un usuario específico:

* **Acceso al sitio web:** inicie sesión en el [centro de administración de PowerApps](https://admin.powerapps.com/)o en el centro de administración de [Microsoft Flow](https://admin.flow.microsoft.com/) .

* **Acceso a PowerShell:**  [cdmlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) 

Este es el desglose de las experiencias que están disponibles para que un administrador elimine todos los tipos de datos personales dentro de cada tipo de recurso:

|Recursos que contienen datos personales|Acceso al sitio web|Acceso a PowerShell|Eliminación automatizada|
|-----|----|----|----|
|Registros generados por el sistema|[Portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/)|||
|Entorno|Centro de administración de Microsoft Flow|Cmdlets de PowerApps||
|Permisos de entorno *|Centro de administración de Microsoft Flow|Cmdlets de PowerApps||
|Historial de ejecución||| Eliminado a través de la Directiva de retención de 28 días|
|Fuente de actividades |||Eliminado a través de la Directiva de retención de 28 días|
|Trabajos de usuario|| ||
|Fluyen|Portal de Microsoft Flow Maker * *|||
|Permisos de Flow|Portal de Microsoft Flow Maker|||
|Detalles del usuario||Cmdlets de PowerApps||
|Conexiones|Portal de Microsoft Flow Maker| ||
|Permisos de conexión|Portal de Microsoft Flow Maker| ||
|Conector personalizado|Portal de Microsoft Flow Maker| ||
|Permisos del conector personalizado|Portal de Microsoft Flow Maker| ||
|Historial de aprobación|Portal de Microsoft PowerApps Maker *|||

\* Con la introducción del Common Data Service, si se crea una base de datos dentro del entorno, los permisos de entorno y los permisos de aplicación controlados por modelos se almacenan como registros dentro de la instancia de base de datos de Common Data Service. Consulte [ejecución de DSRs Against con Common Data Service datos de clientes](https://go.microsoft.com/fwlink/?linkid=872251)para obtener instrucciones sobre cómo responder a DSRs Against para los usuarios que usan el Common Data Service.

\*\* un administrador solo podrá tener acceso a estos recursos desde el portal de Microsoft Flow Maker si al administrador se le ha asignado acceso desde el centro de administración de Microsoft Flow.

## <a name="manage-delete-requests"></a>Administrar solicitudes de eliminación

En los pasos siguientes se describe cómo existen las funciones administrativas para atender las solicitudes de eliminación de RGPD. Estos pasos deben realizarse en el orden que se indica a continuación.

> [!IMPORTANT]
> Para evitar daños en los datos, siga estos pasos en orden.
>
>

## <a name="list-and-re-assign-flows"></a>Enumerar y volver a asignar flujos

En estos pasos se copian los flujos existentes para un usuario que no está en la parte. Si asigna una nueva propiedad a las copias, estos flujos pueden seguir siendo compatibles con los procesos empresariales existentes. La copia de estos flujos es importante para eliminar las vinculaciones de identificadores personales al usuario que se va a quitar y se deben establecer nuevas conexiones para que el flujo se conecte con otras API y aplicaciones SaaS.

1. Inicie sesión en el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/)y, a continuación, seleccione el entorno que contiene los flujos que posee el usuario eliminado.

    ![Ver entornos](./media/gdpr-dsr-delete/view-environments.png)

1. Seleccione **recursos**, > **flujos**y, a continuación, seleccione el título para el flujo que desea reasignar.

    ![Ver flujos](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Seleccione **administrar uso compartido**.

    ![Administrar el uso compartido](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. En el panel de **recursos compartidos** que aparece cerca del borde derecho, agréguelo como propietario y, a continuación, seleccione **Guardar**.

    ![Compartir flujo](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione **Mis flujos**y, a continuación, seleccione **flujos de equipo**.

1. Seleccione los puntos suspensivos **(...)** para el flujo que desea copiar y, a continuación, seleccione **Guardar como**.

    ![Guardar como flujo](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configure las conexiones según sea necesario y, después, seleccione **continuar**.

1. Proporcione un nuevo nombre y, a continuación, seleccione **Guardar**.

    ![Creación de una copia de Flow](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Esta nueva versión del flujo aparece en **Mis flujos**, donde puede compartirla con otros usuarios si lo desea.

    ![Flujos de equipo](./media/gdpr-dsr-delete/team-flows.png)

1. Elimine el flujo original seleccionando los puntos suspensivos **(...)** , seleccione **eliminar**y, a continuación, seleccione **eliminar** de nuevo cuando se le solicite. En este paso también se quitarán los identificadores personales subyacentes que se incluyen en las dependencias del sistema entre el usuario y el Microsoft Flow.

    ![Confirmación de eliminación de flujo](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Habilite la copia del flujo; para ello, Abra **Mis flujos** y, a continuación, active el **control de alternancia.**

    ![Habilitar flujo](./media/gdpr-dsr-delete/toggle-on.png)

1. La copia ahora realiza la misma lógica de flujo de trabajo que la versión original.

## <a name="delete-approval-history-from-microsoft-flow"></a>Eliminar el historial de aprobación de Microsoft Flow

 Los datos de aprobación de Microsoft Flow se almacenan en la versión actual o anterior de Common Data Service. Dentro de una aprobación, existe información personal en forma de asignaciones de aprobación y comentarios incluidos en una respuesta de aprobación. Los administradores pueden tener acceso a los datos siguiendo estos pasos:

1. Inicie sesión en [PowerApps](https://web.powerapps.com/).

1. Seleccione **datos**y, a continuación, seleccione **entidades**.

1. Seleccione los puntos suspensivos **(...)** de la entidad de **aprobación de flujo** y, a continuación, abra los datos en Microsoft Excel.

1. En Microsoft Excel, busque, filtre y elimine los datos de aprobación según sea necesario.

Consulte [ejecución de DSRs Against con Common Data Service datos de clientes](https://go.microsoft.com/fwlink/?linkid=872251)para obtener instrucciones adicionales sobre cómo responder a DSRs Against para los usuarios que usan el Common Data Service.


## <a name="delete-connections-created-by-a-user"></a>Eliminar conexiones creadas por un usuario

Las conexiones se utilizan junto con los conectores para establecer la conectividad con otras API y sistemas SaaS.  Las conexiones incluyen referencias al usuario que las creó y, como resultado, se pueden eliminar para quitar todas las referencias al usuario.

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas sus conexiones mediante la función remove-Connection de los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Eliminación de los permisos del usuario para conexiones compartidas

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas sus asignaciones de roles de conexión para las conexiones compartidas de la función remove-ConnectionRoleAssignment en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Cmdlets de PowerShell para administradores de PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Las asignaciones de roles de propietario no se pueden eliminar sin eliminar el recurso de conexión.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Eliminar conectores personalizados creados por el usuario

Los conectores personalizados complementan los conectores preestablecidos existentes y permiten la conectividad con otras API, SaaS y sistemas desarrollados de personalización. Los conectores personalizados incluyen referencias al usuario que los creó y, como resultado, se pueden eliminar para quitar todas las referencias al usuario.

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todos sus conectores personalizados la función remove-Connector en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Cmdlets de PowerShell para administradores de PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Eliminación de los permisos del usuario para los conectores personalizados compartidos

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas las asignaciones de roles de conector para el conector personalizado compartido con la función remove-ConnectorRoleAssignment en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Cmdlets de PowerShell para administradores de PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Las asignaciones de roles de propietario no se pueden eliminar sin eliminar el recurso de conexión.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Eliminar o volver a asignar todos los entornos creados por el usuario

Como administrador, tiene dos decisiones que debe tomar al procesar una solicitud de eliminación de DSR para un usuario para cada uno de los entornos creados por el usuario:

1. Si determina que el entorno no está siendo utilizado por ningún otro usuario de la organización, puede eliminar el entorno.
1. Si determina que el entorno sigue siendo necesario, puede optar por no eliminar el entorno y agregarse a sí mismo (u otro usuario de su organización) como administrador de entorno.
> [!IMPORTANT]
> Al eliminar un entorno se eliminarán permanentemente todos los recursos del entorno, incluidas todas las aplicaciones, flujos, conexiones, etc., por lo que debe revisar el contenido de un entorno antes de la eliminación.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Conceder acceso a los entornos de un usuario desde el centro de administración de Microsoft Flow

Un administrador puede conceder acceso de administrador a un entorno creado por un usuario específico desde el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/). Para obtener más información sobre la administración de entornos, vaya a [uso de entornos dentro de Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Eliminación de los permisos del usuario en todos los demás entornos

A los usuarios se les pueden asignar permisos (como administrador de entorno, creador de entorno, etc.) en un entorno, que se almacena en el servicio de Microsoft Flow como una "asignación de roles".

Con la introducción del Common Data Service, si se crea una base de datos dentro del entorno, estas "asignaciones de roles" se almacenan como registros dentro de la instancia de base de datos de Common Data Service.

Para obtener más información sobre cómo quitar el permiso de un usuario en un entorno, vaya a [uso de entornos dentro de Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Eliminar configuración de puerta de enlace

La respuesta a las solicitudes de eliminación de asunto de datos para las puertas de enlace de datos locales se puede encontrar [aquí](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Eliminar detalles de usuario

Los detalles de usuario proporcionan una vinculación entre un usuario y un inquilino específico. Antes de ejecutar este comando, asegúrese de que todos los flujos para este usuario se han vuelto a asignar o eliminar. Una vez que se ha completado, un administrador puede eliminar los detalles del usuario mediante una llamada al cmdlet **Remove-AdminFlowUserDetails** y pasando el identificador de objeto del usuario.

Cmdlets de PowerShell para administradores de PowerApps
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Si un usuario todavía posee flujos individuales o de equipo, este comando devolverá un error. Para resolverlo, elimine todos los flujos restantes o flujos de equipo para este usuario y vuelva a ejecutar el comando.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Eliminar el usuario de Azure Active Directory

Una vez que se hayan completado los pasos anteriores, el paso final consiste en eliminar la cuenta de usuario para Azure Active Directory siguiendo los pasos descritos en la documentación de RGPD de solicitud de asunto de datos de Azure, que se puede encontrar en el [portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Eliminar el usuario del inquilino no administrado

En el caso de que sea miembro de un inquilino no administrado, debe realizar una acción de **cierre de cuenta** desde el [portal de privacidad profesional y educativa](https://go.microsoft.com/fwlink/?linkid=873123).

Para determinar si es o no un usuario de un inquilino administrado o no administrado, realice las siguientes acciones:

1. Abra la siguiente dirección URL en un explorador y asegúrese de reemplazar su dirección de correo electrónico en la dirección URL:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Si es miembro de un **inquilino no administrado** , verá un `"IsViral": true` en la respuesta.

    {

     "Inicio de sesión": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. De lo contrario, pertenece a un inquilino administrado.
