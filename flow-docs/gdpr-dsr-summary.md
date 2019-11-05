---
title: Resumen de solicitudes de asunto de datos de RGPD | Microsoft Docs
description: Obtenga información acerca de cómo responder a las solicitudes de RGPD de los datos para Microsoft Flow.
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
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548228"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Responder a las solicitudes de RGPD de los datos para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se prepara a usted y a su organización para el Reglamento general de protección de datos de la Unión Europea (RGPD). En este artículo no solo se describe lo que Microsoft está haciendo para prepararse para el RGPD, sino que también comparte ejemplos de pasos que puede seguir hoy para admitir el cumplimiento de RGPD cuando usa PowerApps, Microsoft Flow y Common Data Service.

## <a name="prerequisites"></a>Requisitos previos

Los usuarios y los administradores pueden realizar las acciones que se describen en este artículo.

### <a name="users"></a>Pueden

Un usuario debe tener una cuenta de Azure Active Directory activa con una [licencia Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Los usuarios que no cumplan este requisito deberán solicitar a un administrador que realice estas acciones.

### <a name="administrators"></a>Administradores

Puede realizar las operaciones que requieren privilegios de administrador, que se describen en este artículo si inicia sesión en el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com/) o en el [PowerShell de administración de PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) con una cuenta que tiene ambos permisos:

- Una licencia de pago o de prueba para el plan 2 de PowerApps.

    [Una licencia de prueba](http://web.powerapps.com/trial) expira en 30 días.

- Administrador [global de Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) o [administrador global de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Inquilinos no administrados
Si es miembro de un inquilino no [administrado](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), lo que significa que su inquilino de Azure ad no tiene un administrador global, podrá seguir los pasos descritos en este artículo para exportar y quitar sus propios datos personales. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Responder a DSRs Against para los datos de clientes de Microsoft Flow

El RGPD otorga derechos a personas (conocidas en el RGPD como asuntos de datos) para administrar los datos personales recopilados por un empresario u otro tipo de agencia u organización (conocido como controlador de datos o simplemente controlador). Los datos personales se definen muy ampliamente bajo el RGPD como cualquier dato relacionado con una persona física identificada o identificable. RGPD proporciona a los interesados derechos específicos sobre sus datos personales. Estos derechos incluyen la obtención de copias de datos personales, la solicitud de correcciones, la restricción de su procesamiento, su eliminación o su recepción en un formato electrónico para que se puedan migrar a otro controlador. Una solicitud formal de un sujeto de datos a un controlador para realizar una acción en sus datos personales se denomina solicitud de derechos de sujeto de datos (DSR).

En este artículo se describe cómo utilizar los productos, servicios y herramientas administrativas de Microsoft para ayudar a los controladores a buscar y actuar en datos personales al responder a DSRs Against. En concreto, este artículo incluye cómo buscar, acceder y actuar sobre datos personales que residen en la nube de Microsoft. A continuación se muestra una introducción rápida de los procesos descritos en esta guía:

1. Detección: Use las herramientas de búsqueda y detección para encontrar más fácilmente los datos del cliente que pueden ser el sujeto de un DSR. Una vez que se recopilan documentos que pueden responder, puede realizar una o varias de las acciones de DSR descritas en los pasos siguientes para responder a la solicitud. Como alternativa, puede determinar que la solicitud no cumple las directrices de su organización para responder a DSRs Against. [Microsoft Flow documentación de detección de DSR](gdpr-dsr-discovery.md)

1. Acceso: recupere los datos personales que residen en la nube de Microsoft y, si se solicita, realice una copia del mismo que pueda estar disponible para el sujeto de datos.

1. Rectificar: realice los cambios o implemente otras acciones solicitadas en los datos personales, si procede.

    Si un interesado en los datos le pide rectificar los datos personales que residen en su organización, usted y su organización deben determinar si es adecuado respetar la solicitud.  La rectificación de los datos puede incluir la realización de acciones tales como la edición, la redacción o la eliminación de datos personales.

    Puede usar Azure Active Directory para administrar las identidades de los usuarios Microsoft Flow. Los clientes empresariales pueden administrar las solicitudes de rectificación DSR, incluidas las características de edición limitadas, según la naturaleza de un servicio de Microsoft determinado.  Como procesador de datos, Microsoft no ofrece la capacidad de corregir los registros generados por el sistema porque estos registros reflejan actividades reales y constituyen un registro histórico de eventos dentro de los servicios de Microsoft.  [Más información acerca de DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Restringir: restrinja el procesamiento de datos personales, ya sea quitando las licencias para varios servicios en línea o desactivando los servicios deseados siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de forma local o en otra ubicación.

    Los interesados en los datos pueden solicitar que restrinja el procesamiento de sus datos personales.  Microsoft proporciona interfaces de programación de aplicaciones (API) e interfaces de usuario (IUS) con este fin.  Estas interfaces permiten al administrador de inquilinos del cliente de la empresa administrar tales DSRs Against a través de una combinación de exportación de datos y eliminación de datos. Un cliente puede (1) exportar una copia electrónica de los datos personales del usuario, incluidas las cuentas, los registros generados por el sistema y los registros asociados, seguido de (2) la eliminación de la cuenta y los datos asociados que se encuentran en los sistemas de Microsoft.

1. Eliminar: Quite permanentemente los datos personales que residen en la nube de Microsoft. [Más información sobre la eliminación de datos personales](gdpr-dsr-delete.md).

1. Exportar: proporcione una copia electrónica (en formato legible por máquina) de datos personales al asunto de los datos. En cada sección de este artículo se describen los procedimientos técnicos que puede llevar a cabo una organización de controlador de datos para responder a un DSR para datos personales en la nube de Microsoft. [Más información sobre la exportación de datos personales](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Registros generados por el sistema

Consulte esta [Guía](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) para obtener más información sobre los registros generados por el sistema para Microsoft Flow.
