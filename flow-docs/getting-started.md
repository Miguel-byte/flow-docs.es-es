---
title: Introducción | Microsoft Docs
description: Formas rápidas de empezar a automatizar el trabajo y la vida con Power Automatic
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 54d1478f34743b6059692b927da8baf2c49a35a7
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589850"
---
# <a name="get-started-with-power-automate"></a>Introducción a Power Automatic

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Programa! Power Automate es un servicio que le ayuda a crear flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, obtener notificaciones, recopilar datos y mucho más.

Los principales tipos de flujos son los flujos de [procesos](business-process-flows-overview.md) [automatizados](get-started-logic-flow.md), [botones](introduction-to-button-flows.md), [programados](run-scheduled-tasks.md)y empresariales.

## <a name="types-of-flows"></a>Tipos de flujos

Power Automatic es uno de los tres pilares de la plataforma de energía. Proporciona una plataforma de código baja para automatizar los procesos y flujos de trabajo. Esta es una lista de los diferentes tipos de flujos:

| **Tipo de flujo**                                                                       | **Caso de uso**                                                                                  | **Dirigir**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Flujos automatizados](get-started-logic-flow.md)                 | Cree un flujo que realice una o varias tareas automáticamente una vez desencadenada por un evento. | [Conectores](https://docs.microsoft.com/connectors/) para servicios en la nube o locales. |
| [Flujos de botón](introduction-to-button-flows.md)              | Ejecutar tareas repetitivas desde cualquier lugar, en cualquier momento, a través del dispositivo móvil.                        |                                                                                        |
| [Flujos programados](run-scheduled-tasks.md)                    | Cree un flujo que realice una o varias tareas según una programación.             |                                                                                        |
| [Flujos de procesos empresariales](business-process-flows-overview.md) | Defina un conjunto de pasos para que las personas sigan el resultado deseado.                 | Procesos humanos                                                                        |
| [Flujos de interfaz de usuario (vista previa)](ui-flows/overview.md)                                                | Grabe y automatice la reproducción de pasos manuales en el software heredado.                    | Aplicaciones web y de escritorio que no tienen API disponibles para la automatización.    |

Puede crear y administrar todos los flujos desde la pestaña **Mis flujos** de Power Automatic.

Si es un usuario de Dynamics 365, también puede estar familiarizado con los procesos de Common Data Service clásico que incluyen, [flujos de trabajo](configure-workflow-steps.md), [acciones](create-actions.md), [flujos de tareas móviles](create-mobile-task-flow.md)y [cuadros de diálogo](use-cds-for-apps-dialogs.md).

El primer paso es [registrarse](sign-up-sign-in.md)o, si ya tiene una cuenta con Power Automatic, [inicie sesión](https://flow.microsoft.com/signin) en su tableta, en el equipo de escritorio o incluso en su teléfono.

## <a name="check-out-the-start-page"></a>Consultar la página de inicio ##

[En la página de inicio](https://flow.microsoft.com) de Power Automate, puede [explorar un conjunto diverso de plantillas](https://flow.microsoft.com/templates) y obtener información sobre las características clave para la automatización de la energía. Puede obtener una idea rápida de lo que es posible y de cómo la automatización de la capacidad puede ayudar a su empresa y su vida.

Con Power Automatic, puede:

- Busque plantillas y servicios fácilmente.

    ![Página de inicio de flujo 1](./media/getting-started/flowhome1.png)

- Elija entre los servicios más populares.

    ![Página de inicio de Flow 2](./media/getting-started/flowhome2.png)

- Vea información general de cada flujo.

    ![Página de inicio de Flow 3](./media/getting-started/flowhome3.png)

Cada plantilla está diseñada para un propósito específico. Por ejemplo, hay plantillas para enviarle un mensaje de texto cuando su jefe le envíe por correo electrónico, agregar clientes potenciales de Twitter a Dynamics 365 o realizar copias de seguridad de los archivos. Estas plantillas son solo la punta del iceberg. Están diseñados para inspirarse en la creación de flujos personalizados para los procesos exactos que necesita.

## <a name="create-your-first-flow"></a>Creación del primer flujo ##

1. Seleccione una plantilla que le resulte útil. Una plantilla sencilla es [**obtener recordatorios diarios en el correo electrónico**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![plantilla de recordatorio diaria](./media/getting-started/template-details.png)

1. Seleccione **continuar**.

    ![Crear conexión](./media/getting-started/create-connection.png)

1. Escriba las direcciones de correo electrónico a las que se enviará el recordatorio diario. A continuación, escriba el mensaje de recordatorio. Por último, seleccione **Crear flujo**y compruebe que el flujo se ejecuta según lo previsto.

    ![Proporcionar credenciales para la conexión](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Puede explorar las condiciones que desencadenan el flujo y la acción resultante de ese evento. Experimente con la configuración para hacer que el flujo sea el suyo propio. Incluso puede Agregar o eliminar acciones.

1. Seleccione **listo**.

[Siga este tutorial](get-started-logic-template.md) para obtener más información sobre la creación de flujos a partir de plantillas.

## <a name="get-creative"></a>Obtener creativo ##

Ahora que ha creado su primer flujo a partir de una plantilla, use cualquiera de los [orígenes de datos](https://flow.microsoft.com/connectors/) más de 150 que admite automatización para [crear sus propios flujos desde cero](get-started-logic-flow.md).

![Creación de un flujo](./media/getting-started/build-a-flow.png)

Cuando se crea un flujo desde cero, se controla el flujo de trabajo completo. Estas son algunas ideas para empezar:

- [Flujos con muchos pasos](multi-step-logic-flow.md).
- [Ejecutar tareas según una programación](run-scheduled-tasks.md).
- [Cree un flujo de aprobación](wait-for-approvals.md).
- [Vea un flujo en acción](see-a-flow-run.md).
- [Publicar una plantilla](publish-a-template.md).
- [Crear flujos a partir de una plantilla de Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Inspeccionar el código

No es necesario ser desarrollador para crear flujos; sin embargo, la función de automatización automatizada proporciona una característica de **código PEEK** que permite a cualquier persona examinar más de cerca el código que se genera para todas las acciones y los desencadenadores de un flujo. Al inspeccionar el código, puede obtener una descripción más clara de los datos que usan los desencadenadores y las acciones. Siga estos pasos para inspeccionar el código que se genera para los flujos desde el diseñador de automatización de energía: 

1. Seleccione el elemento de menú **...** en la esquina superior derecha de cualquier **acción** o **desencadenador**. 
1. Seleccione **inspeccionar código**.

    ![Inspeccionar código](media/getting-started/peek-code.png)

1. Observe la representación JSON completa de las acciones y los desencadenadores. Esto incluye todas las entradas, como el texto que escribe directamente, y las expresiones usadas. Puede seleccionar expresiones aquí y, a continuación, pegarlas en el editor de expresiones de **contenido dinámico** . Esto también puede proporcionarle una manera de comprobar que los datos esperados están presentes en el flujo.

    ![Inspeccionar código](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Encuentre sus flujos fácilmente

Cuando los zumos creativos empiecen a *fluir*, podría crear muchos flujos. No se preocupe, la búsqueda de flujos es fácil: Use el cuadro de búsqueda de la pantalla **Mis flujos**, **flujos de equipo**, **conexiones**o **soluciones** para mostrar solo los flujos que coincidan con los términos de búsqueda especificados.

![Flujos de búsqueda o filtrado](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> El filtro de búsqueda solo encuentra los flujos que se han cargado en la página. Si no encuentra el flujo, pruebe a seleccionar **cargar más** en la parte inferior de la página.

## <a name="get-notifications-when-somethings-wrong"></a>Recibir notificaciones cuando haya algún problema

Use el centro de notificaciones de Power Automatic (que se encuentra en la parte superior derecha del diseñador) para ver rápidamente una lista de flujos con errores recientemente. El centro de notificaciones muestra un número que indica el número de flujos que dieron error recientemente.

Desde el centro de notificaciones, puede ir a la página de **actividades** de Power Automate para ver todos los flujos que se ejecutaron recientemente, notificaciones enviadas o con errores.

![Centro de notificaciones](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Uso de la aplicación móvil ##

Descargue la aplicación móvil Power Automatic para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows). Con esta aplicación, puede [supervisar la actividad de Flow](mobile-monitor-activity.md), [administrar los flujos](mobile-manage-flows.md) y [crear flujos a partir de plantillas](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Estamos aquí para ayudarle ##

Nos complace ver lo que hace con Power Automate y queremos asegurarnos de que tiene una gran experiencia. Asegúrese de consultar nuestros tutoriales de [aprendizaje guiado](https://flow.microsoft.com/guided-learning/) y [Únase a nuestra comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) para hacer preguntas y compartir sus ideas. [Póngase en contacto con el soporte técnico](https://go.microsoft.com/fwlink/?LinkID=787479) si tiene problemas.
