---
title: Iniciar flujos con BTTN | Microsoft Docs
description: Obtenga información acerca de cómo iniciar los flujos con un BTTN
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545687"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Ejecución de los flujos con botones físicos (BTTN) en el botón Corporation (versión preliminar)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Desencadene los flujos presionando un BTTN (un botón físico realizado por [el botón de la Corporación](https://my.bt.tn/)). Por ejemplo, puede presionar un BTTN que desencadene un flujo para realizar estas tareas:

* Póngase en contacto con el Departamento de soporte técnico con información de ubicación
* envía un correo electrónico al equipo
* bloquea el calendario
* reordena los suministros

> [!IMPORTANT]
> Debe [registrar](https://my.bt.tn/) el BTTN antes de poder usarlo en un flujo.
> 
> [!TIP]
> Configure todas las propiedades de BTTN, como el nombre, la ubicación y la dirección de correo electrónico en el [sitio web de BTTN](https://my.bt.tn/) antes de crear el flujo.
> 
> 

También puede desencadenar un flujo mediante un [botón físico de FLIC](flic-button-flows.md).

## <a name="prerequisites"></a>Requisitos previos
* Acceso a [Microsoft Flow](https://flow.microsoft.com).
* Al menos un [BTTN registrado](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Crear un flujo que se desencadene desde un BTTN
En este tutorial, se usa una plantilla de Departamento de soporte técnico para crear un flujo que se puede desencadenar con una sola pulsación de un [BTTN](https://my.bt.tn/). Cuando el flujo se ejecuta, genera una solicitud de soporte técnico y, a continuación, la envía al Departamento de soporte técnico. La solicitud de soporte técnico proporciona al Departamento de soporte técnico la ubicación de la sala donde se necesita ayuda. En este tutorial se muestra cómo crear este flujo a partir de una plantilla, pero puede usar la plantilla en blanco, que le proporciona control total sobre todos los aspectos del flujo.

Puede usar cualquiera de estas plantillas para crear rápidamente flujos para el BTTN y conectarse a zendesk, Google y SharePoint, entre otros:

![plantillas de BTTN](./media/bttn-button-flows/bttn-templates.png)

Sugerencia: para los fines de este tutorial, asigne a su BTTN un nombre que represente una sala de conferencias en un edificio de oficinas típico.

La configuración de BTTN debe ser similar a la de este ejemplo (desde el sitio web de BTTN):

![plantillas de BTTN](./media/bttn-button-flows/bttn-config.png)

Ahora que ha registrado y configurado su BTTN, vamos a empezar a crear el flujo.

### <a name="sign-in-and-select-a-template"></a>Inicio de sesión y selección de una plantilla
1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com).
   
    ![Inicia sesión](./media/bttn-button-flows/sign-into-flow.png)
   
    Nota: como alternativa, puede crear flujos en la aplicación móvil Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)o [Windows Phone](https://aka.ms/flowmobilewindows).
2. Escriba **BTTN** en el cuadro de búsqueda y, a continuación, seleccione el icono de búsqueda.
   
    ![Buscan](./media/bttn-button-flows/bttn-search-template.png)
   
    Después de seleccionar el icono de búsqueda, aparecen todas las plantillas que puede usar con BTTN.
3. Seleccione la plantilla **usar BTTN para llamar al soporte técnico para la sala de reuniones** .
   
    ![plantilla de soporte](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autorice Microsoft Flow para conectarse a su BTTN
1. Si se le solicita, inicie sesión en BTTN y en los servicios de Office 365 Outlook, que habilitará el botón **continuar** .
   
    ![sus](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Cuando inicie sesión en el servicio BTTN, autorice Microsoft Flow para usar su BTTN.
   
    **Importante**: Si no autoriza Microsoft Flow para usar su BTTN, no podrá ver ni conectarse a ellos desde Microsoft Flow.
   
    ![autorizar](./media/bttn-button-flows/authorize-bttn.png)
3. Después de iniciar sesión en ambos servicios, seleccione **continuar**.
   
    ![Funcionando](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Seleccione el BTTN que desencadena el flujo.
1. En la tarjeta **cuando se presione una BTTN** , abra la lista de identificadores de BTTN y, a continuación, seleccione el BTTN que quiere usar.
   
    ![seleccionar BTTN](./media/bttn-button-flows/bttn-id.png)
   
    El flujo debe parecerse ahora a este ejemplo.
   
    ![Información general de Flow](./media/bttn-button-flows/bttn-done.png)
2. Asigne un nombre al flujo y, a continuación, seleccione **Crear flujo** para guardarlo.
   
    ![guardar flujo](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Probar el flujo y confirmar los resultados
1. Presione el botón del BTTN.
2. Vea el historial de ejecución de su flujo para confirmar que se ejecutó correctamente.
   
    Puede comprobar el historial de ejecución en el sitio web de Microsoft Flow o en su dispositivo móvil.
   
    Nota: el estado de ejecución se establece en en **ejecución** hasta que alguien selecciona **confirmación** en el correo electrónico de solicitud de soporte técnico.
3. También puede confirmar que el correo electrónico se envió al equipo de soporte técnico.
   
    Si ha seguido estos pasos, el correo electrónico de soporte técnico tiene un aspecto similar al de este ejemplo:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Solución
* Si el flujo no se ha desencadenado, inicie sesión en el sitio de Button Corporation y confirme si se está grabando la actividad de botón (presiona).
* También puede profundizar en la actividad de ejecución en el sitio de Microsoft Flow y comprobar si hay mensajes de error.

## <a name="more-information"></a>Más información
* [Compartir flujos de botones](share-buttons.md).
* Aprenda a usar [tokens de desencadenadores de botones](introduction-to-button-trigger-tokens.md) para enviar datos actuales cuando se ejecuten los flujos de botón.
* [Instale la aplicación Microsoft Flow para Android](https://aka.ms/flowmobiledocsandroid).
* [Instale la aplicación Microsoft Flow para iOS](https://aka.ms/flowmobiledocsios).

