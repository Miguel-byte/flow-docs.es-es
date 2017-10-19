---
title: "Introducción acerca de los entornos para administradores | Microsoft Docs"
description: "Uso, creación y administración de entornos de Microsoft Flow"
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
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Uso de entornos en Microsoft Flow
## <a name="benefits"></a>Ventajas
Los entornos son una característica nueva de Microsoft Flow que incluye las siguientes ventajas: 

* **Localidad de los datos**: los entornos se pueden crear en distintas regiones y enlazarse a esa ubicación geográfica. Cuando se crea un flujo en un entorno, dicho flujo se enruta a todos los centros de datos de su ubicación geográfica. Esto también mejora el rendimiento. 
  
    Si los usuarios están en Europa, cree y use el entorno en la región de Europa. Si los usuarios están en Estados Unidos, cree y use el entorno en Estados Unidos. 
  
    Si elimina el entorno, también se eliminarán todos los flujos dentro de ese entorno. Esto es aplicable a cualquier elemento que haya creado en ese entorno, incluidas las conexiones, las puertas de enlace, PowerApps y otros.
* **Prevención de pérdida de datos**: los administradores no desean flujos que obtengan datos de una ubicación interna (como *OneDrive para la Empresa*) y que, después, publiquen los datos públicamente (como en *Twitter*). Mediante la prevención de pérdida de datos se controla qué servicios se pueden usar en una directiva solo de datos empresariales. 
  
    Por ejemplo, puede agregar los servicios *SharePoint* y *OneDrive para la Empresa* servicios a una directiva solo de datos empresariales. Los flujos creados en este entorno pueden utilizar los servicios *SharePoint* y *OneDrive para la empresa*. Solo están disponibles los servicios que agregue. 
  
  > [!NOTE]
  > Prevención de pérdida de datos está disponible con los SKU de algunas licencias, entre las que se incluye la licencia de P2. 
  > 
  > 
* **Límite de aislamiento para todos los recursos**: todos los flujos, puertas de enlace, conexiones, conectores personalizados, etc. residen en un entorno específico. No existen en ningún otro entorno. 
* **Common Data Service**: desea crear un flujo que inserta los datos en algún lugar. Las opciones son:
  
  * Insertar datos en un archivo de Excel y almacenar este archivo en una cuenta de almacenamiento en la nube, como OneDrive.
  * Cree su propia instancia de SQL Database y almacene los datos en ella.
  * Utilice Common Data Service para almacenar los datos.
    
    Todos los entornos pueden tener uno o ningún almacenamiento de base de datos para los flujos en Common Data Service. El acceso a Common Data Service depende de la licencia que adquiera; no se incluye con la licencia gratuita.

## <a name="limitations"></a>Limitaciones
Aunque los entornos proporcionan muchas ventajas, también introducen nuevas limitaciones. El hecho de que los entornos sean un límite de aislamiento significa que nunca se pueden tener recursos que hagan referencia a recursos de *otros* entornos. Por ejemplo, es imposible crear un conector personalizado en un entorno y crear un flujo que use ese conector y una puerta de enlace en un entorno diferente.

Por consiguiente, es importante que los entornos se creen solo cuando sea estrictamente necesario. La creación de demasiados entornos dificultará considerablemente que los usuarios de la organización compartan recursos.

## <a name="use-the-default-environment"></a>Uso del entorno predeterminado
El entorno **predeterminado** está disponible para todos los usuarios y estos pueden compartirlo. En este entorno todos los usuarios pueden crear flujos.

> [!TIP]
> En los usuarios de versión preliminar, todos los flujos existentes residen en el entorno predeterminado. Un *usuario de versión preliminar* es alguien que usaba Microsoft Flow antes de su versión de disponibilidad general (GA). 
> 
> 

## <a name="use-the-administrator-center"></a>Uso del centro de administrador
Los administradores utilizar el centro de administrador para crear entornos, agregarles usuarios y otras tareas similares. El centro de administrador se puede abrir de cualquiera de estas dos formas:

