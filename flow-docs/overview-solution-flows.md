---
title: Información general de los flujos que reconocen soluciones | Microsoft Docs
description: Obtenga información sobre las ventajas de la creación de flujos en las soluciones.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548561"
---
# <a name="overview"></a>Visión
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Al hospedar los flujos en una [solución](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), estos se convierten en portátiles, lo que dificulta su traslado y todos sus componentes de un entorno a otro. Un caso de uso típico es que un fabricante de software independiente (ISV) desarrolle flujos en un entorno de espacio aislado y, a continuación, mueva esos flujos a un entorno de prueba. Después de la prueba, el ISV trasladaría los flujos a un entorno de producción para los clientes que compran estos flujos. Este proceso es mucho más fácil cuando se crean flujos en soluciones y, a continuación, se mueven las soluciones y su contenido.

Los flujos que se crean dentro de una solución se conocen como flujos *con reconocimiento de la solución* . Puede agregar varios flujos en una única solución.

> [!NOTE] 
> No se pueden trasladar flujos no compatibles con soluciones (flujos no creados en una solución) a una solución.

## <a name="prerequisites"></a>Requisitos previos

Debe tener los siguientes componentes para crear soluciones y flujos compatibles con soluciones:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Un entorno con la versión 9.1.0.267 o posterior.

  Para comprobar su versión, vaya a [Microsoft Flow centro de administración](https://admin.flow.microsoft.com), seleccione **entornos**, seleccione el entorno que le interese y, a continuación, seleccione la pestaña **detalles** .

## <a name="create-a-solution"></a>Crear una solución

Siga estos pasos para crear una solución:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
1. Seleccione **soluciones** en la barra de navegación.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Seleccione **+ nueva solución**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Proporcione toda la información necesaria para la nueva solución, incluidos **el nombre para mostrar**, el **publicador**, la **versión**y **el nombre**. También es una buena idea proporcionar una descripción de la solución.

   ![](./media/overview-solution-flows/new-solution.png)

1. Seleccione **Guardar y cerrar** en el menú de la parte superior.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   La nueva solución podría aparecer como esta imagen:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Seleccione **soluciones** para actualizar la lista de soluciones si la nueva solución no aparece.

## <a name="learn-more"></a>Aprende más

- [Creación de un flujo en una solución](./create-flow-solution.md)
- [Exportar una solución](./export-flow-solution.md)
- [Importar una solución](./import-flow-solution.md)
- [Editar un flujo compatible con soluciones](./edit-solution-aware-flow.md)
- [Quitar un flujo compatible con soluciones](./remove-solution-aware-flow.md)
