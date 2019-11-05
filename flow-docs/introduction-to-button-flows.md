---
title: Obtenga información sobre cómo automatizar y ejecutar tareas repetitivas con flujos de botones | Microsoft Docs
description: Introducción a los flujos de botón.
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
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547531"
---
# <a name="introducing-button-flows"></a>Introducción a los flujos de botón
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>¿Qué son los flujos de botón?
Hay muchas tareas repetitivas que se quieren ejecutar con solo pulsar un botón. Por ejemplo, puede que tenga que enviar por correo electrónico rápidamente a su equipo para recordarle que se una a la sincronización diaria del equipo, o bien puede iniciar una nueva compilación de Visual Studio online de su código base después de haber notificado que no hay más protecciones planeadas para el día. Los flujos de botón permiten realizar estas y muchas otras tareas simplemente pulsando un botón en el dispositivo móvil.

**Nota:** Puede crear flujos de botón desde el dispositivo móvil o desde el portal de Flow.  
  ![imagen de información general](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>¿Por qué crear botones?
Cree botones para poder ejecutar fácilmente tareas repetitivas desde cualquier lugar y en cualquier momento a través de su dispositivo móvil. La ejecución de botones le ahorra tiempo y, dado que las tareas que realizan se automatizan, habrá menos errores que si lo hiciera manualmente.  

## <a name="create-a-button"></a>Crear un botón
### <a name="prerequisites"></a>Requisitos previos
* Acceso al flujo. El administrador puede proporcionarle acceso.
* Una cuenta con permisos para usar los conectores para crear el botón. Por ejemplo, necesitará una cuenta de Dropbox para crear un botón que acceda a Dropbox.

### <a name="from-the-portal"></a>Desde el portal
En este tutorial, vamos a crear un botón que inicia una compilación de Visual Studio online (VSO) y envía notificaciones para que sepa cuándo se inicia la compilación:  

1. Seleccione la lista desplegable **Mostrar** y elija la categoría de **botón** . Esto filtra la lista de plantillas para solo las que se pueden usar en los flujos de botón.  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-1.png)   
2. Seleccione la plantilla **desencadenar una nueva compilación de VSO en** la lista de plantillas.  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-2.png)  
3. Seleccione el botón **usar esta plantilla** en la página **desencadenar una nueva compilación de VSO** .   
   ![imagen de información general](./media/introduction-to-button-flows/create-button-3.png)  
4. Si no ha iniciado sesión, se le pedirá que lo haga en este momento:  
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-4.png)  
5. Una vez iniciada la sesión en Flow, se le pedirá que inicie sesión en los conectores usados en la plantilla que ha seleccionado. En este ejemplo, en el paso 2, se ha seleccionado la plantilla **desencadenar una nueva compilación en VSO** , por lo que tenemos que iniciar sesión en VSO (y en cualquier otro conector con el que esté trabajando) si aún no ha iniciado sesión:  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Seleccione el botón **Aceptar** si acepta autorizar el flujo para acceder a su cuenta de VSO.  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-5.png)   
   **Nota:** Tendrá que autorizar cada conector de la misma manera. El diseñador debe aparecer como este cuando esté listo para pasar al paso siguiente. Seleccione el botón **continuar para continuar** :  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-6.png)   
7. Ahora está listo para configurar las propiedades de la compilación que desea iniciar:    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-7.png)  
8. Seleccione o escriba el **nombre**de la cuenta, el **nombre del proyecto**, el identificador de la **definición de compilación**, la **rama de origen** y, opcionalmente, **los parámetros**, en la **cola de una nueva compilación** :    
   ![imagen de información general](./media/introduction-to-button-flows/create-button-8.png)  
9. A continuación, configure las propiedades de la notificación de extracción en la tarjeta **enviar una notificación de extracción** . De forma predeterminada, esta notificación de extracción está configurada para enviar un vínculo HTML a una página web que muestra el estado de la compilación:  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-9.png)  
10. Seleccione el botón **Crear flujo** para guardar el flujo de botón: ![imagen de información general](./media/introduction-to-button-flows/create-button-10.png)  
11. Debería ver este mensaje de operación correcta en unos momentos:  
    ![Imagen de información general](./media/introduction-to-button-flows/create-button-11.png)  

