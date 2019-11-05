---
title: Reemplazar cuadros de diálogo con flujos de proceso de negocio o aplicaciones de lienzo | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548812"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Reemplazar cuadros de diálogo con flujos de proceso de negocio o aplicaciones de lienzo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Los [cuadros de diálogo están en desuso](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)y deben reemplazarse por flujos de proceso de negocio o aplicaciones de lienzo. En este tema se describen las distintas funcionalidades de estas opciones, así como las situaciones en las que se puede usar un flujo de proceso empresarial o una aplicación de lienzo insertada en un formulario controlado por modelos para reemplazar un diálogo existente.

## <a name="feature-capability-comparison"></a>Comparación de funcionalidades de características

En esta tabla se muestra el conjunto de funcionalidades de diálogo y las funcionalidades equivalentes en los flujos de proceso de negocio y las aplicaciones de lienzo.


|Funcionalidad del cuadro de diálogo  | ¿Funcionalidad en flujos de procesos empresariales?  | ¿Funcionalidad de las aplicaciones de Canvas?  |
|---------|---------|---------|
|del     | ? <br/> (fase de proceso empresarial)    | ? <br/> (pantalla de la aplicación)        |
|Solo preguntar   |  No    |  ? <br/> Etiquetas        |
|Solicitud y respuesta     |  ? <br/> (solo atributos de entidad)    | ? <br/> (etiquetas y campos de entrada)    |
|Argumentos de entrada     |  Separados <br/> (pasos en la fase de proceso empresarial)    | ? <br/> (parámetros de cadena de consulta)     |
|Variable   |  No     |  ?       |
|Variables de consulta    |  No     |  ?     |
|Lógica de bifurcación condicional    |  ?     | ? <br/>  (vaya a cualquier pantalla de la aplicación)    |
|Utilizar <br/> (iniciar como un cuadro de diálogo secundario)   |  No     | ? <br/> (vaya a cualquier pantalla de la aplicación, inicie una aplicación diferente en una nueva ventana).     |
|Ejecutar flujos de trabajo al inicio o al final    |   ?      |  No <br/> (use un flujo en su lugar)  |
|Ejecutar flujos de trabajo en la entrada    | ?    | No <br/> (use un flujo en su lugar)   |
|Ejecutar flujos de trabajo en la transición de páginas   |  ?       | No <br/> (use un flujo en su lugar)    |
|Empezar a usar una dirección URL  |   No      |  ?     |
|Registro de sesión    |  ?       |  No     |
|Compatibilidad con SDK   |  ?     |  ?     |

### <a name="additional-capabilities-with-business-process-flows"></a>Capacidades adicionales con flujos de procesos empresariales
- Análisis de procesos (vistas, gráficos y tiempo invertido en una fase)
- Controles personalizados

### <a name="additional-capabilities-with-canvas-apps"></a>Funcionalidades adicionales con las aplicaciones de Canvas
- Análisis de aplicaciones (uso de la aplicación & rendimiento)
- Composición de páginas de varias entidades
- Ejecutar flujos
- Conectores de datos (estándar y personalizados)
- Iniciar como una aplicación independiente
- Diseño configurable

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Elección entre un flujo de proceso empresarial o una aplicación de lienzo
Al elegir el reemplazo del diálogo, es importante tener en cuenta la experiencia del usuario que desea ofrecer. Tenga en cuenta también que casi cualquier cuadro de diálogo se puede modelar con una aplicación de lienzo.

Los flujos de procesos empresariales son idóneos para reemplazar cuadros de diálogo que modelan procesos que proporcionan orientación a través de una secuencia de trabajo general que requiere colaboración entre grupos de usuarios y el contexto de la aplicación Dynamics 365. Por ejemplo, revisión y enrutamiento de la oferta. 

