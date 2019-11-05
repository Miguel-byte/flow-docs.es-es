---
title: Más información acerca de los entornos de Microsoft Flow | Microsoft Docs
description: Aprenda a usar entornos para aislar los flujos
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
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547933"
---
# <a name="choosing-an-environment"></a>Elección de un entorno
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se explica cómo Microsoft Flow **entornos** en los que puede crear y aislar de forma segura los flujos, las puertas de enlace, las conexiones y otros recursos.

Aprenderá lo siguiente:

* Características que proporcionan los entornos.
* Cambiar entre entornos.
* Cómo crear un flujo en el entorno adecuado.

## <a name="environments-overview"></a>Información general sobre entornos

Cuando se crea un flujo, se elige un entorno para hospedar el flujo y los recursos que usa el flujo. Puede usar entornos independientes para diferentes escenarios.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Estos son algunos escenarios para el uso de entornos

Escenario|Norma
-----|-----
Desea crear un flujo que use una conexión a Microsoft Common Data Service.|Coloque el flujo y el Common Data Service en el mismo entorno. Esto garantiza que todos los datos se aíslan dentro de ese entorno (límite de aislamiento).
Está creando un flujo para el Departamento de recursos humanos. Desea asegurarse de que solo los usuarios del Departamento de recursos humanos tienen acceso al flujo.|Cree un entorno y agréguele solo los usuarios de recursos humanos. Coloque el flujo y cualquier otro recurso que use el flujo en este entorno.
Hay usuarios en Europa que utilizan un flujo para Mostrar datos de SharePoint.|Cree un entorno en Europa y, a continuación, cree el flujo y la conexión de SharePoint en él. Este entorno de Europa ofrece a los usuarios europeos el mejor rendimiento, ya que todos los recursos son locales en Europa (localidad de datos).

Para crear entornos, debe ser un administrador de Microsoft Flow. Los administradores controlan quién tiene acceso a los entornos. Para más información sobre cómo crear y administrar entornos, consulte el tema [administrar entornos](environments-overview-admin.md) .

## <a name="switching-environments"></a>Cambio de entornos

Microsoft Flow facilita el cambio entre entornos. Al cambiar de entorno, solo verá los elementos creados en ese entorno específico; no podrá ver ni tener acceso a los elementos de ningún otro entorno.

A continuación se muestra un ejemplo.

Ha creado un flujo denominado *NewEmployee* en el entorno de *recursos humanos* . En [Microsoft Flow](https://flow.microsoft.com), abra el entorno de *ventas* . El flujo *NewEmployee* no aparece en la lista. Para ver el flujo *NewEmployee* , abra el entorno de *recursos humanos* . Recuerde que las mismas reglas se aplican a cualquier otro elemento que haya creado en el entorno, incluidas las conexiones, las puertas de enlace, los flujos, etc.

Siga estos pasos para cambiar de entorno:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. En la esquina superior derecha, verá una imagen que representa el perfil.

   ![imagen de perfil](./media/environments-overview-maker/default-environment.png)

1. Seleccione la imagen. En una lista desplegable se muestran todos los entornos disponibles. Se comprueba el entorno en el que está conectado actualmente:

   ![imagen de la lista de entornos](./media/environments-overview-maker/all-environments.png)
1. Para cambiar a otro entorno, seleccione ese entorno en la lista:

   ![seleccionar un entorno al que cambiar](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow cambia al nuevo entorno.

## <a name="create-flows-in-the-right-environment"></a>Crear flujos en el entorno adecuado

Antes de crear un flujo, seleccione el entorno en el que va a agregar el flujo y sus recursos.

> [!NOTE]
> Si crea un flujo en un entorno equivocado, tendrá que eliminarlo y, a continuación, crearlo en el entorno correcto.

Tenga en cuenta los siguientes factores al elegir un entorno para hospedar los flujos:

* Solo puede crear puertas de enlace en el entorno predeterminado. Por lo tanto, si desea utilizar una puerta de enlace para conectar el flujo a datos locales, deberá usar el entorno predeterminado.
* Las bases de datos de Microsoft Common Data Service están asociadas a un entorno específico. Por lo tanto, si desea crear un flujo que use el Common Data Service, debe crear el flujo en el entorno que hospeda la base de datos.
* Verá todos los entornos en los que puede editar recursos. Sin embargo, deberá pedir a un administrador que le agregue como creador a todos los entornos en los que desea crear flujos.

> [!NOTE]
> Siempre podrá crear flujos en el entorno predeterminado.

## <a name="next-steps"></a>Pasos siguientes

* [Creación de un flujo a partir de una plantilla](get-started-logic-template.md)
* [Creación de un flujo](get-started-logic-flow.md)
* [Información general del entorno para administradores](environments-overview-admin.md)
