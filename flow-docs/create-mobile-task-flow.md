---
title: Creación de un flujo de tareas móviles con PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546423"
---
# <a name="create-a-mobile-task-flow"></a>Crear un flujo de tareas móviles
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Diseñe un flujo en Dynamics 365 para teléfonos o Dynamics 365 para tabletas basadas en las tareas comunes que realizan los usuarios. Por ejemplo, si necesitan realizar regularmente una serie de pasos de seguimiento después de las reuniones de cliente, cree un flujo de tareas. Cuando los usuarios tocan la nueva tarea en su aplicación móvil, se dirigirán de principio a fin para que no olviden un paso importante.  
  
 Los flujos de tareas pueden usar la lógica y los formularios de varias entidades, y pueden tener lógica de formulario que se ejecuta en las páginas de flujo de tareas.  
  
## <a name="create-a-task-flow"></a>Crear un flujo de tareas
  
1. Asegúrese de que tiene el rol de seguridad Administrador del sistema o Personalizador del sistema o permisos equivalentes. Los roles de seguridad Director de administrador, vicepresidente o director general también pueden crear flujos de tareas móviles. 
  
2. Abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y seleccione **procesos**.  
  
3.  En la barra de herramientas **acciones** , seleccione **nuevo**.  
  
4.  En el cuadro de diálogo **Crear proceso** , complete los campos obligatorios:  
  
    -   Escriba un nombre de proceso.  
  
    -   En la lista **categoría** , seleccione **flujo de procesos empresariales**.  
  
    -   En la lista **entidad** , seleccione la entidad que desee.  
  
5.  Seleccione la opción **Ejecutar proceso como flujo de tareas (móvil en línea)** .  
  
6.  Seleccione **Aceptar**.
  
     El diseñador de flujo de tareas se abre en una nueva ventana.  
  
     ![Ventana del diseñador de flujo de tareas](media/task-flow-designer-window.png "Ventana del diseñador de flujo de tareas") 
  
7.  Si los usuarios van progresando de una página a otra en orden, arrastre el componente de **Página** desde la pestaña **componentes** en el lado derecho de la pantalla y colóquelo en el signo + en el lugar adecuado. Para agregar un nombre a una página, seleccione la página, seleccione la pestaña **propiedades** , escriba un nuevo nombre y, a continuación, seleccione **aplicar**.  
  
8.  Para agregar una rama al flujo de tareas, arrastre el componente **condición** desde la pestaña **componentes** y colóquelo en el signo + en el punto adecuado. Para establecer las propiedades de la condición, seleccione la condición, establezca las propiedades en la pestaña **propiedades** y, a continuación, seleccione **aplicar**.  
  
    > [!NOTE]
    >  A medida que agrega páginas y condiciones al flujo de tareas, verá un minimapa en la esquina inferior izquierda de la ventana en la que se muestran todas las páginas y condiciones del flujo de tareas.  
  
9. Para agregar una etiqueta de campo, etiqueta o sección a una página, arrastre la etiqueta **campo**, **etiqueta**o **sección** desde la pestaña **componentes** a la página correspondiente. Para cambiar las propiedades de uno de estos elementos, seleccione el elemento, establezca las propiedades en la pestaña **propiedades** y, a continuación, seleccione **aplicar**.  
  
10. Para validar el flujo de tareas, seleccione **validar** en la barra de acciones.  
  
11. Para guardar el proceso como borrador, seleccione **Guardar** en la parte superior de la pantalla. (Siempre que un proceso sea un borrador, los usuarios no podrán utilizarlo).  
  
12. Para activar el flujo de tareas para que los usuarios puedan usarlo, seleccione **Activar**.  
  
> [!TIP]
>  Estas son algunas sugerencias que hay que tener en cuenta al trabajar en el flujo de tareas en la ventana del diseñador:  
>   
> -  Para tomar una instantánea de todo en la ventana flujo de tareas, seleccione **instantánea** en la barra de acciones.  
> -  Para conectar un componente válido a otro componente válido en el diseñador, seleccione **conector** en la barra de acciones.  
> -  Puede hacer que las imágenes de la pantalla sean más grandes o más pequeñas si selecciona los botones **aumentar el nivel de zoom** o **reducir el nivel de zoom** en la esquina superior derecha de la pantalla. Seleccione el botón **ajustar al lienzo para colocar** las imágenes hasta el tamaño más grande que quepa en la pantalla.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Crear un flujo de procesos empresariales](create-business-process-flow.md)   

