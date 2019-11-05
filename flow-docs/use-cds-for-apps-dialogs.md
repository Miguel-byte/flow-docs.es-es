---
title: Usar cuadros de diálogo Common Data Service para procesos guiados (desusado) | MicrosoftDocs
description: Los cuadros de diálogo son procesos sincrónicos o interactivos que recopilan y procesan información mediante scripts paso a paso para dirigir a los usuarios a través de un proceso.
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548738"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Usar cuadros de diálogo Common Data Service para procesos guiados (desusado)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los [cuadros de diálogo están desusados](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Debe reemplazar los cuadros de diálogo con las aplicaciones de lienzo o los flujos de procesos empresariales. Más información: [reemplazar cuadros de diálogo con flujos de proceso de negocio o aplicaciones de lienzo](replace-dialogs.md) 

Los cuadros de diálogo son procesos sincrónicos o interactivos en Common Data Service que recopilan y procesan información mediante scripts paso a paso para dirigir a los usuarios a través de un proceso. Por ejemplo, puede crear cuadros de diálogo para que actúen como guía para los representantes del servicio para la resolución de casos y la escalación de casos. Del mismo modo, puede crear diálogos para estandarizar procesos de ventas, como la calificación de oportunidades y la puntuación de clientes potenciales.

## <a name="differences-between-workflows-and-dialogs"></a>Diferencias entre flujos de trabajo y cuadros de diálogo

En la tabla siguiente se proporciona información sobre las diferencias entre Common Data Service flujos de trabajo y cuadros de diálogo.  


| Flujos     |    Cuadros      |
|---------------|--------------|
|                                                                                                  Puede ser iniciado por un usuario o se puede automatizar.                                                                                                   |                                                                                          Debe ser iniciado por un usuario.                                                                                          |
|                                  Son procesos asincrónicos o en tiempo real y no requieren que los datos proporcionados por el usuario se ejecuten hasta su finalización. Los procesos asincrónicos se ejecutan en segundo plano mientras los procesos en tiempo real se ejecutan inmediatamente.                                   | Son procesos en tiempo real que requieren que los datos proporcionados por el usuario se ejecuten hasta su finalización. Al ejecutar estos procesos, se le presenta una interfaz similar a un asistente para que pueda realizar las selecciones adecuadas para ejecutar los procesos. |
|                                                    La entidad que almacena los detalles sobre un flujo de trabajo asincrónico en ejecución es `AsyncOperation` mientras se utiliza un `Process` para un flujo de trabajo en tiempo real.                                                     |                                                       La entidad que almacena la información generada por un cuadro de diálogo en ejecución es la entidad `ProcessSession`.                                                       |
|                  Los desencadenadores se admiten para los flujos de trabajo. Para obtener una lista de los desencadenadores admitidos, consulte [tipos, desencadenadores y entidades compatibles para los procesos](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Los desencadenadores no se admiten en los cuadros de diálogo.                                                                                    |
  
### <a name="see-also"></a>Vea también
[Reemplazar cuadros de diálogo con flujos de proceso de negocio o aplicaciones de lienzo](replace-dialogs.md)
