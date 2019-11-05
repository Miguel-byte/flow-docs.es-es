---
title: Comparta sus botones con otros usuarios. | Microsoft Docs
description: Comparta sus botones con otros usuarios para que puedan usar los botones y ahorrar tiempo.
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 098ebf9d8e02ede22a7914a2458375eb3641544a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548425"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Compartir flujos de botones en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
En la aplicación móvil de Microsoft Flow, puede compartir [flujos de botones](introduction-to-button-flows.md) (botones) con otros usuarios o grupos de la organización. Cuando comparte un botón, la persona o el grupo con quien comparte puede ejecutar el botón, de la misma forma que ejecuta sus propios botones. También puede [compartir un vínculo](share-buttons.md#re-share-a-button) a los botones que otra persona compartió con usted. Puede [dejar de compartir](share-buttons.md#stop-sharing-a-button) los botones en cualquier momento.

> Las capturas de pantallas usadas en este documento se han tomado de un dispositivo Android. Si utiliza un iPhone, las imágenes pueden aparecer de manera diferente, pero la funcionalidad es la misma.
> 
> 

Siga [estos pasos](share-buttons.md#use-shared-buttons) para usar un botón que alguien haya compartido con usted.

## <a name="prerequisites"></a>Requisitos previos
Para compartir botones, necesita:

* Una cuenta con acceso a [Microsoft Flow](https://flow.microsoft.com).
* Flujo que se va a compartir.
* Un dispositivo móvil con la aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
* Un grupo o usuario de la organización con quien compartir el botón.

## <a name="share-a-button"></a>Compartir un botón
Puede compartir un botón desde la pestaña **botones** de la aplicación móvil Microsoft Flow.

1. Puntee en el icono pequeño que hay junto al botón que desea compartir.
   
    ![botón compartir](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Puntee en **invitar a otros** en la página de **usuarios del botón** .
   
    ![botón compartir](./media/share-buttons/share-button-flows-button-users.png)
3. Busque y, a continuación, seleccione el grupo o la persona con quien desea compartir el botón.
   
    ![botón compartir](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Puntee en **Enviar** en la página **invitar a otros** .
   
    ![botón compartir](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Pulse **listo** en la página que indica que la operación de uso compartido de botón se completó correctamente.
   
    ![botón compartir](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Requerir a los usuarios que usen sus propias conexiones
> [!NOTE]
> Cuando comparte un botón, puede permitir que las personas con las que ha compartido el botón usen todas las conexiones que utiliza el botón. También puede exigirles que usen sus propias conexiones. Si permite que otros usuarios usen sus conexiones, no podrán acceder a las credenciales en la conexión ni volver a usarlas en ningún otro flujo.
> 
> 

Siga estos pasos para solicitar a las personas con las que ha compartido los botones que usen sus propias conexiones.

1. Seleccione **Administrar conexiones** en la pantalla que aparece inmediatamente después de compartir un botón.
2. Seleccione **Editar** en el botón que desea administrar.
3. Seleccione **proporcionado por el usuario** o su dirección de correo electrónico.
   
    Su elección indica cuyas conexiones deben usarse en el botón compartido.
   
    ![botón compartir](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Puede ver o cambiar su elección en cualquier momento. Para ello, seleccione la pestaña **flujos** > el flujo que compartió > **usuarios y conexiones** > la pestaña **conexiones** > **Editar** en el botón que desea administrar.
   
    ![botón compartir](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Ver la lista de usuarios del botón
Puede ver todos los grupos o usuarios con los que se comparte un botón siguiendo estos pasos en la pestaña **botones** :

1. Puntee en el icono pequeño situado junto al botón en el que está interesado.
2. En la página **usuarios del botón** , vea todos los grupos o usuarios con los que se comparte el botón.
   
    ![ver los usuarios del botón](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Dejar de compartir un botón
Puede dejar de compartir un botón siguiendo estos pasos en la pestaña **botones** :

1. Puntee en el icono pequeño que hay junto al botón que ya no desea compartir.
2. En la página **usuarios del botón** , puntee en el usuario o grupo con el que desea dejar de compartir el botón.
   
    ![botón detener uso compartido](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Pulse **quitar usuario** cuando se muestre la página del usuario.
   
    ![botón detener uso compartido](./media/share-buttons/share-button-flows-remove-user.png)
4. Espere a que se complete la operación de eliminación. Observe que la lista de **usuarios del botón** se actualiza y que el usuario o el grupo que quitó ya no aparece.
   
    ![botón detener uso compartido](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Supervisar el historial de ejecución
Todo el historial de ejecución, incluidas las ejecuciones iniciadas por una persona con la que se comparte un botón, solo aparece en la pestaña **actividad** de la aplicación móvil Microsoft Flow del creador del botón.

## <a name="use-shared-buttons"></a>Usar botones compartidos
Antes de poder ejecutar un botón que alguien ha compartido con usted, debe agregarlo a la pestaña **botones** de la página **agregar botones** .

1. Puntee en **obtener más** (o en el banner los **nuevos botones están disponibles** si aparece) en la pestaña **botones** .
   
    ![nuevo botón compartido conmigo](./media/share-buttons/share-button-flows-banner.png)
2. Puntee en el botón que desea usar.
   
    El botón ahusado se agrega inmediatamente a la pestaña **botones** de la aplicación Microsoft Flow. Después, puede usar el botón de la pestaña **botones** , al igual que cualquier otro botón que aparezca en la lista.
   
    ![nuevo botón compartido conmigo](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Volver a compartir un botón
Puede compartir un vínculo a un botón que se ha compartido con usted.

1. Seleccione **...** junto al botón que desea compartir.
2. Seleccione **compartir vínculo de botón**.
   
    ![volver a compartir vínculo de botón](./media/share-buttons/re-share-button.png)
3. Seleccione la aplicación que desea usar para compartir el botón y, a continuación, siga los pasos para enviar el botón a la persona con la que desea compartir.

## <a name="stop-using-a-shared-button"></a>Dejar de usar un botón compartido
Si ya no desea usar un botón que se ha compartido con usted, quítelo de la pestaña **botones** :

1. En la pestaña **botones** , puntee en **...** junto al botón que ya no desea usar.
   
    ![botón Quitar](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Puntee en **quitar** en el menú que aparece.

Eso es todo. El botón ya no aparece en la pestaña **botones** de la aplicación Microsoft Flow.

> [!NOTE]
> Después de quitar un botón compartido, puede volver a agregarlo seleccionando **obtener más** en la pestaña **botones** .
> 
> 

