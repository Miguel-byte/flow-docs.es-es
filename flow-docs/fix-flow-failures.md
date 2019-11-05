---
title: Solución de problemas de un flujo | Microsoft Docs
description: Resolver algunas de las razones más comunes por las que los flujos producen errores
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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547874"
---
# <a name="troubleshooting-a-flow"></a>Solución de problemas de un flujo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>Sugerencias de reparación en el correo electrónico

Las sugerencias de reparación se envían a los propietarios de flujos por correo electrónico cada vez que se produce un error en un flujo. Estos mensajes de correo electrónico de sugerencias de reparación contienen comentarios específicos y accionables sobre determinados errores. Por ejemplo, un error común es la configuración de un flujo que intenta obtener el administrador de una persona en Office 365, pero no hay ningún administrador configurado en Azure Active Directory (Azure AD). Si esta o varias condiciones hacen que se produzca un error en el flujo, recibirá un correo electrónico de sugerencias de reparación similar al siguiente:

![Sugerencias de reparación](media/fix-flow-failures/repair-tips-email.png)

El correo electrónico de sugerencias de reparación contiene las siguientes secciones:

Name|Denominación
---|---
Tiempo|Muestra la hora en que se produjo el error del flujo por primera vez.
Qué ha pasado|Proporciona una descripción del problema que causó el error en el flujo.
Corrección de Cómo|Proporciona sugerencias para resolver el problema que provoca el error en el flujo.
Sugerencias para la solución de problemas|Proporciona detalles, incluido el número de veces que se ha producido un error en el flujo y un vínculo para volver a intentar el flujo con los mismos datos de entrada.

Para corregir los errores detectados, seleccione **corregir mi flujo** y siga los pasos del correo electrónico de sugerencias de reparación.

Los correos electrónicos de sugerencias de reparación son opcionales. Si no desea recibirlos, simplemente desactívelo en el menú propiedades para el flujo específico.

Si se produce un error en el flujo, también puede solucionarlo directamente en Microsoft Flow.  Estos son algunos escenarios de error comunes y sugerencias sobre cómo corregirlos.

## <a name="identify-the-error"></a>Identificación del error
Antes de poder corregir un flujo, debe identificar por qué se produjo el error. Pulse o haga clic en el icono de notificaciones en la parte superior del portal web (o abra la pestaña **actividad** en la aplicación móvil) y, a continuación, haga clic o pulse en el flujo en la lista que aparece.

![Notificaciones](./media/fix-flow-failures/notifications-toolbar.png)

Aparecen los detalles sobre el flujo y al menos un paso muestra un icono de exclamación rojo. Abra ese paso y revise el mensaje de error.

![Mensaje de error](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Errores de autenticación
En muchos casos, los flujos producen errores debido a un error de autenticación. Si tiene este tipo de error, el mensaje de error contiene **no autorizado** o aparece un código de error **401** o **403** . Normalmente, se puede corregir un error de autenticación mediante la actualización de la conexión:

1. En la parte superior del portal web, haga clic o pulse en el icono de engranaje para abrir el menú de **configuración** y, después, pulse o haga clic en **conexiones**.
2. Desplácese a la conexión para la que vio el mensaje de error **no autorizado** .
3. Junto a la conexión, pulse o haga clic en el vínculo **comprobar contraseña** en el mensaje acerca de la conexión que no se autentica.
4. Compruebe sus credenciales siguiendo las instrucciones que aparecen, vuelva al error de ejecución de flujo y, a continuación, haga clic o pulse en **volver a enviar**.
   
    El flujo debería ejecutarse ahora según lo esperado.

## <a name="action-configuration"></a>Configuración de la acción
También se producirá un error en los flujos si un valor de una acción del flujo no funciona según lo esperado. En este caso, el mensaje de error contiene una **Solicitud incorrecta** o **no se encuentra**, o aparece un código de error **400** o **404** .

El mensaje de error debe especificar cómo corregir el error. Deberá hacer clic o pulsar en el botón **Editar** y, a continuación, corregir el problema dentro de la definición de flujo. Guarde el flujo actualizado y, a continuación, haga clic o pulse en volver a **Enviar** para probar la ejecución de nuevo con la configuración actualizada.

## <a name="other-failures"></a>Otros errores
Si aparece el código de error **500** o **502** , el error es temporal o transitorio. Pulse o haga clic en volver a **Enviar** para probar el flujo de nuevo.

## <a name="getting-help-from-support-or-the-community"></a>Obtener ayuda de soporte técnico o de la comunidad

Cuando necesite ayuda, puede usar nuestras opciones de **autoayuda** o puede **solicitar ayuda** a otros usuarios.

### <a name="self-help"></a>Autoayuda 

1. Vaya al [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Vaya a la categoría **autoayuda** y seleccione una de las opciones de autoayuda.

    ![Sección ask for help. Póngase en contacto con soporte técnico.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Solicitar ayuda de otros usuarios

1. Vaya al [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Seleccione **ponerse en contacto con soporte técnico** en la sección **ask for Help** .
    
    ![Sección ask for help. Póngase en contacto con soporte técnico.](media/fix-flow-failures/ask-for-help.png)

1. Complete el **tipo de problema**y la **categoría**y, a continuación, indique la información **que necesita ayuda con** los campos y, a continuación, seleccione **ver soluciones**. 

1. Observe que la sección **soluciones** se muestra después de seleccionar **ver soluciones**. Contiene una lista de los resultados que puede usar para ayudar a resolver el problema al que está enfrentado. 

    ![Detalles de la aplicación auxiliar integrada](media/fix-flow-failures/integrated-helper-details.png)

Si necesita ayuda con un problema, la ayuda está disponible en nuestra [comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) y en Microsoft. 

