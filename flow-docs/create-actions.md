---
title: Crear una acción personalizada | MicrosoftDocs
description: Use acciones personalizadas si desea automatizar una serie de comandos en el sistema. Las acciones expanden el vocabulario disponible para que los desarrolladores expresen los procesos empresariales.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b00e6e0b3ca2da357eb98d1b6de7756ff5cc75
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546822"
---
# <a name="create-a-custom-action"></a>Crear una acción personalizada
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Use acciones personalizadas si desea automatizar una serie de comandos en el sistema. Las acciones expanden el vocabulario disponible para que los desarrolladores expresen los procesos empresariales. Con los verbos principales como crear, actualizar, eliminar y asignar proporcionado por el sistema, una acción usa esos verbos básicos para crear verbos más expresivos como aprobar, escalar, enrutar o programar. Si cambia la definición de un proceso empresarial, alguien que no sea desarrollador puede editar la acción personalizada para que no sea necesario cambiar el código.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Crear una acción  
  
> [!IMPORTANT]
>  Si va a crear una acción que se va a incluir como parte de una solución que se va a distribuir, créela en el contexto de la solución. Vaya a **[configuración](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **soluciones** y busque la solución no administrada de la que esta acción formará parte. A continuación, en la barra de menús, seleccione **nuevo** > **proceso**. Esto garantiza que el prefijo de personalización asociado con el nombre de la acción será coherente con otros componentes de la solución. Después de crear la acción, no se puede cambiar el prefijo.  
  
 Al igual que los procesos de flujo de trabajo, las acciones tienen las siguientes propiedades en el cuadro de diálogo **Crear proceso** .  
  
 **Nombre del proceso**  
 Después de escribir un nombre para el proceso, se creará un nombre único para él quitando los espacios o caracteres especiales del nombre del proceso.  
  
 **Categoría**  
 Esta propiedad establece que se trata de un proceso de acción. No se puede cambiar después de guardar el proceso.  
  
 **ID**  
 Con los procesos de acciones, puede seleccionar una entidad para proporcionar contexto para el flujo de trabajo, al igual que otros tipos de procesos, pero también tiene la opción de elegir **ninguno (global)** . Úselo si la acción no requiere el contexto de una entidad específica. No se puede cambiar después de guardar el proceso.  
  
 **Automáticamente**  
 Utilice esta propiedad para elegir si se va a compilar una nueva acción desde cero o si se va a iniciar a partir de una plantilla existente.  
 
A diferencia de los procesos de flujo de trabajo, no es necesario establecer las siguientes opciones:  
  
- **Iniciar cuando**: las acciones se inician cuando el código llama al mensaje que se genera para ellos.  
  
- **Ámbito**: las acciones siempre se ejecutan en el contexto del usuario que realiza la llamada.  
  
- **Ejecutar en segundo plano**: las acciones son siempre flujos de trabajo en tiempo real.  
  
Las acciones también tienen algo que los procesos de flujo de trabajo no son los argumentos de entrada y salida.

> [!NOTE]
> Puede habilitar una acción personalizada desde un flujo de trabajo sin escribir código. Más información: [invocación de acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar una acción  
 Debe desactivar los procesos para poder editarlos.  
  
 Puede editar una acción creada como parte de una solución no administrada o incluida en una solución instalada en su organización. Si la solución es una solución administrada, es posible que no pueda modificarla. El publicador de soluciones tiene la opción de editar las propiedades administradas para que no se pueda editar la acción que se instala con una solución administrada.  
  
 Cuando se guarda una acción, se genera un nombre único basado en el nombre del proceso. Este nombre único tiene el prefijo de personalización agregado del editor de la solución. Este es el nombre del mensaje que utilizará un programador en su código.  
  
 Al editar una acción, tiene las siguientes opciones:  
  
 **Nombre del proceso**  
 Una vez creado el proceso y se genera el nombre único a partir del nombre del proceso, puede editar el nombre del proceso. Es posible que desee aplicar una Convención de nomenclatura para facilitar la búsqueda de procesos específicos.  
  
 **Nombre único**  
 Cuando se guarda una acción, se genera un nombre único basado en el nombre del proceso. Este nombre único tiene el prefijo de personalización del editor de soluciones agregado. Este es el nombre del mensaje que utilizará un programador en su código. No cambie este nombre único si el proceso se ha activado y se espera que el código llame a la acción con este nombre.  
  
> [!IMPORTANT]
>  Después de activar la acción y escribir el código para que use un nombre único, no se debe cambiar el nombre único sin cambiar también el código que hace referencia a él.  
  
 **Habilitar reversión**  
 Por lo general, los procesos que admiten transacciones "deshará" (o revertirán) toda la operación si se produce un error en alguna parte de ellos. Hay algunas excepciones a esto. Es posible que algunas acciones que los desarrolladores puedan hacer en el código Iniciado por la acción no admitan transacciones. Por ejemplo, si el código realiza acciones en otros sistemas que están fuera del ámbito de la transacción. No se pueden revertir mediante la acción que se ejecuta en una aplicación. Algunos mensajes de la plataforma no admiten transacciones. Pero todo lo que se puede hacer con la interfaz de usuario de la acción será compatible con las transacciones. Todas las acciones que forman parte de un flujo de trabajo en tiempo real se consideran en la transacción, pero con las acciones tiene la opción de no participar en esto.  
  
 Debe consultar con el desarrollador que utilizará este mensaje para determinar si debe estar en la transacción o no. Por lo general, una acción debe estar en transacción si las acciones realizadas por el proceso empresarial no tienen sentido a menos que se completen correctamente. El ejemplo clásico es la transferencia de fondos entre dos cuentas bancarias. Si retira fondos de una cuenta, debe depositarlos en el otro. Si se produce un error, ambos deben producir un error.  
  
> [!NOTE]
>  No se puede habilitar la reversión Si una acción personalizada se invoca directamente desde dentro de un flujo de trabajo. Puede habilitar la reversión Si un mensaje de servicios Web de PowerApps desencadena una acción.  
  
 **Activar como**  
 Al igual que todos los procesos, puede activar el proceso como una plantilla y usarlo como punto de partida avanzado para los procesos que siguen un patrón similar.  
  
 **Definir argumentos de proceso**  
 En esta área, especificará los datos que la acción espera iniciar y los datos que se pasarán de la acción. Más información: [definir argumentos de proceso](#define-process-arguments)  
  
 **Agregar fases y pasos**  
 Al igual que otros procesos, se especifican las acciones que deben realizarse y cuándo realizarlas. Más información: [Agregar fases y pasos](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Definir argumentos de proceso  
 Cuando un desarrollador usa un mensaje, puede comenzar con algunos datos que pueden pasar al mensaje. Por ejemplo, para crear un nuevo registro de caso, puede haber un valor de título de caso que se pasa como argumento de entrada.  
  
 Una vez finalizado el mensaje, es posible que el desarrollador necesite pasar algunos datos que el mensaje ha modificado o generado en otra operación del código. Estos datos son el argumento de salida.  
  
 Los argumentos de entrada y salida deben tener un nombre, un tipo y cierta información sobre si el argumento siempre es obligatorio. También puede proporcionar una descripción.  
  
 El nombre del mensaje y la información sobre todos los argumentos del proceso representan la "firma" para el mensaje. Una vez que se activa una acción y se usa en el código, la firma no debe cambiar. Si esta firma cambia, se producirá un error en cualquier código que utilice el mensaje. La única excepción a esto puede ser cambiar uno de los parámetros para que no siempre sea necesario.  
  
 Puede cambiar el orden de los argumentos si los ordena o los mueve arriba o abajo porque los argumentos se identifican por nombre, no por el orden. Además, al cambiar la descripción no se interrumpirá el código mediante el mensaje.  
  
### <a name="action-process-argument-types"></a>Tipos de argumento de proceso de acción  
 En la tabla siguiente se describen los tipos de argumento de proceso de acción.  
  
|Automáticamente|Denominación|  
|----------|-----------------|  
|booleano|`true` o `false` valor.|  
|DateTime|Valor que almacena información de fecha y hora.|  
|Decimal|Valor numérico con precisión decimal. Se usa cuando la precisión es extremadamente importante.|  
|ID|Un registro para la entidad especificada. Al seleccionar entidad, la lista desplegable está habilitada y permite seleccionar el tipo de entidad.|  
|EntityCollection|Colección de registros de entidad.|  
|EntityReference|Objeto que contiene el nombre, el identificador y el tipo de un registro de entidad que lo identifica de forma única. Al seleccionar EntityReference, la lista desplegable está habilitada y permite seleccionar el tipo de entidad.|  
|flot|Valor numérico con precisión decimal. Se utiliza cuando los datos proceden de una medida que no es absolutamente precisa.|  
|entero|Un número entero.|  
|Económico|Valor que almacena los datos sobre una cantidad de dinero.|  
|Lista desplegable|Valor que representa una opción para un atributo OptionSet.|  
|String@|Valor de texto.|  
  
> [!NOTE]
> No se pueden establecer valores de argumento de **EntityCollection** en la interfaz de usuario para condiciones o acciones. Se proporcionan para que las usen los desarrolladores en el código personalizado. Más información: [creación de sus propias acciones](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Agregar fases y pasos  
 Las acciones son un tipo de proceso muy similar a los flujos de trabajo en tiempo real. Todos los pasos que se pueden usar en los flujos de trabajo en tiempo real se pueden usar en las acciones. Para obtener información acerca de los pasos que se pueden usar para los flujos de trabajo en tiempo real y las acciones, vea [pasos y fases de flujo de trabajo](configure-workflow-steps.md).  
  
 Además de los pasos que se pueden usar para los flujos de trabajo en tiempo real, las acciones también tienen el paso **asignar valor** .  En acciones, solo se pueden usar para establecer argumentos de salida. Puede usar el Asistente de formulario para establecer los argumentos de salida en valores específicos o, más probablemente, en los valores del registro en el que se ejecuta la acción, los registros relacionados con ese registro con una relación de varios a uno, los registros creados en un paso anterior o los valores que forman parte del propio proceso.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Invocar acciones personalizadas desde un flujo de trabajo](invoke-custom-actions-workflow-dialog.md)   

 
 
