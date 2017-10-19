---
title: "Automatización de tareas mediante la creación de un flujo | Microsoft Docs"
description: "Cree un flujo para realizar automáticamente una o varias acciones, como enviar correo, cuando se produzcan eventos, como que alguien agregue una fila a una lista de SharePoint."
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Creación de un flujo en Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Cree un flujo que realice automáticamente una o varias tareas después de que lo desencadene un evento. Por ejemplo, cree un flujo que le envíe una notificación por correo electrónico cuando alguien envíe un tweet que contenga una palabra clave que especifique. En este ejemplo, el envío de un tweet es el evento y el envío de correo es la acción.

## <a name="prerequisites"></a>Requisitos previos
* Una cuenta en [flow.microsoft.com](https://flow.microsoft.com)
* Una cuenta de Twitter
* Credenciales de Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especificación del evento que va a iniciar el flujo
En primer lugar, será preciso que seleccione el evento, o *desencadenador*, que inicia el flujo.

1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior y, después, seleccione **Crear desde cero**.
   
    ![Opciones de flujos de la barra de navegación izquierda](./media/get-started-logic-flow/create-logic-flow.png)
2. En el cuadro **Buscar todos los conectores y desencadenadores**, escriba o pegue **Twitter** y seleccione **Twitter -Cuando se publica un tweet nuevo**.
   
    ![Evento de Twitter](./media/get-started-logic-flow/twitter-search.png)
3. Si no ha conectado su cuenta de Twitter a Microsoft Flow, seleccione **Iniciar sesión en Twitter** y especifique sus credenciales.
   
    ![Inicio de sesión en Twitter](./media/get-started-logic-flow/twitter-signin.png)
4. En el cuadro **Buscar texto**, escriba la palabra clave que desea buscar.
   
    ![Palabra clave de Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificación de una acción
1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![Agregar acción](./media/get-started-logic-flow/add-action-icon.png)
2. En el cuadro **Buscar todos los conectores y acciones**, escriba o pegue **enviar correo electrónico** y seleccione **Office 365 Outlook - Enviar un correo electrónico**.
   
    ![Lista de acciones](./media/get-started-logic-flow/send-email.png)
3. Si se le solicita, seleccione el botón de inicio de sesión y especifique sus credenciales.
4. En el formulario que aparece, escriba o pegue la dirección de correo electrónico en el **Para** y, a continuación, seleccione el nombre en la lista de contactos que aparece.
   
    ![Mensaje de correo electrónico en blanco](./media/get-started-logic-flow/blank-email.png)
5. En el cuadro **Asunto**, escriba o pegue **Nuevo tweet de:** y, a continuación, agregue un espacio.
   
    ![Línea de asunto con marcador de posición](./media/get-started-logic-flow/message-token.png)
6. En la lista de tokens, seleccione **Twitteado por** para agregarle un marcador de posición.
   
    ![Agregar parámetro](./media/get-started-logic-flow/add-parameter.png)
7. Haga clic o pulse en el cuadro **Cuerpo**, después en el token **Texto del tweet** para agregarle un marcador de posición.
8. (opcional) Agregue más tokens, otro tipo de contenido, o ambas cosas, al cuerpo del correo electrónico.
9. Cerca de la parte superior de la pantalla, asigne un nombre al flujo y, después, seleccione **Crear flujo**.
   
    ![Seleccionar el botón Crear flujo](./media/get-started-logic-flow/create-button.png)
10. Seleccione **Listo** para actualizar la lista de los flujos.
    
     ![Seleccionar el botón Listo](./media/get-started-logic-flow/done-button.png)
11. Envíe un tweet con la palabra clave que ha indicado.
    
     Un minuto después un mensaje de correo electrónico le notificará el nuevo tweet.

## <a name="manage-a-flow"></a>Administración de un flujo
1. En [flow.microsoft.com](https://flow.microsoft.com), seleccione **Mis flujos** en la barra de navegación superior.
2. En la lista de flujos, realice una de las siguientes acciones:
   
   * Para pausar un flujo, establezca el control de alternancia en **Desactivar**.
     
       ![Pausar el flujo](./media/get-started-logic-flow/pause-flow.png)
   * Para reanudar un flujo, establezca el control de alternancia en **Activar**.
     
       ![Reanudar el flujo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar un flujo, seleccione el icono de lápiz que se corresponde al flujo que se desea editar.
     
       ![Seleccionar flujo](./media/get-started-logic-flow/select-flow.png)
   * Para eliminar un flujo, seleccione el icono **...** , seleccione **Eliminar**y, después, seleccione **Eliminar** en el cuadro de mensaje que aparece.
     
       ![Icono de eliminar](./media/get-started-logic-flow/delete-icon.png)
   * Para ver el historial de ejecuciones de un flujo, seleccione dicho flujo en la página **Mis flujos de** y vea el historial de la sección **HISTORIAL DE EJECUCIONES** de la página que se abre.
     
       ![historial de ejecuciones](./media/get-started-logic-flow/run-history.png)
     
     Seleccione una ejecución de flujo en la lista de ejecuciones para ver las entradas y salidas de cada paso.

**Nota**: Una cuenta puede tener un máximo de 50 flujos. Si ya los tiene, para crear uno es preciso eliminar otro antes.

## <a name="next-steps"></a>Pasos siguientes
* [Agregue pasos](multi-step-logic-flow.md), como las diferentes formas de recibir una notificación, a su flujo.
* [Ejecute las tareas según una programación](run-tasks-on-a-schedule.md), cuándo desea que una acción se produzca: cada día, en una fecha concreta o después de un número determinado de minutos.
* [Agregue un flujo a una aplicación](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para que la aplicación pueda iniciar la lógica en la nube.
* [Cree flujos de equipo](create-team-flows.md) e invite a otros a colaborar en el diseño de flujos.

