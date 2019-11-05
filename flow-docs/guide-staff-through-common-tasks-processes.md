---
title: Creación de una lógica de negocios personalizada a través de procesos con PowerApps | MicrosoftDocs
description: Obtenga información sobre los diferentes tipos de lógica de negocios que puede usar en la aplicación.
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545327"
---
# <a name="create-custom-business-logic-through-processes"></a>Crear lógica de negocios personalizada a través de procesos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Definir y aplicar procesos empresariales coherentes es una de las principales razones por las que los usuarios usan aplicaciones controladas por modelos. Los procesos coherentes ayudan a garantizar que las personas que usan el sistema puedan centrarse en su trabajo y no en recordar para realizar un conjunto de pasos manuales. Los procesos pueden ser simples o complejos y pueden cambiar con el tiempo.  
  
PowerApps incluye varios tipos de procesos, cada uno diseñado para un propósito diferente:  
  
-   Flujos de procesos empresariales  
  
-   Flujos de tareas móviles  
  
-   Flujos  
  
-   Operaciones  
  
 De forma similar a los procesos, también puede crear reglas de negocio y recomendaciones. Para obtener más información, consulte [crear reglas de negocios y recomendaciones para aplicar lógica en un formulario](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  El uso de procesos puede afectar a los requisitos de licencia para PowerApps y flujos. Para obtener más información, consulte [requisitos de licencia de entidad](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Cuándo usar los flujos de procesos empresariales  
 Utilice un flujo de procesos empresariales cuando desee que el personal se desplace por las mismas fases y siga los mismos pasos para interactuar con un cliente. Por ejemplo, utilice un flujo de procesos empresariales si desea que todos los usuarios controlen las solicitudes del servicio de atención al cliente de la misma manera, o para requerir que el personal adquiera la aprobación de una factura antes de enviar un pedido.  
  
 Su entorno incluye varios flujos de procesos empresariales listos para usar para las tareas comunes de ventas, servicios y marketing que puede usar con pocos o ningún cambio necesario. O bien, puede crear el suyo propio. Vea el tema siguiente para obtener más información sobre los flujos de procesos empresariales:  
  
-   [Crear un flujo de procesos empresariales](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Cuándo usar flujos de trabajo  
 Use flujos de trabajo para automatizar procesos empresariales en segundo plano. Los flujos de trabajo normalmente se inician mediante eventos del sistema, por lo que el usuario no tiene que tener en cuenta que se están ejecutando. Los flujos de trabajo que operan en segundo plano son "asincrónicos". Los flujos de trabajo también se pueden configurar para que los usuarios los inicien manualmente. Si desea automatizar tareas comunes, como enviar automáticamente un correo electrónico de confirmación a un cliente cuando se envía un pedido. Los flujos de trabajo que funcionan en tiempo real son "sincrónicos". Para obtener más información sobre los flujos de trabajo, consulte [procesos de flujo de trabajo](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Cuándo usar acciones  
 Use acciones si desea automatizar una serie de comandos en el sistema. Las acciones expanden el vocabulario disponible para que los desarrolladores expresen los procesos empresariales. Con los verbos principales como crear, actualizar, eliminar y asignar proporcionado por el sistema, una acción usa esos verbos básicos para crear verbos más expresivos como aprobar, escalar, enrutar o programar. Si cambia la definición de un proceso empresarial, alguien que no sea desarrollador puede editar la acción para que no sea necesario cambiar el código.  Para obtener más información sobre las acciones, vea [acciones](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Cuándo usar Microsoft Flow  
 Use Microsoft Flow cuando necesite crear flujos de trabajo automatizados que realicen acciones entre su entorno y la aplicación o el servicio favorito, como Dynamics 365, Twitter, Dropbox, Google Services, Office 365 y SharePoint. Puede desencadenar un flujo basado en una acción específica o invocar desde dentro de la aplicación. Más información: [uso de Microsoft Flow para automatizar procesos entre servicios](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>¿Dónde puedo crear procesos?  
 Hay dos rutas de acceso para navegar a los procesos:  
  
- Abra el [Explorador de soluciones](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) y vaya a **componentes > procesos.** Esta ruta de acceso proporciona un acceso cómodo cuando se realizan otros trabajos de personalización en las herramientas de personalización.  

- **[Configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > procesos.** Esta ruta de acceso permite usar vistas definidas para la entidad de proceso, incluidas las vistas personalizadas.  
  
 Los flujos de procesos empresariales individuales también se pueden editar mediante el botón **Editar proceso** de la barra de comandos para el formulario en el que está activo el flujo del proceso empresarial.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>¿Quién puede crear procesos?  
 Solo las personas con el rol de seguridad Administrador del sistema, Personalizador del sistema o Director Ejecutivo-negocio pueden crear procesos que se aplican a todo el entorno. Las personas con otros roles pueden crear procesos con nivel de acceso limitado. Por ejemplo, las personas con el nivel de acceso de usuario pueden crear flujos de trabajo para su propio uso con registros de su propiedad.  
  
 En la tabla siguiente se muestra el nivel de acceso de los procesos en función de los roles de seguridad predeterminados.  
  
|||  
|-|-|  
|**Rol de seguridad**|**Nivel de acceso**|  
|Director Ejecutivo|Organización|  
|Administrador del sistema|Organización|  
|Personalizador del sistema|Organización|  
|Vicepresidente de marketing|Primario: unidades de negocio secundarias|  
|Vicepresidente de ventas|Primario: unidades de negocio secundarias|  
|Service Manager|Unidad de negocio|  
|Administrador de marketing|Unidad de negocio|  
|Jefe de ventas|Unidad de negocio|  
|Administrador de programación|Unidad de negocio|  
|Representante de atención al cliente|Usuario|  
|Marketing profesional|Usuario|  
|Vendedor|Usuario|  
|Aquél|Usuario|  
  
> [!NOTE]
>  Aunque es posible que los usuarios puedan crear flujos de procesos de negocio, flujos de trabajo en tiempo real o procesos de acción, deberán tener los privilegios **Activar flujos de proceso de negocio** o **activar procesos en tiempo real** para activarlos.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Más información acerca de los flujos de trabajo y las acciones  
 Los procesos pueden comprobar las condiciones, aplicar la lógica de bifurcación y realizar acciones. Realizan estas acciones en una serie de pasos. En la tabla siguiente se describen los pasos disponibles en flujo de trabajo y procesos de acción. Para obtener más información, consulte los temas de cada tipo de proceso.  
  
|Pasar|Tipo de proceso|Denominación|  
|----------|------------------|-----------------|  
|**Media**|Flujo de trabajo, acción|Las fases facilitan la lectura de la lógica del flujo de trabajo y explican la lógica del flujo de trabajo. Sin embargo, las fases no afectan a la lógica o el comportamiento de los flujos de trabajo. Si un proceso tiene fases, todos los pasos del proceso deben estar incluidos en una fase.|  
|**Condición de comprobación**|Flujo de trabajo, acción|Instrucción lógica "If-\<" > then ".<br /><br /> Puede comprobar los valores del registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de N:1 o cualquier registro creado en los pasos anteriores. Según estos valores, puede definir pasos adicionales cuando se `true`la condición.|  
|**Rama condicional**|Flujo de trabajo, acción|Una instrucción "else-if-then" lógica, el editor usa el texto "de lo contrario, si \<condición >:"<br /><br /> Seleccione una condición de comprobación que haya definido previamente y puede Agregar una rama condicional para definir pasos adicionales cuando la condición de comprobación devuelva `false`.|  
|**Acción predeterminada**|Flujo de trabajo, acción|Instrucción "Else" lógica. el editor usa el texto "otherwise:"<br /><br /> Seleccione una condición de comprobación, una rama condicional, una condición de espera o una rama de espera paralela que haya definido previamente, y puede usar una acción predeterminada para definir los pasos para todos los casos que no coincidan con los criterios definidos en los elementos Condition o Branch.|  
|**Condición de espera**|Solo flujo de trabajo en segundo plano|Permite a un flujo de trabajo en segundo plano pausarse hasta que se cumplan los criterios definidos por la condición. El flujo de trabajo se inicia de nuevo automáticamente cuando se cumplen los criterios de la condición de espera.|  
|**Rama de espera paralela**|Solo flujo de trabajo en segundo plano|Define una condición de espera alternativa para un flujo de trabajo en segundo plano con un conjunto de pasos adicionales correspondiente que se realiza solo cuando se cumple el criterio inicial. Puede usar ramas de espera paralelas para crear límites de tiempo en la lógica del flujo de trabajo. Ayudan a evitar que el flujo de trabajo espere indefinidamente hasta que se cumplan los criterios definidos en una condición de espera.|  
|**Asignar valor**|Actuar|Establece un valor en un parámetro de variable o de salida en el proceso.|  
|**Crear registro**|Flujo de trabajo, acción|Crea un nuevo registro para una entidad y asigna valores a los atributos.|  
|**Actualizar registro**|Flujo de trabajo, acción|Puede actualizar el registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro en una relación de N:1 o cualquier registro creado en los pasos anteriores.|  
|**Asignar registro**|Flujo de trabajo, acción|Puede asignar el registro en el que se está ejecutando el flujo de trabajo, cualquiera de los registros vinculados a ese registro con una relación de N:1 o cualquier registro creado en los pasos anteriores.|  
|**Enviar correo electrónico**|Flujo de trabajo, acción|Envía un correo electrónico. Puede optar por crear un nuevo mensaje de correo electrónico o usar una plantilla de correo electrónico configurada para la entidad del registro en el que se está ejecutando el flujo de trabajo o cualquier entidad que tenga una relación de N:1 con la entidad, o bien la entidad para los registros creados en pasos anteriores.|  
|**Iniciar flujo de trabajo secundario**|Flujo de trabajo, acción|Inicia un proceso de flujo de trabajo que se ha configurado como un flujo de trabajo secundario.|  
|**Cambiar estado**|Flujo de trabajo, acción|Cambia el estado del registro en el que se está ejecutando el proceso, cualquiera de los registros vinculados a ese registro con una relación de N:1 o cualquier registro creado en los pasos anteriores.|  
|**Detener flujo de trabajo**|Flujo de trabajo, acción|Detiene el flujo de trabajo o la acción actual. Puede establecer un estado de **correcto** o **cancelado** y especificar un mensaje de estado.|  
|**Paso personalizado**|Flujo de trabajo, acción|Proporciona extensiones a los elementos lógicos disponibles de forma predeterminada. Los pasos pueden incluir condiciones, acciones, otros pasos o una combinación de estos elementos. Los desarrolladores pueden crear pasos de flujo de trabajo personalizados. De forma predeterminada, no hay pasos personalizados disponibles.|

  

