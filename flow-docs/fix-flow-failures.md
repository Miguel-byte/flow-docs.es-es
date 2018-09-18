---
title: Solución de problemas en un flujo | Microsoft Docs
description: Resolución de algunos de los motivos más habituales por los que los flujos producen un error
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
ms.date: 01/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 30efc05dad57bc86a99b90e849fd1c9459930e54
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689488"
---
# <a name="troubleshooting-a-flow"></a>Solución de problemas en un flujo
## <a name="identify-the-error"></a>Identificación del error
Antes de que pueda corregir un flujo, debe identificar el motivo por el que se produjo un error. Haga clic o pulse en el icono de notificaciones de la parte superior del portal web (o abra la pestaña **Actividad** en la aplicación móvil) y, a continuación, haga clic o pulse en el flujo en la lista que aparece.

![Notificaciones](./media/fix-flow-failures/notifications-toolbar.png)

Los detalles del flujo aparecen y, al menos en un paso se muestra un icono rojo con el signo de exclamación. Abra ese paso y revise el mensaje de error.

![Mensaje de error](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>Errores de autenticación
En muchos casos, los flujos dan error debido a un error de autenticación. Si tiene este tipo de error, el mensaje de error contiene el texto **No autorizado** o aparece un código de error **401** o **403**. Normalmente, se puede corregir un error de autenticación mediante la actualización de la conexión:

1. En la parte superior del portal web, haga clic o pulse en el icono de engranaje para abrir el menú **Configuración** y, a continuación, haga clic o pulse en **Conexiones**.
2. Desplácese hasta la conexión en la que aparecía el mensaje de error de **No autorizado**.
3. Junto a la conexión, haga clic o pulse en el vínculo **Repetir contraseña** del mensaje sobre la conexión que no se autentica.
4. Compruebe sus credenciales mediante las instrucciones que aparecen, vuelva al error de ejecución del flujo y, a continuación, haga clic o pulse en **Volver a enviar**.
   
    El flujo debe ya ejecutarse según lo previsto.

## <a name="action-configuration"></a>Configuración de acciones
Los flujos también pueden producir un error si una opción de una acción del flujo no funciona según lo previsto. En este caso, el mensaje de error contiene el texto **Solicitud incorrecta** o **No se encuentra**, o aparece un código de error **400** o **404**.

El mensaje de error debe especificar cómo corregir el error. Debe hacer clic o pulsar en el botón **Editar** y, a continuación, corregir el problema dentro de la definición de flujo. Guarde el flujo actualizado y, a continuación, haga clic o pulse en **Volver a enviar** para probar la ejecución de nuevo con la configuración actualizada.

## <a name="other-failures"></a>Otros errores
Si aparece el código de error **500** o **502**, el error es temporal o transitorio. Haga clic o pulse en **Volver a enviar** para probar el flujo de nuevo.

Si se produce algún otro problema, [pregunte en nuestra comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) ya que otros podrían haber detectado un problema similar.

