---
title: Reemplazar flujos de trabajo de Common Data Service clásico con Microsoft Flow | Microsoft Docs
description: Describe las funcionalidades de Microsoft Flow y los patrones recomendados para usar Flow en lugar de un flujo de trabajo clásico.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548523"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Reemplazar flujos de trabajo de Common Data Service clásico con flujos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este tema se comparan las capacidades de Microsoft Flow con el flujo de trabajo clásico.

Microsoft Flow tiene ventajas significativas en comparación con el modelo de flujo de trabajo clásico; debe considerar la posibilidad de usar Microsoft Flow para automatizar los procesos en lugar del flujo de trabajo clásico. 

Cree flujos en lugar de flujos de trabajo de Common Data Service clásico para crear nuevos procesos de automatización. Además, debe revisar los procesos de flujo de trabajo clásico existentes y considerar su sustitución con flujos.

## <a name="feature-capability-comparison"></a>Comparación de funcionalidades de características

En esta tabla se resume una comparación entre las funciones de Microsoft Flow y flujos de trabajo clásicos. 

*Vamos a agregar continuamente nuevas capacidades a Microsoft Flow para que sea más fácil e incluso mejor que las capacidades de flujo de trabajo clásico. Actualizaremos la información de esta tabla a medida que Microsoft Flow las funcionalidades. Vuelva a consultar con frecuencia. Para obtener información sobre las próximas funcionalidades de Flow que le ayudarán a reemplazar el flujo de trabajo clásico por Flow, consulte [novedades y planeación de Microsoft Flow](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) en las notas de la versión de abril de 2019.*

<table>
<tr>
<th colspan="2">Pueda</th>
<th>Microsoft Flow</th>
<th>Flujo de trabajo clásico</th>
</tr>
<tr>
<td rowspan="5">Archiva</td>
<td>Bifurcación condicional</td>
<td>?</td>
<td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Bucle
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Condiciones de espera en los campos
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Rama paralela
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Conectores integrados a sistemas externos (desencadenar y realizar acciones en servicios externos)
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Boletin
                    
                </td>
                <td>
                    
   Contenido dinámico
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acceso a la imagen previa de datos de eventos
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar flujos de trabajo secundarios
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar acciones Common Data Service (incluido personalizado)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar actividades de flujo de trabajo personalizadas
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Agrupar pasos para ejecutarlos en una transacción
                    
                </td>
                <td>
                    
   Sí (conjuntos de cambios)
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Flujos de trabajo de aprobación
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Remota
                    
                </td>
                <td>
                    
   Desencadenamiento de cambios de campo
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Desencadenar condicionalmente en valores de campo (por ejemplo, en una fecha determinada de un campo de fecha)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Desencadenador en varios eventos de entidad de Common Data Service
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecución a petición
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ámbitos de ejecución    <br/>
   (por ejemplo, organización, unidad de negocio, usuario)
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar según una programación
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar de forma sincrónica (en tiempo real)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Histo
                    
                </td>
                <td>
                    
   Auditoría
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ejecutar análisis
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Creación y portabilidad
                    
                </td>
                <td>
                    
   Compatibilidad con soluciones
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   ?
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Diseñador moderno
                    
                </td>
                <td>
                    
   ?
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
<td>Creación asistida por AI</td>
<td>?</td>
<td>No</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Escenario de ejemplo: reemplazar el flujo de trabajo con un flujo

Imagine un escenario de ventas en el que ha agrupado un presupuesto para un cliente y ahora necesita solicitar la aprobación del equipo de administración antes de enviar el presupuesto al cliente. Con los flujos de trabajo clásicos, esto no habría sido fácil de hacer y la mayoría de las soluciones para esto obligaba a los desarrolladores a escribir actividades de flujo de trabajo personalizadas para recuperar los elementos de línea de presupuesto.

Con los flujos, esto es más fácil de compilar, tal y como se muestra en el tutorial más adelante, en el que se tratan algunas de las funcionalidades de Microsoft Flow para admitir el escenario. Esto incluye:

-   Creación de un flujo que se ejecuta a petición

-   Obtener una lista de registros relacionados con una entidad Common Data Service

-   Crear bucles en una lista de registros

-   Envío de solicitudes de aprobación

Para permitir que el vendedor desencadene la solicitud de aprobación a petición:

