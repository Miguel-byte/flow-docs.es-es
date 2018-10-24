---
title: Uso de las acciones | Microsoft Docs
description: Con las acciones, puede realizar operaciones como Crear, Actualizar, Eliminar, Asignar o Realizar acción. Internamente, una acción crea un mensaje personalizado
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aaa1d90368cbf513b46a939e7ea512a66b2c0a14
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688965"
---
# <a name="use-actions"></a>Uso de las acciones

Las acciones abren una gama de posibilidades para crear la lógica de negocios. Con las acciones, puede realizar operaciones como Crear, Actualizar, Eliminar, Asignar o Realizar acción. Internamente, una acción crea un mensaje personalizado. Los desarrolladores denominan "mensajes" a estas acciones. Cada uno de estos mensajes se basa en las acciones realizadas en un registro de entidad. Si el objetivo de un proceso es crear un registro, después actualizarlo y luego asignarlo, hay tres pasos independientes. Cada paso se define mediante las características de la entidad, no necesariamente por el proceso de negocio.  
  
Las acciones proporcionan la capacidad de definir un solo verbo (o mensaje) que coincide con una operación que se debe realizar para la empresa. Estos mensajes nuevos se controlan mediante un proceso o un comportamiento, en lugar de lo que se puede hacer con una entidad. Estos mensajes se pueden corresponder a verbos como Escalar, Convertir, Programar, Enrutar o Aprobar, lo que sea necesario. La adición de estos verbos ayuda a proporcionar un vocabulario más completo para definir con fluidez los procesos de negocio. Puede aplicar este vocabulario más completo desde clientes o integraciones en lugar de tener que escribir la acción dentro de los clientes. Esto también lo hace más fácil porque puede administrar y registrar como una sola unidad si la acción es correcta o no.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensajes configurables  
 Después de definir y activar una acción, un desarrollador puede usar ese mensaje como cualquiera de los que proporciona la plataforma. Pero una diferencia significativa es que ahora alguien que no sea un desarrollador puede aplicar cambios a lo que se debe realizar cuando se use ese mensaje. Puede configurar la acción para modificar los pasos cuando cambien los procesos de negocio. Mientas que los argumentos del proceso no varíen no será necesario cambiar el código personalizado que use ese mensaje.  
  
 Los procesos de flujo de trabajo y los complementos siguen proporcionando características similares para definir la automatización. Los procesos de flujo de trabajo todavía proporcionan la capacidad de que un usuario que no sea desarrollador aplique los cambios. Pero la diferencia radica en cómo se componen los procesos de negocio y cómo un desarrollador puede escribir su código. Una acción es un mensaje que opera en el mismo nivel que cualquiera de los mensajes proporcionados por la plataforma. Los desarrolladores pueden registrar complementos para las acciones.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensajes globales 
 
 A diferencia de los flujos de trabajo de CDS for Apps o los [complementos](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), no es necesario asociar una acción con una entidad específica. Puede definir acciones "globales" a las que se puede llamar de forma independiente.

## <a name="next-steps"></a>Pasos siguientes

[Creación de una acción personalizada](create-actions.md)  
  

