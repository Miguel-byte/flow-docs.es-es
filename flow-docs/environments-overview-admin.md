---
title: Información general del entorno para administradores | Microsoft Docs
description: Uso, creación y administración de entornos en Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: eb3e1050d22b8f672f47214952428b86186ba145
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547975"
---
# <a name="using-environments-within-microsoft-flow"></a>Uso de entornos dentro de Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="benefits"></a>Privilegios

Los entornos ofrecen las siguientes ventajas:

* **Localidad**de los datos: los entornos se pueden crear en distintas regiones y están enlazados a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se enruta a todos los centros de recursos de esa ubicación geográfica. Esto también proporciona una ventaja de rendimiento.

    Si los usuarios están en Europa, cree y use el entorno en la región de Europa. Si los usuarios están en el Estados Unidos, cree y use el entorno en el 

    > [!IMPORTANT]
    > Si elimina el entorno, también se eliminarán todos los flujos dentro de ese entorno. Esto se aplica a cualquier elemento que cree en ese entorno, incluidas las conexiones, las puertas de enlace, PowerApps, etc.
* **Prevención de pérdida de datos**: como administrador, no desea que los flujos obtengan datos de una ubicación interna (como *OneDrive para la empresa* o una lista de SharePoint que contenga información salarial) y, a continuación, publiquen los datos públicamente (por ejemplo *, Twitter*). Use la prevención de pérdida de datos para controlar qué servicios pueden compartir datos dentro de la implementación de Microsoft Flow.

    Por ejemplo, puede Agregar los servicios *SharePoint* y *OneDrive para la empresa* a una directiva solo de datos empresariales. Los flujos creados en este entorno pueden usar los servicios de *SharePoint* y *OneDrive para la empresa* . Sin embargo, no podrán compartir datos con otros servicios que no estén incluidos en la Directiva de solo datos empresariales.

  > [!NOTE]
  > La prevención de pérdida de datos está disponible con algunas SKU de licencia, incluida la licencia P2.

* **Límite de aislamiento para todos los recursos**: todos los flujos, puertas de enlace, conexiones, conectores personalizados, etc. residen en un entorno específico. No existen en ningún otro entorno.
* **Common Data Service**: estas son las opciones si desea crear un flujo que inserte datos en un servicio:

  * Inserte datos en un archivo de Excel y almacene el archivo de Excel en una cuenta de almacenamiento en la nube, como OneDrive.
  * Cree una SQL Database y, a continuación, almacene los datos en ella.
  * Use el Common Data Service para almacenar los datos.

    Cada entorno puede tener un máximo de una base de datos para los flujos en el Common Data Service. El acceso al Common Data Service depende de la licencia que haya adquirido; el Common Data Service no se incluye con la licencia gratuita.

## <a name="limitations"></a>Límite

Aunque los entornos proporcionan muchas ventajas, también introducen nuevas limitaciones. El hecho de que los entornos sean un límite de aislamiento significa que nunca se pueden tener recursos que hagan referencia *a recursos entre* entornos. Por ejemplo, no puede crear un conector personalizado en un entorno y, a continuación, crear un flujo que use ese conector personalizado en un entorno diferente.

## <a name="use-the-default-environment"></a>Usar el entorno predeterminado

Todos los usuarios comparten el entorno **predeterminado** y cualquier usuario puede crear flujos en el entorno **predeterminado** .

> [!TIP]
> Si es un usuario de vista previa, todos los flujos existentes se encuentran en el entorno predeterminado. Un *usuario de versión preliminar* es alguien que estaba usando Microsoft Flow antes de su lanzamiento a disponibilidad general (GA).

## <a name="the-admin-center"></a>Centro de administración

Los administradores usan el centro de administración para crear y administrar entornos. Estas son las dos formas de abrir el centro de administración:

### <a name="option-1-select-settings"></a>Opción 1: seleccionar configuración

1. Inicie sesión en [Flow.Microsoft.com](https://flow.microsoft.com).
1. Seleccione el engranaje de configuración y elija **centro de administración** en la lista:

   ![Configuración y portal de administrador](./media/environments-overview-admin/settings.png)
1. Se abre el centro de administradores.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opción 2: abrir admin.flow.microsoft.com

Vaya a [admin.Flow.Microsoft.com](https://admin.flow.microsoft.com)e inicie sesión con su cuenta profesional.

## <a name="create-an-environment"></a>Crear un entorno

1. En el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com), seleccione **entornos**. Verá todos los entornos existentes: ![entornos](./media/environments-overview-admin/environments-list.png)
2. Seleccione **nuevo entorno** y proporcione la información necesaria:


   |     Propiedad     |                                                 Denominación                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nombre del entorno |              Escriba el nombre de su entorno, como `Human Resources`o `Europe flows`.              |
   |      Region      | Elija la ubicación para hospedar su entorno. Para obtener el mejor rendimiento, utilice una región más cercana a los usuarios. |
   | Tipo de entorno |                  Elija un tipo de entorno basado en su licencia: producción o prueba.                   |

     ![configuración del entorno](./media/environments-overview-admin/new-environment-dialog.png)
3. Haga clic en **crear entorno**.
4. Ahora tiene una opción para **crear una base de datos** u **omitir**.
5. Si decide crear la **base de datos**, se le solicitará una **moneda** y un **idioma** para la base de datos. Además, también puede elegir que se implementen aplicaciones y datos de ejemplo.

   ![Opciones de configuración de base de datos](./media/environments-overview-admin/create-database-dialog2.png)


Ahora puede Agregar usuarios al entorno de.

## <a name="manage-your-existing-environments"></a>Administrar los entornos existentes

1. En el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com), seleccione **entornos**:

   ![elemento de menú entornos](./media/environments-overview-admin/select-environments.png)
