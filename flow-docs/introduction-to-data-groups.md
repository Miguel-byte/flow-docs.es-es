---
title: Grupos de datos para Microsoft Flow | Microsoft Docs
description: Introducción a los grupos de datos para Microsoft PowerApps y Microsoft Flow.
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
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547444"
---
# <a name="learn-all-about-data-groups"></a>Obtener información acerca de los grupos de datos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>¿Qué es un grupo de datos?
Los grupos de datos son una manera sencilla de clasificar servicios dentro de una [Directiva de prevención de pérdida de datos (DLP)](prevent-data-loss.md). Los dos grupos de datos disponibles son el grupo **Business Data Only (solo datos empresariales** ) y el grupo **no Business Data allowed (sin datos profesionales** ). Las organizaciones pueden determinar los servicios que se colocan en un grupo de datos determinado. Una buena manera de clasificar servicios es colocarlos en grupos, en función del impacto en la organización. De forma predeterminada, todos los servicios se colocan en el grupo de datos **no Business Data allowed** . Los servicios de un grupo de datos se administran al crear o modificar las propiedades de una directiva DLP desde el centro de administración.

## <a name="how-data-is-shared-between-data-groups"></a>Cómo se comparten los datos entre grupos de datos
No se pueden compartir datos entre servicios ubicados en grupos diferentes. Por ejemplo, si coloca SharePoint y Salesforce en el grupo **Business Data Only (solo datos empresariales** ) y coloca Facebook y Twitter en el grupo **no Business Data allowed (sin datos profesionales** ), no puede crear un flujo que mueva datos entre SharePoint y Facebook. Aunque los datos no se pueden compartir entre los servicios de grupos diferentes, puede compartir datos entre los servicios de un grupo específico. Por lo tanto, volviendo al ejemplo anterior, como SharePoint y Salesforce se colocaban en el mismo grupo de datos, los flujos creados por los usuarios finales pueden compartir datos entre SharePoint y Salesforce. Del mismo modo, los usuarios finales pueden crear flujos y PowerApps que compartan datos entre Facebook y Twitter. El punto clave es que los servicios de un grupo específico pueden compartir datos, mientras que los servicios de grupos diferentes no pueden compartir datos.  

Además, se debe designar un grupo de datos como grupo *predeterminado* . Inicialmente, el grupo **no Business Data allowed** es el grupo *predeterminado* y todos los servicios están en el grupo de datos. Un administrador puede cambiar el grupo de datos predeterminado al grupo de datos **Business Data Only (solo datos profesionales** ). **Tenga en cuenta** que los nuevos servicios que se agreguen al flujo se colocarán en el grupo *predeterminado* designado. Por esta razón, se recomienda que mantenga el grupo **no se permiten datos empresariales** como grupo predeterminado y que agregue servicios manualmente en el grupo **solo datos empresariales** , una vez que su organización haya evaluado el impacto de permitir que los datos empresariales se compartan con el nuevo servicio.

## <a name="add-services-to-a-data-group"></a>Agregar servicios a un grupo de datos
En este tutorial, agregaremos SharePoint y Salesforce al grupo de datos **Business Data Only (solo datos empresariales** ) de una directiva de prevención de pérdida de datos (DLP). 

1. Seleccione el vínculo **+ Agregar** que se encuentra dentro del cuadro de grupo **Business Data Only (solo datos empresariales** ) de una directiva DLP:    
   ![agregar imagen](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Seleccione SharePoint y Salesforce y, a continuación, seleccione **Agregar servicios** para agregar ambos al grupo Business Data Only (solo datos profesionales):    
   ![agregar imagen de servicios](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Seleccione **Guardar Directiva** en el menú de la parte superior:  
   ![guardar](./media/introduction-to-data-groups/add-to-data-group-4.png) de Directiva 
4. Tenga en cuenta que tanto SharePoint como Salesforce están ahora en el grupo Business Data Only (solo datos empresariales):  
   ![Grupo de datos profesionales actualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

En este tutorial, ha agregado SharePoint y Salesforce al grupo de datos **Business Data Only (solo datos empresariales** ) de una directiva DLP. Si una persona que forma parte del entorno de la Directiva DLP crea una aplicación que comparte datos entre SharePoint o Salesforce y cualquier servicio del grupo de datos **no Business Data allowed** , la aplicación no podrá ejecutarse.

## <a name="remove-services-from-a-data-group"></a>Quitar servicios de un grupo de datos
Dado que todos los servicios deben estar en uno de los grupos de datos disponibles, para quitar un servicio de un grupo específico, basta con agregar el servicio a otro grupo y, después, guardar la Directiva.  

## <a name="change-the-default-data-group"></a>Cambiar el grupo de datos predeterminado
En este tutorial, se cambiará el grupo de datos predeterminado del grupo de datos **no Business Data allowed** al grupo de datos **Business Data Only (solo datos** profesionales).  

**Importante** : los nuevos servicios que se agreguen al flujo se colocarán en el grupo *predeterminado* designado. Por esta razón, se recomienda que mantenga el grupo **no se permiten datos empresariales** como grupo predeterminado y que agregue los servicios manualmente al grupo **Business Data Only (solo datos empresariales** ).

1. Seleccione la opción **...** que se encuentra en la esquina superior derecha del grupo de datos que desea designar como grupo de datos predeterminado:    
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Seleccione **establecer como grupo predeterminado**:  
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Seleccione **Guardar Directiva** en el menú de la parte superior:  
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que el grupo de datos ahora está designado como el grupo de datos predeterminado:  
   ![cambiar el grupo predeterminado](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Pasos siguientes
* [Más información sobre las directivas de prevención de pérdida de datos (DLP)](prevent-data-loss.md)
* [Más información acerca de los entornos](environments-overview-admin.md)   

