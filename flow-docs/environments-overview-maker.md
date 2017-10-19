---
title: Cambio de entornos al crear de una instancia de Microsoft Flow | Microsoft Docs
description: "Cómo se usan distintos entornos al crear una instancia de Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>Elección de un entorno
Con Microsoft Flow, es posible trabajar en entornos diferentes y cambiar fácilmente de unos a otros. En este artículo se tratan los siguientes temas relativos al entorno:

* Trasfondo de lo que proporcionan los entornos
* Cambio de entornos
* Creación de un flojo en el entorno adecuado

## <a name="environments-overview"></a>Introducción a los entornos
Los entornos proporcionan un límite de aislamiento para los flujos, las conexiones, las puertas de enlace y otros recursos. Cuando se crea un flujo, se puede elegir en qué entorno se va a hospedar y los recursos que va a usar. Se pueden usar entornos distintos para diferentes escenarios.

Estos son algunos ejemplos:

* Crea un flujo que usa una conexión a Microsoft Common Data Service. En este escenario, tanto el flujo como Common Data Service residen en el mismo entorno. Esto garantiza que todos los datos se aíslan en dicho entorno (límite de aislamiento).
* Crea un flujo para el departamento de recursos humanos. Desea asegurarse de que los usuarios del departamento de recursos humanos son los únicos que tienen acceso al flujo. Por ejemplo, no desea que el grupo de ventas use el flujo. En este escenario, puede usar un entorno independiente, en el que los usuarios de recursos humanos son los únicos que tienen permisos, para hospedar el flujo, y todos los recursos que usa el flujo, incluidas las puertas de enlace o conexiones.
* Hay usuarios en Europa que utilizan un flujo para mostrar datos de SharePoint. En este escenario, cree un entorno en Europa que hospede el flujo y la conexión de SharePoint. Este entorno de Europa ofrece a los usuarios europeos el mejor rendimiento, ya que todos los recursos son locales en Europa (localidad de los datos).

Los administradores de Microsoft Flow crean los entornos. Dichos administradores también controlan quién tiene acceso a los distintos entornos.

En este tema se muestra cómo navegar entre los distintos entornos. Para más información acerca de cómo crearlos y administrarlos, consulte la sección sobre [administración de entornos](environments-overview-admin.md).

## <a name="switching-environments"></a>Cambio de entornos
Microsoft Flow facilita el cambio de entorno. Cuando realiza un cambio, puede ver todos los elementos de ese entorno específico. No verá los elementos de ningún otro entorno.

Aquí se muestra un ejemplo.

Cree un flujo denominado *NewEmployee* en el entorno de *recursos humanos*. En [flow.microsoft.com](http://flow.microsoft.com), abra el entorno de *ventas*. El flujo *NewEmployee* no aparece en la lista. Para ver el flujo *NewEmployee*, abra el entorno de *recursos humanos*. Recuerde que esto se puede aplicar a todos los elementos que cree en ese entorno, incluidas las conexiones, las puertas de enlace, PowerApps, etc.

1. Abra [flow.microsoft.com](http://flow.microsoft.com).
2. En la esquina superior derecha, verá el nombre y el entorno en el que se encuentra:  
   ![](./media/environments-overview-maker/default-environment.png)
   
    En la imagen, observe las notificaciones. Estas notificaciones son específicas para el flujo de este entorno predeterminado.
3. Seleccione su nombre. En la lista desplegable, se muestran todos los entornos disponibles. Se comprueba el entorno actual:  
   ![](./media/environments-overview-maker/all-environments.png)
4. Para cambiar a otro entorno, seleccione ese entorno en la lista:  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow cambia automáticamente al nuevo entorno:  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    En la imagen, observe que no hay ninguna notificación. El nuevo entorno de Europa no tiene ninguna notificación.

## <a name="create-flows-in-the-right-environment"></a>Creación de flujos en el entorno adecuado
Antes de crear un flujo, asegúrese siempre de seleccionar el entorno en que desea que esté. De lo contrario, tendrá eliminar y volver a crear el flujo en el entorno correcto.

Considere los siguientes factores al elegir en qué entorno se crean los flujos:

* Las puertas de enlace se crean en el entorno predeterminado. Las puertas de enlace no se pueden crear en otros entornos, por lo que si desea conectarse a datos locales tendrá que usar el entorno predeterminado.
* Los flujos solo pueden usar conexiones y otros recursos que se encuentren en el mismo entorno. No pueden usar recursos de otro entorno. Por ejemplo, cree un flujo que utilice un conector personalizado. Este conector personalizado debe estar en el mismo entorno que el flujo.
* La base de datos de Microsoft Common Data Service está siempre asociada a exactamente un entorno, lo que significa que si alguna vez desea trabajar con los datos de Common Data Service debe seleccionar el entorno en el que se encuentre la base de datos.
* Verá todos los entornos en los que se pueden editar recursos. Sin embargo, esto no significa que se puedan crear recursos nuevos en todos los entornos. Por consiguiente, es posible que en algunos entornos no pueda crear flujos nuevos. Es preciso que tenga que solicitar al administrador que le agregue como **Creador** de dicho entorno, o bien, elegir otro entorno para crear el flujo (siempre podrá crear flujos en el entorno predeterminado).

## <a name="what-you-did"></a>Lo que ha hecho
Con estos pasos, cambie entre entornos que tenga permiso para usar. Ahora, empiece a crear los flujos.

## <a name="next-steps"></a>Pasos siguientes
[Creación de un flujo desde una plantilla](get-started-logic-template.md)  
[Crear un flujo](get-started-logic-flow.md)  
[Introducción acerca de los entornos para administradores](environments-overview-admin.md)

