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
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547374"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Límites y configuración en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Este tema contiene información sobre los límites actuales y los detalles de configuración de los flujos.

## <a name="request-limits"></a>Límites de solicitudes
Estos son los límites de una única solicitud de salida.

### <a name="timeout"></a>Super

| Name | Ilimitado |
| --- | --- |
| Tiempo de espera de solicitud para llamadas sincrónicas |120 segundos |
| Tiempo de espera de solicitud para llamadas asincrónicas|Presentan. Max es 30 días. |

### <a name="message-size"></a>Tamaño del mensaje

| Name | Ilimitado | Apunte |
| --- | --- | --- |
| Tamaño del mensaje |100 MB |No todas las API admiten los 100 MB completos. |
| Límite de evaluación de expresión |131.072 caracteres |`@concat()`, `@base64()``string` no pueden superar este límite. |

### <a name="retry-policy"></a>Directiva de reintentos

| Name | Ilimitado |
| --- | --- |
| Intentos de reintento |90 | El valor predeterminado es 4. Para cambiar la configuración predeterminada de la acción usar | 
| Retraso máximo de reintentos |1 día | |
| Retraso mínimo de reintento |5 segundos | |

## <a name="run-duration-and-retention"></a>Duración y retención de la ejecución
Estos son los límites de una sola ejecución de flujo.

| Name | Ilimitado | Apunte |
| --- | --- | --- |
| Duración de la ejecución |30 días |Incluye flujos de trabajo con pasos pendientes como las aprobaciones. Después de 30 días, se agota el tiempo de espera de todos los pasos pendientes. Las aprobaciones que han agotado el tiempo de espera se quitan del centro de aprobaciones. Si alguien intenta aprobar una solicitud de tiempo de espera agotado, recibirá un mensaje de error. |
| Retención de almacenamiento |30 días |Esta es la hora de inicio de la ejecución. |
| Intervalo de periodicidad mínima |1 minuto | |
| Intervalo de periodicidad máximo |500 días | |
| Retención de historial de ejecución máxima |28 días, según las reglas de RGPD. | |
|Intervalo de aplazamiento mínimo: licencia gratis y plan 1|5 segundos||
|Intervalo de aplazamiento mínimo: licencia del plan 2|1 segundo||

## <a name="looping-and-debatching-limits"></a>Límites de bucle y desagrupación
Estos son los límites de una sola ejecución de flujo.

| Name | Ilimitado | Apunte |
| --- | --- | --- |
| Aplicar a cada artículo: licencia gratuita|5\.000 |Puede usar la acción de filtrado para filtrar matrices más grandes según sea necesario. |
| Aplicar a cada elemento: licencia de plan 1 y plan 2|100.000 |Puede usar la acción de filtrado para filtrar matrices más grandes según sea necesario. |
| Iteraciones hasta |5\.000 | |
| Elementos de spliton-licencia gratuita |5\.000 ||
| Elementos de spliton: licencia de plan 1 y plan 2 |100.000 ||
| Aplicar a cada paralelismo |50 |De forma predeterminada, los bucles se ejecutan en secuencia (esencialmente, el paralelismo es 1). Puede configurar hasta 50 en paralelo. |
| Ejecuciones de acciones por 5 minutos: gratis, Office365, licencias del plan 1 y planes de prueba | 2\.000 | Además, puede distribuir una carga de trabajo en más de un flujo según sea necesario. |
|Ejecuciones de acciones por 5 minutos: licencias del plan 2 de pago|100.000|Además, puede distribuir una carga de trabajo en más de un flujo según sea necesario.|
|Ejecuciones de acciones por 5 minutos: licencias del plan 2 de pago|150.000|Además, puede distribuir una carga de trabajo en más de un flujo según sea necesario.|
| Llamadas salientes simultáneas de acciones: licencia gratis y plan 1 | ~ 500 | Reducir el número de solicitudes simultáneas o reducir la duración según sea necesario. |
| Ejecuciones de acciones por 24 horas: gratis, Office365, licencias del plan 1 y planes de evaluación | ~ 2.500 | Reducir el número de solicitudes simultáneas o reducir la duración según sea necesario. | 

