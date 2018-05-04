---
title: Solicitudes de eliminación del titular de los datos de acuerdo con el RGPD en Microsoft Flow | Microsoft Docs
description: Obtenga información acerca de cómo usar Microsoft Flow para responder a solicitudes de eliminación del titular de los datos de acuerdo con el RGPD.
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
ms.openlocfilehash: d750ee2bc672d08bff940341349663b4721f9a57
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Respuesta a solicitudes de eliminación del titular de los datos de acuerdo con el RGPD para Microsoft Flow

El "derecho a borrado" mediante la eliminación de los datos personales de los datos de cliente de una organización es una de las principales protecciones contempladas en el RGPD. La eliminación de los datos personales incluye la eliminación de todos los datos personales y los registros generados por el sistema, excepto la información del registro de auditoría.

Microsoft Flow permite a los usuarios crear flujos de trabajo de automatización que formen parte de las operaciones cotidianas de su organización. Cuando un usuario abandone la organización, un administrador tendrá que revisar y determinar manualmente si se debe o no eliminar ciertos datos y recursos creados por el usuario. Hay otros datos personales que se eliminan automáticamente en el momento en que se elimina una cuenta de usuario de Azure Active Directory.

En la siguiente tabla se muestra cuáles datos personales se eliminan automáticamente y cuáles datos requieren que un administrador los revise y elimine manualmente:

|Requiere revisión y eliminación manual|Se elimina automáticamente cuando se elimina el usuario de Azure Active Directory|
|------|------|
|Entorno*|Registros generados por el sistema|
|Permisos del entorno**|Historial de ejecución|
|Flujos|Trabajos de usuario|
|Permisos de flujo|Puerta de enlace |
|Detalles del usuario|Permisos de puerta de enlace |
|Conexiones*||
|Permisos de conexión||
|Conector personalizado*||
|Permisos de conector personalizado||

* Cada uno de estos recursos contiene registros "Creado por" y "Modificado por" que incluyen datos personales. Por motivos de seguridad, estos registros se conservan hasta que se elimina el recurso.

* En el caso de entornos que incluyen una base de datos de Common Data Service for Apps, los permisos de entorno (por ejemplo, qué usuarios están asignados a los roles Creador de entorno y Administrador) se almacenan como registros de la base de datos de Common Data Service. Vea [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Ejecución de derechos de titulares de datos en datos de clientes de Common Data Service) para obtener instrucciones sobre cómo responder a DSR para los usuarios que usan Common Data Service.

En el caso de los datos y recursos que requieren una revisión manual, Microsoft Flow ofrece las experiencias siguientes para buscar o cambiar los datos personales de un usuario específico:

