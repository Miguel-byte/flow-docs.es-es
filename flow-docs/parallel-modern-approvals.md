---
title: Creación de un flujo de trabajo de aprobación moderna en paralelo | Microsoft Docs
description: Creación de un flujo de trabajo de aprobación moderna paralelo
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548953"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Crear flujos de trabajo de aprobación paralela con Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En un flujo de trabajo de aprobación en paralelo, se necesitan varias personas para aprobar elementos como facturas, pedidos de compra, solicitudes de vacaciones, etc. La aprobación de cada persona es independiente de los demás aprobadores.

En este tutorial, usamos Microsoft Flow para crear un flujo que automatiza un flujo de trabajo de aprobación en paralelo. Este flujo automatiza un proceso de solicitud de vacaciones de los empleados que requiere la aprobación de todas las personas (o equipos) que el empleado admite con regularidad. Los empleados usan una [lista de SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) para solicitar vacaciones. Se requieren aprobaciones de vacaciones del administrador directo del empleado, el equipo de ventas y el equipo de recursos humanos. Cada solicitud de vacaciones se enruta a cada aprobador para tomar una decisión. El flujo envía un correo electrónico con los cambios de estado y, a continuación, actualiza SharePoint con las decisiones.

## <a name="prerequisites"></a>Requisitos previos

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

