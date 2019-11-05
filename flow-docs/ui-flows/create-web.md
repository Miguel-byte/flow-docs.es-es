---
title: Aprenda a crear flujos de interfaz de usuario para sitios web | Microsoft Docs
description: Aprenda a automatizar aplicaciones web con flujos de interfaz de usuario.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589877"
---
# <a name="create-and-test-your-web-ui-flows"></a>Crear y probar los flujos de la interfaz de usuario Web

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Siga estos pasos para crear un flujo de interfaz de usuario web simple:

## <a name="create-a-web-ui-flow"></a>Creación de un flujo de IU Web

1. Abra la [versión siguiente de Microsoft Edge](https://www.microsoftedgeinsider.com/) o Google Chrome y, a continuación, vaya a [Power Automatic](https://flow.microsoft.com/).

1. Iniciar sesión con una cuenta profesional o educativa si es necesario.

1. Seleccione **Mis flujos** > **flujos de interfaz de usuario (vista previa)**  > **nuevo**.

   ![Crear nuevo flujo de IU](../media/create-windows-ui-flow/create-new.png "Crear nuevo flujo de IU")

1. Seleccionar **aplicación Web** > **siguiente**
    
   ![Seleccionar aplicación Web](../media/create-web-ui-flow/select-web-app.png "Seleccionar aplicación Web")

1. Escriba un nombre para el flujo de la interfaz de usuario en el campo **nombre de flujo** .

1. Escriba la dirección URL del sitio web que desea automatizar en el campo **dirección URL base** y, a continuación, seleccione **iniciar grabadora**.

   ![Asignar un nombre y una dirección URL](../media/create-web-ui-flow/give-a-name.png "Asignar un nombre y una dirección URL") 

   Se inicia el IDE de Selenium.

   >[!TIP] 
   >Sugerencia: puede grabar acciones en varios sitios Web HTTP o HTTPS dentro de la misma pestaña.  

1. En el IDE de Selenium, seleccione el botón de **grabación** en rojo en la parte superior derecha de la pantalla para iniciar la grabadora.

   Se abre la dirección URL que eligió en el paso anterior.

   ![Seleccionar REC](../media/create-web-ui-flow/select-rec.png "Seleccionar REC")

1.  Realice las acciones que desea grabar en el sitio Web. 
    
    >[!TIP]
    >En la parte inferior derecha, puede ver el estado de la grabación.

    ![Estado de grabación](../media/create-web-ui-flow/recording-status.png "Estado de grabación")

1.  Cuando haya terminado de grabar, seleccione en el botón de **Stop** rojo situado en la esquina superior derecha del IDE de Selenium.

    ![Botón detener](../media/create-web-ui-flow/stop-button.png "Botón detener" )

1. Seleccione el botón **Ejecutar prueba actual** en la parte superior izquierda de la pantalla para ver el flujo de la interfaz de usuario que acaba de crear.

    ![Ejecutar prueba actual](../media/create-web-ui-flow/run-test.png "Ejecutar prueba actual")

   >[!TIP]
   >Puede establecer el tiempo de espera entre pasos para ralentizar la reproducción local para las pruebas. Esta configuración es solo para pruebas y no tiene ningún impacto cuando se implementa el flujo de la interfaz de usuario.  
  
1. Seleccione el botón **Guardar proyecto** en la parte superior derecha del IDE de Selenium. Esto cierra y, a continuación, carga el proyecto.

Ahora que ha creado un flujo de interfaz de usuario Web, úselo en otros flujos.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitaciones y problemas conocidos de los flujos de interfaz de usuario Web

>[!WARNING]
>**Las contraseñas en el IDE de Selenium se almacenan en texto sin formato.**  


**Los flujos de la interfaz de usuario ya no registran ni reproducen aplicaciones de Windows después de instalar una nueva versión.**

Debe desinstalar la versión anterior antes de instalar una nueva.

Para ello, abra el menú Inicio, vaya a **configuración** > **aplicaciones**, busque **flujos de interfaz de usuario** en la lista de aplicaciones > flujos de interfaz de **usuario (versión preliminar)** y, a continuación, seleccione "desinstalar". El asistente le guiará a través del proceso.

**Perfil de usuario temporal para la reproducción**

Las grabaciones del IDE de Selenium se realizan con el perfil del usuario actual, pero la reproducción se realiza mediante un perfil de usuario temporal. Esto significa que los sitios web que necesitan autenticación no pueden solicitar credenciales durante una sesión de grabación, pero los pasos de autenticación serán necesarios durante la reproducción. 

Para solucionarlo, el usuario debe modificar manualmente el script para insertar los comandos necesarios para el proceso de inicio de sesión.

**Otras limitaciones**

-   Grabar aplicaciones de escritorio durante una sesión de grabación en Web. Si necesita automatizar aplicaciones web y de escritorio, puede crear flujos de interfaz de usuario independientes para cada tipo y, a continuación, combinarlos en un flujo.

-   Multi-Factor Authentication (MFA) no es compatible, use un inquilino que no requiera MFA.

-   No se admiten estos comandos del IDE de Selenium: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, ECHO, MouseOut, MouseUpAt y MouseDownAt.

-   No se admite el clic con el botón secundario. 

-   Se genera una entrada de flujo de IU Web adicional cuando se usan comandos foreach. Para evitar este problema, especifique cualquier valor en los campos adicionales. No afecta a la reproducción.

-   Si el archivo. Side contiene varios proyectos de prueba, solo se ejecuta el primero que se creó. 

     >[!TIP]
     >Tenga en cuenta que el IDE de Selenium ordena las pruebas por nombre, no por fecha de creación, por lo que es posible que la primera prueba creada no sea la primera de la lista.

-   Es posible que la reproducción directamente en el IDE de Selenium no se comporte según lo previsto. Sin embargo, la reproducción en tiempo de ejecución a través de la infraestructura de flujo de IU se comporta correctamente.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre cómo [ejecutar flujos de interfaz de usuario](run-ui-flow.md).

- Si desea hacer más cosas con los flujos de la interfaz de usuario, también puede probar flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md) .

