---
title: Use la acción aplicar a cada para recorrer en iteración una matriz de elementos. | Microsoft Docs
description: Use Microsoft Flow para recorrer en bucle una matriz de elementos para comprobar varias condiciones y realizar acciones en función de esas condiciones.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e2852de959f62d5c0ee76fabc9841e3fc9663f73
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546004"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Usar la acción aplicar a cada de Microsoft Flow para procesar una lista de elementos periódicamente
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Muchos desencadenadores pueden iniciar inmediatamente un flujo en función de un evento, como cuando llega un nuevo correo electrónico en la bandeja de entrada. Estos desencadenadores son excelentes, pero a veces desea ejecutar un flujo que consulta a un origen de datos según una programación predefinida, realizando ciertas acciones en función de las propiedades de los elementos del origen de datos. Para ello, el flujo se puede iniciar según una programación (por ejemplo, una vez al día) y usar una acción de bucle como **aplicar a cada** una de ellas para procesar una lista de elementos. Por ejemplo, puede usar **Apply to Each** para actualizar registros de una base de datos o una lista de elementos de Microsoft SharePoint.

En este tutorial, vamos a crear un flujo que se ejecuta cada 15 minutos y hace lo siguiente:

1. Obtiene los últimos 10 mensajes sin leer de la bandeja de entrada de Office 365 Outlook.
2. Comprueba cada uno de los 10 mensajes para confirmar si alguno de ellos se ha **cumplido ahora** en el asunto.
3. Comprueba si el correo electrónico procede de su jefe o se envió con importancia alta.
4. Envía una notificación de envío y marca como leída cualquier correo electrónico que se haya **cumplido ahora** en el asunto y que sea de su jefe o se haya enviado con importancia alta.

En este diagrama se muestran los detalles del flujo que crearemos en este tutorial:

