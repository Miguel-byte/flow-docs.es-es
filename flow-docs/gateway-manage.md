---
title: Administración de puertas de enlace de datos locales | Microsoft Docs
description: Ver e instalar una puerta de enlace de datos local en Microsoft Flow
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
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 180ff4b54fdf395c8524fd1ff132e9adedf1c848
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690385"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Administración de un puerta de enlace de datos local en Microsoft Flow

Instale y administre una puerta de enlace de datos local para integrar de forma segura varias aplicaciones que están en la nube con sus datos y aplicaciones locales a través de Microsoft Flow.

Con una puerta de enlace, puede conectarse a datos locales a través de estas conexiones:

* SharePoint
* SQL Server
* Oracle
* Informix
* Sistema de archivos
* DB2

> [!IMPORTANT]
> Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP y HTTPS.


## <a name="prerequisites"></a>Requisitos previos

* El nombre de usuario y la contraseña que se usaron para [registrarse](sign-up-sign-in.md) en Microsoft Flow.
* Permisos administrativos en una puerta de enlace.

  Tiene estos permisos de manera predeterminada para cada puerta de enlace que instale. Además, un administrador de otra puerta de enlace puede conceder estos permisos para esa puerta de enlace.
* Una licencia que admita puertas de enlace Para más información, consulte la sección "Conectividad" de la [página de precios](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Las puertas de enlace y las conexiones locales solo puede crearlas en su [entorno predeterminado](environments-overview-maker.md).



## <a name="view-your-gateways"></a>Visualización de las puertas de enlace

En la esquina superior derecha del [sitio web de Microsoft Flow](https://flow.microsoft.com), seleccione el icono del engranaje y, después, seleccione **Puertas de enlace**.

![Puerta de enlace bajo administración][1]

> [!NOTE]
> Si ha creado o se le ha concedido acceso a una puerta de enlace en PowerApps, aparecerá en la lista **Mis puertas de enlace** de Microsoft Flow.



## <a name="install-a-gateway"></a>Instalación de una puerta de enlace

1. Descargue el [Asistente para instalación de puerta de enlace](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Ejecute el asistente y especifique las mismas credenciales con las que ha iniciado sesión en Microsoft Flow.

    Después de registrar y configurar la puerta de enlace correctamente, se muestra en la lista **Puertas de enlace** de Microsoft Flow.

Para más información, consulte [Información acerca de las puertas de enlace de datos locales de Microsoft Flow](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
