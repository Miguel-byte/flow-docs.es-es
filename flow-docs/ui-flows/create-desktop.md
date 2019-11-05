---
title: Aprenda a crear flujos de interfaz de usuario de escritorio | Microsoft Docs
description: Aprenda a crear flujos de interfaz de usuario de escritorio para aplicaciones Windows.
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
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589796"
---
# <a name="create-and-test-desktop-ui-flows"></a>Crear y probar flujos de IU de escritorio

[Este tema es documentación preliminar y está sujeto a cambios].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Cree flujos de IU de escritorio para automatizar las aplicaciones de escritorio de Windows. 

Consulte los [problemas conocidos](create-desktop.md#known-issues-and-solutions) que se encuentran más adelante en este tema para obtener más información sobre los problemas con los que puede encontrarse, soluciones alternativas para estos problemas y escenarios que no se admiten en esta versión preliminar.


> [!TIP]
> Puede automatizar otras aplicaciones de escritorio de Windows siguiendo un patrón similar.

## <a name="create-a-desktop-ui-flow"></a>Crear un flujo de IU de escritorio

En los pasos siguientes, se muestra cómo automatizar la aplicación calculadora para sumar dos números y, después, almacenar el resultado para su uso posterior. 

1. Asegúrese de que el [dispositivo está listo](setup.md) para crear flujos de interfaz de usuario. <!--Todo: link to the prereqs section-->

1. Use la [versión de cromo de Microsoft Edge](https://www.microsoftedgeinsider.com) o Google Chrome para abrir [Power Automatic](https://flow.microsoft.com)y, a continuación, inicie sesión con una cuenta de correo electrónico profesional o educativa.

1. Seleccione **Mis flujos** > **flujos de interfaz de usuario (vista previa)**  > **nuevo**.

   ![Crear nuevo flujo de IU](../media/create-windows-ui-flow/create-new.png "Crear nuevo flujo de IU")

1. Elija **aplicación de escritorio** y, a continuación, seleccione **siguiente**.

   ![Seleccionar escritorio](../media/create-windows-ui-flow/select-desktop.png "Seleccionar escritorio") 

1. Escriba un nombre para el flujo de la interfaz de usuario en el campo **nombre de flujo** y, a continuación, seleccione **siguiente**.

   ![Seleccionar escritorio](../media/create-windows-ui-flow/give-a-name.png "Seleccionar escritorio") 

1. Seleccione **siguiente** en la parte inferior para omitir la pantalla **Configurar entradas** opcional, ya que no usamos entradas en este tutorial.

1. Seleccione la tarjeta **registrar aplicación** para expandirla.

   ![Selección de la aplicación de registro](../media/create-windows-ui-flow/select-record-app.png "Selección de la aplicación de registro")

1. Seleccione **iniciar la grabadora**.

   ![Seleccionar la grabadora de Launch](../media/create-windows-ui-flow/select-launch-recorder.png "Seleccionar la grabadora de Launch")

   El control de la grabadora se muestra en la parte superior de la pantalla.

   ![El control de la grabadora](../media/create-windows-ui-flow/recorder-control.png "El control de la grabadora")

1. Inicie la aplicación calculadora.

     >[!TIP]
     >Al mantener el mouse sobre los controles de la aplicación, observará que un contorno azul resalta cada control. Espere siempre el resaltado azul antes de seleccionar un control.
     >
     >Si el resaltado azul no aparece alrededor del elemento, es posible que no se grabe correctamente.

1. Seleccione **registro** en el control de la grabadora.
1. Seleccione el primer número, seleccione **+** , seleccione el segundo número y, a continuación, seleccione **=** .

    ![La aplicación calculadora](../media/create-windows-ui-flow/app-to-record.png "La aplicación calculadora")

1. Seleccione **listo** en el control de la grabadora después de completar las acciones que desea grabar.

1. Cierre la aplicación que grabó.

1. Seleccione la tarjeta que empieza por "ejecutar script <app name>" para ver capturas de pantallas de los pasos grabados.

     >[!TIP]
     >Seleccione **...**  > **eliminar** para quitar cualquier paso adicional que desee quitar.

    ![Mostrar pasos grabados](../media/create-windows-ui-flow/show-recorded-steps.png "Mostrar pasos grabados")

1. Seleccione **siguiente**. 

1. Seleccione **siguiente** para omitir el paso de configuración opcional de **salidas** , ya que no estamos usando salidas en este tutorial.

## <a name="test-your-ui-flow"></a>Probar el flujo de la interfaz de usuario

Siempre es una buena idea probar el flujo de la interfaz de usuario. Para ello, seleccione el botón **probar ahora** y vea la ejecución del flujo de la interfaz de usuario.
    
 >[!IMPORTANT]
 >Para obtener los mejores resultados, no interactúe con el dispositivo mientras dure la reproducción.

1. Seleccione **Guardar y salir** para guardar el flujo y salir de la característica flujos de interfaz de usuario.


## <a name="known-issues-and-solutions"></a>Problemas conocidos y soluciones

- Abra y maximice las aplicaciones que quiera *grabar antes de* empezar a grabar.

- Puede que desee agregar una acción de [ **cierre** ](edit-desktop.md#add-a-manual-action) al final del flujo de la interfaz de usuario, ya que flujos de interfaz de usuario inicia una nueva instancia de las aplicaciones con cada prueba o ejecución.

- Seleccione **...**  > **eliminar** en la tarjeta acciones grabadas para quitar cualquier acción innecesaria o duplicada. Se pueden crear acciones duplicadas según el tipo y la velocidad de grabación. 

- Es posible que los clics con el botón secundario no se reproduzcan correctamente. En tal caso, durante la grabación, haga clic en izquierda para enfocar flujos de IU en el elemento de la interfaz de usuario de destino y, a continuación, haga clic con el botón derecho.

- Si la interfaz de usuario ya no registra ni reproduce aplicaciones de Windows después de instalar una nueva versión, desinstale la versión anterior y, a continuación, instale una nueva versión.


### <a name="unsupported-application-types"></a>Tipos de aplicación no admitidos

-   Interacciones en Windows (explorador de archivos, menú Inicio, barra de tareas, etc.).

-   Exploradores Web (Chrome, IE, Edge, Edge cromo, Firefox, Mozilla, etc.).
    En su lugar, consulte [creación de un flujo de interfaz de usuario Web](edit-web.md) para automatizar sitios Web.

-   Aplicaciones Java.

-   Haga clic una vez en aplicaciones.

-   Aplicaciones con una vista Web como, por ejemplo, aplicaciones de electrones.

-   Microsoft Office 2016 y versiones anteriores. 

-   Microsoft Office en línea.

### <a name="unsupported-configurations"></a>Configuraciones no admitidas

-   Varias pantallas.

-   Grabar a través de un cliente de máquina virtual (Escritorio remoto, Citrix, etc.), ya sea con la aplicación flujos de interfaz de usuario que se ejecuta en el dispositivo host o en la máquina virtual. No se admite ninguno.

-   Varias instancias de una aplicación en las que los títulos de ventana principal son idénticos.

-   Ventanas de aplicaciones con títulos idénticos, por ejemplo, Microsoft Outlook con varias ventanas de correo sin **título (html)** nuevas ventanas de correo activas al mismo tiempo.

-   Sesiones de grabación simultáneas en un dispositivo determinado.

-   Sesiones de reproducción simultáneas en un dispositivo determinado. En el caso de las ejecuciones de flujo de la interfaz de usuario simultáneas, la primera tiene prioridad y las siguientes generan un error hasta que se completa la primera.

-   Reproducción en un dispositivo con una distribución de teclado diferente a la del dispositivo en el que se grabó.

-   Grabar en un dispositivo o una sesión de Windows mientras el explorador con Microsoft Flow está en otro dispositivo o sesión de Windows.

### <a name="unsupported-action-types-and-behaviors"></a>Tipos de acción y comportamientos no admitidos

No se registrarán las acciones siguientes:

-   Haga doble clic en.

-   Movimiento del mouse.

-   Mantener el mouse.

-   Haga clic y arrastre.

-   Entrada táctil o de lápiz.

-   Abra la aplicación antes de la grabación.

-   Aplicación cerrada antes de que se inicie la reproducción.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportamientos no confiables y soluciones alternativas para Microsoft Office (escritorio)
- Ancle la cinta de opciones antes de comenzar la reproducción para evitar problemas que pueden producirse si la cinta de opciones está configurada para ocultarse automáticamente durante la reproducción.
- No seleccione elementos haciendo clic y arrastrando. Por ejemplo, no use Mayús + clic para seleccionar celdas en Microsoft Excel y no seleccione texto en Microsoft Word o Microsoft PowerPoint arrastrando el mouse.
- Es posible que algunos elementos no funcionen correctamente en flujos de interfaz de usuario (versión preliminar) para las aplicaciones de escritorio de Microsoft Word y Microsoft PowerPoint. Por ejemplo, las opciones del menú Archivo, como iniciar desde cero o hacer clic con el botón secundario en controles como agregar un párrafo en Microsoft Word o cambiar el diseño de las diapositivas en Microsoft PowerPoint pueden no funcionar.

## <a name="next-steps"></a>Pasos siguientes

- Aprenda a [desencadenar el flujo de la interfaz de usuario](run-ui-flow.md) que acaba de crear.

- Si desea hacer más cosas con los flujos de la interfaz de usuario, también puede probar flujos de interfaz de usuario con parámetros de [entrada y salida](inputs-outputs-web.md) .