Como alternativa, las aplicaciones de Canvas se pueden usar para reemplazar cuadros de diálogo que modelan tareas prescriptivas, como un script de llamada para la prospección del cliente potencial o para simplificar la experiencia del usuario para otras tareas, como la actualización de una oportunidad. Tenga en cuenta que estos escenarios pueden incluso beneficiarse de tener una aplicación de lienzo independiente. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Sustitución de diálogo con el escenario de flujo de procesos empresariales
Imagine que tiene un cuadro de diálogo que, en una serie de páginas, solicita datos clave del usuario, genera una oferta, envía un correo electrónico a los revisores para aceptar o rechazar la oferta antes de enviarla por correo electrónico al cliente. Este tipo de proceso se modela de forma más eficaz mediante un flujo de procesos empresariales. 

Para reemplazar el cuadro de diálogo, empiece por identificar las fases clave en el proceso. Estos podrían incluir una fase de *preparación del contenido* para asegurarse de que todos los productos se muestran y se aplican descuentos, una fase de *generación de cotizaciones* para crear la oferta y revisarla para ver la precisión del formato, una fase de *revisión principal* para la que enviar la oferta revisión y aprobación, una fase de *revisión secundaria* para revisar la oferta en determinadas circunstancias y, por último, una fase de *entrega de presupuesto* para enviar la oferta al cliente.

A continuación, identifique los pasos clave que los usuarios deben seguir en el proceso. Por ejemplo, la fase de *preparación del contenido* podría contener un sencillo paso verdadero o falso para que el usuario Compruebe los productos que se van a entrecomillar, un paso de búsqueda obligatorio para seleccionar una lista de precios y un paso numérico para introducir un descuento antes de pasar a la siguiente fase. La fase de *generación de ofertas* podría tener un [paso de acción](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) para crear una oferta basada en toda la información capturada anteriormente en la fase de preparación de *contenido* y su registro de Dynamics 365 relacionado. Las fases de revisión *principal* y de *revisión secundaria* pueden tener varios pasos verdadero o falso para guiar la revisión de la oferta, junto con un paso necesario para capturar el estado de aprobación y asegurarse de que el proceso solo se puede pasar a la siguiente fase una vez que la aprobación es recibieron. Configure la [seguridad de nivel de campo](/customer-engagement/admin/field-level-security) en este paso para asegurarse de que solo los revisores autorizados pueden proporcionar la aprobación en la oferta.  Además, se puede Agregar un flujo de trabajo a las fases de revisión *principal* y de *revisión secundaria* , de modo que, al entrar, se envía una notificación por correo electrónico a todos los revisores. 

Por último, configure las fases y los pasos del flujo de procesos empresariales, junto con la lógica condicional para guiar el flujo del proceso. En este ejemplo, puede Agregar una [rama condicional](enhance-business-process-flows-branching.md) después de la fase de *revisión principal* , de modo que, si un paso indica la necesidad de un segundo nivel de revisión, la fase siguiente del proceso es la fase de *revisión secundaria* ; de lo contrario, es el  *Fase de entrega de cotización* .

Para que este flujo de procesos empresariales esté disponible para los usuarios, asegúrese de que los usuarios adecuados tienen privilegios en el flujo de procesos empresariales y, a continuación, actívelo.

