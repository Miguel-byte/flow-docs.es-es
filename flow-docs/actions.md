---
title: Usar acciones | MicrosoftDocs
description: Con las acciones, puede realizar operaciones, como crear, actualizar, eliminar, asignar o realizar una acción. Internamente, una acción crea un mensaje personalizado.
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544604"
---
# <a name="use-actions"></a>Usar acciones
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Las acciones abren una variedad de posibilidades para crear lógica de negocios. Con las acciones, puede realizar operaciones, como crear, actualizar, eliminar, asignar o realizar una acción. Internamente, una acción crea un mensaje personalizado. Los desarrolladores hacen referencia a estas acciones como "mensajes". Cada uno de estos mensajes se basa en las acciones realizadas en un registro de entidad. Si el objetivo de un proceso es crear un registro, actualizarlo y, a continuación, asignarlo, hay tres pasos independientes. Cada paso está definido por las capacidades de la entidad, no necesariamente por el proceso empresarial.  
  
Las acciones proporcionan la capacidad de definir un único Verbo (o mensaje) que coincida con una operación que se debe realizar para su negocio. Estos nuevos mensajes están controlados por un proceso o un comportamiento en lugar de lo que se puede hacer con una entidad. Estos mensajes pueden corresponder a verbos, como escalar, convertir, programar, enrutar o aprobar, todo lo que necesite. La adición de estos verbos ayuda a proporcionar un vocabulario más completo para que pueda definir de forma fluida sus procesos empresariales. Puede aplicar este vocabulario más completo desde clientes o integraciones en lugar de tener que escribir la acción en los clientes. Esto también facilita la tarea, ya que permite administrar y registrar el éxito o el fracaso de toda la acción como una sola unidad.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensajes configurables  
 Una vez que se define y activa una acción, un desarrollador puede usar ese mensaje como cualquiera de los otros mensajes proporcionados por la plataforma. Sin embargo, una diferencia importante es que ahora alguien que no es un desarrollador puede aplicar cambios a lo que se debe hacer cuando se usa el mensaje. Puede configurar la acción para modificar los pasos a medida que cambian sus procesos empresariales. No es necesario cambiar cualquier código personalizado que use ese mensaje, siempre que los argumentos de proceso no cambien.  
  
 Los procesos y complementos de flujo de trabajo continúan proporcionando funcionalidades similares para definir la automatización. Los procesos de flujo de trabajo todavía proporcionan la funcionalidad para que un desarrollador que no es de pueda aplicar cambios. Pero la diferencia radica en cómo se componen los procesos empresariales y cómo un desarrollador puede escribir su código. Una acción es un mensaje que funciona en el mismo nivel que cualquiera de los mensajes proporcionados por la plataforma. Los desarrolladores pueden registrar complementos para las acciones.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensajes globales 
 
 A diferencia de los flujos de trabajo de Common Data Service o los [Complementos](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), no es necesario asociar una acción a una entidad específica. Puede definir acciones "globales" que se pueden llamar por sí mismas.

## <a name="next-steps"></a>Pasos siguientes

[Crear una acción personalizada](create-actions.md)  
  

