---
title: Límites y configuración | Microsoft Docs
description: Límites y configuración
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8a8a6561840f91ab61b8d7440f1620c2e7cd0076
ms.sourcegitcommit: a505b0aac796960d57fccee92eb18c6566ac9c35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "53006964"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Límites y configuración en Microsoft Flow
Este tema contiene información sobre los límites actuales y detalles de la configuración de flujos.

## <a name="request-limits"></a>Límites de solicitudes
Límites para una única solicitud saliente.

### <a name="timeout"></a>Tiempo de espera

| Nombre | Límite |
| --- | --- |
| Tiempo de espera de solicitud para las llamadas sincrónicas |120 segundos |
| Tiempo de espera de solicitud para las llamadas asincrónicas|Configurable. El máximo es 30 días. |

### <a name="message-size"></a>Tamaño del mensaje

| Nombre | Límite | Notas |
| --- | --- | --- |
| Tamaño del mensaje |100 MB |No todas las API admiten los 100 MB por completo. |
| Límite de la evaluación de expresión |131 072 caracteres |`@concat()`, `@base64()`, `string` no pueden superar este límite. |

### <a name="retry-policy"></a>Directiva de reintentos

| Nombre | Límite |
| --- | --- |
| Número de reintentos |90 | El valor predeterminado es 4. Para cambiar el valor predeterminado, use la configuración de la acción | 
| Reintentar retraso máximo |1 día | |
| Reintentar retraso mínimo |5 segundos | |

## <a name="run-duration-and-retention"></a>Duración y retención de la ejecución
Estos son los límites de una sola ejecución de flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Duración de la ejecución |30 días |Incluye flujos de trabajo con pasos pendientes, como aprobaciones. Después de 30 días, cualquier paso pendiente agotará el tiempo de espera. Las aprobaciones que agoten el tiempo de espera se quitarán del centro de aprobaciones. Si algún usuario intenta aprobar una solicitud que haya agotado el tiempo de espera, recibirá un mensaje de error. |
| Retención de almacenamiento |30 días |Contados desde la hora de inicio de la ejecución. |
| Intervalo de periodicidad mínimo |1 minuto | |
| Intervalo de periodicidad máximo |500 días | |
| Retención máxima del historial de ejecución |28 días, según las reglas del RGPD. | |

## <a name="looping-and-debatching-limits"></a>Repetición en bucle y fragmentación de límites
Estos son los límites de una sola ejecución de flujo.

| Nombre | Límite | Notas |
| --- | --- | --- |
| Aplicar a cada elemento |100 000 |100 000 solo está disponible para los planes premium. De lo contrario, tiene un límite de 5000. Puede usar la acción de filtrado para filtrar matrices de mayor tamaño según sea necesario. |
| Iteraciones Until |5000 | |
| Elementos de SplitOn |100 000 |Al igual que en el caso de Aplicar a cada uno, el límite será de 5000 a menos que su plan sea premium. |
| Aplicar a cada paralelismo |50 |De forma predeterminada, los bucles se ejecutan en secuencia (básicamente, el paralelismo es 1). Puede configurar hasta 50 en paralelo. |
| Ejecuciones de acciones cada 5 minutos | 100 000 | Además, puede distribuir una carga de trabajo por más de un flujo según sea necesario. |
| Llamadas salientes simultáneas de acciones | ~2500 | Reduzca la cantidad de solicitudes simultáneas o la duración según sea necesario. | 

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

### <a name="logic-apps"></a>Logic Apps
Las llamadas realizadas desde un flujo van directamente a través del servicio Azure Logic Apps. Algunos ejemplos de estas llamadas incluyen HTTP o HTTP + OpenAPI. Consulte [la documentación de Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) adecuada según las direcciones IP que usa el servicio.

### <a name="connectors"></a>Conectores
Las llamadas realizadas desde un conector (por ejemplo, la API de SQL o la de SharePoint) procederán de las direcciones IP especificadas a continuación:

| Región | IP de salida |
| --- | --- |
| Asia Pacífico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250  |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Canadá | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japón | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| Sudamérica | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Versión preliminar (Estados Unidos)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |

Por ejemplo, use las direcciones IP que deba autorizar para Azure SQL Database.

### <a name="required-services"></a>Servicios necesarios
En la tabla siguiente se enumeran los servicios a los que se conecta Microsoft Flow. Asegúrese de que ninguno de estos servicios están bloqueado en la red.

Dominios | Protocolos | Usos
--------|  ---------| -----
management.azure.com|HTTPS|Acceso a Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|HTTPS|Acceso a la biblioteca de autenticación de Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|HTTPS|Acceso a la Graph API de Azure AD: para obtener información del usuario, como una foto del perfil.
*.azure-apim.net|HTTPS|Acceso al runtime para los conectores.
*.flow.microsoft.com|HTTPS|Acceso al sitio de Microsoft Flow.
*.powerapps.com|HTTPS|Acceso al sitio de PowerApps.
*.azureedge.net|HTTPS|Acceso a la red CDN de Microsoft Flow.
nps.onyx.azure.net|HTTPS|Acceso a NPS (Net Promoter Score).
