---
ms.openlocfilehash: 0e46ba9a9ff1044e72b8550b47d126e2999cfb71
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461025"
---
## <a name="what-is-an-environment"></a>Qué es un entorno:
Un entorno es un espacio virtual que se utiliza para almacenar, administrar y compartir aplicaciones, flujos y datos empresariales en Common Data Service. Los entornos están geolocalizados, por lo que todas las aplicaciones y los datos almacenados en la base de datos de un entorno también lo están.  

## <a name="terms-you-should-get-familiar-with"></a>Términos con los que debe familiarizarse

| **Término** | **Descripción** |
| --- | --- |
| **Centro de administración** |El centro de administración es un [portal web](https://admin.flow.microsoft.com) para administrar todos los entornos y las directivas de prevención de pérdida de datos. |
| **Common Data Service** |Common Data Service permite agregar funcionalidades de almacenamiento de datos y modelado a las aplicaciones. |
| **Roles de entorno** |Los dos roles de entorno son Administrador de entorno y Creador de entorno. |
| **Roles de usuario** |Los dos roles de usuario predeterminados son Usuario de la organización y Propietario de la base de datos. Puede agregar roles y asociar permisos a dichos roles. |

## <a name="purposes-for-an-environment"></a>Propósitos de un entorno
Puede usar entornos para:  

* Separar las aplicaciones, los flujos y los datos empresariales en función de los distintos roles, requisitos de seguridad o usuarios.  
* Aplicaciones independientes, flujos y datos empresariales en función de la ubicación de los equipos o los departamentos.
* Administrar entornos de prueba y de producción.  

## <a name="how-to-use-environments"></a>Cómo usar entornos
Los entornos pueden tener diversos propósitos, según sus necesidades de organización; algunos ejemplos son:  

* Puede elegir generar todas las aplicaciones y flujos en un solo entorno. 
* Puede elegir crear un entorno para distintos tipos de aplicaciones y flujos. Por ejemplo, podría crear un entorno para las pruebas y otro para la producción.  
* También puede crear entornos en función de la estructura organizativa o incluso de la ubicación geográfica de los equipos o los departamentos. Por ejemplo, si tiene equipos en Australia, México y Europa, podría crear un entorno para cada una de estas ubicaciones con el fin de administrarlas de forma independiente.  

**Nota**: Los usuarios no ven los entornos, por lo que no deben preocuparse por el entorno en el que se encuentran. Los entornos son una herramienta para que los administradores clasifiquen, administren y compartan aplicaciones y flujos de la organización.  

## <a name="what-are-roles"></a>¿Qué son los roles?
A cualquier persona con acceso a un entorno se le debe asignar los roles **Administrador de entorno** o **Creador de entorno**. Los administradores del entorno pueden realizar todas las tareas administrativas en un entorno. Un creador del entorno puede crear recursos en un entorno existente. Un usuario individual puede tener ambos roles a la vez.  

**Nota**: Todos los usuarios tendrán acceso a un entorno predeterminado cuando se les conceda acceso a Microsoft Flow. Los usuarios pueden tener acceso a varios entornos.  

## <a name="create-an-environment"></a>Creación de un entorno
Los entornos se crean en el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com) con estos pasos:  

1. Asigne un nombre a su entorno.
2. Seleccione la región en la que se hospedará el entorno.
3. Opcionalmente, puede decidir crear una base de datos para su entorno. Si así lo desea, puede crear una base de datos después de haber creado un entorno.
4. Opcionalmente, seleccione quién tendrá acceso a la base de datos. Puede restringir el acceso o dar acceso a todos a la base de datos. 

## <a name="add-users-to-an-environment"></a>Incorporación de usuarios a un entorno
Después de crear un entorno, puede agregar usuarios a los roles Administración de entorno o Creador de entorno. Al igual que con todas las demás tareas administrativas, puede hacerlo desde el centro de administración.  

Una vez que haya creado el entorno y agregado los usuarios, también puede crear una directiva de prevención de pérdida de datos (DLP) que le ayude a administrar el uso de sus datos empresariales. Eso se tratará en el tema siguiente. 