#### <a name="option-1-select-settings"></a>Opción 1: seleccione Configuración
1. Inicie sesión en [flow.microsoft.com](https://flow.microsoft.com).
2. Seleccione el icono de engranaje para la configuración y elija **Centro de administración** en la lista:  
   ![Configuración y Portal de administrador](./media/environments-overview-admin/settings.png)
3. Se abre el centro de administrador.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>Opción 2: abra admin.flow.microsoft.com
Vaya a [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e inicie sesión con su cuenta de trabajo. Se abre el centro de administrador.

## <a name="create-an-environment"></a>Creación de un entorno
1. En el [Centro de administración de Microsoft Flow](https://admin.flow.microsoft.com), seleccione **Entornos**. Aparecerán todos los entornos existentes:  
   ![](./media/environments-overview-admin/environments-list.png)
2. Seleccione **Nuevo entorno**. Escriba la siguiente información:
   
   | Propiedad | Descripción |
   | --- | --- |
   | Nombre de entorno |Escriba el nombre del entorno, como `Human Resources` o `Europe flows`. |
   | Región |Elija la ubicación para hospedar el entorno. Para obtener un rendimiento óptimo, use la región más cercana a los usuarios. Por ejemplo, si los usuarios de Flow se encuentran en Londres, elija la región de Europa. Si los usuarios de Flow se encuentran en Nueva York, elija la región de Estados Unidos. |
3. Seleccione **Crear un entorno**. Aparecerá el nuevo entorno. 

A continuación, agregue usuarios al entorno.

## <a name="manage-your-existing-environments"></a>Administre los entornos existentes
1. En el [Centro de administración de Microsoft Flow](https://admin.flow.microsoft.com), seleccione **Entornos**:  
   ![](./media/environments-overview-admin/select-environments.png)  
2. Seleccione un entorno para abrir sus propiedades. 
3. **Detalles** muestra información adicional sobre el entorno, entre la que se incluye su creador, su ubicación geográfica y otras propiedades:  
   ![](./media/environments-overview-admin/open-environment.png)
4. Seleccione **Seguridad**. En **Environment roles** (Roles del entorno), hay dos opciones: **Administrador** y **Creador**:  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    Un **Creador** puede crear nuevos recursos en un entorno, como flujos, conexiones de datos y puertas de enlace. 
   
   > [!NOTE]
   > No es preciso que un usuario sea **Creador** para *editar* los recursos de un entorno, solo para crear recursos *nuevos netos*. El creador de cada recurso puede determinar quién puede modificar dicho recurso, así como otorgar permisos de edición a los usuarios que no son creadores del entorno.
   > 
   > 
   
    Un **Administrador** puede crear directivas de prevención de pérdida de datos y también realizar tareas administrativas como crear entornos, agregar usuarios a un entorno y asignar los privilegios de administrador o creador.  
   
   1. Seleccione el rol **Creador de entornos** y, a continuación, seleccione **Usuarios**:  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. Escriba un nombre, una dirección de correo electrónico o un grupo de usuarios al que desee asignar el rol de creador. Cuando empiece a escribir, IntelliSense empezará a enumerar los usuarios o grupos que coincidan con el texto. 
   3. Seleccione **Guardar** para completar la incorporación de usuarios. 
5. En **Seguridad**, seleccione **Roles de usuario**:  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    Se muestran los roles existentes y se incluyen las opciones para editar o eliminar el rol. 
   
    Seleccione **Nuevo rol** para crear un rol nuevo. 
6. En **Seguridad**, seleccione **Conjuntos de permisos**:  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    Se enumeran todos los permisos existentes y se incluyen las opciones para editar o eliminar el rol. 
   
    Seleccione **Nuevo conjunto de permisos** para crear uno nuevo. 
7. En **Base de datos**, puede elegir si crea una base de datos para almacenar los datos. Esta base de datos forma parte de Common Data Services.

## <a name="commonly-asked-questions"></a>Preguntas más frecuentes
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>¿Puedo migrar Microsoft Flow en mi entorno de Estados Unidos a un entorno de Europa?
No, los flujos no se pueden mover entre entornos. Vuelva a crear el flujo en el entorno diferente.

##### <a name="which-license-includes-the-common-data-service"></a>¿Qué licencia incluye Common Data Service?
Solo el plan 2 de Microsoft PowerApps incluye los derechos necesarios para crear bases de datos con Common Data Service. Sin embargo, todos planes de pago (los planes 1 y 2 de Microsoft Flow y los planes 1 y 2 de Microsoft PowerApps) tienen los derechos necesarios para usar Common Data Service.

[Precios de Flow](https://flow.microsoft.com/pricing/) puede ayudarle a elegir el plan más adecuado para usted.  

[Preguntas sobre facturación](billing-questions.md) también resulta útil navegar por algunas de las preguntas comunes que hemos recibido. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>¿Se puede usar Common Data Service fuera de un entorno?
No. Common Data Service requiere un entorno. [Obtenga más información](common-data-model-intro.md) sobre él.

##### <a name="what-regions-include-microsoft-flow"></a>¿Qué regiones incluye Microsoft Flow?
Microsoft Flow admite la mayoría de las regiones que admite Office 365, consulte [la información general sobre las regiones](regions-overview.md) para más detalles.

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>¿Qué necesito para crear mi propio entorno personalizado?
Todos los usuarios con la licencia de plan 2 de Microsoft Flow pueden crear sus propios entornos, además del entorno predeterminado. Todos los usuarios de Microsoft Flow, incluidos Office 365 y gratuito, pueden utilizar los entornos creados que crean los administradores del plan 2, pero no pueden crear sus propios entornos. 

