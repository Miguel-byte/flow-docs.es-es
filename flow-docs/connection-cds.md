---
title: Cree un flujo automatizado con Common Data Service | Microsoft Docs
description: Crear flujos de trabajo mediante una conexión Common Data Service y Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547113"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Creación de un flujo automatizado mediante el uso de Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Con el conector de Common Data Service, puede crear flujos que se inician mediante la creación y actualización de eventos en la base de datos de Common Data Service. Además, puede realizar acciones de creación, actualización, recuperación y eliminación en los registros de la base de datos de Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Iniciar un flujo desde Common Data Service

Puede usar cualquiera de los siguientes desencadenadores para iniciar el flujo:

- Cuando se selecciona un registro
- Cuando se crea un registro
- Cuando se elimina un registro
- Cuando se actualiza un registro


> [!div class="mx-imgBorder"]
> ![seleccionar un desencadenador](./media/cds-connector/Triggers.png)

Si el desencadenador seleccionado requiere que se seleccione un entorno, puede elegir `(Current)`, que siempre usará la base de datos en el entorno en el que se ejecuta Microsoft Flow. Si desea que el flujo se desencadene siempre en función de un evento en un entorno específico, seleccione ese entorno.

> [!div class="mx-imgBorder"]
> ![elegir entorno](./media/cds-connector/Environments.png)

Puede usar ámbitos para determinar si el flujo se ejecuta si crea un nuevo registro, si un usuario de la unidad de negocio crea un nuevo registro o si un nuevo registro lo crea cualquier usuario de la organización.

> [!div class="mx-imgBorder"]
> ![elija el ámbito](./media/cds-connector/Scopes.png)

|ID|Temporización del desencadenador|
| --- | --- |
|Unidad de negocio|La acción se realiza en un registro propiedad de la unidad de negocio|
|Organización|Cualquier persona de la organización o la base de datos realiza la acción|
|Primario: unidad de negocio secundaria|La acción se realiza en un registro propiedad de la unidad de negocio o de una unidad de negocio secundaria|
|Usuario|La acción se realiza en un registro que es propiedad del usuario|

Los desencadenadores que se ejecutan cuando se actualiza un registro también pueden utilizar atributos de filtrado. Esto garantiza que el flujo solo se ejecuta cuando se actualiza cualquiera de los atributos definidos.

> [!IMPORTANT]
> Use atributos de filtro para evitar que el flujo se ejecute de forma innecesaria.

Este flujo se desencadena cada vez que se actualiza el primer o el último nombre del contacto que posee el usuario del flujo.

> [!div class="mx-imgBorder"]
> ![atributos de filtro](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Desencadenar privilegios

Para crear un flujo que se desencadene en función de crear, actualizar o eliminar en un registro, el usuario debe tener permisos de nivel de usuario para crear, leer, escribir y eliminar en la entidad de registro de devolución de llamada. Además, en función de los ámbitos definidos, es posible que el usuario necesite al menos ese nivel de lectura en la misma entidad.  [Más información](https://docs.microsoft.com/power-platform/admin/database-security) sobre la seguridad del entorno.

## <a name="write-data-into-common-data-service"></a>Escribir datos en Common Data Service

Use cualquiera de las siguientes acciones para escribir datos en Common Data Service:

- Crear un nuevo registro
- Actualizar un registro

Este es un ejemplo de cómo crear una tarea de seguimiento cuando el usuario especificado crea un nuevo registro de cuenta.  

> [!div class="mx-imgBorder"]
> tarea de seguimiento de ![](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Conceptos avanzados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Escribir datos en los campos de cliente, propietario y referentes

Para escribir datos en los campos de cliente, propietario y referente a, se deben rellenar dos campos.

| Categoría de campo | Configuración de ejemplo |
| --- | --- |
| Sobre | En relación con el identificador del registro (por ejemplo, ID. de cuenta) y el tipo con respecto a la selección de la lista. |
| Cliente | Representa el identificador del registro y el tipo de cliente tal como se seleccionó en la lista. |
| Propietario | Representa el identificador del usuario o equipo del sistema y el tipo de propietario tal como se seleccionó en la lista. |

### <a name="enable-upsert-behavior"></a>Habilitar el comportamiento de Upsert

Puede aprovechar el comando **actualizar un registro** para proporcionar acciones de Upsert, que actualiza el registro si ya existe o crea un nuevo registro. Para invocar Upsert, proporcione la entidad y una clave GUID. Si existe el registro con el tipo y la clave especificados, se produce una actualización. De lo contrario, se crea un registro con la clave especificada.

### <a name="trigger-behavior"></a>Comportamiento del desencadenador

Si tiene un desencadenador registrado en la actualización de un registro, el flujo se ejecuta para cada actualización *confirmada* en el registro especificado. El servicio invoca el flujo de forma asincrónica y con la carga que captura en el momento en que se produce la invocación.

> [!NOTE]
> Si tiene dos actualizaciones que se producen en unos segundos, el flujo se puede desencadenar más de una vez con el contenido de la versión más reciente.

Las ejecuciones de Flow se pueden retrasar si hay un trabajo pendiente de trabajos del sistema en su entorno.  Si se produce este retraso, el flujo se desencadena cuando se ejecuta el trabajo del sistema para invocar el flujo.
