---
title: Configuración de flujos de interfaz de usuario en el dispositivo | Microsoft Docs
description: Configuración de flujos de interfaz de usuario en el dispositivo
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589677"
---
# <a name="set-up-ui-flows"></a>Configuración de flujos de IU

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Antes de poder usar el dispositivo para crear flujos de interfaz de usuario, debe asegurarse de que cumple los requisitos que se describen aquí.

> [!TIP]
> Antes de crear un flujo de interfaz de usuario, Compruebe la [lista de conectores](https://flow.microsoft.com/connectors/) para ver si la aplicación que desea automatizar ya tiene un conector. Si es así, considere la posibilidad de crear un flujo en lugar de un flujo de la interfaz de usuario. También puede crear su [propio conector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Requisitos previos

- Plan de energía de [pago](https://flow.microsoft.com/pricing/) o de [prueba](https://flow.microsoft.com/manage/) automatizado.

- Una cuenta profesional o educativa para iniciar sesión en Power Automatic y en el dispositivo Windows.

- Un dispositivo que ejecuta Windows 10, Windows Server 2016 o Windows Server 2019.
- Un teclado de EE. UU. (QWERTY) adjunto.

- La [siguiente versión de Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome.

- Un [entorno](https://docs.microsoft.com/power-platform/admin/environments-overview) con una [base de datos de Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

> [!IMPORTANT]
> Los flujos de la interfaz de usuario se están implementando actualmente entre regiones. Si no ve la característica de vista previa o no puede crear nuevos flujos de interfaz de usuario, inténtelo de nuevo más tarde.


## <a name="limitations"></a>Límite

Flujos de interfaz de usuario (versión preliminar) está disponible en inglés.

No se admite lo siguiente:

-   Flujos de IU de escritorio

    -   Varios monitores
    -   Máquinas virtuales
    -   Doble clic, desplazamiento del mouse, entrada táctil o de lápiz
    -   Interacciones en Windows (explorador de archivos, menú Inicio, barra de tareas, etc.)

-   Flujos de interfaz de usuario Web

    -   Clic con el botón derecho
    -   La información de sesión de usuario (por ejemplo, cookies) no se reutilizará durante la reproducción. Tendrá que editar el script para insertar la información de inicio de sesión cuando sea necesario para los sitios Web.

Encontrará limitaciones específicas de características incluidas en la documentación de cada característica.

## <a name="get-your-device-ready"></a>Preparar el dispositivo

Instale los siguientes componentes para crear y ejecutar flujos de interfaz de usuario:

|  | **Name**                             | **Uso**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [La aplicación flujos de la interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Grabar aplicaciones Windows de escritorio                                  |          |
|   | Extensión del explorador de flujos de IU           | Grabe y pruebe aplicaciones Windows de escritorio. Grabe aplicaciones Web. |                                                                                              |
|   | Controlador Webdriver                            | Prueba y ejecución de aplicaciones de escritorio de Windows                            |                                                                                              |
|   | [IDE de Selenium](https://go.microsoft.com/fwlink/?linkid=2107665) | Grabar y reproducir aplicaciones Web                                 |  |
|   | [Puerta](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Se usa para permitir que los eventos, flujos programados o flujos de botón se conecten a, desencadenar los flujos de la interfaz de usuario (que se ejecutan dentro de la organización) y ejecutarlos.              |  | 

## <a name="install-the-ui-flows-app"></a>Instalación de la aplicación flujos de interfaz de usuario

El instalador de flujos de interfaz de usuario contiene todos los componentes necesarios para registrar, editar y probar flujos de interfaz de usuario para el escritorio. 

>[!IMPORTANT]
>El instalador de flujos de la interfaz de usuario instala el componente Webdriver y la extensión del explorador flujos de la interfaz de usuario. Ambos son necesarios para registrar, probar y ejecutar flujos de interfaz de usuario para el escritorio.

Siga estos pasos para instalar la aplicación flujos de interfaz de usuario:

1. [Descargue el instalador de la aplicación flujos de interfaz de usuario](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra el archivo **setup. Microsoft. Flow. UIflow. exe** . Es probable que este archivo esté en la carpeta **descargas** después de descargarlo en el paso anterior.
1. Siga las instrucciones del instalador de la **instalación de flujos de interfaz de usuario (versión preliminar)** para completar la instalación.

## <a name="activate-the-ui-flows-browser-extension"></a>Activar la extensión del explorador flujos de la interfaz de usuario 

Una vez que se complete el instalador de flujos de la interfaz de usuario, el explorador le pedirá que active la extensión.

- En Microsoft Edge (cromo), seleccione cada icono de advertencia en la parte superior derecha del explorador y, a continuación, seleccione **Habilitar extensión**.
-   En Google Chrome, seleccione **Habilitar extensión** cuando se le solicite.  


## <a name="install-selenium-ide"></a>Instalación del IDE de Selenium

El IDE de Selenium es una herramienta de código abierto que permite grabar y reproducir interacciones humanas en sitios Web.

Con flujos de interfaz de usuario, puede ejecutar scripts del IDE de Selenium desde Power Automatic y mantenerlos almacenados de forma segura (con el gobierno de ti adecuado) en Common Data Service.

Siga estos pasos para instalar el IDE de Selenium:

1. [Descargue e instale](https://go.microsoft.com/fwlink/?linkid=2107665) el IDE de Selenium para la próxima versión de Microsoft Edge o Google Chrome.

1. En Microsoft Edge (cromo), seleccione **permitir extensiones de otros almacenes**y, a continuación, seleccione **Agregar a Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalación de la puerta de enlace de datos local

Necesitará la puerta de enlace para desencadenar el flujo de la interfaz de usuario desde un [flujo de eventos, programaciones o botones.](../getting-started.md/#types-of-flows)

>[!TIP]
>La puerta de enlace no es necesaria si solo desea crear, editar y probar los flujos de interfaz de usuario en el dispositivo.

[Instale la puerta de enlace de datos local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), si es necesario.

## <a name="uninstall-ui-flows"></a>Desinstalar flujos de IU

1. Abra el menú **inicio** > **configuración** > **aplicaciones**.
1. Busque **flujos de interfaz de usuario (versión preliminar)** y, a continuación, selecciónelo.
1. Seleccione **desinstalar**.

## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [crear flujos de IU de escritorio](create-desktop.md).
- Aprenda a [crear flujos de interfaz de usuario Web](create-web.md).
- Obtenga información sobre cómo ejecutar [flujos de interfaz de usuario](run-ui-flow.md).
- Aprenda a [administrar flujos de interfaz de usuario](manage.md).
- Más información sobre la [puerta de enlace local](../gateway-reference.md/#use-a-gateway)

