---
title: Obtenga información acerca de cómo automatizar tareas repetitivas con flujos de botones que aceptan datos proporcionados por el usuario | Microsoft Docs
description: Microsoft Flow facilita la automatización de tareas repetitivas. Los flujos pueden incluso tomar entradas del usuario al ejecutar una tarea repetitiva.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a1bc5161bdd0e6a098d57cefafba99d3c89e6c97
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546462"
---
# <a name="introducing-button-flows-with-user-input"></a>Introducción de los flujos de botones con datos proporcionados por el usuario
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cree un flujo de botones para ejecutar tareas rutinarias simplemente punteando un botón. Personalice el flujo permitiendo al usuario proporcionar detalles específicos que se usarán cuando se ejecute el flujo. Este tema le guía a través de la creación de un flujo de botones que toma la entrada del usuario y, a continuación, ejecuta el flujo de botones, resaltando cómo proporcionar la entrada del usuario.

Puede crear un flujo de botón en el sitio web de Microsoft Flow o en la aplicación móvil para Microsoft Flow. En este tema, usará el sitio Web.

### <a name="prerequisites"></a>Requisitos previos
* Una cuenta en el sitio web de Microsoft Flow.

## <a name="open-the-template"></a>Abrir la plantilla
1. Inicie sesión en el [sitio web de Microsoft Flow](https://flow.microsoft.com), escriba **Visual Studio** en el cuadro de búsqueda y, a continuación, haga clic o pulse en el icono de búsqueda para buscar todas las plantillas relacionadas con Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Seleccione la plantilla **abrir un error de prioridad 2 en Visual Studio** :
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Seleccione **el botón usar esta plantilla** :
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Esta plantilla usa el Visual Studio Team Services (VSTS) y los servicios de notificaciones de extracción. Tendrá que iniciar sesión en estos servicios si no tiene una conexión a ninguno de ellos. El botón **iniciar sesión** solo aparecerá si necesita iniciar sesión en un servicio.
4. Después de iniciar sesión en todos los servicios necesarios, seleccione el botón **continuar** :
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. opta Cambie el nombre del flujo escribiendo un nombre de su elección en el cuadro de la parte superior del portal:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizar la entrada del usuario
1. En la tarjeta del desencadenador, seleccione **Editar**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Seleccione el icono de **+** para expandir la página de forma que pueda agregar campos de entrada personalizados:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Escriba el **título** y la **Descripción** de entrada de cada campo personalizado que desee que esté disponible cuando alguien ejecute el flujo.  
   
    En este ejemplo, creará dos campos de entrada personalizados (**pasos de reproducción de errores** y **gravedad del error**) para que cualquier persona que use este flujo pueda escribir los pasos para reproducir el error y valorar la gravedad del error:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalizar el error
1. Puntee en la barra de título **crear una nueva** tarjeta de elemento de trabajo:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Realice las selecciones adecuadas para el entorno de VSTS y, después, seleccione **Editar**:
   
    Por ejemplo, conéctese a myinstance.visualstudio.com escribiendo **instanceof**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Seleccione **Mostrar opciones avanzadas** para mostrar los otros campos de esta tarjeta:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Coloque el cursor delante del token del **título del error** y, a continuación, escriba "Severity:" en el campo de texto del **título** .
5. Con el cursor todavía en el campo de texto del título, seleccione el token **gravedad del error** y, a continuación, escriba "--".  
6. En el campo de texto **Descripción** , coloque el cursor justo después del token de **Descripción del error** y, a continuación, presione Entrar para iniciar una nueva línea.
7. Coloque el cursor en la nueva línea y, a continuación, seleccione el token de **pasos de reproducción de errores** :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalización de la notificación de extracción
1. Puntee en la barra de título de la tarjeta **enviar una notificación de envío** para expandirla.
2. En la lista de tokens de contenido dinámico, seleccione **Ver más**y, a continuación, agregue el token de **dirección URL** en el campo de texto del **vínculo** .
3. En el campo de texto de **etiqueta de vínculo** , agregue el token de **identificador** :
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Pulse en **Crear flujo** en el menú para crear el flujo: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Ejecutar el flujo
En este tutorial, usará la aplicación móvil de Microsoft Flow para ejecutar el flujo de botón que acaba de crear. Proporcionará todos los datos proporcionados por el usuario para crear un error con un título, una descripción, los pasos de reproducción y un nivel de gravedad.  

1. En la aplicación móvil de Microsoft Flow, puntee en la pestaña **botones** y, a continuación, puntee en el botón **crear informe de errores con pasos** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Escriba el título del error que está notificando y, a continuación, puntee en **siguiente**. Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Escriba la descripción del error que está notificando y, a continuación, puntee en **siguiente**. Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Escriba los pasos para reproducir el error que está notificando y, a continuación, puntee en **siguiente**. Por ejemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Escriba la gravedad del error que está notificando y, a continuación, pulse **listo**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    El flujo se ejecuta.
6. opta Puntee en la pestaña **actividad** para mostrar los resultados.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. opta Para mostrar los resultados detallados de la ejecución del flujo, puntee en el paso **crear un nuevo elemento de trabajo** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Usar diferentes tipos de entrada

Los flujos de botón también pueden aceptar tipos de datos enriquecidos. Esta es la lista de tipos de entrada de datos que los flujos de botón aceptan: 

- Negrita
- Desplegables (como botones de radio)
- Dirección de correo electrónico
- Archivo (por ejemplo, una fotografía en el teléfono)
- Casilla sí o no
- Números
- Fecha (con un selector de calendario)

Para usar estos tipos de entrada, agregue el desencadenador **desencadenar manualmente un** desencadenador de flujo y, a continuación, agregue cualquiera de estos tipos al flujo:

![Opciones de entrada](media/button-flow-with-user-input-tokens/input-options.png)

Además, es posible que desee designar algunas entradas según sea necesario y otras como opcionales. Use el menú de acción (... en el lado derecho) en cada campo de entrada. Hay un límite de cinco entradas por botón.

![Seleccionar tokens opcionales](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Pasos siguientes
* [Compartir flujos de botones](share-buttons.md)
* [Más información sobre los flujos de botón](introduction-to-button-flows.md)  
* [Más información sobre los flujos de botón con tokens de desencadenador](introduction-to-button-trigger-tokens.md)  

