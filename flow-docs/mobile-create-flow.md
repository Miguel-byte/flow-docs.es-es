---
title: Crear un flujo desde el teléfono | Microsoft Docs
description: Cree un flujo a partir de una plantilla que, por ejemplo, envíe una notificación de envío cuando reciba correo de una dirección que especifique.
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549055"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Cree un flujo desde el teléfono mediante Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cree un flujo desde el teléfono mediante una plantilla, que puede encontrar buscando en una lista de servicios, examinando categorías o especificando palabras clave. Siga los pasos de este tema para crear un flujo que envíe una notificación de envío a su teléfono cuando reciba correo de su administrador.

Si no está familiarizado con Microsoft Flow, [obtenga información general](getting-started.md).

## <a name="prerequisites"></a>Requisitos previos
* Una [cuenta para Microsoft Flow](sign-up-sign-in.md).
* La aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows) en un [dispositivo compatible](getting-started.md#use-the-mobile-app). Los gráficos de este tema reflejan la versión de iPhone de la aplicación, pero la interfaz de un dispositivo Android o Windows Phone es similar.
* Para usar la plantilla que se muestra en este tema, también necesitará:
  
  * Credenciales de Office 365.
  * Notificaciones de envío habilitadas en el teléfono.

## <a name="find-a-template"></a>Buscar una plantilla
1. Abra la aplicación móvil y pulse **examinar** en la parte inferior de la pantalla.
   
    ![Icono examinar](./media/mobile-create-flow/browse-icon.png)
   
    Puede encontrar una plantilla de cualquiera de estas maneras:
   
   * Especifique una palabra clave en el cuadro de búsqueda de la parte superior de la pantalla.
   * Puntee en una opción de la lista de servicios.
   * Desplácese hacia abajo para mostrar una variedad de categorías y, a continuación, puntee en una plantilla en cualquier categoría.
     
       ![Pestaña examinar](./media/mobile-create-flow/browse-tab.png)
     
     En este tutorial, abrirá la plantilla que envía una notificación de envío cuando recibe correo de su administrador.
2. En la lista de servicios, pulse **ver todo**.
   
    ![Mostrar lista de servicios](./media/mobile-create-flow/list-services.png)
3. Pulse el icono de **notificación**de la extracción.
   
    ![Notificaciones de envío](./media/mobile-create-flow/push-notifications.png)
4. En la barra de búsqueda, escriba **correo electrónico**y, a continuación, puntee en la plantilla para enviar una notificación de envío cuando reciba un mensaje de su administrador.
   
    ![Elegir plantilla](./media/mobile-create-flow/choose-template.png)
5. En la pantalla que proporciona detalles sobre la plantilla que ha seleccionado, pulse **usar esta plantilla**.
   
    ![Confirmar plantilla](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Finalizar el flujo
1. Si se le solicita, pulse **iniciar sesión**y proporcione sus credenciales para Office 365 Outlook, usuarios de Office 365 o ambos.
   
    ![Iniciar sesión en Office 365](./media/mobile-create-flow/office-signin.png)
   
    Puede usar las mismas conexiones al crear otros flujos.
2. En la esquina superior derecha, puntee en **siguiente**.
   
    ![Puntee en siguiente](./media/mobile-create-flow/next.png)
   
    En la pantalla siguiente se muestra el evento desencadenador y todas las acciones resultantes.
   
    ![Desencadenar eventos y acciones](./media/mobile-create-flow/flow-structure.png)
   
    Para esta plantilla, el correo nuevo desencadena el flujo, que recupera la información (incluida la dirección de su administrador) y le envía una notificación de envío cuando recibe correo de esa dirección. Algunas plantillas requieren cierta personalización para funcionar correctamente, pero esta plantilla no.
3. opta Cerca de la parte superior de la pantalla, escriba un nombre diferente para el flujo.
   
    ![Cambiar el nombre del flujo](./media/mobile-create-flow/rename-flow.png)
4. En la esquina superior derecha, pulse **crear**.
   
    ![Crear flujo](./media/mobile-create-flow/create-flow.png)
   
    Se creará el flujo y comprobará si hay correo electrónico desde el administrador hasta que PAUSE o elimine el flujo.

## <a name="next-steps"></a>Pasos siguientes
* [Supervise la actividad de Flow](mobile-monitor-activity.md).
* [Administrar los flujos](mobile-manage-flows.md).

