---
title: Ejecutar flujos según las propiedades del correo electrónico | Microsoft Docs
description: Iniciar un flujo basado en propiedades como el asunto, la dirección del remitente o la dirección del destinatario de un correo electrónico.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544951"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Desencadenar un flujo basado en las propiedades del correo electrónico
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Use el desencadenador **cuando llega un nuevo correo electrónico** para crear un flujo que se ejecuta cuando una o varias de las siguientes propiedades de correo coinciden con los criterios que proporcione:

| Propiedad | Cuándo usar |
| --- | --- |
| Directorio |Desencadene un flujo cada vez que lleguen correos electrónicos a una carpeta específica. Esta propiedad puede ser útil si tiene reglas que enruten correos electrónicos a carpetas diferentes. |
| Para |Desencadenar un flujo en función de la dirección a la que se envió un correo electrónico. Esta propiedad puede ser útil si recibe un correo electrónico que se envió a direcciones de correo electrónico diferentes en la misma bandeja de entrada. |
| De |Desencadene un flujo en función de la dirección de correo electrónico del remitente. |
| Importance |Desencadene un flujo en función de la importancia con la que se enviaron los mensajes de correo electrónico. El correo electrónico se puede enviar con una importancia alta, normal o baja. |
| Tiene datos adjuntos |Desencadenar un flujo en función de la presencia de datos adjuntos en los correos electrónicos entrantes. |
| Filtro de asunto |Busque la presencia de palabras específicas en el asunto de un correo electrónico. Después, el flujo ejecuta *acciones* basadas en los resultados de la búsqueda. |

> [!IMPORTANT]
> Cada [plan de Microsoft Flow](https://flow.microsoft.com/pricing/) incluye una cuota de ejecución. Compruebe siempre las propiedades en el desencadenador del flujo cuando sea posible. Al hacerlo, se evita el uso innecesario de la cuota de ejecución. Si comprueba una propiedad en una condición, cada ejecución se recuenta en la cuota de ejecución del plan, incluso si no se cumple la condición de filtro que ha definido. 

Por ejemplo, si se comprueba la dirección de un correo electrónico en una condición, cada ejecución se recuenta en la *cuota de ejecución* del plan, aunque no sea *de* la dirección que le interese.
> 
> 

En los siguientes tutoriales, se activan todas las propiedades del desencadenador **cuando llega un nuevo correo electrónico** . Para obtener más información, visite las [preguntas de facturación](billing-questions.md#what-counts-as-a-run) más frecuentes y la página de [precios](https://ms.flow.microsoft.com/pricing/) .

## <a name="prerequisites"></a>Requisitos previos
* Una cuenta con acceso a [Microsoft Flow](https://flow.microsoft.com)
* Una cuenta de Office 365 Outlook
* La aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows)
* Conexiones a Office, Outlook y el servicio de notificaciones de extracción

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Desencadenar un flujo basado en el asunto de un correo electrónico
En este tutorial, se crea un flujo que envía una notificación de envío a su teléfono móvil si el asunto de cualquier correo electrónico nuevo tiene la palabra "lotería". El flujo marca entonces cualquier correo electrónico como *leído*.

>[!NOTE]
>Aunque en este tutorial se envía una notificación de envío, es libre de usar cualquier otra acción que se ajuste a sus necesidades de flujo de trabajo. Por ejemplo, puede almacenar el contenido del correo electrónico en otro repositorio, como Google Sheets o un archivo de Microsoft Excel almacenado en Dropbox.

Bien, comencemos:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. En el cuadro **filtro de asunto** , escriba el texto que utiliza el flujo para filtrar los correos electrónicos entrantes.
   
     En este ejemplo, estamos interesados en cualquier correo electrónico que tenga la palabra "lotería" en el asunto.
   
    ![Opciones avanzadas](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que desea recibir cuando reciba un correo electrónico que coincida con el **filtro de asunto** que especificó anteriormente.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asigne un nombre al flujo. A continuación, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![guardar flujo](./media/email-triggers/email-triggers-subject-notification.png)

Finaliza! Ahora recibirá una notificación de envío cada vez que reciba un correo electrónico que contenga la palabra "lotería" en el asunto.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Desencadenar un flujo basado en el remitente de un correo electrónico
En este tutorial, se crea un flujo que envía una notificación de envío a su teléfono móvil si llega un correo electrónico nuevo desde un remitente específico (dirección de correo electrónico). El flujo también marca el correo electrónico como *leído*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. En el cuadro **de** , escriba la dirección de correo electrónico del remitente. 
   
     El flujo realiza acciones en cualquier correo electrónico que se envíe desde esta dirección.
   
    ![Propiedad email](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que le gustaría recibir siempre que llegue un mensaje de la dirección de correo electrónico que especificó anteriormente.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asigne un nombre al flujo y, a continuación, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![guardar flujo](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Desencadenar un flujo cuando lleguen correos electrónicos a una carpeta específica
Si tiene reglas que enruten el correo electrónico a diferentes carpetas en función de determinadas propiedades, como la dirección, puede que desee este tipo de flujo.

Comencemos:

> [!NOTE]
> Si aún no tiene una regla que enrute el correo electrónico a una carpeta distinta de la bandeja de entrada, cree una regla de este tipo y confírmela mediante el envío de un correo electrónico de prueba.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Seleccione la carpeta a la que va a enrutar correos electrónicos específicos. Para mostrar todas las carpetas de correo electrónico, primero seleccione el icono **Mostrar selector** , que se encuentra en el lado derecho del cuadro **carpeta** en la tarjeta **cuando llegue un correo electrónico nuevo** .
   
    ![Seleccionar carpeta](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Escriba los detalles de la notificación móvil que le gustaría recibir cuando llegue un correo electrónico a la carpeta que seleccionó anteriormente. Si todavía no lo ha hecho, escriba las credenciales del servicio de notificaciones.
   
    ![Detalles de la notificación](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Asigne un nombre al flujo y, a continuación, guárdelo seleccionando **Crear flujo** en la parte superior de la página.
   
    ![guardar flujo](./media/email-triggers/email-triggers-7.png)

Pruebe el flujo enviando un correo electrónico que se enrute a la carpeta que seleccionó anteriormente en este tutorial.

