---
title: Crear un flujo de aprobación que requiere que todos los usuarios aprueben | Microsoft Docs
description: Cree un flujo de aprobación que requiera que todos los usuarios aprueben o una persona para rechazar una solicitud.
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
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 191792c356dc6b5e3a285a16050a306d4e6039f2
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545201"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Crear un flujo de aprobación que requiera que todos los usuarios aprueben
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este tutorial se muestra cómo crear un flujo de trabajo de aprobación que requiere que todos (todos los aprobadores asignados) acepten la aprobación de una solicitud de vacaciones, pero cualquier aprobador puede rechazar toda la solicitud.

Este tipo de flujo de trabajo de aprobación es útil en una organización que requiere que el administrador de una persona y el administrador del administrador acuerden una solicitud de vacaciones para que se apruebe. Sin embargo, cualquier administrador puede rechazar la solicitud sin la información de la otra persona.

> [!NOTE]
> Aunque en este tutorial se resalta un escenario de aprobación de vacaciones, puede usar este tipo de flujo de aprobación en cualquier situación en la que se necesiten varios aprobadores para aprobar una solicitud.
>
>

## <a name="prerequisites"></a>Requisitos previos

* Acceso a [Microsoft Flow](https://flow.microsoft.com), Microsoft Office 365 Outlook y Microsoft Office 365 usuarios.
* Una [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194)de SharePoint.

    En este tutorial se da por supuesto que ha creado una lista de SharePoint que se usa para solicitar vacaciones. Consulte el tutorial de [aprobaciones en paralelo](parallel-modern-approvals.md) para obtener un ejemplo detallado en el que se detalla el aspecto que podría tener su lista de SharePoint.
* Familiaridad con los conceptos básicos de la creación de flujos.

    Puede revisar cómo agregar [acciones, desencadenadores](multi-step-logic-flow.md#add-another-action)y [condiciones](add-condition.md). En los pasos siguientes se da por hecho que sabe cómo realizar estas acciones.

> [!NOTE]
> Aunque usamos SharePoint y Office 365 Outlook en este tutorial, puede usar otros servicios como zendesk, Salesforce, Gmail o cualquiera de los servicios de más de [200](https://flow.microsoft.com/connectors/) que Microsoft Flow admita.
>
>

## <a name="create-the-flow"></a>Creación del flujo

> [!NOTE]
> Si no ha creado previamente una conexión a SharePoint u Office 365, siga las instrucciones cuando se le pida que inicie sesión.
>
>

En este tutorial se usan tokens. Para mostrar la lista de tokens, pulse o haga clic en cualquier control de entrada y, a continuación, busque el token en la lista de **contenido dinámico** que se abre.

Inicie sesión en [Microsoft Flow](https://flow.microsoft.com)y, a continuación, realice los pasos siguientes para crear el flujo.

1. Seleccione **Mis flujos** > **crear desde**cero, en la parte superior derecha de la pantalla.
1. Agregue el desencadenador **SharePoint-cuando se crea o modifica un elemento** .
1. Escriba la **dirección del sitio** para el sitio de SharePoint que hospeda la lista de solicitudes de vacaciones y, a continuación, seleccione el **nombre de lista**de lista.
1. Agregue la acción **Office 365 usuarios-obtener administrador V2** , seleccione el cuadro **usuario (UPN)** y, a continuación, agregue el token **creado por correo electrónico** .

    El token **creado por correo electrónico** se encuentra en la categoría **cuando se crea o modifica un elemento** de la lista de **contenido dinámico** . Este token proporciona dinámicamente el acceso a los datos sobre el administrador de la persona que creó el elemento en SharePoint.

1. Agregue otra acción **usuarios de Office 365-obtener administrador V2** y, a continuación, agregue el token de **correo** al cuadro **usuario (UPN)** .

    El token de **correo** se encuentra en la categoría **obtener administrador V2 2** de la lista de **contenido dinámico** . Este token proporciona acceso de forma dinámica a la dirección de correo electrónico para el administrador del administrador.

    También puede cambiar el nombre de la tarjeta **Get Manager V2 2** a algo que sea significativo, como "omitir administrador de nivel".
1. Agregue la acción **iniciar una aprobación** y, a continuación, seleccione **todos en la lista asignado** de la lista **tipo de aprobación** .

   > [!IMPORTANT]
   > Si un aprobador rechaza, la solicitud de aprobación se considera rechazada para todos los aprobadores.
   >
   >
1. Use la tabla siguiente como guía para completar la tarjeta **iniciar una aprobación** .

   | Campo | Denominación |
   | --- | --- |
   |  Tipo de aprobación |Use **cualquiera de la lista asignada** para indicar que cualquiera de los aprobadores puede aprobar o rechazar la solicitud. </p>Use **todos los usuarios de la lista asignada** para indicar que solo se aprueba una solicitud si todos los usuarios aceptan y se deniega la solicitud si una sola persona la rechaza. |
   |  Titulo |Título de la solicitud de aprobación. |
   |  Asignado a |Las direcciones de correo electrónico de los aprobadores. |
   |  Indicaciones |Cualquier información adicional que desee enviar a los aprobadores que aparecen en el campo **asignado a** . |
   |  Vínculo de elemento |Dirección URL del elemento de aprobación. En este ejemplo, es un vínculo al elemento en SharePoint. |
   |  Descripción del vínculo del elemento |Una descripción de texto para el **vínculo del elemento**. |

   > [!TIP]
   > La acción **iniciar una aprobación** proporciona varios tokens, incluido el **Resumen**de **respuesta** y respuesta. Use estos tokens en el flujo para proporcionar informes completos de los resultados de una ejecución de un flujo de solicitud de aprobación.
   >
   >

    La tarjeta **iniciar una aprobación** es una plantilla para la solicitud de aprobación que se envía a los aprobadores. Configúrelo de manera que sea útil para su organización. A continuación se muestra un ejemplo.

    ![iniciar una aprobación](media/all-assigned-must-approve/start-an-approval-card.png)

1. Agregue la acción **Office 365 Outlook-enviar un correo electrónico** y configúrela para enviar un correo electrónico con los resultados de la solicitud.

    Este es un ejemplo del aspecto que podría tener la tarjeta **Enviar un correo electrónico** .

    ![Enviar un correo electrónico](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Las acciones que siguen a la acción **iniciar una aprobación** se ejecutan en función de la selección realizada en la lista **tipo de aprobación** de la tarjeta **iniciar una aprobación** . En la tabla siguiente se muestra el comportamiento en función de la selección.
>
>

| Tipo de aprobación | Conducta |
| --- | --- |
| Cualquier persona de la lista asignada |Las acciones que siguen a la acción **iniciar una aprobación** se ejecutan después de que uno de los aprobadores decida. |
| Todos los usuarios de la lista asignada |Las acciones que siguen a la acción **iniciar una aprobación** se ejecutan después de que un aprobador rechace o todos apruebe la solicitud. |

En la parte superior de la pantalla, escriba un nombre para el flujo en el cuadro **nombre de flujo** y, a continuación, seleccione **Crear flujo** para guardarlo.

Enhorabuena, el flujo ha finalizado. Si lo ha seguido, el flujo es similar a esta imagen.

![imagen de flujo general](media/all-assigned-must-approve/overall-flow.png)

Ahora, cada vez que se agrega un elemento a la lista de SharePoint o si un elemento cambia, el flujo desencadena y envía solicitudes de aprobación a todos los aprobadores que se enumeran en el cuadro **asignado a** de la tarjeta **iniciar una aprobación** . El flujo envía solicitudes de aprobación a través de la aplicación móvil de Microsoft Flow y por correo electrónico. La persona que crea el elemento en SharePoint recibe un correo electrónico que resume los resultados, lo que indica claramente si la solicitud se ha aprobado o rechazado.

Este es un ejemplo de la solicitud de aprobación que se envía a cada aprobador.

![solicitud de aprobación](media/all-assigned-must-approve/approval-request.png)

Este es un ejemplo del aspecto que puede tener una respuesta y un resumen de la respuesta después de que se ejecute el flujo.

![tokens de respuesta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Más información sobre las aprobaciones

* [Aprobaciones modernas de un aprobador único](modern-approvals.md)
* [Aprobaciones modernas secuenciales](sequential-modern-approvals.md)
* [Aprobaciones modernas en paralelo](parallel-modern-approvals.md)
* [Aprobaciones y Microsoft Common Data Service](common-data-model-approve.md)
* [Aprobar solicitudes sobre la marcha](mobile-approvals.md)
