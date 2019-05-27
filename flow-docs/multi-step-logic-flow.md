---
title: Adición de varias acciones y una opción avanzada | Microsoft Docs
description: Expanda un flujo para incluir una opción avanzada, como la configuración el correo electrónico para que tenga alta prioridad y agregar otra acción al mismo evento.
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
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9dd2aed8b8cdb1f0a8e673c5466291f60baaf41d
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "64466531"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Agregar varias acciones y opciones avanzadas a un flujo
Para personalizar un flujo, agregue una o varias opciones avanzadas y varias acciones al mismo desencadenador. Por ejemplo, agregue una opción avanzada que envíe un mensaje de correo electrónico con prioridad alta. Además de enviar correo cuando se agrega un elemento a una lista de SharePoint, cree un archivo en Dropbox que contenga la misma información.

## <a name="prerequisites"></a>Requisitos previos
* [Crear un flujo](get-started-logic-flow.md)

## <a name="add-another-action"></a>Adición de otra acción
En este procedimiento, agregará una acción en el medio del flujo. Dicha acción guardará un archivo en Dropbox y archivar el elemento en la lista.

1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.
2. En la lista de flujos, seleccione el flujo que quiere editar.
3. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![Agregar contraído](./media/multi-step-logic-flow/add-action.png)
4. En la lista de acciones posibles, busque **Crear archivo** y seleccione **Dropbox - Crear archivo**.
   
    ![buscar crear archivo](./media/multi-step-logic-flow/create-file-search.png)
5. Si se le solicita, especifique las credenciales de Dropbox.
6. Seleccione el icono de carpeta en el lado derecho del cuadro **Ruta de acceso a la carpeta**.
7. Busque y seleccione la carpeta en la que desea colocar el nuevo archivo.
   
    ![buscar crear archivo](./media/multi-step-logic-flow/create-file-folder.png)
8. Escriba el nombre del nuevo archivo en el cuadro **Nombre de archivo**. Asegúrese de anexar una extensión, por ejemplo, ".txt", al nombre del archivo. En este caso, vamos a usar **TweetId** en el nombre del archivo para garantizar la unicidad de los archivos. Es posible que tenga que seleccionar **Ver más** para encontrar el token **TweetId**.
9. Agregue el texto que desea que contenga el archivo escribiendo en el cuadro **Contenido del archivo**. También puede agregar tokens en el cuadro **Contenido del archivo**.
   
    ![nombre de archivo y contenido](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Si asigna al archivo un nombre que coincida con el nombre de un archivo existente (de la carpeta seleccionada), se sobrescribirá el archivo existente.
   > 
   > 
10. Seleccione **Actualizar flujo**, que se encuentra en el menú situado en la parte superior de la pantalla.
11. Envíe un tweet que contenga la palabra clave que ha especificado.
    
     Al cabo de un minuto, se crea un archivo en su cuenta de Dropbox.

## <a name="reorder-or-delete-an-action"></a>Reordenación o eliminación de acciones
* Para recibir correo electrónico después de que se haya creado el archivo en Dropbox, mueva la acción de Dropbox arrastrando su barra de título hasta que quede encima de la acción del correo electrónico. Suelte la acción de Dropbox sobre la flecha situada entre el desencadenador (**Cuando se publica un tweet nuevo**) y la acción de correo electrónico. (El cursor indica si la acción está correctamente situada).
  
  > [!NOTE]
  > No puede mover un paso delante de otro si usa los resultados de dicho paso.
  > 
  > 
  
    ![Eliminar el menú](./media/multi-step-logic-flow/draggingaction.png)
* Para eliminar una acción, seleccione los puntos suspensivos (...) que están cerca del borde derecho de la barra de título de la acción que desea eliminar, seleccione **Eliminar** y, luego, seleccione **Aceptar**.
  
    ![Eliminar el menú](./media/multi-step-logic-flow/deletemenu.png)
  
     **Nota**: No se puede eliminar una acción si usa los resultados de ella en cualquier lugar en el flujo. Una vez que quite los resultados de los campos, podrá eliminar la acción.

## <a name="add-advanced-options"></a>Agregar opciones avanzadas
Comience con un flujo que tenga una acción **Enviar un correo electrónico**.

1. Seleccione **Mostrar opciones avanzadas**, que se encuentra en la parte inferior de la tarjeta **Enviar un correo electrónico**.
   
     Verá las opciones avanzadas para enviar un correo electrónico.
   
    ![Desencadenadores de SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Seleccione **Alta** en la lista **Importancia** y, después, seleccione **Ocultar opciones avanzadas** para ocultarlas.
3. Seleccione **Actualizar flujo**, que se encuentra en el menú situado en la parte superior de la pantalla.
   
     Este paso guarda los cambios.

