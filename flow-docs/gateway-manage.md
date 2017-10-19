---
title: "Administración de puertas de enlace de datos locales | Microsoft Docs"
description: Ver e instalar una puerta de enlace de datos local en Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
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
> Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP, pero no tráfico HTTPS.
> 
> 

## <a name="prerequisites"></a>Requisitos previos
* El nombre de usuario y la contraseña que se usaron para [registrarse](sign-up-sign-in.md) en Microsoft Flow.
* Permisos administrativos en una puerta de enlace.
  
  De manera predeterminada, tiene estos permisos en todas las puertas de enlace que instale y un administrador de otra puerta de enlace puede concederle estos permisos para dicha puerta.
* Una licencia que admita puertas de enlace Para más información, consulte la sección "Conectividad" de la [página de precios](https://flow.microsoft.com/pricing/).
* Las puertas de enlace y las conexiones locales solo puede crearlas en su [entorno predeterminado](environments-overview-maker.md).

## <a name="view-your-gateways"></a>Visualización de las puertas de enlace
En la esquina superior derecha del [sitio web de Microsoft Flow](https://flow.microsoft.com), haga clic o pulse el icono del engranaje y, después, haga clic pulse **Puertas de enlace**.

![Puerta de enlace bajo administración][1]

**Nota**: Si ha creado o se le ha concedido acceso a una puerta de enlace en PowerApps, aparecerá en la lista **Mis puertas de enlace** de Microsoft Flow.

## <a name="install-a-gateway"></a>Instalación de una puerta de enlace
1. Descargue el [Asistente para instalación de puerta de enlace](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).
   
    Otra forma de descargar este asistente se puede hacer clic o pulsar el icono de engranaje de la esquina superior derecha del [sitio web de Microsoft Flow](https://flow.microsoft.com), hacer clic o pulsar **Puertas de enlace** y, después, hacer clic o pulsar **Crear puerta de enlace**.
   
    ![Instalación de puerta de enlace][2]
2. Ejecute el asistente y especifique las mismas credenciales con las que ha iniciado sesión en Microsoft Flow.
   
    Después de registrar y configurar la puerta de enlace correctamente, se muestra en la lista **Mis puertas de enlace** de Microsoft Flow.

Para más información, consulte [Información acerca de las puertas de enlace de datos locales de Microsoft Flow](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
