---
title: Microsoft Flow aplicación móvil ahora admite la administración de aplicaciones móviles de Microsoft Intune. | Microsoft Docs
description: Microsoft Flow aplicación móvil ahora admite la administración de aplicaciones móviles de Microsoft Intune.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547395"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow aplicación móvil admite Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La aplicación móvil Microsoft Flow para iOS y Android admite la administración de aplicaciones móviles (MAM) de Intune sin inscripción de dispositivos. El uso de MAM permite a los administradores de ti crear y aplicar directivas de datos móviles para proteger los datos de la organización.

## <a name="why-intune-support-is-important"></a>¿Por qué es importante la compatibilidad con Intune?

Las organizaciones buscan más control sobre los datos que residen en los dispositivos móviles de los empleados. Es posible que las organizaciones deseen restringir cómo se mueven los datos al dispositivo y asegurarse de que los datos se quitan, en caso de que el empleado abandone la organización.

## <a name="what-is-microsoft-application-management-mam"></a>Qué es la administración de aplicaciones de Microsoft (MAM)

MAM permite a las organizaciones crear directivas que rigen cómo se usan las aplicaciones en un inquilino. Esto incluye aplicar el cifrado de datos de la aplicación, lo que limita la capacidad de copiar o extraer datos solo en aplicaciones aprobadas o de aplicar un PIN en un dispositivo.

### <a name="prerequisites"></a>Requisitos previos

- Una directiva de [protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies)de Intune.
- Un grupo de Azure Active Directory (Azure AD).
- Portal de empresa. Una ventaja clave del uso de MAM es que no es necesario inscribir los dispositivos en MAM de Intune. Lo único que se necesita es el Portal de empresa, que está disponible en el App Store y en el almacén de Google Play.
- Versión 2.31.0 de la aplicación móvil Microsoft Flow para iOS, Android o Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Creación de una directiva de protección de aplicaciones, asignación de aplicaciones a la Directiva, definición de la configuración y adición de usuarios a un grupo de Azure AD

Para que se administre la aplicación móvil Microsoft Flow, debe:

1. Cree una directiva de protección de aplicaciones.
1. Asigne la aplicación móvil Microsoft Flow a la Directiva de protección de aplicaciones.
1. Asigne la configuración de directiva. Por ejemplo, puede asignar la Directiva para requerir un PIN para acceder al dispositivo móvil que ejecuta la aplicación móvil Microsoft Flow.
1. Aplique la Directiva de protección de aplicaciones a un grupo de Azure AD específico.
1. Agregue todos los usuarios a los que se aplica la Directiva de protección de aplicaciones al grupo de Azure AD.

Siga estos pasos para crear una [Directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies) que requiera Microsoft Flow los usuarios de aplicaciones móviles escriban un PIN para poder acceder a la aplicación. 


## <a name="test-the-app-protection-policy"></a>Prueba de la Directiva de protección de aplicaciones

Después de crear la Directiva de protección de aplicaciones y asignar usuarios al grupo de Azure AD, es el momento de usar la aplicación móvil Microsoft Flow y confirmar que la Directiva funciona.

Para confirmar que la Directiva funciona, siga estos pasos:

1. Instale el Microsoft Flow aplicación móvil en un dispositivo cuya plataforma coincida con una de las plataformas que ha definido en la Directiva de protección de aplicaciones.
1. Inicie sesión en la aplicación móvil con una cuenta que se encuentra en el grupo Azure AD que restringe el uso de la aplicación móvil a los usuarios que tienen un PIN.

A continuación, se le pedirá que:
1. Instale el Portal de empresa.
1. Establezca el PIN si aún no tiene un PIN que cumpla los criterios de la Directiva de protección de aplicaciones.


## <a name="learn-more"></a>Aprende más

Aprenda a crear una [Directiva de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies).

