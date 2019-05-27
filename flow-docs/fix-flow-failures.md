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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992721"
---
# <a name="troubleshooting-a-flow"></a>Solución de problemas en un flujo

## <a name="repair-tips-in-email"></a>Reparar las sugerencias de correo electrónico

Sugerencias de reparación se envían a los propietarios del flujo por correo electrónico cada vez que se produce un error en un flujo. Estas sugerencias de reparación de los correos electrónicos contienen comentarios específicos y procesables sobre determinados errores. Por ejemplo, un error común es la configuración de un flujo que intenta obtener el Administrador de una persona en Office 365, pero no hay ningún administrador configurado en Azure Active Directory (Azure AD). Si esto u otras varias condiciones hacen que el flujo de un error, obtendrá un correo electrónico de sugerencias de reparación similar al siguiente:

![Sugerencias de reparación](media/fix-flow-failures/repair-tips-email.png)

El correo electrónico de sugerencias de reparación contiene las siguientes secciones:

Nombre|Descripción
---|---
tiempo|Muestra el tiempo que el flujo de error en primer lugar.
Qué ha pasado|Proporciona una descripción del problema que provocó el error en el flujo.
Cómo corregir|Proporciona sugerencias para resolver el problema que provocan el error en el flujo.
Sugerencias para solucionar problemas|Proporciona detalles como el número de veces que el flujo de error y un vínculo para volver a intentar el flujo con los mismos datos de entrada.

Para corregir los errores notificados, seleccione **corregir mi flujo** y siga los pasos descritos en el correo electrónico de sugerencias de reparación.

Los correos electrónicos de reparación sugerencias son opcionales. Si no desea recibirlos, bastará con apagar ellos desde el menú de propiedades para el flujo específico.

Si se produce un error en el flujo, también puede solucionar directamente en Microsoft Flow.  Estos son algunos escenarios comunes de error y sugerencias sobre cómo corregirlos.

## <a name="identify-the-error"></a>Identificación del error
Antes de que pueda corregir un flujo, debe identificar el motivo por el que se produjo un error. Haga clic o pulse en el icono de notificaciones de la parte superior del portal web (o abra la pestaña **Actividad** en la aplicación móvil) y, a continuación, haga clic o pulse en el flujo en la lista que aparece.

![Notificaciones](./media/fix-flow-failures/notifications-toolbar.png)

Los detalles del flujo aparecen y, al menos en un paso se muestra un icono rojo con el signo de exclamación. Abra ese paso y revise el mensaje de error.

![Mensaje de error](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Errores de autenticación
En muchos casos, los flujos dan error debido a un error de autenticación. Si tiene este tipo de error, el mensaje de error contiene el texto **No autorizado** o aparece un código de error **401** o **403**. Normalmente, se puede corregir un error de autenticación mediante la actualización de la conexión:

1. En la parte superior del portal web, haga clic o pulse el icono de engranaje para abrir el **configuración** menú y, a continuación, haga clic o pulse **conexiones**.
2. Desplácese hasta la conexión en la que aparecía el mensaje de error de **No autorizado**.
3. Junto a la conexión, haga clic o pulse en el vínculo **Repetir contraseña** del mensaje sobre la conexión que no se autentica.
4. Compruebe sus credenciales mediante las instrucciones que aparecen, vuelva al error de ejecución del flujo y, a continuación, haga clic o pulse en **Volver a enviar**.
   
    El flujo debe ya ejecutarse según lo previsto.

## <a name="action-configuration"></a>Configuración de acciones
Los flujos también pueden producir un error si una opción de una acción del flujo no funciona según lo previsto. En este caso, el mensaje de error contiene el texto **Solicitud incorrecta** o **No se encuentra**, o aparece un código de error **400** o **404**.

El mensaje de error debe especificar cómo corregir el error. Debe hacer clic o pulsar en el botón **Editar** y, a continuación, corregir el problema dentro de la definición de flujo. Guarde el flujo actualizado y, a continuación, haga clic o pulse en **Volver a enviar** para probar la ejecución de nuevo con la configuración actualizada.

## <a name="other-failures"></a>Otros errores
Si aparece el código de error **500** o **502**, el error es temporal o transitorio. Haga clic o pulse en **Volver a enviar** para probar el flujo de nuevo.

## <a name="getting-help-from-support-or-the-community"></a>Obtención de Ayuda de soporte técnico o de la Comunidad

Si necesita ayuda, puede usar nuestro **Self Help** opciones o puede **pedir ayuda** de otras personas.

### <a name="self-help"></a>Autoayuda 

1. Vaya a la [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Vaya a la **Self Help** categoría y seleccione una de las opciones de autoayuda.

    ![Solicitar la sección de ayuda. Póngase en contacto con soporte técnico.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Solicite ayuda de otros usuarios

1. Vaya a la [sitio de soporte técnico](https://flow.microsoft.com/support/).
1. Seleccione **póngase en contacto con soporte** en el **pedir ayuda** sección.
    
    ![Solicitar la sección de ayuda. Póngase en contacto con soporte técnico.](media/fix-flow-failures/ask-for-help.png)

1. Completar la **tipo de problema**, **categoría**y el **Díganos qué necesita ayuda con** campos y, a continuación, seleccione **ver soluciones**. 

1. Tenga en cuenta que el **soluciones** sección se muestra después de seleccionar **ver soluciones**. Contiene una lista de resultados que puede usar para ayudar a solucionar el problema que se enfrenta. 

    ![Detalles de la aplicación auxiliar integrada](media/fix-flow-failures/integrated-helper-details.png)

Si necesita ayuda con un problema, la Ayuda está disponible desde nuestro [Comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) y Microsoft. 

