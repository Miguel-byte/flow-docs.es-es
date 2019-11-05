---
title: Agregar un flujo de trabajo a petición a un flujo de procesos empresariales
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546115"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Agregar un flujo de trabajo a petición a un flujo de procesos empresariales
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Puede desencadenar flujos de trabajo a petición desde dentro de un flujo de procesos empresariales. Por ejemplo, puede Agregar un flujo de trabajo a petición a un flujo de procesos empresariales para que se cree una actividad, como una tarea o un correo electrónico, cada vez que se complete una fase. 

Un flujo de trabajo se activa en función de dónde se coloca el flujo de trabajo en el diseñador de flujo de procesos empresariales.
- Procesos de la fase a petición. Cuando el flujo de trabajo se coloca en una fase de flujo de procesos empresariales, el flujo de trabajo se desencadena al entrar o salir de la fase. 
- Procesos globales a petición. Cuando el flujo de trabajo se coloca en el área de **flujos de trabajo globales** , el flujo de trabajo se desencadena en la activación del proceso o el archivo del proceso (cuando el estado cambia a un estado aplicado, completado, reactivado o abandonado). 

Tenga en cuenta los siguientes requisitos al agregar un flujo de trabajo a un flujo de procesos empresariales.
- En el caso de los flujos de trabajo agregados a una fase: solo se pueden usar flujos de trabajo activos y a petición creados para la misma entidad de la fase en la que se agrega el flujo de trabajo.  
- Para flujos de trabajo globales: solo puede usar flujos de trabajo activos y a petición creados para la entidad principal del flujo de procesos empresariales.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Agregar un flujo de trabajo a petición a una fase de flujo de procesos empresariales

Para agregar un flujo de trabajo a petición desde el diseñador de flujo de procesos empresariales, arrastre el componente de flujo de trabajo a una fase de proceso o a la sección flujos de trabajo globales. 

En el sitio de [PowerApps](https://web.powerapps.com) , seleccione **controlado por modelos** (parte inferior izquierda del panel de navegación). 

Abra el diseñador de flujo de procesos empresariales. Puede hacerlo de una de estas dos maneras.
- Si el flujo de procesos empresariales ya está agregado a una aplicación, vaya a **aplicaciones**, junto a la aplicación que quiera seleccionar **...** y, después, seleccione **Editar**. En el diseñador de aplicaciones, seleccione el flujo de procesos empresariales y, a continuación, seleccione ![abrir el diseñador de flujo de procesos empresariales](media/dynamics365-open-designer.PNG).  
- En caso contrario, abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), en el panel de navegación izquierdo, seleccione **procesos**y, a continuación, seleccione el flujo de procesos empresariales que desee. 

Decida si desea que uno de los siguientes eventos de flujo de proceso de negocio desencadene el flujo de trabajo a petición. 
- Procesos de la fase a petición. Desencadena el flujo de trabajo en la entrada o al salir de la fase. 
- Procesos globales a petición. Desencadena el flujo de trabajo en la activación del proceso o el archivado del proceso (cuando el estado cambia a un estado aplicado, completado, reactivado o abandonado). 

En el ejemplo siguiente, se agrega un flujo de trabajo a petición denominado **mi flujo de trabajo a petición** a la **fase 1** del flujo de procesos empresariales. 

1. Expanda la fase 1 para mostrar la sección **proceso desencadenado** . 
2. Seleccione la pestaña **componentes** y arrastre **flujo de trabajo** a la sección **proceso desencadenado** .
    ![agregar un flujo de trabajo a una fase](media/add-workflow-to-bpf-1.png) alternativamente, puede arrastrar el **flujo de trabajo** a la sección **flujos de trabajo globales** , que desencadena el flujo de trabajo en la activación del proceso o el archivado del proceso.
 ![agregar worfklow para procesar la activación o el archivo](media/add-workflow-to-bpf-global.png)
3. En el cuadro de búsqueda de la pestaña **propiedades** , escriba y busque el nombre del flujo de trabajo a petición que desee agregar a la fase flujo de proceso empresarial y, a continuación, seleccione **aplicar**.
    ![escriba el nombre y seleccione aplicar](media/add-workflow-to-bpf-2.png)
4. En la pestaña **propiedades** , en **desencadenador** , seleccione **entrada de fase** o salir de **fase**.  
    ![Seleccionar desencadenador de flujo de trabajo](media/workflow-trigger.png)
   
    Como alternativa, cuando se coloca el flujo de trabajo en la sección **flujos de trabajo globales** , se **aplican**las opciones del desencadenador, se **reactivan**los procesos, se **abandona el proceso**y se **completa el proceso**.

5. Seleccione **Actualizar** en la barra de herramientas del diseñador de flujo de proceso empresarial.
 
## <a name="next-steps"></a>Pasos siguientes
[Usar procesos de flujo de trabajo para automatizar procesos que no requieren la interacción del usuario](workflow-processes.md) <br/>
[Tutorial: creación de un flujo de procesos empresariales para estandarizar procesos](create-business-process-flow.md) <br/>
[Automatización del flujo de procesos empresariales en Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