![Información general sobre el flujo que se está creando](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Requisitos previos
Estos son los requisitos para realizar correctamente los pasos de este tutorial:

* Una cuenta registrada para usar [Microsoft Flow](https://flow.microsoft.com).
* Una cuenta de Office 365 Outlook.
* La aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
* Conexiones con Office 365 Outlook y el servicio de notificaciones de extracción.

## <a name="create-a-flow"></a>Creación de un flujo
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com):
2. Seleccione la pestaña **Mis flujos** y, después, cree un flujo desde un espacio en blanco:
   
    ![crear desde cero](./media/apply-to-each/foreach-1.png)
3. Escriba "programación" en el cuadro de búsqueda para buscar todos los servicios y desencadenadores relacionados con la programación.
4. Seleccione el desencadenador **programación-periodicidad** para indicar que el flujo se ejecutará según una programación que se va a proporcionar a continuación:
   
    ![programar acción de periodicidad](./media/apply-to-each/foreach-2.png)
5. Establecer la programación para que se ejecute cada 15 minutos:
   
    ![ejecuciones de programación](./media/apply-to-each/foreach-3.png)
6. Seleccione **+ nuevo paso**, **Agregar una acción**y, a continuación, escriba **Outlook** en el cuadro de búsqueda para buscar todas las acciones relacionadas con Microsoft Outlook.
7. Seleccione la acción **Office 365 Outlook-obtener correos electrónicos** :
   
    ![seleccionar la acción obtener correos electrónicos](./media/apply-to-each/foreach-4.png)
8. Se abrirá la tarjeta **obtener correos electrónicos** . Configure la tarjeta **obtener correos electrónicos** para seleccionar los 10 correos electrónicos no leídos principales en la carpeta Bandeja de entrada. No incluya datos adjuntos porque no se usarán en el flujo:
   
    ![configurar tarjeta de correo electrónico](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Hasta ahora, ha creado un flujo sencillo que obtiene algunos mensajes de correo electrónico de su bandeja de entrada. Estos mensajes de correo electrónico se devolverán en una matriz; la acción **aplicar a cada** requiere una matriz, por lo que es exactamente lo que se necesita.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Agregar acciones y condiciones
1. Seleccione **+ nuevo paso**, **más**y, a continuación, **agregue una acción aplicar a cada uno** :
   
    ![seleccionar aplicar a cada](./media/apply-to-each/foreach-6.png)
2. Inserte el token de **cuerpo** en el cuadro **Seleccione una salida de los pasos anteriores** de la tarjeta **aplicar a cada** . Esto extrae el cuerpo de los correos electrónicos que se usarán en la acción **aplicar a cada uno** :
   
    ![Agregar token de cuerpo](./media/apply-to-each/foreach-7.png)
3. Seleccione **Agregar una condición**:
   
    ![Agregar condición](./media/apply-to-each/foreach-8.png)
4. Configure la tarjeta **condición** para buscar las palabras "reunirse ahora" en el asunto de cada correo electrónico:
   
   * Inserte el token de **asunto** en el cuadro **nombre de objeto** .
   * Seleccione **Contains** en la lista **relación** .
   * Escriba **reunirse ahora** en el cuadro **valor** .
     
     ![configuración de la condición](./media/apply-to-each/foreach-subject-condition.png)
5. Seleccione **más**y, a continuación, seleccione **Agregar una condición** en la rama en **caso afirmativo, no hacer nada** . Se abrirá la tarjeta de la **condición 2** ; Configure esa tarjeta como esta:
   
   * Inserte el token de **importancia** en el cuadro **nombre de objeto** .
   * Seleccione **es igual a** en la lista **relación** .
   * Escriba **alto** en el cuadro **valor** .
     
     ![Agregar condición](./media/apply-to-each/foreach-importance-condition.png)
6. Seleccione **Agregar una acción** en la sección en **caso afirmativo, no hacer nada** . Se abrirá la tarjeta **elegir una acción** , donde podrá definir qué debe ocurrir si la condición de búsqueda (el correo electrónico **meet Now** se envió con importancia alta) es true:
   
    ![Agregar acción](./media/apply-to-each/foreach-9.png)
7. Busque **notificación**y, después, seleccione la acción **notificaciones-enviarme una notificación por móvil** :
   
    ![buscar y seleccionar notificación](./media/apply-to-each/foreach-10.png)
8. En la tarjeta **enviarme una notificación por móvil** , proporcione los detalles de la notificación de envío que se enviará si el asunto de un correo electrónico contiene "reunirse ahora" y, a continuación, seleccione **Agregar una acción**:
   
    ![configurar notificación](./media/apply-to-each/foreach-11.png)
9. Escriba **leer** como término de búsqueda y, a continuación, seleccione la acción **Office 365 Outlook-marcar como leído** . Esto marcará cada correo electrónico como leído después de enviar la notificación de envío:
   
    ![acción agregar marca como lectura](./media/apply-to-each/foreach-12.png)
10. Agregue el token de ID. de **mensaje** al cuadro **ID** . de mensaje de la tarjeta **marcar como leído** . Es posible que tenga que seleccionar **Ver más** para encontrar el token de ID. de **mensaje** . Indica el identificador del mensaje que se marcará como leído:
    
     ![Agregar ID. de mensaje](./media/apply-to-each/foreach-13.png)
11. Volver a la tarjeta de la **condición 2** , en la rama **si no, no hacer nada** :
    
    * Seleccione **Agregar una acción**y, a continuación, escriba **obtener administrador** en el cuadro de búsqueda.
    * Seleccione la acción **Office 365 usuarios-obtener administrador** de la lista de resultados de la búsqueda.
    * Escriba la dirección de correo electrónico *completa* en el cuadro **usuario** de la tarjeta **obtener administrador** .
      
      ![Agregar y configurar la acción obtener administrador](./media/apply-to-each/foreach-get-manager.png)
12. Seleccione **más**y, a continuación, seleccione **Agregar una condición** de la rama **si no** . Se abrirá la tarjeta **condición 3** . Configure la tarjeta para comprobar si la dirección de correo electrónico del remitente del correo electrónico (el token de) es la misma que la dirección de correo electrónico de su jefe (el token de correo electrónico):
    
    * Inserte el token **desde** en el cuadro Nombre de **objeto** .
    * Seleccione **Contains** en la lista **relación** .
    * Escriba token de **correo electrónico** en el cuadro **valor** .
      
      ![configuración de la condición de búsqueda](./media/apply-to-each/foreach-condition3-card.png)
13. Seleccione **Agregar una acción** en la sección en **caso afirmativo, no hacer nada** de la tarjeta **condición 3** . Se abrirá la tarjeta **si es Yes** , donde podrá definir qué debe ocurrir si la condición de búsqueda (el correo electrónico se envió desde su jefe) es verdadera:
    
     ![configuración de la condición](./media/apply-to-each/foreah-condition3-add-action.png)
14. Busque **notificación**y, después, seleccione la acción **notificaciones-enviarme una notificación por móvil** :
    
     ![buscar acción de notificación](./media/apply-to-each/foreach-10.png)
15. En la tarjeta **enviarme una notificación de Mobile 2** , proporcione los detalles de la notificación de envío que se enviará si el correo electrónico procede de su jefe y, a continuación, seleccione **Agregar una acción**:
    
     ![configurar tarjeta de notificación](./media/apply-to-each/foreach-boss-notification.png)
16. Agregue la acción **Office 365 Outlook-marcar como leído** . Esto marcará cada correo electrónico como leído después de enviar la notificación de envío:
    
     ![acción agregar marca como lectura](./media/apply-to-each/foreach-12.png)
17. Agregue el token de ID. de **mensaje** a la **marca como tarjeta de lectura 2** . Es posible que tenga que seleccionar **Ver más** para encontrar el token de ID. de **mensaje** . Indica el identificador del mensaje que se marcará como leído:
    
     ![configurar la acción marcar como leído](./media/apply-to-each/foreach-mark-as-read2.png)
18. Asigne un nombre al flujo y, a continuación, créelo:
    
     ![Asigne un nombre al flujo y guárdelo](./media/apply-to-each/foreach-14.png)

Si ha seguido estos pasos, el flujo debe ser similar a este diagrama:

![Información general sobre el flujo creado](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Ejecución del flujo
1. Envíese a sí mismo un correo electrónico de alta importancia que incluye **reunirse ahora** en el asunto (o que alguien de su organización le envíe un correo electrónico).
2. Confirme que el correo electrónico está en la bandeja de entrada y que no se ha leído.
3. Inicie sesión en Microsoft Flow, seleccione **Mis flujos**y, después, seleccione **Ejecutar ahora**:
   
    ![Ejecutar ahora](./media/apply-to-each/foreach-run-1.png)
4. Seleccione **Ejecutar flujo** para confirmar que realmente desea ejecutar el flujo:
   
    ![confirmar ejecución](./media/apply-to-each/foreach-run-2.png)
5. Transcurridos unos instantes, debería ver los resultados de la ejecución correcta:
   
    ![resultados de la ejecución](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Ver los resultados de la ejecución
Ahora que ha ejecutado el flujo correctamente, debe recibir la notificación de envío en el dispositivo móvil.

1. Abra la aplicación Microsoft Flow en el dispositivo móvil y, a continuación, seleccione la pestaña **actividad** . Verá la notificación de la extracción de la reunión:
   
    ![Seleccione la pestaña actividad.](./media/apply-to-each/foreach-notification-1.png)
2. Para ver el contenido completo de la notificación, es posible que tenga que seleccionar la notificación. Verá la notificación completa, similar a la siguiente:
   
    ![Detalles de la notificación](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Si no recibe la notificación de envío, confirme que el dispositivo móvil tiene una conexión de datos de trabajo.
   > 
   > 

