---
title: "Solicitudes de aprobación con Microsoft Flow | Microsoft Docs"
description: "Aprenda a usar Microsoft Flow para administrar un flujo de trabajo de aprobación."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>Solicitudes de aprobación
Además de ayudarle a **recibir notificaciones**, **copiar archivos** y **recopilar datos**, Microsoft Flow también le ayudará a **simplificar los procesos de aprobación**.

## <a name="vacation-scenario"></a>Escenario de vacaciones
Suponga que usted es el **director** de un equipo y le pide a los empleados que creen **solicitudes de vacaciones** en una **lista de SharePoint**. Ahora desea generar un **proceso de aprobación** en torno a estos elementos de lista para que las nuevas solicitudes de vacaciones se **procesen rápidamente** y se le **notifique automáticamente** al solicitante.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint y Microsoft Flow
**SharePoint** trae Microsoft Flow **integrado**.  Desde la **lista de SharePoint**, haga clic en el menú desplegable **Flujo** y, a continuación, en **Crear flujo**.

![Crear flujo](./media/learning-approvals/new-flow.png)   

En el **menú de la derecha**, busque una **plantilla** parecida a esta.

![Plantilla de aprobación](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>Uso de la plantilla
El desencadenador de **SharePoint** en la plantilla aparece **rellenado previamente** con su información de lista.  Todo lo que tiene que hacer es agregar una **dirección de correo electrónico** para el **aprobador**.  Observe que este **no cambia el elemento de SharePoint original**.  Para ello, necesitamos agregar la acción **SharePoint: actualizar elementos**.

![Actualización de elementos](./media/learning-approvals/update-item.png)

¿Qué sucede con la opción **if no** de *Enviar emailScope*?  De forma predeterminada, no realiza ninguna acción.  Puede agregar una acción para enviar al autor de la solicitud un mensaje informándole de que su solicitud se ha rechazado. 

![If no](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>Siguiente lección
Ahora revisaremos lo que hemos aprendido en esta sección.