* **Acceso a sitio web:** inicie sesión en el [centro de administración de PowerApps](https://admin.powerapps.com/) o el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/).

* **Acceso a PowerShell:** [cdmlets de PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). 

Este es el desglose de las experiencias que están disponibles para que un administrador elimine cada tipo de datos personales dentro de cada tipo de recurso:

|Recursos que contienen datos personales|Acceso al sitio web|Acceso a PowerShell|Eliminación automatizada|
|-----|----|----|----|
|Registros generados por el sistema|[Portal de confianza de servicios de Office 365](https://servicetrust.microsoft.com/)|||
|Entorno|Centro de administración de Microsoft Flow|Cmdlets de PowerApps||
|Permisos del entorno*|Centro de administración de Microsoft Flow|Cmdlets de PowerApps||
|Historial de ejecución||| Eliminación a través de la directiva de retención de 28 días|
|Fuente de actividades ||Cmdlets de PowerApps||
|Trabajos de usuario|| ||
|Flujos|Portal de creador de Microsoft Flow**|||
|Permisos de flujo|Portal de creador de Microsoft Flow|||
|Detalles del usuario|| ||
|Conexiones|Portal de creador de Microsoft Flow| ||
|Permisos de conexión|Portal de creador de Microsoft Flow| ||
|Conector personalizado|Portal de creador de Microsoft Flow| ||
|Permisos de conector personalizado|Portal de creador de Microsoft Flow| ||
|Historial de aprobación|Portal de creador de Microsoft PowerApps *|||

*Con la introducción de Common Data Service for Apps, si se crea una base de datos dentro del entorno, los permisos del entorno y los permisos de aplicaciones controlados por modelo se almacenan como registros dentro de la instancia de la base de datos de Common Data Service for Apps. Vea [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Ejecución de derechos de titulares de datos en datos de clientes de Common Data Service) para obtener instrucciones sobre cómo responder a DSR para los usuarios que usan Common Data Service.

**Un administrador solo podrá obtener acceso a estos recursos desde el portal de creador de Microsoft Flow si el administrador le asignado acceso desde el centro de administración de Microsoft Flow.

## <a name="manage-delete-requests"></a>Administración de las solicitudes de eliminación

En los pasos siguientes se describen las funciones administrativas que existen para atender las solicitudes de eliminación de acuerdo con el RGPD.

> [!IMPORTANT]
> Para evitar daños en los datos, siga estos pasos en orden.
>
>

## <a name="list-and-re-assign-flows"></a>Enumeración y reasignación de flujos

Estos pasos copian flujos existentes para un usuario saliente. Si asigna una propiedad nueva a las copias, estos flujos pueden continuar admitiendo los procesos empresariales existentes. La copia de estos flujos es importante para eliminar vínculos de identificación personal para el usuario saliente, y se deben establecer nuevas conexiones para que el flujo se conecte con otras API y sistemas SaaS.

1. Inicie sesión en el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/) y, a continuación, seleccione el entorno que contiene los flujos que posee el usuario eliminado.

    ![Vista de entornos](./media/gdpr-dsr-delete/view-environments.png)

1. Seleccione **Recursos** > **Flujos** y, a continuación, seleccione el título del flujo que desea reasignar.

    ![Vista de flujos](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Seleccione **Administrar uso compartido**.

    ![Administrar uso compartido](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. En el panel **Recurso compartido** que aparece cerca del borde derecho, agréguese como propietario y, a continuación, seleccione **Guardar**.

    ![Flujo del recurso compartido](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/), seleccione **Mis flujos** y, después, seleccione **Flujos del equipo**.

1. Seleccione los puntos suspensivos **(...)** del flujo que desea copiar y, a continuación, seleccione **Guardar como**.

    ![Flujo guardar como](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configure las conexiones según sea necesario y, a continuación, seleccione **Continuar**.

1. Proporcione un nombre nuevo y, a continuación, seleccione **Guardar**.

    ![Creación de copia del flujo](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Esta nueva versión del flujo de aparece en **Mis flujos**, donde puede compartirla con otros usuarios si lo desea.

    ![Flujos del equipo](./media/gdpr-dsr-delete/team-flows.png)

1. Elimine el flujo original seleccionando sus puntos suspensivos **(...)** , luego **Eliminar** y, cuando se le solicite, otra vez **Eliminar**. Con este paso también se quitarán los identificadores personales subyacentes que se incluyen en las dependencias del sistema entre el usuario y Microsoft Flow.

    ![Confirmación de la eliminación del flujo](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Habilite la copia del flujo; para ello, abra **Mis flujos** y, a continuación, ponga el control de alternancia en **Activado**.
    ![Habilitación de flujo](./media/gdpr-dsr-delete/toggle-on.png)

1. La copia ahora realiza la misma lógica de flujo de trabajo que la versión original.

## <a name="delete-approval-history-from-microsoft-flow"></a>Eliminación de historial de aprobación de Microsoft Flow

 Los datos de aprobación de Microsoft Flow se almacenan en la versión anterior o actual de Common Data Service for Apps. Dentro de una aprobación, existe información personal en forma de asignaciones de aprobación y comentarios incluidos en una respuesta de aprobación. Los administradores pueden tener acceso a esos datos siguiendo estos pasos:

1. Inicie sesión en [PowerApps](https://web.powerapps.com/).

1. Seleccione **Datos** y, a continuación, seleccione **Entidades**.

1. Seleccione los puntos suspensivos **(...)**  de la entidad **Flow Approval** (Aprobación de flujo) y, a continuación, abra los datos en Microsoft Excel.

1. En Microsoft Excel, busque, filtre y, a continuación, elimine los datos de aprobación según sea necesario.

Vea [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Ejecución de derechos de titulares de datos en datos de clientes de Common Data Service) para obtener más instrucciones sobre cómo responder a DSR para los usuarios que usan Common Data Service.

## <a name="delete-connections-created-by-a-user"></a>Eliminación de las conexiones creadas por un usuario

Las conexiones se utilizan junto con los conectores para establecer la conectividad con otras API y sistemas SaaS.  Las conexiones incluyen referencias al usuario que las creó y, como resultado, se pueden eliminar para quitar todas las referencias al usuario.

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas sus conexiones mediante la función Remove-Connection desde los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

Cmdlets de PowerShell de administración de PowerApps

No disponible.

## <a name="delete-the-users-permissions-to-shared-connections"></a>Eliminación de los permisos del usuario para conexiones compartidas

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas sus asignaciones de roles de conexión para la función Remove-ConnectionRoleAssignment de las conexiones compartidas en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

> [!NOTE]
> Las asignaciones de roles de propietario no se pueden eliminar sin eliminar el recurso de conexión.
>
>

Cmdlets de PowerShell de administración de PowerApps

No disponible.

## <a name="delete-custom-connectors-created-by-the-user"></a>Eliminación de conectores personalizados creados por el usuario

Los conectores personalizados complementan los conectores incluidos y permiten la conectividad con otras API y sistemas SaaS y de desarrollo personalizado. Los conectores personalizados incluyen referencias al usuario que las creó y, como resultado, se pueden eliminar para quitar todas las referencias al usuario.

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todos sus conectores personalizados mediante la función Remove-Connector en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Cmdlets de PowerShell de administración de PowerApps

No disponible.

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Eliminación de los permisos del usuario para conectores compartidos

Cmdlets de PowerShell de creador de PowerApps

Un usuario puede eliminar todas sus asignaciones de roles de conector para el conector personalizado compartido mediante la función Remove-ConnectorRoleAssignment en los [cmdlets de PowerShell de creador de PowerApps](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> Las asignaciones de roles de propietario no se pueden eliminar sin eliminar el recurso de conexión.
>
>

Cmdlets de PowerShell de administración de PowerApps

No disponible.

## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Eliminación o reasignación de todos los entornos creados por el usuario

Como administrador, tendrá que elegir entre dos opciones al procesar una solicitud de eliminación de derechos de titulares de datos para un usuario para cada uno de los entornos que ha creado el usuario:

1. Si determina que nadie más de su organización va a utilizar el entorno, puede optar por eliminarlo.
1. Si determina que el entorno sigue siendo necesario, puede optar por no eliminar el entorno y agregarse a usted mismo (u otro usuario de su organización) como administrador del entorno.
    > [!IMPORTANT]
    > La eliminación de un entorno eliminará permanentemente todos los recursos en el entorno, como aplicaciones, flujos, conexiones, etc., así que revise el contenido de un entorno antes de su eliminación.
    >
    >

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Concesión de acceso a los entornos de un usuario desde el centro de administración de Microsoft Flow

Un administrador puede conceder acceso de administrador a un entorno creado por un usuario específico desde el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/). Para obtener más información sobre la administración de entornos vaya a [Uso de entornos en Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Eliminación de los permisos del usuario para el resto de entornos

Es posible asignar permisos a los usuarios (como Administrador de entorno, Creador de entorno, etc.) en un entorno, que se almacenan en el servicio Microsoft Flow como "asignación de roles".

Con la introducción de Common Data Service for Apps, si se crea una base de datos dentro del entorno, estas "asignaciones de roles" se almacenan como registros dentro de la instancia de la base de datos de Common Data Service for Apps.

Para obtener más información acerca de cómo quitar el permiso de un usuario en un entorno, vaya a [Uso de entornos en Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).