La lista de SharePoint Online que cree debe incluir las columnas siguientes:

   ![Columnas de lista de SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Anote el nombre y la dirección URL de la lista de SharePoint Online. Estos elementos se usan más adelante para configurar el desencadenador **SharePoint-cuando se crea un elemento** .

## <a name="create-your-flow-from-the-blank-template"></a>Crear el flujo a partir de la plantilla en blanco

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Agregar un desencadenador

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Información de SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtener el administrador de la persona que creó la solicitud de vacaciones

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Asignar un nombre al flujo y guardarlo

1. Proporcione un nombre para el flujo y, a continuación, seleccione el icono **Guardar** para guardar el trabajo que hemos hecho hasta ahora.

   ![guardar flujo](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Seleccione el icono **Guardar** periódicamente para guardar los cambios en el flujo.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Agregar una acción de aprobación para el administrador inmediato

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Esta acción envía la solicitud de vacaciones a la dirección de correo electrónico en el cuadro de **asignado a** , por lo que debe insertar el token de **correo electrónico** de la lista **obtener administrador (V2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Insertar una acción de aprobación de rama paralela para el equipo de ventas

1. Seleccione la flecha hacia abajo que se encuentra entre las tarjetas **obtener administrador (V2)** e **iniciar una aprobación** .
2. Seleccione el signo más que aparece en la flecha hacia abajo después de seleccionarlo.
3. Seleccione **Agregar una rama paralela**.
4. Seleccione **Agregar una acción**.

    ![obtener configuración de administrador](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Busque, seleccione y, a continuación, configure una acción **iniciar una aprobación** que envíe la solicitud de vacaciones al equipo de ventas. Consulte los [pasos que se usan para agregar una acción de aprobación para el administrador inmediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) si no está seguro de cómo agregar la acción **iniciar una aprobación** .

> [!IMPORTANT]
> Use la dirección de correo electrónico del equipo de ventas en el cuadro de **asignado a** de la acción **iniciar una aprobación 2** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Inserción de una acción de aprobación de rama paralela para el equipo de recursos humanos

1. Repita los pasos para [insertar una rama paralela para el equipo de ventas](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) y, a continuación, configure una acción **iniciar una aprobación** para enviar solicitudes de vacaciones a recursos humanos.

> [!IMPORTANT]
> Use la dirección de correo electrónico del equipo de recursos humanos en el cuadro de **asignado a** de la acción **iniciar una aprobación 3** .
> 
> 

Si ha seguido estos pasos, el flujo debe ser similar al de este ejemplo:

   ![flujo con ramas paralelas](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opciones después de Agregar ramas paralelas

Después de haber agregado acciones a las ramas paralelas, tiene dos opciones para agregar más pasos al flujo:

1. Use el botón pequeño **Insertar un nuevo paso** (el botón circular más que aparece al seleccionar cualquier espacio en blanco en una bifurcación o el área que se encuentra justo debajo de una bifurcación). Este botón agrega un paso a esa **rama concreta**. Los pasos que agregue con este botón se ejecutan una vez completada esta rama específica.
1. Use el botón **nuevo paso** grande en la parte inferior del flujo de trabajo completo. Los pasos que agregue con este botón se ejecutan una vez completadas todas las ramas.

En las secciones siguientes, usamos el botón de **inserción de un nuevo paso** para realizar estos pasos en cada rama:

* Agregue una condición que compruebe si se aprobó o rechazó la solicitud de vacaciones.
* Envíe un correo electrónico que informe al empleado de la decisión.
* Actualice la solicitud de vacaciones en SharePoint con la decisión de aprobación.

A continuación, usamos el botón **nuevo paso** más grande para enviar un correo electrónico que resume todas las decisiones tomadas en la solicitud de vacaciones.

Continuemos:

## <a name="add-a-condition-to-each-branch"></a>Agregar una condición a cada rama

1. Seleccione cualquier espacio en blanco en la rama **iniciar una aprobación** .
2. Seleccione el botón pequeño **Insertar un nuevo paso** (el botón circular más que aparece después de seleccionar el espacio en blanco del paso anterior).
3. Seleccione **Agregar una condición** en el menú que aparece.
4. Seleccione el primer cuadro de la tarjeta **condición** y, a continuación, seleccione el token de **respuesta** de la categoría **iniciar una aprobación** en la lista contenido dinámico.

    ![flujo con condición de ramas paralelas](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Confirme que la lista (en el medio de la **tarjeta de condición**) está establecida en **es igual a**.
6. Escriba **aprobar** (este texto distingue entre mayúsculas y minúsculas) en el último cuadro.
7. La tarjeta de condición ahora debe ser similar a la de este ejemplo:

    ![flujo con condición de ramas paralelas](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Esta condición comprueba la respuesta de la acción **iniciar una aprobación** que se dirige al administrador del empleado.
   > 
   > 
8. Repita los pasos anteriores en las ramas **iniciar una aprobación 2** (solicitud de aprobación para ventas) e **iniciar una aprobación 3** (la solicitud de aprobación a recursos humanos).

## <a name="add-email-actions-to-each-branch"></a>Agregar acciones de correo electrónico a cada rama

Realice los pasos siguientes en el lado **sí** de la rama **condición** .

   Nota: el flujo usa estos pasos para enviar un correo electrónico cuando se aprueba la solicitud:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar plantilla de correo electrónico aprobada previamente](includes/media/parallel-modern-approvals/yes-email-config.png)

Para enviar un correo electrónico cuando se rechaza una solicitud, use la rama **si NO hay** un lado de la **condición** y repita los pasos anteriores para agregar una plantilla para el correo electrónico de rechazo.

Repita los pasos anteriores en las ramas **iniciar una aprobación 2** (solicitud de aprobación para ventas) e **iniciar una aprobación 3** (la solicitud de aprobación a recursos humanos).

## <a name="update-the-vacation-request-with-the-decision"></a>Actualización de la solicitud de vacaciones con la decisión

Realice los pasos siguientes para actualizar SharePoint cuando se tomen decisiones.

   Nota: Asegúrese de realizar estos pasos en **si** es así y en **si no** en los lados de la rama.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Actualizar configuración de elemento](./media/parallel-modern-approvals/configure-update-item.png)

Repita los pasos anteriores en las ramas **iniciar una aprobación 2** e **iniciar una aprobación 3** .

## <a name="complete-the-flow"></a>Completar el flujo

1. Seleccionar **nuevo paso** > **Agregar una acción**

    ![Actualizar configuración de elemento](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Siga los pasos proporcionados anteriormente para enviar un correo electrónico que resume los resultados de cada aprobación. Envíe este correo electrónico al empleado que solicitó las vacaciones. La tarjeta puede ser similar a la de este ejemplo:

   ![Actualizar configuración de elemento](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Más información sobre las aprobaciones modernas

[Introducción a las aprobaciones modernas](modern-approvals.md)

