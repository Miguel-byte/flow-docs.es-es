---
title: Introducción | Microsoft Docs
description: Formas rápidas de empezar a automatizar el trabajo y la vida con Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f667401774e49505009cd416f6975ff38683a5c7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035255"
---
# <a name="get-started-with-microsoft-flow"></a>Introducción a Microsoft Flow #

<iframe width="560" height="315" src="https://www.youtube.com/embed/iMteXfAvDSE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Bienvenido. Microsoft Flow es un servicio con el que podrá crear flujos de trabajo automatizados entre sus aplicaciones y servicios favoritos para sincronizar archivos, recibir notificaciones, recopilar datos y mucho más.

Los principales tipos de flujos son [automatizados](get-started-logic-flow.md), [botón](introduction-to-button-flows.md), [programados](run-scheduled-tasks.md) y [proceso empresarial](business-process-flows-overview.md).

Si es un personalizador de Dynamics 365 Customer Engagement, puede que también esté familiarizado con los procesos clásicos de Common Data Service, entre los que se incluyen [flujos de trabajo](configure-workflow-steps.md), [acciones](create-actions.md), [flujos de tareas móviles](create-mobile-task-flow.md) y [cuadros de diálogo](use-cds-for-apps-dialogs.md).

El primer paso es [registrarse](sign-up-sign-in.md) o, si ya tiene una cuenta de Microsoft Flow, [iniciar sesión](https://flow.microsoft.com/signin) directamente en su tableta o equipo de escritorio, o incluso en su teléfono.

## <a name="check-out-the-start-page"></a>Visitar la página de inicio ##

[En la página de inicio](https://flow.microsoft.com) de Microsoft Flow, puede [explorar una amplia variedad de plantillas](https://flow.microsoft.com/templates) y obtener más información sobre las características clave. Se hará una idea rápidamente de lo que Microsoft Flow puede hacer y de cómo puede ayudarle tanto en el ámbito profesional como personal.

Con Microsoft Flow, puede hacer lo siguiente:

- Buscar fácilmente servicios y plantillas.

    ![Página de inicio de Flow (1)](./media/getting-started/flowhome1.png)

- Elegir un servicio de entre los más populares.

    ![Página de inicio de Flow (2)](./media/getting-started/flowhome2.png)

- Ver información general sobre cada flujo.

    ![Página de inicio de Flow (3)](./media/getting-started/flowhome3.png)

Cada plantilla está diseñada para un propósito específico. Por ejemplo, el envío de un mensaje de texto cuando su jefe le envíe correos electrónicos, la incorporación de clientes potenciales de Twitter a Dynamics 365 o la realización de copias de seguridad de sus archivos. Estas plantillas son solo el aspecto más destacado, pero hay mucho más. Están diseñadas para inspirarle a crear flujos personalizados para cualquier proceso que necesite.

## <a name="create-your-first-flow"></a>Creación del primer flujo ##

1. Seleccione una plantilla que le resulte útil. Una plantilla sencilla es [**Recibir recordatorios diarios en el correo**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![plantilla de recordatorio diario](./media/getting-started/template-details.png)

1. Seleccione **Continuar**.

    ![Creación de una conexión](./media/getting-started/create-connection.png)

1. Escriba las direcciones de correo electrónico a la que se enviará el recordatorio diario. A continuación, escriba el mensaje recordatorio. Por último, seleccione **Crear flujo** y compruebe que el flujo se ejecuta como cabría esperar.

    ![Indicar las credenciales para la conexión](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Ahora puede explorar las condiciones que desencadenan el flujo y la acción que se deriva de dichos eventos. Aproveche para experimentar con la configuración y crear su propio flujo. Incluso puede agregar o eliminar acciones.

1. Seleccione **Listo**.

[Siga este tutorial](get-started-logic-template.md) para obtener más información sobre la creación de flujos a partir de plantillas.

## <a name="get-creative"></a>Creatividad ##

Ahora que ha creado su primer flujo a partir de una plantilla, use cualquiera de los más de [150 orígenes de datos](https://flow.microsoft.com/connectors/) que Microsoft Flow admite para [crear sus propios flujos desde cero](get-started-logic-flow.md).

![Compilación de un flujo](./media/getting-started/build-a-flow.png)

Si crea un flujo de trabajo desde cero, podrá controlarlo en su totalidad. Aquí le presentamos algunas ideas para empezar:

- [Flujos con muchos pasos](multi-step-logic-flow.md)
- [Ejecución de tareas de forma programada](run-scheduled-tasks.md)
- [Creación de un flujo de aprobación](wait-for-approvals.md)
- [Visualización de un flujo en acción](see-a-flow-run.md)
- [Publicación de una plantilla](publish-a-template.md)
- [Creación de flujos desde una plantilla de Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/)


## <a name="peek-at-the-code"></a>Inspeccionar el código

No es necesario ser programador para crear flujos, sin embargo, Microsoft Flow proporcionan un **inspeccionar código** característica que permite a cualquier usuario echar un vistazo más de cerca el código que se genera para todas las acciones y desencadenadores en un flujo. Inspeccionar el código podría dar una comprensión más clara de los datos que se usa desencadenadores y acciones. Siga estos pasos para ver el código que se genera para los flujos desde dentro del Diseñador de Microsoft Flow: 

1. Seleccione el **...**  elemento de menú en la esquina superior derecha de cualquier **acción** o **desencadenador**. 
1. Seleccione **inspeccionar código**.

    ![Inspeccionar código](media/getting-started/peek-code.png)

1. Tenga en cuenta la representación JSON completa de las acciones y desencadenadores. Esto incluye todas las entradas, como escribir directamente el texto y las expresiones usadas. Puede seleccionar las expresiones aquí y, a continuación, péguelos en el **contenido dinámico** editor de expresiones. También esto puede proporcionar una forma para comprobar los datos esperados están presentes en el flujo.

    ![Inspeccionar código](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Encontrar fácilmente los flujos

Cuando su creatividad inicio *fluir*, podría crear varios flujos. No se preocupe, buscar los flujos es fácil: use el cuadro de búsqueda en el **Mis flujos**, **flujos del equipo**, **conexiones**, o **soluciones** pantalla para mostrar sólo flujos que coinciden con los términos de búsqueda que especifique.

![Filtrar o buscar flujos](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> El filtro de búsqueda sólo busca flujos que se han cargado en la página. Si no encuentra el flujo, pruebe a seleccionar **cargar más** en la parte inferior de la página.

## <a name="get-notifications-when-somethings-wrong"></a>Recibir notificaciones cuando algo va mal

Use el centro de notificaciones de Microsoft Flow (ubicada en la parte superior derecha del diseñador) a rápidamente vea una lista de flujos han fallado recientemente. El centro de notificaciones muestra un número que indica el número de flujos que no se pudo recientemente.

Desde el centro de notificaciones, puede navegar a la **actividad** página de Microsoft Flow para ver todos los flujos que recientemente se ejecutó, enviar notificaciones o con errores.

![Centro de notificaciones](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Uso de la aplicación móvil ##

Descargue la aplicación móvil de Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) o [Windows Phone](https://aka.ms/flowmobilewindows). Con la aplicación, podrá [supervisar la actividad de los flujos](mobile-monitor-activity.md), [administrarlos](mobile-manage-flows.md) y [crearlos a partir de plantillas](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Podemos ayudarle ##

Tenemos muchas ganas de ver lo que puede hacer con Microsoft Flow y queremos asegurarnos de que tenga una gran experiencia. No olvide visitar nuestros tutoriales de [aprendizaje paso a paso](https://flow.microsoft.com/guided-learning/) ni de [unirse a nuestra comunidad](http://go.microsoft.com/fwlink/?LinkID=787467), donde podrá realizar preguntas y compartir sus ideas. [Póngase en contacto con soporte técnico](http://go.microsoft.com/fwlink/?LinkID=787479) si surge algún problema.
