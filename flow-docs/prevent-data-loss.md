---
title: Introducción a las directivas de prevención de pérdida de datos (DLP). | Microsoft Docs
description: Introducción a las directivas de prevención de pérdida de datos para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 46f646fb81fcf7043ff612a240528fed72638048
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548547"
---
# <a name="data-loss-prevention-dlp-policies"></a>Directivas de prevención de pérdida de datos (DLP)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este documento se presentan las directivas de prevención de pérdida de datos, que ayudan a proteger los datos de la organización para que no se compartan con una lista de los conectores que se definen.

## <a name="whats-a-data-loss-prevention-policy"></a>¿Qué es una directiva de prevención de pérdida de datos?

Los datos de una organización son fundamentales para su éxito. Sus datos deben estar disponibles para la toma de decisiones, pero deben protegerse para que no se compartan con audiencias que no deberían tener acceso a ellos. Para proteger estos datos, Microsoft Flow le proporciona la capacidad de crear y aplicar directivas que definen qué conectores de consumidor pueden acceder a los datos empresariales y compartirlos. Estas directivas que definen cómo se pueden compartir los datos se conocen como directivas de prevención de pérdida de datos (DLP).

## <a name="why-create-a-dlp-policy"></a>¿Por qué crear una directiva de DLP?

Cree una directiva DLP para definir claramente qué conectores de consumidor pueden acceder a los datos empresariales y compartirlos. Por ejemplo, es posible que una organización que usa Microsoft Flow no quiera que sus datos empresariales de SharePoint se publiquen automáticamente en su fuente de Twitter. Para evitarlo, cree una directiva de DLP que impida el uso de los datos de SharePoint como origen de los tweets.

## <a name="benefits-of-a-dlp-policy"></a>Ventajas de una directiva DLP

* Garantiza que los datos se administran de manera uniforme en toda la organización.
* Evita que los datos empresariales importantes se publiquen accidentalmente en conectores como sitios de redes sociales.

## <a name="managing-dlp-policies"></a>Administración de directivas DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Requisitos previos para la administración de directivas DLP

* Permisos de administrador de entorno o administrador de inquilinos.

    Puede obtener más información sobre los permisos en el [artículo sobre entornos](environments-overview-admin.md).