1. Seleccione un entorno para abrir sus propiedades.
1. Use la pestaña **detalles** para ver información adicional sobre un entorno, incluido quién creó el entorno, su ubicación geográfica, etc.:

   ![pestaña detalles](./media/environments-overview-admin/open-environment.png)
1. Seleccione **seguridad**.

    Si no seleccionó **crear base de datos** en los pasos anteriores, en **roles de entorno**, hay dos opciones: administración de **entorno** y **creador de entorno**:

    ![roles de administrador](./media/environments-overview-admin/environment-roles.png)

    Un **creador** puede crear nuevos recursos como flujos, conexiones de datos y puertas de enlace en un entorno.

   > [!NOTE]
   > No es necesario que un usuario sea **creador** para *Editar* los recursos de un entorno. Cada creador determina quién puede editar sus recursos mediante la concesión de permisos a los usuarios que no son creadores del entorno.
   > 
   > 

    Un **Administrador** puede crear directivas de prevención de pérdida de datos y realizar otras tareas administrativas, como crear entornos, agregar usuarios a entornos y asignar privilegios de administrador o creador.

   1. Seleccione el rol **creador de entorno** y, a continuación, seleccione **usuarios**: rol ![Maker](./media/environments-overview-admin/add-environment-maker.png)
   1. Escriba un nombre, una dirección de correo electrónico o un grupo de usuarios al que desee asignar el rol de **creador** .
   1. Seleccione **Guardar**.

1. En **seguridad**, seleccione **roles de usuario**:

    ![roles de usuario](./media/environments-overview-admin/security-user-roles.png)

    Se enumeran los roles existentes, incluidas las opciones para editar o eliminar el rol.

    Seleccione **nuevo rol** para crear un nuevo rol.
1. En **seguridad**, seleccione **conjuntos de permisos**:

    ![configuración de permisos](./media/environments-overview-admin/security-permission-set.png)

    Verá todos los conjuntos de permisos y opciones existentes para editar o eliminar roles.

    Seleccione **nuevo conjunto de permisos** para crear un nuevo conjunto de permisos.
1. Si eligió **crear la base**de datos, para almacenar los datos, esta base de datos forma parte de la Common Data Service. Al hacer clic en la pestaña **seguridad** , se le pedirá que navegue hasta el **centro de administración de instancias de Dynamics 365** , donde se puede aplicar la seguridad basada en roles.
![configuración de seguridad de Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Seleccione el usuario de la lista de usuarios en el entorno o la instancia.
  ![configuración de seguridad de Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Asigne el rol al usuario.

   ![asignar rol al usuario](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> A los usuarios o grupos asignados a estos roles de entorno no se les concede automáticamente acceso a la base de datos del entorno (si existe) y el propietario de la base de datos debe conceder acceso por separado. 
>
>

### <a name="database-security"></a>Seguridad de base de datos
La capacidad de crear y modificar un esquema de base de datos y conectarse a los datos almacenados en una base de datos aprovisionada en su entorno se controla mediante los roles de usuario y los conjuntos de permisos de la base de datos. Puede administrar los roles de usuario y los conjuntos de permisos de la base de datos de su entorno en la sección **roles de usuario** y **conjuntos de permisos** de la pestaña **seguridad** . 

   ![asignar rol al usuario](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="can-i-move-a-flow-between-environments"></a>¿Puedo trasladar un flujo entre entornos?

Sí, los flujos se pueden exportar desde un entorno e importarse en otro entorno.

### <a name="which-license-includes-the-common-data-service"></a>¿Qué licencia incluye el Common Data Service?

Solo Microsoft PowerApps plan 2 incluye derechos para crear bases de datos con el Common Data Service. Sin embargo, todos los planes de pago (Microsoft Flow planes 1 y 2 y Microsoft PowerApps planes 1 y 2) tienen los derechos para usar el Common Data Service.

Elija un plan adecuado para usted visitando la página de [precios de Microsoft Flow](https://flow.microsoft.com/pricing/) .

Consulte el documento [preguntas de facturación](billing-questions.md) para obtener respuestas a las preguntas más frecuentes sobre la facturación.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>¿Se puede usar el Common Data Service fuera de un entorno?

No. El Common Data Service requiere un entorno. [Obtenga más](common-data-model-intro.md) información al respecto.

### <a name="what-regions-include-microsoft-flow"></a>¿Qué regiones incluyen Microsoft Flow?

Microsoft Flow admite la mayoría de las regiones que admite Office 365, consulte [la información general de las regiones](regions-overview.md) para obtener más detalles.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>¿Qué se necesita para crear mi propio entorno personalizado?

Todos los usuarios con la licencia del plan 2 de Microsoft Flow pueden crear sus propios entornos. Todos los usuarios Microsoft Flow pueden usar entornos creados por los administradores del plan 2, pero no pueden crear sus propios entornos.
