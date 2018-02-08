---
title: "Límites y configuración | Microsoft Docs"
description: "Límites y configuración"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: stepsic
ms.openlocfilehash: 60caaba88e825e97a49c3cf65d0ecceff586046c
ms.sourcegitcommit: b943fa83d7ca2d1a313c0c7b2cf0d7e4a9528b85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2018
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Límites y configuración en Microsoft Flow
Este tema contiene información sobre los límites actuales y detalles de la configuración de flujos.

## <a name="request-limits"></a>Límites de solicitudes
Límites para una única solicitud saliente.

### <a name="timeout"></a>Tiempo de espera
| Nombre | Límite |
| --- | --- |
| Tiempo de espera de solicitud |120 segundos |

### <a name="message-size"></a>Tamaño del mensaje
| Nombre | Límite | Notas |
| --- | --- | --- |
| Tamaño del mensaje |100 MB |No todas las API admiten los 100 MB por completo. |
| Límite de la evaluación de expresión |131 072 caracteres |`@concat()`, `@base64()`, `string` no pueden superar este límite. |

### <a name="retry-policy"></a>Directiva de reintentos
| Nombre | Límite |
| --- | --- |
| Número de reintentos |4 |

## <a name="run-duration-and-retention"></a>Duración y retención de la ejecución
Estos son los límites de una sola ejecución de flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Duración de la ejecución |30 días |Incluye flujos de trabajo con pasos pendientes, como aprobaciones. Después de 30 días, cualquier paso pendiente agotará el tiempo de espera. Las aprobaciones que agoten el tiempo de espera se quitarán del centro de aprobaciones. Si algún usuario intenta aprobar una solicitud que haya agotado el tiempo de espera, recibirá un mensaje de error. |
| Retención de almacenamiento |30 días |Contados desde la hora de inicio de la ejecución. |
| Intervalo de periodicidad mínimo |1 minuto | |
| Intervalo de periodicidad máximo |500 días | |

## <a name="looping-and-debatching-limits"></a>Repetición en bucle y fragmentación de límites
Estos son los límites de una sola ejecución de flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Elementos para ForEach |5000 |Puede usar la acción de filtrado para filtrar matrices de mayor tamaño según sea necesario. |
| Iteraciones Until |5000 | |
| Elementos de SplitOn |5000 | |
| Paralelismos para ForEach |1 | |

## <a name="definition-limits"></a>Límites de definición
Estos son los límites de un solo flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Acciones por flujo de trabajo |250 |Puede agregar flujos de trabajo anidados para ampliar este límite según sea necesario. |
| Profundidad permitida de anidamiento de acciones |5 |Puede agregar flujos de trabajo anidados para ampliar este límite según sea necesario. |
| Número máximo de caracteres por cada expresión |8192 | |
| `action`/`trigger` límite de nombre |80 | |
| `description` límite de longitud |256 | |

## <a name="sharepoint-limits"></a>Límites de SharePoint
Hay [limitaciones](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) en cómo se puede usar Microsoft SharePoint con Microsoft Flow y PowerApps.

## <a name="ip-address-configuration"></a>Configuración de la dirección IP
La dirección IP desde la que se envían las solicitudes de Microsoft Flow depende de la [región](regions-overview.md) donde está ubicado el [entorno](environments-overview-admin.md) que contiene el flujo. Actualmente no se publican FQDN disponibles para escenarios de flujo.

### <a name="logic-app-service"></a>Servicio Logic Apps
Las llamadas realizadas desde un flujo van directamente a través del servicio Azure Logic Apps. Algunos ejemplos de estas llamadas incluyen HTTP o HTTP + OpenAPI. Estas llamadas proceden de las direcciones IP siguientes:

| Región | IP de salida |
| --- | --- |
| Asia |168.63.200.173, 13.75.89.159, 23.97.68.172, 13.75.94.173, 40.83.127.19, 52.175.33.254, 52.163.93.214, 52.187.65.81, 52.187.65.155, 13.76.133.155, 52.163.228.93, 52.163.230.166 |
| Australia |13.75.153.66, 104.210.89.222, 104.210.89.244, 13.75.149.4, 104.210.91.55, 104.210.90.241, 13.73.115.153, 40.115.78.70, 40.115.78.237, 13.73.114.207, 13.77.3.139, 13.70.159.205 |
| Canadá |52.233.29.92, 52.228.39.241, 52.228.39.244, 52.232.128.155, 52.229.120.45, 52.229.126.25 |
| Europa |13.79.173.49, 52.169.218.253, 52.169.220.174, 40.113.12.95, 52.178.165.215, 52.178.166.21, 13.95.155.53, 52.174.54.218, 52.174.49.6, 40.68.222.65, 40.68.209.23, 13.95.147.65 |
| India |52.172.157.194, 52.172.184.192, 52.172.191.194, 52.172.154.168, 52.172.186.159, 52.172.185.79, 52.172.9.47, 52.172.49.43, 52.172.51.140, 52.172.50.24, 52.172.55.231, 52.172.52.0 |
| Japón |13.71.146.140, 13.78.84.187, 13.78.62.130, 13.71.158.3, 13.73.4.207, 13.71.158.120, 40.74.140.173, 40.74.81.13, 40.74.85.215, 40.74.140.4, 104.214.137.243, 138.91.26.45 |
| Estados Unidos |137.135.106.54, 40.117.99.79, 40.117.100.228, 13.92.98.111, 40.121.91.41, 40.114.82.191, 52.160.90.237, 138.91.188.137, 13.91.252.184, 52.160.92.112, 40.118.244.241, 40.118.241.243 |

### <a name="services"></a>Servicios
Las llamadas realizadas desde una API conectada a través de un flujo (por ejemplo, la API de SQL o la de SharePoint) procederán de la dirección IP especificada a continuación:

| Región | IP de salida |
| --- | --- |
| Asia |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australia |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Canadá |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| India |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japón |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Estados Unidos |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Estados Unidos (acceso prioritario) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

Por ejemplo, use las direcciones IP que deba autorizar para Azure SQL Database.

En la tabla siguiente se enumeran los servicios a los que se conecta Microsoft Flow. Asegúrese de que ninguno de estos servicios están bloqueado en la red.

Dominios | Protocolos | Usos
--------|  ---------| -----
management.azure.com|HTTPS|Acceso a Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|HTTPS|Acceso a la biblioteca de autenticación de Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|HTTPS|Acceso a la Graph API de Azure AD: para obtener información del usuario, como una foto del perfil.
*.azure-apim.net|HTTPS|Acceso al runtime para los conectores.
*.flow.microsoft.com|HTTPS|Acceso al sitio de Microsoft Flow.
*.powerapps.com|HTTPS|Acceso al sitio de PowerApps.
psux.azureedge.net|HTTPS|Acceso a la red CDN de Microsoft Flow.