Enhorabuena, ha creado un flujo de botones. Ahora puede ejecutar este flujo de botón en cualquier momento y lugar desde la pestaña **botones** de la aplicación Flow. Simplemente presione el "botón" y se ejecutará. La aplicación móvil Microsoft Flow está disponible para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Desde el dispositivo móvil
**Nota**: aunque en este tutorial se muestran las pantallas de un dispositivo Android, las pantallas y la experiencia en un dispositivo iOS son similares.

En la aplicación Flow:

1. Seleccione la pestaña **Browse (examinar** ) y desplácese hasta la categoría Button ( **botón** ).  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Seleccione el vínculo **ver todo** . Esto muestra todas las plantillas de botón listas para usar.     
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Seleccione la plantilla **Enviar un correo electrónico para recordar a su equipo que se va a unir a una reunión**    
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Seleccione el vínculo **usar esta plantilla** en la parte inferior de la página.    
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Deberá iniciar sesión en todos los servicios que usa esta plantilla:    
   ![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Seleccione el vínculo **siguiente** después de haber iniciado sesión en todos los servicios.      
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Seleccione el vínculo **crear** . Aquí también puede revisar el flujo y realizar los cambios necesarios para personalizar el correo electrónico, por ejemplo.        
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Transcurridos unos instantes, se crea el flujo de botones. Seleccione **ver mi flujo**:   
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Visualización de todos los flujos en la pestaña **Mis flujos**  
   ![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Enhorabuena, ha creado un flujo de botones. Ahora puede ejecutar este flujo de botón en cualquier momento y lugar desde la pestaña **botones** de la aplicación Flow. Simplemente presione el "botón" y se ejecutará. La aplicación Flow está disponible actualmente en dispositivos móviles iOS y Android.  

![Imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Desencadenar un flujo de botón
Ahora que ha creado un flujo de botones, es el momento de ejecutarlo. Dado que solo puede ejecutar flujos de botón desde la aplicación Flow, asegúrese de que ha instalado Flow en el dispositivo móvil Android o iOS.  

1. Ahora, inicie la aplicación Flow, pulse la pestaña **Buttons (botones** ) que se encuentra en la parte inferior de la página y pulse el *botón* que representa el flujo de botón que desea desencadenar:  
   ![imagen de información general](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Vea el progreso mientras se ejecuta el flujo:  
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por último, se actualiza la página, lo que indica que se ha completado el flujo de botones:  
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-3.png)   

Eso es todo lo que hay que hacer para ejecutar un flujo. 

Ahora debería recibir la notificación de la extracción, que indica que se ha enviado el correo electrónico.  

## <a name="monitor-your-button-flow-runs"></a>Supervisión de las ejecuciones de flujo de botones
Puede supervisar los flujos de botón en la pestaña **actividad** de la aplicación Flow:   
![imagen de información general](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Nota**: Pulse cualquier actividad para profundizar en los resultados de la ejecución y obtener información sobre la ejecución.  

![Imagen de información general](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Administrar flujos de botón
Tiene el control total de los flujos de botones para que pueda habilitar o deshabilitar, editar o eliminar un botón en cualquier momento y en cualquier lugar. En la aplicación móvil o en el portal de Flow, seleccione **Mis flujos** para empezar a administrar los flujos.    

En la pestaña **Mis flujos** de la aplicación Flow:

1. Seleccione el flujo que desea administrar:    
   ![Imagen de información general](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Puede pulsar cualquiera de estas opciones, en función de lo que le gustaría realizar:    
   ![Imagen de información general](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Puntee en **eliminar flujo** para eliminar un flujo.  

**Nota:** Todo el historial de ejecución se elimina al eliminar un flujo:   
![imagen de información general](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Pulse en **Actualizar** cuando haya terminado de editar un flujo de botones para guardar los cambios:   
   ![imagen de información general](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Pulse en **historial de ejecución** para ver los resultados de todas las ejecuciones de un flujo de botones determinado:    
   ![imagen de información general](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Si deshabilita un flujo, ya no estará disponible en la pestaña **botones** :    
   ![imagen de información general](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Pasos siguientes
* [Compartir flujos de botones](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos en tiempo real cuando se ejecuten los flujos de botón.
* Instale la aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).