## <a name="throughput-limits"></a>Límites de rendimiento

|Name|Ilimitado|Apunte|
|---|---|---|
|Punto de conexión de tiempo de ejecución: número de llamadas de lectura permitidas por 5 minutos-licencia gratuita y plan 1|6\.000||
|Punto de conexión de tiempo de ejecución: número de llamadas de lectura permitidas por 5 minutos-licencia del plan 2|60.000||
|Punto de conexión de tiempo de ejecución: invocar llamadas por 5 minutos-licencia gratuita y plan 1|4\.500||
|Punto de conexión de tiempo de ejecución: número de llamadas de invocación por 5 minutos-licencia del plan 2|45.000||
|Cantidad de rendimiento permitido por 5 minutos-licencia gratuita y plan 1|600 MB||
|Cantidad de rendimiento permitido por 5 minutos-licencia del plan 2|6 GB||
|Cantidad de flujos de contenido que se pueden producir (entradas/salidas de acciones) por hora-gratis, plan 1 y licencia de plan 2|200 GB||


## <a name="definition-limits"></a>Límites de definición
Estos son los límites de un único flujo.

| Name | Ilimitado | Apunte |
| --- | --- | --- |
| Acciones por flujo de trabajo |250 |Puede Agregar flujos de trabajo anidados para extenderlo según sea necesario. |
| Profundidad de anidamiento de acciones permitidas |203 |Puede Agregar flujos de trabajo anidados para extenderlo según sea necesario. |
| Número máximo de caracteres por expresión |8\.192 | |
| `action`/límite de nombres `trigger` |80 | |
| límite de longitud de `description` |256 | |

## <a name="sharepoint-limits"></a>Límites de SharePoint
Existen [limitaciones](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) en el uso de Microsoft SharePoint con Microsoft Flow y PowerApps.

## <a name="ip-address-configuration"></a>Configuración de la dirección IP
La dirección IP desde la que se envían las solicitudes de Microsoft Flow depende de la [región](regions-overview.md) en la que se encuentra el [entorno](environments-overview-admin.md) que contiene el flujo. Actualmente no se publican FQDN disponibles para los escenarios de Flow.

>[!IMPORTANT]
> Algunas llamadas a un flujo pueden provienen de direcciones IP que se enumeran en la documentación de [Logic apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) . Algunos ejemplos de estas llamadas son HTTP o HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Las llamadas realizadas desde un flujo van directamente a través del servicio de aplicaciones lógicas de Azure. Algunos ejemplos de estas llamadas son HTTP o HTTP + OpenAPI. Consulte [la documentación de Logic apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) para la que el servicio usa las direcciones IP.

### <a name="connectors"></a>Conexiones
Las llamadas realizadas desde un conector en un flujo (por ejemplo, la API de SQL o la API de SharePoint) procederán de las direcciones IP que se enumeran aquí:

| Region | IP de salida |
| --- | --- |
| Asia Pacífico | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canadá | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Centroeuropeo | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japón | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Sudamérica | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Vista previa (Estados Unidos)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Por ejemplo, si debe autorizar las direcciones IP para la base de datos SQL de Azure, debe usar estas direcciones.

### <a name="required-services"></a>Servicios requeridos
En la tabla siguiente se enumeran los servicios a los que se conecta Microsoft Flow. Asegúrese de que ninguno de estos servicios está bloqueado en la red.

Dominios | Protocolos | Utilización
--------|  ---------| -----
management.azure.com|https|Acceso al Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Acceso a Biblioteca de autenticación de Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Acceso a Azure AD Graph API: para obtener información de usuario como, por ejemplo, una foto de perfil.
*. azure-apim.net|https|Acceso al tiempo de ejecución de los conectores.
*. flow.microsoft.com|https|Acceso al sitio Microsoft Flow.
*. powerapps.com|https|Acceso al sitio de PowerApps.
*. azureedge.net|https|Acceso al Microsoft Flow red CDN.
nps.onyx.azure.net|https|Acceso a NPS (puntuación de red promotor).
