---
title: Common Data Service | Microsoft Docs
description: Cree un flujo para importar datos, exportar datos o crear aprobaciones con el Common Data Service.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546961"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Cree un flujo que use el Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Mejore la eficacia operativa con una vista unificada de los datos empresariales mediante la creación de un flujo que use el [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implemente esta base de datos empresarial segura que incluye entidades de negocio estándar con el formato correcto (como ventas, compras, servicio de atención al cliente y productividad) en su organización. Almacene los datos de la organización en una o varias [entidades personalizadas](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), que ofrecen varias ventajas sobre los orígenes de datos externos, como Microsoft Excel y Salesforce.

Por ejemplo, aproveche el Common Data Service dentro de Microsoft Flow de estas maneras clave:

* Cree un flujo para importar datos, exportar datos o realizar acciones en la parte superior de los datos (por ejemplo, enviar una notificación). Tenga en cuenta que este enfoque no es un servicio de sincronización completo; simplemente permite trasladar datos de una en una cada entidad.
  
    Para obtener pasos detallados, consulte los procedimientos que se describen más adelante en este tema.
* En lugar de [crear un bucle de aprobación a través del correo electrónico](wait-for-approvals.md), cree un flujo que almacene el estado de aprobación en una entidad y cree una aplicación personalizada en la que los usuarios puedan aprobar o rechazar los elementos.
  
    Para obtener pasos detallados, consulte [crear un bucle de aprobación con el Common Data Service](common-data-model-approve.md).

**Requisitos previos**

* Regístrese en [Microsoft Flow](https://flow.microsoft.com) y [PowerApps](https://web.powerapps.com).
  
    Si tiene problemas, compruebe si [Microsoft Flow](sign-up-sign-in.md) y [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) admiten el tipo de cuenta que tiene y si la organización no ha bloqueado la suscripción.
* Si no ha usado el Common Data Service antes, abra la pestaña **entidades** de [powerapps.com](https://web.powerapps.com/#/entities)y, a continuación, haga clic o pulse en **crear mi base de datos**.

## <a name="sign-in-to-your-environment"></a>Iniciar sesión en su entorno
1. Abra el [portal de Microsoft Flow](https://flow.microsoft.com)y, a continuación, haga clic o pulse en **iniciar sesión** en la esquina superior derecha.
   
    **Nota**: es posible que tenga que abrir el menú de la parte superior izquierda para mostrar el botón **iniciar sesión** .
   
    ![Inicia sesión](./media/common-data-model-intro/signin-flow.png)
2. En el menú de la parte superior derecha, seleccione el entorno en el que creó la base de datos en powerapps.com.
   
    **Nota**: Si no selecciona el mismo entorno, no verá las entidades.
   
    ![Seleccionar entorno](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Abrir una plantilla
1. En el cuadro **plantillas de búsqueda** de la parte superior de la pantalla, escriba o pegue **común**y, a continuación, presione Entrar.
   
    ![Buscar plantillas](./media/common-data-model-intro/template-search.png)
2. En la lista de plantillas, pulse o haga clic en la plantilla que importa los datos del origen que desee en la entidad (u *objeto*) que desee.
   
    Por ejemplo, haga clic o pulse en la plantilla que copia la información de contacto de Dynamics 365 en el Common Data Service.
   
    ![Elegir una plantilla](./media/common-data-model-intro/choose-template.png)
3. Pulse o haga clic en **usar esta plantilla**.
   
    ![Usar plantilla](./media/common-data-model-intro/use-template.png)
4. Si aún no ha creado una conexión desde Microsoft Flow a Dynamics 365, pulse o haga clic en **iniciar sesión**y, después, proporcione sus credenciales si se le solicitan.
   
    ![Inicio de sesión en Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Pulse o haga clic en **continuar**.
   
    ![Confirmar cuentas](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Compilación del flujo
1. En la primera tarjeta, especifique el evento que desencadenará el flujo.
   
    Por ejemplo, va a crear un flujo que copiará contactos nuevos de una instancia de Dynamics 365 en el Common Data Service. En **al crear un registro**, especifique la instancia haciendo clic o pulsando en la flecha hacia abajo y, a continuación, haciendo clic o pulsando en una opción de la lista que aparece.
   
    ![Especificar la instancia de Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. opta Cerca de la parte superior de la pantalla, especifique un nombre diferente para el flujo que está creando.
   
    **Nota**: Si la ventana del explorador no está maximizada, la interfaz de usuario podría tener un aspecto ligeramente diferente.
   
    ![Flujo de nombres](./media/common-data-model-intro/name-flow.png)
3. Pulse o haga clic en **Crear flujo**.
   
    **Nota**: Si la ventana del explorador no está maximizada, solo puede aparecer la marca de verificación.
   
    ![Crear flujo](./media/common-data-model-intro/create-flow.png)

Ahora, cada vez que se cree el objeto en el sistema de origen, se importará en el Common Data Service. Si no encuentra una plantilla que requiera lo que necesita, puede [crear un flujo desde cero](get-started-logic-flow.md) que opere sobre el Common Data Service.

Puede realizar acciones en los cambios de la base de datos. Por ejemplo, puede enviar correo de notificación cada vez que cambien los datos.