* Una [licencia de Microsoft Flow P2](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Creación de una directiva de DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Requisitos previos para la creación de directivas de DLP

Para crear una directiva DLP, debe tener permisos para al menos un entorno.

Siga estos pasos para crear una directiva de DLP que impida que los datos del sitio de SharePoint de la empresa se publiquen en Twitter:

1. Inicie sesión en el [centro de administración de Microsoft Flow](https://admin.flow.microsoft.com) (centro de administración).

1. Seleccione la pestaña directivas de datos y, a continuación, seleccione el vínculo **nueva Directiva** :

    ![Inicia sesión](./media/prevent-data-loss/create-policy-1.png)
1. Seleccione la pestaña **grupos de datos** .

1. Escriba el nombre de la Directiva DLP como *acceso seguro a datos para contoso* en la etiqueta nombre de la **Directiva de datos** en la parte superior de la página:

    ![Inicia sesión](./media/prevent-data-loss/create-policy-2.png)

1. Seleccione el [entorno](environments-overview-admin.md) en la pestaña **entornos** .

    > [!NOTE]
    > Como administrador de entorno, puede crear directivas que se apliquen a un solo entorno. Como administrador de inquilinos, puede crear directivas que se apliquen a cualquier combinación de entornos:
    >
    >

    ![Seleccionar entorno](./media/prevent-data-loss/create-policy-3.png)

1. Seleccione la pestaña **grupos de datos** :

    ![seleccionar grupos de datos](./media/prevent-data-loss/create-policy-4.png)

1. Seleccione el vínculo **Agregar** que se encuentra dentro del cuadro de grupo **Business Data Only (solo datos empresariales** ):

    ![Seleccione Agregar](./media/prevent-data-loss/create-policy-5.png)

1. Seleccione los conectores de **SharePoint** y **Salesforce** en la página **Agregar conectores** :

   ![seleccionar conectores](./media/prevent-data-loss/create-policy-6.png)

1. Seleccione el botón **Agregar conectores** para agregar los conectores que pueden compartir datos empresariales.

1. Seleccione **Guardar Directiva** en la esquina superior derecha de la pantalla.

1. Transcurridos unos instantes, la nueva Directiva de DLP se mostrará en la lista de directivas de prevención de pérdida de datos:

    ![Lista de DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Opcional** Envíe un correo electrónico u otra comunicación a su equipo y le avise de que ya hay disponible una nueva Directiva de DLP.

Enhorabuena, ahora ha creado una directiva de DLP que permite a la aplicación compartir datos entre SharePoint y Salesforce, y bloquea el uso compartido de datos con cualquier otro servicio.

> [!NOTE]
> Al agregar un servicio a un grupo de datos, se quita automáticamente del otro grupo de datos. Por ejemplo, si Twitter se encuentra actualmente en el grupo de datos **Business Data Only (solo datos empresariales** ) y no desea permitir que los datos empresariales se compartan con Twitter, simplemente agregue el servicio Twitter al grupo de datos **no Business Data allowed** . Esto quitará Twitter del grupo de datos Business Data Only (solo datos profesionales).
>
>

## <a name="data-sharing-violations"></a>Infracciones de uso compartido de datos

Suponiendo que ha creado la Directiva DLP descrita anteriormente, si un usuario crea un flujo que comparte datos entre Salesforce (que está en el grupo de datos **Business Data Only** ) y Twitter (que está en el grupo de datos **no Business Data allowed** ), el usuario será se informa de que el flujo se ha **suspendido** debido a un conflicto con la Directiva de prevención de pérdida de datos que ha creado.

![Crear flujo](./media/prevent-data-loss/10.png)

Si los usuarios se pongan en contacto con usted sobre los flujos suspendidos, aquí tiene algunas cosas que debe tener en cuenta:

1. En este ejemplo, si hay una razón empresarial válida para compartir datos empresariales entre SharePoint y Twitter, puede editar la Directiva de DLP.

1. Pida al usuario que edite el flujo para que cumpla con la Directiva de DLP.

1. Pida al usuario que deje el flujo en el estado suspendido hasta que se realice una decisión sobre el uso compartido de datos entre estas dos entidades.

## <a name="find-a-dlp-policy"></a>Búsqueda de una directiva DLP

### <a name="admins"></a>Administradores

Los administradores pueden usar la característica de búsqueda desde el centro de administración para buscar directivas DLP específicas.

> [!NOTE]
> Los administradores deben publicar todas las directivas DLP para que los usuarios de la organización conozcan las directivas antes de crear flujos.
>
>

### <a name="makers"></a>Decisiones

Si no tiene permisos de administrador y desea obtener más información sobre las directivas de DLP de su organización, póngase en contacto con el administrador. También puede obtener más información en el [artículo](environments-overview-maker.md) sobre el fabricante de entornos.

> [!NOTE]
> Solo los administradores pueden editar o eliminar directivas de DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Editar una directiva DLP

1. Inicie el [centro de administración](https://admin.flow.microsoft.com)de.

1. En el centro de administración que se inicia, seleccione el vínculo **directivas de datos** en el lado izquierdo.

    ![seleccionar directivas de datos](./media/prevent-data-loss/2.png)

1. Busque en la lista de directivas de DLP existentes y seleccione el botón Editar junto a la Directiva que desea editar.

1. Realice los cambios necesarios en la Directiva. Puede modificar el entorno o los servicios de los grupos de datos, por ejemplo.

1. Seleccione **Guardar Directiva** para guardar los cambios.

> [!NOTE]
> Los administradores de entorno pueden ver las directivas DLP creadas por administradores de inquilinos, pero no pueden editarlas los administradores del entorno.
>
>

## <a name="delete-a-dlp-policy"></a>Eliminación de una directiva DLP

1. Inicie el [centro de administración](https://admin.flow.microsoft.com)de.

1. Seleccione la pestaña **directivas de datos** en el lado izquierdo.

    ![pestaña seleccionar directivas de datos](./media/prevent-data-loss/2.png)

1. Busque en la lista de directivas de DLP existentes y seleccione el botón Eliminar junto a la Directiva que desea eliminar:

    ![Seleccione el botón eliminar](./media/prevent-data-loss/3-delete.png)

1. Confirme que realmente desea eliminar la Directiva; para ello, seleccione el botón **eliminar** :

    ![Confirme que realmente desea eliminar la Directiva.](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Permisos de directiva de DLP

Solo los administradores de inquilinos y de entornos pueden crear y modificar directivas de DLP. Obtenga más información sobre los permisos en el artículo sobre [entornos](environments-overview-admin.md) .


## <a name="custom-and-http-connectors"></a>Conectores HTTP y personalizados

Los conectores personalizados y HTTP se deben agregar a DLPs mediante una plantilla de Microsoft Flow o un PowerShell.

> [!TIP]
> No se puede cambiar de la versión de esquema 2018-11-01. No se puede quitar la compatibilidad con HTTP de una directiva. Si intenta quitar la compatibilidad con HTTP, la Directiva DLP podría estar dañada. Además, si se actualiza una directiva de DLP para admitir conectores HTTP, es posible que los flujos actuales que usan estas funcionalidades HTTP se cierren.

Estos son los conectores HTTP que se pueden agregar a una directiva:

- HTTP (y HTTP + Swagger)
- Webhook HTTP
- Solicitud HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Adición de conectores personalizados y conectores HTTP con plantillas

Para agregar un conector personalizado a una Directiva mediante una [plantilla](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), escriba el nombre de la Directiva, el grupo al que se va a agregar el conector y el nombre, el identificador y el tipo del conector. Ejecute el flujo una vez para agregar el conector personalizado a la Directiva y al grupo especificados.

Para agregar los conectores HTTP a una directiva existente a través de la [plantilla](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), escriba el nombre de la Directiva a la que desea agregar y, a continuación, ejecute el flujo.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Incorporación de conectores personalizados y HTTP con PowerShell

Para agregar compatibilidad con conectores personalizados o conectores HTTP a una Directiva mediante PowerShell, [Descargue](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) e importe los scripts de PowerShell de PowerApps más recientes y, después, use estos cmdlets: "New-AdminDlpPolicy", "Set-AdminDlpPolicy", " Add-CustomConnectorToPolicy ' y ' Remove-CustomConnectorFromPolicy ' para modificar la Directiva. Use el cmdlet "Get-Help-detailed" como referencia.


> [!IMPORTANT]
> Use la versión del esquema 2018-11-01 al crear o actualizar una directiva DLP para incluir conectores HTTP. La adición de compatibilidad con HTTP mediante la plantilla o PowerShell solo afectará a la Directiva especificada. Las nuevas directivas creadas a través del centro de administración no contendrán los conectores HTTP.



## <a name="next-steps"></a>Pasos siguientes

* [Más información acerca de los entornos](environments-overview-admin.md)
* [Más información sobre Microsoft Flow](getting-started.md)
* [Más información sobre el centro de administración](admin-center-introduction.md)
* [Más información sobre la integración de datos](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
