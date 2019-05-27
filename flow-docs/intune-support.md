---
title: Aplicación móvil Microsoft Flow ahora admite la administración de aplicaciones móviles de Microsoft Intune. | Microsoft Docs
description: Aplicación móvil Microsoft Flow ahora admite la administración de aplicaciones móviles de Microsoft Intune.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65060500"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Aplicación móvil Microsoft Flow admite Microsoft Intune

La aplicación móvil Microsoft Flow para iOS y Android admite la administración de aplicaciones móviles de Intune (MAM) sin inscripción de dispositivos. Mediante MAM permite a los administradores de TI crear y aplicar directivas de datos móviles para proteger los datos de la organización.

## <a name="why-intune-support-is-important"></a>¿Por qué es importante soporte técnico de Intune

Las organizaciones están buscando más control sobre los datos que residen en dispositivos móviles de empleado. Es posible que las organizaciones desean restringir cómo se mueven esos datos en el dispositivo y asegúrese de que quitan los datos, el empleado debe salir de la organización.

## <a name="what-is-microsoft-application-management-mam"></a>¿Qué es Microsoft Application Management (MAM)

MAM permite a las organizaciones crear directivas que rigen cómo se usan las aplicaciones dentro de un inquilino. Esto incluye su cifrado de datos de aplicación, limitar la capacidad de copiar o extraer datos a solo las aplicaciones aprobadas o exigir un PIN en un dispositivo.

### <a name="prerequisites"></a>Requisitos previos

- Una Intune [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).
- Un grupo de Azure Active Directory (Azure AD).
- Portal de empresa. Una ventaja clave del uso de MAM es que los dispositivos no necesitan estar inscrito en Intune MAM. Todo lo que necesita es el Portal de empresa, que está disponible en la aplicación de Store y Google Play store.
- Versión 2.31.0 de la aplicación móvil Microsoft Flow para iOS, Android o Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Crear una directiva de protección de aplicaciones, asignación de aplicaciones a la directiva, definir la configuración y agregar usuarios a un grupo de Azure AD

Para que la aplicación móvil Microsoft Flow administrarlos, debe:

1. Crear una directiva de protección de aplicaciones.
1. Asigne la aplicación móvil Microsoft Flow a la directiva de protección de aplicaciones.
1. Asignar a la configuración de directiva. Por ejemplo, podría asignar la directiva para requerir un PIN acceder al dispositivo móvil que se ejecuta la aplicación móvil Microsoft Flow.
1. Aplicar la directiva de protección de aplicaciones a un determinado grupo de Azure AD.
1. Agregue todos los usuarios al que se aplica la directiva de protección de aplicaciones para el grupo de Azure AD.

Siga estos pasos para crear un [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies) que requiere que los usuarios de la aplicación móvil de Microsoft Flow escribir un PIN para poder tener acceso a la aplicación. 


## <a name="test-the-app-protection-policy"></a>Probar la directiva de protección de aplicaciones

Una vez que ha creado la directiva de protección de aplicaciones y los usuarios asignados al grupo de Azure AD, es el momento de usar la aplicación móvil Microsoft Flow y confirme que funciona la directiva.

Para confirmar que funciona la directiva, siga estos pasos:

1. Instale la aplicación móvil Microsoft Flow en un dispositivo cuya plataforma coincida con una de las plataformas que se ha definido en la directiva de protección de aplicaciones.
1. Inicie sesión en la aplicación móvil con una cuenta que se encuentra en el grupo de Azure AD que restringe el uso de la aplicación móvil a los usuarios que tienen un PIN.

A continuación, se pedirá que:
1. Instalar el Portal de empresa.
1. Si no tiene ya un PIN que cumpla los criterios de la directiva de protección de aplicación, establezca el PIN.


## <a name="learn-more"></a>Más información

Aprenda a crear un [directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).