1. Inicie sesión en [Microsoft Flow](https://flow.microsoft.com/) y cree un flujo en una solución. Más información: [crear un flujo en una solución](create-flow-solution.md). 

1. En la lista de desencadenadores, seleccione **Common Data Service (entorno actual): cuando se selecciona un registro** y seleccione **comillas** como entidad. Este desencadenador permite que un flujo se ejecute a petición en un registro o lista de registros.

1. Con el desencadenador configurado, agregue acciones para que se ejecuten en nuestro flujo. Esto proporcionará el aprobador con los detalles de Resumen necesarios para identificar los elementos y valores entre comillas. Comience agregando la acción **Common Data Service (entorno actual) – list Records** . Dado que queremos obtener artículos de línea individuales de una oferta, establezca la entidad en **líneas de Comillas**. Para asegurarse de que solo se muestren los elementos de la línea de presupuesto que pertenecen a la oferta para la que se desencadenó el flujo, se especificará un criterio de filtro de estilo OData. En el campo **filtrar consulta** , escriba *\_quoteid_value EQ* y seleccione *Quote* en la lista de valores dinámicos que aparecen.

    ![Definición del flujo](media/define-flow-1.png "Definición del flujo")

1. Como queremos resumir los elementos de línea de presupuesto para la aprobación, agregue la acción **inicializar variable** . Establezca el campo **nombre** en *Resumen de línea de presupuesto* y el **tipo** en cadena (desde la lista desplegable) y deje el campo de **valor** vacío.

1. Agregue la acción **anexar a variable de cadena** y, a continuación, seleccione la variable de *Resumen de línea de presupuesto* que hemos creado anteriormente. En el campo **valor** , seleccione *cantidad, nombre, precio por unidad, cantidad extendida y importe manual* en la lista de valores dinámicos. El diseñador de Microsoft Flow identifica que estos valores son de una lista de elementos de línea de presupuesto y agrega esta acción en un bucle **Apply to Each** para asegurarse de que se agrega información de cada elemento de línea a este Resumen.

    ![Definición del flujo](media/define-flow-2.png "Definición del flujo")

1. Para solicitar la aprobación del Resumen de la oferta que hemos creado, agregue la **aprobación: iniciar y esperar una acción de aprobación** . Seleccione un tipo de aprobación (por ejemplo, aprobar/rechazar – primero para responder), asigne un **título** a la solicitud de aprobación (por ejemplo, el nombre de la oferta para la que se solicita la aprobación, seleccionado en la lista de valores dinámicos), escriba la dirección de correo electrónico del persona que necesita revisar y aprobar el presupuesto en el campo **asignado a** . En el campo de detalles, agregue la variable de *Resumen de línea de Comillas* , junto con cualquier otra información que pueda ser relevante mediante el selector de valores dinámicos (por ejemplo, la cantidad total).

1. Para determinar lo que ocurre cuando se acepta o rechaza una aprobación, agregue la acción de **condición** . Seleccione *resultado* en la lista de valores dinámicos en el primer campo de la condición *, en* la lista desplegable del segundo campo y escriba *Accept* en el tercer campo de la condición. Por último, agregue acciones basadas en el resultado de la aprobación (por ejemplo, enviar un correo electrónico de notificación).

    ![Definición del flujo](media/define-flow-3.png "Definición del flujo")

Ahora se crea la estructura de aprobación, por lo que el aprobador tiene toda la información necesaria para tomar una decisión sobre los pasos siguientes. Este es el flujo de ejemplo a petición completo para solicitar la aprobación:

![Estructura de flujo de aprobación](media/approval-flow-structure.png "Estructura de flujo de aprobación")

Al ejecutar este flujo con la oferta, se resumen los elementos de la línea de presupuesto de esa oferta y se envía una solicitud de aprobación a la que el aprobador puede responder desde Microsoft Flow, o el correo electrónico accionable que reciben. A continuación se muestra un ejemplo de la pantalla:

![Flujo en acción](media/flow-in-action.png "Flujo en acción")

## <a name="recommended-patterns"></a>Patrones recomendados


-   **Flujos de trabajo con lógica condicional else-if compleja**  
    
    En lugar de usar condiciones, se recomienda usar la [acción switch](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) en su lugar.

-   **Flujos de trabajo que se ejecutan desde el complemento o el código**  
    
    Se recomienda volver a diseñar el flujo para que empiece con los desencadenadores.

    -   Use desencadenadores de Common Data Service para ejecutar flujos basados en eventos que contengan.

    -   Para ejecutar flujos basados en eventos de un servicio externo, aproveche más de 260 conectores integrados.

    -   En el caso de los escenarios en los que un conector que necesita no está disponible de forma rápida, cree fácilmente su propio conector personalizado [aprenda a crear conectores personalizados](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Por último, si hay escenarios en los que no puede desencadenar el flujo mediante Common Data Service conector, uno de los conectores integrados o crear un conector personalizado, aproveche el [desencadenador cuando se recibe una solicitud HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) para invocar el flujo.

-   **Flujos de trabajo que se ejecutan de forma recursiva**  
    
    Use el bucle [do-Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) o [Apply to Each](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) en los flujos en su lugar.

-   **Flujos de trabajo que necesitan una lista de registros**  
    
    Use la acción **Mostrar registros** . Al usar esta acción, defina los criterios de filtrado de registros mediante la sintaxis de OData para optimizar la acción minimizando el número de registros que desea recuperar.

-   **Flujos de trabajo que están en suspensión para ejecutarse según una programación**  
    
    Use el desencadenador de **periodicidad** para ejecutar la lógica de negocios a intervalos periódicos.

-   **Flujos de trabajo para los que se administraron ejecuciones para asegurarse de que las actividades se ejecutaron en una sola transacción**  
    
    [Use la [acción de conjunto de cambios](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) para asegurarse de que todas las acciones que contiene se realizan como una sola unidad atómica en la que todos se ejecutan correctamente o se producen errores como un grupo. Si se produce un error en cualquiera de las acciones de un conjunto de cambios, se revierten los cambios realizados por las operaciones completadas.

-   **Supervisión de ejecuciones de flujo de trabajo para errores**  
    
    En Microsoft Flow, use la **opción ejecutar después** de en una acción para configurarla para que se ejecute cuando se produzca un error en la acción anterior. Por ejemplo, enviar un Microsoft Flow notificación móvil cuando se produce un error en la acción **actualizar un registro** o se agota el tiempo de espera.

## <a name="faqs"></a>+


-   **Tengo una licencia de Dynamics 365. ¿Puedo usar Microsoft Flow?**

    Cada usuario de Dynamics 365 tiene derecho a utilizar Microsoft Flow. Revise la información de licencia: <https://flow.microsoft.com/pricing/>

-   **¿Con qué frecuencia se pueden desencadenar Mis flujos?**

    -   Los flujos de Dynamics 365 (o Common Data Service) se ejecutan casi en tiempo real después del desencadenador porque usan webhooks (no se requiere ningún sondeo)

    -   Al igual que con el acceso directo a la API, hay limitaciones/límites en el sistema, completamente documentado aquí: <https://docs.microsoft.com/flow/limits-and-config>

    -   En concreto, hay un límite de 100 000 acciones por cada 5 minutos, por flujo, y un solo bucle en un flujo no puede procesar más de 100 000 elementos a la vez.

    -   Máximo de 6 GB de rendimiento por 5 minutos

-   **¿Durante cuánto tiempo se puede ejecutar un solo flujo?**  
    
    Una sola ejecución de flujo agota el tiempo de espera después de 30 días.

-   **¿Cómo mueve Mis flujos entre entornos?**  
    
    Al igual que los flujos de trabajo clásicos, puede crear flujos en soluciones para admitir todo el ciclo de vida de la aplicación para los procesos.

-   **¿Se realiza un seguimiento de Microsoft Flow dependencias en Common Data Service?**  
    
    De forma similar a otros componentes de una solución, se realiza un seguimiento de todas las dependencias de los flujos de soluciones en Common Data Service.

-   **¿Qué ocurre con los flujos de trabajo sincrónicos?** 
 
    Debe volver a evaluar la necesidad de flujos de trabajo sincrónicos para identificar si el objetivo o partes del flujo de trabajo se pueden compilar con un flujo. En concreto, vemos de nuestros datos de telemetría que los flujos de trabajo sincrónicos son un gran colaborador de una experiencia de rendimiento deficiente del usuario final. En el caso de muchos usos, aunque sería preferible dividir estas acciones como asincrónicas para que el usuario pueda continuar con su actividad mientras Microsoft Flow continúa asegurando la finalización de la acción.

-   **Con Microsoft Flow, ¿mis datos permanecerán dentro de la región (es decir, la misma región que el entorno de Dynamics 365 o Common Data Service)?**  
    
    Sí, Microsoft Flow siempre usa la misma región que Common Data Service.

-   **¿Es necesario realizar cambios en el proxy o el Firewall?**  
    
    Consulte la [referencia de configuración de direcciones IP](limits-and-config.md#ip-address-configuration) para determinar si es necesario realizar algún cambio en el proxy o firewall.
