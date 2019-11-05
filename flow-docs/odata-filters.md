---
title: Filtrar y copiar datos | Microsoft Docs
description: Aprenda a filtrar y copiar datos de un origen a un destino con Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: be5863c51e17bdba32d79891725a81b386ec2e90
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548923"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Filtrar y copiar datos con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
En este tutorial se muestra cómo crear un flujo que supervisa un origen de elementos nuevos o modificados y, a continuación, copia los cambios en un destino. Puede crear un flujo como este si los usuarios escriben datos en una ubicación, pero el equipo los necesita en una ubicación o formato diferente.

Aunque este tutorial copia los datos de una [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) de Microsoft SharePoint (el origen) a una tabla de [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (el destino), puede copiar los datos entre cualquiera de los servicios de más de [150](https://flow.microsoft.com/connectors/) que admite Microsoft Flow.

> [!IMPORTANT]
> Los cambios que realice en el destino no se copiarán en el origen porque no se admiten las sincronizaciones bidireccionales. Si intenta configurar una sincronización bidireccional, creará un bucle infinito en el que los cambios se envían indefinidamente entre el origen y el destino.
> 
> 

## <a name="prerequisites"></a>Requisitos previos
* Acceso a un origen de datos y un destino. En este tutorial no se incluyen los pasos para crear el origen y el destino.
* Acceso a [Microsoft Flow](https://flow.microsoft.com).
* Un conocimiento básico de cómo se almacenan los datos.
* Familiaridad con los conceptos básicos de la creación de flujos. Puede revisar cómo agregar [acciones, desencadenadores](multi-step-logic-flow.md#add-another-action)y [condiciones](add-condition.md). En los pasos siguientes se da por hecho que sabe cómo realizar estas acciones.

> [!TIP]
> No es necesario que coincidan todos los nombres de columna del origen y del destino, pero debe proporcionar datos para todas las columnas *necesarias* al insertar o actualizar un elemento. Microsoft Flow identifica los campos obligatorios.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Información general rápida de los pasos
Si está familiarizado con Microsoft Flow, siga estos pasos rápidos para copiar datos de un origen de datos a otro:

1. Identifique el origen que va a supervisar y el destino en el que va a copiar los datos modificados. Confirme que tiene acceso a ambos.
2. Identifique al menos una columna que identifique de forma única los elementos en el origen y el destino. En el ejemplo siguiente, usamos la columna **title** , pero puede usar las columnas que desee.
3. Configure un desencadenador que supervise los cambios en el origen.
4. Busque el destino para determinar si el elemento modificado existe.
5. Use una **condición** similar a la siguiente:
   * Si el elemento nuevo o modificado no existe en el destino, créelo.
   * Si el elemento nuevo o modificado existe en el destino, actualícelo.
6. Desencadene el flujo y, a continuación, confirme que los elementos nuevos o modificados se están copiando desde el origen al destino.

> [!NOTE]
> Si no ha creado una conexión a SharePoint o Azure SQL Database anteriormente, siga las instrucciones cuando se le pida que inicie sesión.
> 
> 

Estos son los pasos detallados para crear el flujo.

## <a name="monitor-the-source-for-changes"></a>Supervisar el origen de los cambios
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com), seleccione **Mis flujos** > **crear desde**cero.
2. Busque **sharepoint** > seleccione el desencadenador **SharePoint-cuando se crea o modifica un elemento** de la lista de desencadenadores.
3. Escriba la **dirección del sitio** y, a continuación, seleccione el **nombre de lista** en la tarjeta **cuando se crea o modifica un elemento** .
   
    Proporcione la **dirección del sitio** y el **nombre de lista** de la lista de SharePoint que el flujo supervisa para los elementos nuevos o actualizados.
   
    ![configurar el desencadenador de SharePoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Buscar el elemento nuevo o modificado en el destino
Usamos la acción **SQL Server-obtener filas** para buscar el elemento nuevo o modificado en el destino.

1. Seleccione **nuevo paso** > **Agregar una acción**.
2. Busque **obtener filas**, seleccione **SQL Server-obtener filas**y, a continuación, seleccione la tabla que desea supervisar en la lista **nombre de tabla** .
3. Seleccione **Mostrar opciones avanzadas**.
4. En el cuadro de **consulta de filtro** , escriba el **título EQ '** , seleccione el token de **título** de la lista de contenido dinámico y, a continuación, escriba **'** .
   
    En el paso anterior se supone que está coincidentes con los títulos de las filas en el origen y en el destino.
   
    La tarjeta **obtener filas** debe ser ahora similar a la de esta imagen:
   
    ![intentar obtener el elemento de la base de datos de destino](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Compruebe si se encontró el elemento nuevo o modificado
Seleccione **nuevo paso** > **Agregar una condición** para abrir la tarjeta **condición** .

En la tarjeta condición:

1. Active la casilla de la izquierda.
   
    Se abre la lista **agregar contenido dinámico de las aplicaciones y conectores que se usan en este flujo** .
2. Seleccione **valor** en la categoría **obtener filas** .
   
   > [!TIP]
   > Confirme que ha seleccionado **valor** en la categoría **obtener filas** . No seleccione el **valor** en la categoría **cuando se crea o modifica un elemento** .
   > 
   > 
3. Seleccione **es igual a** en la lista del cuadro centro.
4. Escriba **0** (cero) en el cuadro del lado derecho.
   
    La tarjeta **condición** se parece ahora a esta imagen:
   
    ![configuración de una condición](media/odata-filters/configure-condition.png)
5. Seleccione **Editar en modo avanzado**.
   
    Cuando se abra el modo avanzado, verá **\@es igual a (cuerpo (' Get_rows ')? [' valor '], 0)** expresión en el cuadro. Edite esta expresión agregando la **longitud ()** alrededor del **cuerpo (' Get_items ')? [' función Value ']** . La expresión completa tiene ahora el siguiente aspecto: **@equals(longitud (' Get_rows ')? [' valor ']), 0)**
   
    La tarjeta **condición** se parece ahora a esta imagen:
   
    ![configuración de una condición](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Agregar la función **length ()** permite que el flujo Compruebe la lista de **valores** y determine si contiene elementos.
   > 
   > 

Cuando el flujo "obtiene" elementos del destino, hay dos resultados posibles.

| Enlace | Paso siguiente |
| --- | --- |
| El elemento existe |[Actualizar el elemento](odata-filters.md#update-the-item-in-the-destination) |
| El elemento no existe |[Crear un nuevo elemento](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Las imágenes de las tarjetas **Insertar fila** y **Actualizar fila** que se muestran a continuación pueden diferir de las suyas, ya que estas tarjetas muestran los nombres de las columnas de la tabla Azure SQL Database que se está usando en el flujo.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Crear el elemento en el destino
Si el elemento no existe en el destino, créelo mediante la acción **SQL Server-Insertar fila** .

En la rama en **caso afirmativo** de la **condición**:

1. Seleccione **Agregar una acción**, busque **Insertar fila**y, a continuación, seleccione **SQL Server-Insertar fila**.
   
    Se abre la tarjeta **Insertar fila** .
2. En la lista **nombre de tabla** , seleccione la tabla en la que se insertará el nuevo elemento.
   
    La tarjeta **Insertar fila** se expande y muestra todos los campos de la tabla seleccionada. Los campos con un asterisco (*) son necesarios y se deben rellenar para que la fila sea válida.
3. Seleccione cada campo que desee rellenar y escriba los datos.
   
    Puede escribir los datos manualmente, seleccionar uno o más tokens del **contenido dinámico**, o escribir cualquier combinación de texto y tokens en los campos.
   
    La tarjeta **Insertar fila** ahora es similar a esta imagen:
   
    ![configuración de una condición](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Actualizar el elemento en el destino
Si el elemento existe en el destino, actualícelo con los cambios.

1. Agregue la acción **SQL Server-actualizar fila** a la rama **If no** de la **condición**.
2. Siga los pasos de la sección [creación del elemento](odata-filters.md#create-the-item-in-the-destination) de este documento para rellenar los campos de la tabla.
   
    ![Ver entornos](media/odata-filters/update-row.png)
3. En la parte superior de la página, escriba un nombre para el flujo en el cuadro **nombre de flujo** y, a continuación, seleccione **Crear flujo** para guardarlo.
   
    ![asignar un nombre al flujo](media/odata-filters/give-the-flow-a-name.png)

Ahora, cada vez que un elemento de la lista de SharePoint (origen) cambia, el flujo se desencadena e inserta un nuevo elemento o actualiza un elemento existente en el Azure SQL Database (destino).

> [!NOTE]
> El flujo no se desencadena cuando se elimina un elemento del origen. Si se trata de un escenario importante, considere la posibilidad de agregar una columna independiente que indique si ya no se necesita un elemento.
> 
> 

## <a name="learn-more"></a>Aprende más
Use [operaciones de datos](data-operations.md) en los flujos.

