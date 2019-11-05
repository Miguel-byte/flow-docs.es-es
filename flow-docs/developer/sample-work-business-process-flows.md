---
title: 'Ejemplo: trabajar con flujos de procesos empresariales | MicrosoftDocs'
description: En el ejemplo se muestra cómo trabajar mediante programación con flujos de procesos empresariales, como recuperar las instancias de flujo de proceso empresarial para un registro de entidad, recuperar la ruta de acceso activa para una instancia de flujo de proceso de negocio y sus fases de proceso, y cambiar el fase activa.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547766"
---
# <a name="sample-work-with-business-process-flows"></a>Ejemplo: trabajar con flujos de procesos empresariales
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Este ejemplo muestra cómo trabajar mediante programación con flujos de procesos empresariales, como recuperar las instancias de flujo de proceso empresarial para un registro de entidad, recuperar la ruta de acceso activa para una instancia de flujo de proceso de negocio y sus fases de proceso, y cambiar el fase activa. Para obtener información acerca de estos conceptos, consulte [trabajar con flujos de procesos empresariales mediante código](business-process-flows-code.md) .  

 Este ejemplo está disponible para su descarga desde el [ejemplo: trabajar con flujos de procesos empresariales](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Antes de poder ejecutar el ejemplo:  

1. Tener acceso a un entorno de Common Data Service.  

2. Tener los privilegios adecuados en las entidades de clientes potenciales, oportunidades y flujo de trabajo y los registros de entidad de definición de flujo de procesos empresariales utilizados en este ejemplo.  

3. Tenga Visual Studio 2015 o posterior para ejecutar el ejemplo.  

4. Tenga conexión a Internet para descargar el proyecto de ejemplo y para restaurar los paquetes NuGet que se usan en el proyecto de ejemplo.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Qué hace este ejemplo  

1.  Crea un registro de cliente potencial de ejemplo. De esta forma, se crea automáticamente una instancia del flujo de proceso empresarial "lead to oportunidad sales Process" para el registro de clientes potenciales.  

2.  Convierte el registro de clientes potenciales en un registro de oportunidad.  


4.  Recupera las instancias de flujo de procesos empresariales asociadas al registro de "oportunidad" mediante el mensaje de `RetrieveProcessInstances`. El primer registro de la colección devuelta es la instancia de flujo del proceso empresarial activo para el registro de la oportunidad, que es "proceso de ventas de la oportunidad" en este caso.  

5.  Recupera la ruta de acceso activa y las fases de proceso de la instancia "lead to oportunidad sales Process" mediante el `RetrieveActivePath` mensaje.  

6.  Recupera la etapa activa actualmente para la instancia "lead to oportunidad sales Process" y pregunta al usuario si desea pasar a la siguiente fase. Al confirmar la migración, establece la fase siguiente en la ruta de acceso activa como la etapa activa para la instancia "lead to oportunidad sales Process".  

7.  Por último, pregunta al usuario si desea eliminar los registros creados durante la ejecución del ejemplo.  

     Este es el resultado del ejemplo:  

    ![Salida de ejemplo](media/work-with-bpf-sample-output.png "Salida de ejemplo")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Ejecutar el ejemplo  

1. [Descargue](https://go.microsoft.com/fwlink/p/?LinkId=846108) el proyecto de ejemplo de Visual Studio WorkWithBPF y extráigalo en una carpeta del equipo.  

2. Busque el archivo de `WorkWithBPF.sln` en la carpeta extraída y ábralo en Visual Studio.  

3. El proyecto de ejemplo usa paquetes NuGet que deben restaurarse antes de ejecutar el ejemplo. Asegúrese de que la restauración automática de paquetes NuGet está habilitada en Visual Studio. Más información: [habilitar y deshabilitar la restauración de paquetes NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    También puede seleccionar **proyecto** > **administrar paquetes NuGet**y seleccionar **restaurar** para restaurar manualmente los paquetes que se usan en el ejemplo.  

4. Presione F5 o seleccione **Depurar** > **iniciar depuración**.  

5. Si no ha ejecutado previamente uno de los ejemplos antes, deberá escribir información para ejecutar el código; de lo contrario, escriba el número de una de las instancias que ha configurado previamente.  


   |                                 Pregunte                                  |                                                                                             Denominación                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Escriba un nombre de servidor y un puerto de Dynamics 365 [crm.dynamics.com]       | Escriba el nombre del servidor de Dynamics 365. El valor predeterminado es Dynamics 365 (en línea) (crm.dynamics.com) en Norteamérica.<br /><br /> Ejemplo <br />crm5.dynamics.com |
   | ¿Esta organización está aprovisionada en Microsoft servicios en línea (y/n) [n] |                                                 Escriba **y** si se trata de una organización aprovisionada de Microsoft servicios en línea. De lo contrario, escriba **n**.                                                  |
   |                          Escriba dominio\nombredeusuario                          |                                                                                    Escriba el cuenta de Microsoft.                                                                                     |
   |                             Escribir contraseña                              |                      Escriba la contraseña. Los caracteres se mostrarán como "\*" en la ventana. La contraseña se guarda de forma segura en el administrador de credenciales de Microsoft para su reutilización posterior.                       |
   |                Especifique un número de organización (1-n) [1]                 |                      En la lista de organizaciones que se muestran a la que pertenece, escriba el número correspondiente. El valor predeterminado es 1, que indica la primera organización de la lista.                       |


6. El ejemplo llevará a cabo las operaciones descritas en [lo que hace este ejemplo](#what-this-sample-does) y puede pedirle opciones adicionales.  

7. Cuando se haya completado el ejemplo, presione Entrar para cerrar la ventana de la consola.  