Para obtener más información sobre cómo crear un flujo de procesos empresariales, vea [Tutorial: crear un flujo de procesos empresariales para estandarizar procesos](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Reemplazo de diálogo con el escenario de aplicación de Canvas

Supongamos que tiene un cuadro de diálogo que sigue un script de llamada que guía a los representantes de ventas a través de clientes potenciales de llamada en frío. Este proceso se puede capturar fácilmente con una aplicación de lienzo.

Comience con la conexión a los orígenes de datos que necesitará para leer y escribir datos. En este ejemplo, se utiliza una [conexión a Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) para la información de clientes potenciales, cuentas y contactos.

Comience por identificar el número de pantallas necesarias. En este ejemplo, puede decidir tener cinco pantallas. 
-   Pantalla 1. Para seleccionar un cliente potencial de una lista a la que llamar.
-   Pantalla 2. Para las introducciones, comprobar la disponibilidad de una conversación y programar una devolución de llamada en una fecha posterior. 
-   Pantalla 3. Para determinar BANT (presupuesto, autoridad, necesidad y escala de tiempo). 
-   Pantalla 4. Para capturar los pasos siguientes y programar llamadas de seguimiento. 
-   Pantalla 5. Gracias por su tiempo al final de la llamada.

A continuación, compile cada pantalla. En la primera pantalla, [cree una galería](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de clientes potenciales a los que se debe llamar. En el segundo, use etiquetas para dar título a la pantalla y proporcione el script de llamada, mientras usa controles como botones de radio para capturar si es un buen momento para que la persona hable. Si es así, use la lógica condicional para habilitar un botón para navegar a la pantalla siguiente y, si no es así, mostrar un script en la misma pantalla para intentar programar una devolución de llamada con el cliente. Del mismo modo, defina el script de llamada en las pantallas siguientes.

Por último, [defina la navegación entre pantallas](/powerapps/maker/canvas-apps/functions/function-navigate). En este ejemplo, además de desplazarse por las pantallas de forma secuencial, es posible que desee navegar por el usuario desde la segunda pantalla hasta la última pantalla (el final del script agradece el cliente potencial de su tiempo) si el cliente potencial no está interesado en tener una conversación.

Para que esta aplicación esté disponible para los usuarios, publique la aplicación. Tenga en cuenta cómo se podría transformar este escenario a través de la disponibilidad de una aplicación independiente que proporcione scripts de llamada y admita la entrada de datos rápida.

Imagine que quiere insertar esta experiencia en Dynamics 365 sales. Para ello, empiece con la creación de un iframe en un formulario de ventas de Dynamics 365. A continuación, vaya a la sección **aplicaciones** en el menú de PowerApps, seleccione la aplicación que acaba de publicar, copie el vínculo Web en la pestaña **detalles** y péguelo como dirección URL para el iframe. 

Teniendo esto un paso más, supongamos que desea que esta aplicación esté disponible en el formulario principal del cliente potencial y que esté en el contexto del cliente potencial para que la aplicación no requiera que el usuario seleccione un cliente potencial en la primera pantalla. Para pasar información relevante a la aplicación, solo tiene que modificar la dirección URL de iframe para anexar una cadena de consulta que contenga esta información, como identificadores de clientes potenciales o de cuenta, usando JavaScript que se ejecuta en un evento determinado, como en el formulario de carga. A continuación, actualice la aplicación para quitar la primera pantalla (para la selección de clientes potenciales) y, en su lugar, acceda a los valores pasados a la aplicación a través de la cadena de consulta mediante la [función param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Preguntas más frecuentes sobre reemplazo de diálogo

¿Se realiza un seguimiento de las dependencias de las aplicaciones de Canvas? 
- Se realiza un seguimiento de las dependencias de las aplicaciones de canvas de la misma manera que las dependencias de las aplicaciones Dynamics 365.

¿Puedo iniciar una aplicación de lienzo como un elemento emergente desde un botón de la barra de comandos?
- ?. Para ello, simplemente establezca la dirección URL de destino en la de la aplicación de lienzo, obtenida de la sección de **detalles** de la aplicación, tal como se describió anteriormente.

¿Se pueden llamar a los flujos de trabajo desde una aplicación de lienzo?
- Esto no se admite. En su lugar, se recomienda usar un flujo. Más información: [Introducción a los flujos de botones con datos proporcionados por el usuario](button-flow-with-user-input-tokens.md)

¿Puedo convertir automáticamente cuadros de diálogo en flujos de proceso de negocio o aplicaciones de lienzo?
- No hay ninguna manera automatizada de convertir cuadros de diálogo en flujos de procesos empresariales o aplicaciones de lienzo.


## <a name="see-also"></a>Vea también
[Tutorial: creación de un flujo de procesos empresariales para estandarizar procesos](create-business-process-flow.md) </br>
[¿Qué son las aplicaciones de lienzo en PowerApps?](/powerapps/maker/canvas-apps/getting-started)


