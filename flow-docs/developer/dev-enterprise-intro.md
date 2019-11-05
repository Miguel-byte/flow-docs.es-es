---
title: Microsoft Flow para desarrolladores empresariales, ISV y asociados | Microsoft Docs
description: Una introducción al desarrollo de soluciones para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547822"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow para desarrolladores empresariales, fabricantes de software independientes y asociados
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Como programador, puede ampliar Microsoft Flow, habilitando soluciones aún más eficaces para las organizaciones y los clientes.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow para desarrolladores empresariales

Como desarrollador empresarial, permita a su organización crear soluciones personalizadas sólidas en Microsoft Flow:

- **Cree conectores personalizados**: desarrolle conectores personalizados para conectarse a los servicios web y de datos de su organización a través de Microsoft Flow. [Aprende más](https://docs.microsoft.com/connectors/custom-connectors/)

- **Compilar Azure Functions**: elabore Azure Functions para ampliar las aplicaciones con lógica de servidor personalizada. [Aprende más](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Inserte Microsoft Flow**: Inserte Microsoft Flow directamente en sus experiencias de sitio web para crear soluciones integradas, flujos de trabajo de superficie o procesos en los que la gente de su organización ya realiza su trabajo. [Aprende más](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow para ISV y asociados de Microsoft

Como asociado de Microsoft o fabricante de software independiente (ISV), acelere la adopción de los clientes mediante la ampliación de sus productos para la integración con los procesos de negocio y datos de sus clientes, y agregue y personalice flujos de trabajo para automatizar procesos empresariales como parte de su aplicación. Una vez que haya completado los siete pasos siguientes, la aplicación tendrá la capacidad de aprovechar un potente motor de flujo de trabajo de escala de nube que puede conectarse a más de 200 servicios diferentes.

| Etapas | Pasar | ¿Cuándo es necesario? |
| --- | --- | --- |
| DevelopMentor | 1. cree un conector personalizado para sus datos | Si desea exponer sus propios datos de ISV a PowerApps o Microsoft Flow |
| DevelopMentor | 2. agregar compatibilidad con la aplicación para autenticar a los usuarios con Azure Active Directory (Azure AD) | Si desea incrustar la Microsoft Flow o la interfaz de usuario en Microsoft AppSource | 
| DevelopMentor | 3. Insertar la interfaz de usuario de Microsoft Flow en la aplicación mediante nuestro iframe basado en Web | Si desea incluir la creación o administración de flujos en la aplicación | 
| DevelopMentor | 4. crear y publicar plantillas de flujo | Si desea crear flujos previamente para sus clientes | 
| DevelopMentor | 5. agregar lógica de aplicación para implementar flujos mediante programación | Si desea implementar automáticamente los flujos pregenerados para los clientes | 
| Firmas | 6. conceder a sus clientes licencias para Microsoft Flow a través del programa proveedor de soluciones de Microsoft Cloud | Si los clientes no tienen licencias de Office 365 o Dynamics 365 |
| Firmas | 7. Mostrar la solución en Microsoft AppSource | Se recomienda para aumentar la visibilidad de la solución de ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. conectarse a las API o habilitar a los clientes para que se conecten a las API

Como ISV, a menudo tiene datos de propiedad que desea que los clientes accedan a través de sus flujos. Puede exponer el acceso a cualquiera de los datos a través de un conector personalizado. [Aprende más](https://docs.microsoft.com/connectors/custom-connectors/)

Una vez creado, hay dos maneras de poner el conector a disposición de los clientes:
- El conector se puede implementar en el inquilino del cliente a través de las API de REST o PowerShell.
- Para que el conector personalizado esté disponible públicamente para todos los usuarios, puede enviar el conector para su certificación. [Aprende más](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. autenticación 

Para llamar a las API de REST e insertar la interfaz de usuario autenticada, la aplicación debe usar Azure AD inicio de sesión único federado para autenticar a los usuarios finales y a los clientes. [Vaya aquí](https://identity.microsoft.com/) para obtener información sobre cómo habilitar el SSO federado de AAD. No se admite el acceso no autenticado o el acceso con proveedores de identidades que no sean Azure AD. 

### <a name="3-embedding-ui-components"></a>3. incrustar componentes de interfaz de usuario

Inserte Microsoft Flow dentro de la aplicación para habilitar la integración profunda y en contexto entre la aplicación y todos los demás servicios que Microsoft Flow admite. [Aprende más](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. crear y publicar plantillas de flujo

Una vez que tenga un conector, debe publicar plantillas que muestren cómo usar el servicio. Estas plantillas servirán de ejemplo que los usuarios pueden usar para aprender y, a continuación, extenderse a sus propios flujos de trabajo únicos. [Aprende más](../publish-a-template.md)

### <a name="5-deployment"></a>5. implementación

Para proporcionar a los usuarios finales acceso a los flujos que pueden usar automáticamente, implemente los flujos en el Azure AD inquilino del usuario. Use un paquete de implementación que implemente con nuestras API de REST o PowerShell. [Aprende más](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. licencias

Si los clientes ya tienen Office 365 o Dynamics 365 y estas licencias están asociadas a las identidades en las que los usuarios inician sesión con Azure AD, no hay ningún requisito de licencia adicional para usted. Sin embargo, si los clientes no usan Office 365 o Dynamics 365, debe adquirir derechos de uso en su nombre para Microsoft Flow, de modo que tengan licencia para aprovechar esos componentes incrustados en la aplicación.

Ofrecemos el programa de [proveedores de soluciones Microsoft Cloud](https://partner.microsoft.com/cloud-solution-provider) para adquirir licencias en nombre de sus clientes. Hay dos planes de [precios](https://flow.microsoft.com/pricing/) diferentes disponibles para Microsoft Flow, que debe comprobar para ver los detalles del plan y las características.

### <a name="7-list-on-appsource"></a>7. lista en AppSource

Una vez que haya integrado Microsoft Flow en la aplicación, puede enumerarlo en AppSource. Con AppSource, puede generar nuevos clientes potenciales para su empresa mediante la creación de una aplicación y su publicación en AppSource para que los nuevos clientes las prueben. [Aprende más](dev-appsource-test-drive.md)
