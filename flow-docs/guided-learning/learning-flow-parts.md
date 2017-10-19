---
title: "Bloques de creación de Microsoft Flow | Microsoft Docs"
description: "Vea las distintas partes de Microsoft Flow y cómo se relacionan. Cree nuevos flujos a partir de plantillas o desde cero."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 9U8jMRO-Jv0
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 6a7fe2d56c7bc3b2253b675ce26f3f29042a7a71
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="building-blocks-of-microsoft-flow"></a>Bloques de creación de Microsoft Flow
Ahora que conoce los aspectos básicos de Microsoft Flow, vamos a realizar **un recorrido por Microsoft Flow**. Veremos rápidamente cómo se crean flujos a partir de plantillas o desde cero.

## <a name="check-out-the-templates"></a>Selección de plantillas
En flow.microsoft.com, si hace clic en el vínculo **Plantillas** en la parte superior de la página, aparecerán varias plantillas que puede utilizar inmediatamente con los servicios web. Explore estas plantillas para **hacerse una idea rápidamente** de lo que Microsoft Flow puede hacer y de cómo puede ayudarle en el ámbito profesional.

![Plantillas de Flow](./media/learning-flow-parts/template-list.png)

Cada flujo de plantilla está diseñado para un propósito específico, como recibir notificaciones cuando ocurre algo, copiar un nuevo archivo de un servicio a otro o realizar un seguimiento de las aprobaciones de SharePoint. Estas plantillas están **listas para usarse**.  Solo tiene que **configurar las plantillas** para añadir flujos a su cuenta. Para ello, haga clic en **Usar esta plantilla**, inicie sesión en los servicios necesarios y, a continuación, complete los formularios que siguen.  Por ejemplo, este es un flujo creado a partir de una plantilla para enviar notificaciones de correo electrónico cuando se modifica una lista de SharePoint. 

![Plantilla de ejemplo de Flow](./media/learning-flow-parts/example-template.png)

Hay cientos de plantillas disponibles que puede encontrar en **Microsoft Flow para web** o **Microsoft Flow para móviles**.

![Flow para web y para móviles](./media/learning-flow-parts/flow-web-mobile.png)

## <a name="create-a-flow-from-scratch"></a>Creación de un flujo desde cero
Ha visto cómo crear un flujo mediante una plantilla, pero qué ocurre si desea automatizar una tarea para la que no encuentra una plantilla apropiada. En tal caso, puede **crear un flujo desde cero**.  Cuando se crea un flujo desde cero, parte de un lienzo en blanco al que añade **servicios, desencadenadores y acciones** para crear el flujo.  

![Flujo en blanco](./media/learning-flow-parts/flow-from-blank.png)

## <a name="building-blocks-of-a-flow"></a>Bloques de creación de un flujo
Tanto si compila un flujo desde una plantilla como si lo hace desde cero, los flujos contendrán **bloques de creación** que, en cierta forma, trabajan juntos de forma muy similar a un diagrama de flujo.

* Los **servicios** son los orígenes y destinos de los datos de un flujo.
* Los **desencadenadores** son los eventos que inician un flujo.
* Las **acciones** son las tareas que realiza el flujo.
* Las **condiciones** permiten la ramificación de la lógica if/then en un flujo.
* Los **bucles** se usan para realizar iteraciones sobre las acciones de más de una vez.

### <a name="services"></a>Servicios
Microsoft Flow puede conectar con muchos **aplicaciones y servicios** distintos.  Algunos servicios de ejemplo son **Twitter**, **Github**, **Wunderlist**, **Office 365** y **Google Docs**.  Estos no solo son los **orígenes** que proporcionan datos a Microsoft Flow, sino que también proporcionan **destinos** al trabajo realizado por Microsoft Flow.  Para ver toda la lista de servicios, haga clic en el vínculo **Servicios** de la parte superior de **flow.microsoft.com**.

![Conectores de Flow](./media/learning-flow-parts/flow-connectors.png)

### <a name="triggers"></a>Desencadenadores
Todos los flujos comienzan con un **desencadenador**.  Hay muchos tipos diferentes de desencadenadores.  Algunos de ellos son los eventos de los servicios web conectados, como **cuando un usuario concreto envía un tweet** o **un archivo se guarda en su cuenta de Dropbox**.  Otros desencadenadores están integrados, como la **ejecución de un flujo en una programación periódica** o la **ejecución de un flujo en respuesta a una solicitud web**.  Por último, hay desencadenadores manuales, como iniciar un flujo haciendo clic en un **botón de Microsoft Flow o Microsoft PowerApps**.  Los desencadenadores a menudo **pasan información sobre el evento que ha ocurrido** a las acciones de un flujo.

![Desencadenadores de Flow](./media/learning-flow-parts/flow-triggers.png)  

### <a name="actions"></a>Acciones
Un **acción** representa lo que desea que **ocurra** realmente después de que se desencadene el flujo.  Puede tratarse de una **notificación**, una **copia de datos o archivos** de un origen a un destino u otra acción, como la **publicación en redes sociales** o la **demora durante un período**.  Las acciones también se pueden utilizar para **recuperar datos de un servicio** para usarlo con otras acciones.

![Acciones de Flow](./media/learning-flow-parts/flow-actions.png) 

### <a name="conditions"></a>Condiciones
Las **condiciones** permiten agregar la toma de decisiones a un flujo.  Cuando se evalúa una condición, el flujo se ramifica en dos rutas, **sí** y **no**.   Por ejemplo, si desea copiar las fotografías de sus vacaciones que publicó en **Dropbox** a **OneDrive**, puede crear una condición después un desencadenador **Nuevo archivo de Dropbox** que compruebe si el nombre de archivo contiene la palabra *vacaciones*, y en caso afirmativo, copiar el archivo a **OneDrive**, pero que no haga nada en caso contrario.

![Condición de Flow](./media/learning-flow-parts/flow-condition.png) 

### <a name="loops"></a>Bucles
Los **bucles** permiten ejecutar una acción más de una vez, como por ejemplo si una acción debe producirse varias veces o una vez por elemento de una colección de elementos.

## <a name="next-lesson"></a>Siguiente lección
En este tema, hemos echado un vistazo a Microsoft Flow.  Hemos explorado las **plantillas** y explicado cómo **crear un flujo desde cero**.  Creamos flujos mediante la conexión con aplicaciones y servicios, **desencadenadores** para iniciar el flujo, **acciones** para hacer que algo que ocurra en el flujo, **condiciones** para tomar decisiones y **bucles** para iterar en un flujo.  **La manera más sencilla de familiarizarse con Microsoft Flow es empezar con una plantilla** y conectarla a las aplicaciones y servicios que ya utiliza. 

A continuación, revisaremos lo que hemos aprendido hasta ahora en este curso.

