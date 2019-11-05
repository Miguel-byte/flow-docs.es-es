---
title: Más información sobre la administración de puertas de enlace de datos locales | Microsoft Docs
description: Vea e instale una puerta de enlace de datos local en Microsoft Flow.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547664"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Administración de una puerta de enlace de datos local en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Instale y administre una puerta de enlace de datos local para integrar de forma segura una variedad de aplicaciones basadas en la nube con sus datos y aplicaciones locales a través de Microsoft Flow.

Con una puerta de enlace, puede conectarse a datos locales a través de estas conexiones:

* Apache Impala
* Conectores personalizados que cree
* DB2
* Sistema de archivos
* Http con Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (vista previa)

> [!IMPORTANT]
> Las puertas de enlace de datos de Microsoft SharePoint ahora admiten el tráfico HTTP y HTTPS.

## <a name="prerequisites"></a>Requisitos previos

* El nombre de usuario y la contraseña que usó para [suscribirse](sign-up-sign-in.md) a Microsoft Flow.
* Permisos administrativos en una puerta de enlace.

  Tiene estos permisos de forma predeterminada para cada puerta de enlace que instale. Además, un administrador de otra puerta de enlace puede concederle estos permisos para esa puerta de enlace.
* Una licencia que admite puertas de enlace. Para obtener más información, consulte la sección "conectividad" de la [Página de precios](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Puede crear una puerta de enlace y una conexión local solo en el [entorno predeterminado](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalación de una puerta de enlace

Para instalar una puerta de enlace, siga los pasos descritos en [instalación de una puerta de enlace de datos local](/data-integration/gateway/service-gateway-install). Instale la puerta de enlace en modo estándar porque la _puerta de enlace de datos local (modo personal)_ solo está disponible para Power BI.

## <a name="view-your-gateways"></a>Visualización de las puertas de enlace

En la esquina superior derecha del [sitio web de Microsoft Flow](https://flow.microsoft.com), seleccione el icono de engranaje y, a continuación, seleccione **puertas de enlace**.

![Puerta de enlace bajo administración][1]

> [!NOTE]
> Si ha creado o se le ha concedido acceso a una puerta de enlace en PowerApps, esa puerta de enlace aparece en la lista **mis puertas de enlace** de Microsoft Flow.

## <a name="cluster-your-gateways"></a>Agrupar las puertas de enlace

Puede crear [clústeres de alta disponibilidad de instalaciones de puerta de enlace de datos locales](/data-integration/gateway/service-gateway-high-availability-clusters) para evitar los puntos únicos de error en el acceso a los recursos de datos locales.

De forma predeterminada, Microsoft Flow usa la puerta de enlace principal del clúster. Si la puerta de enlace principal no está disponible, el servicio cambia a la siguiente puerta de enlace del clúster, y así sucesivamente.

Una vez que haya configurado un clúster de puerta de enlace, puede permitir que el tráfico se distribuya en todas las puertas de enlace del clúster.

Siga estos pasos para distribuir el tráfico a través de las puertas de enlace:

1. Seleccione **datos** en la barra de navegación del lado izquierdo.
1. Seleccione **puertas de enlace**.
1. Seleccione cualquiera de las puertas de enlace.
1. Seleccione **distribuir solicitudes en todas las puertas de enlace activas de este clúster**.
1. Seleccione **aplicar** para guardar los cambios.

Para obtener más información, consulte Descripción de las [puertas de enlace](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
