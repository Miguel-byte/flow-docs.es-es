---
title: "Introducción a las directivas de prevención de pérdida de datos (DLP). | Microsoft Docs"
description: "Introducción a las directivas de prevención de pérdida de datos de Microsoft Flow."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/24/2016
ms.author: deonhe
ms.openlocfilehash: 29eaa9299e09c641538ab8f9dfbc9954bca66a3b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="data-loss-prevention-dlp-policies"></a>Directivas de prevención de pérdida de datos (DLP)
## <a name="what-is-a-data-loss-prevention-policy"></a>¿Qué es una directiva de prevención de pérdida de datos?
Los datos de una organización son fundamentales para su éxito. Es preciso que sus datos estén disponibles para la toma de decisiones, pero deben protegerse para que no se puedan compartir con audiencias que no deberían tener acceso a ellos. Para proteger estos datos, Microsoft Flow (Flow) proporciona la capacidad de crear y aplicar directivas que definen qué datos empresariales específicos de los conectores o servicios al consumidor se pueden compartir. Estas directivas que definen cómo se pueden compartir los datos se conocen como directivas de prevención de pérdida de datos (DLP).

## <a name="why-create-a-dlp-policy"></a>Razones para crear una directiva de DLP
Las directivas de DLP se crean para definir con claridad qué datos empresariales de servicios al consumidor pueden compartirse. Por ejemplo, es posible que una organización que usa Flow no desee que sus datos empresariales que se almacenan en SharePoint se publiquen automáticamente en su cronología de Twitter. Para evitarlo, se puede crear una directiva de DLP que bloquee el uso de los datos de SharePoint como origen de tweets.

## <a name="benefits-of-a-dlp-policy"></a>Ventajas de una directiva de DLP
* Asegúrese de que los datos se administran de forma uniforme en toda la organización  
* Impide que los datos empresariales importantes se publiquen accidentalmente en servicios como sitios de redes sociales.   

## <a name="managing-dlp-policies"></a>Administración de directivas de DLP
**Requisitos previos**  
Para crear, editar o eliminar directivas de DLP, se requieren los siguientes elementos: 

* Permisos de administrador de entornos o administrador de inquilinos. Para más información acerca de los permisos, consulte el [tema de los entornos](environments-overview-admin.md).  
* Una [licencia P2 de Flow](billing-questions.md).  

## <a name="create-a-dlp-policy"></a>Creación de una directiva de DLP
**Requisitos previos**  
Para crear una directiva de DLP, es preciso tener permisos al menos en un entorno.  

Siga estos pasos para crear una directiva de DLP que impida que los datos almacenados en la base de datos de SharePoint de su empresa se publiquen en Twitter:  

1. En la pestaña Directivas de datos, haga clic en el vínculo **Nueva directiva**:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-1.png)    
2. Escriba el nombre de la directiva de DLP, como por ejemplo *Secure Data Access for Contoso*, en la etiqueta **Data Policy Name** (Nombre de directiva de datos) de la parte superior de la página que se abre:   
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-2.png)  
3. Seleccione el [entorno](environments-overview-admin.md) en la pestaña **Se aplica a**.  
   **Nota:** Los administradores de entorno pueden crear directivas que se aplican a un único entorno. Los administradores de inquilinos pueden crear una directiva que se aplique a todos los entornos, uno o varios entornos seleccionados, o todos los entornos (excepto un conjunto seleccionado):  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-3.png)  
4. Seleccione la pestaña **Grupos de datos**:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-4.png)  
5. Seleccione el vínculo **+ Agregar** que se encuentra dentro del cuadro del grupo **Business data only** (Solo datos profesionales):    
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-5.png)  
6. Seleccione los servicios **SharePoint** y **Salesforce** en la página **Agregar servicios**:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-6.png)  
7. Haga clic en el botón **Agregar servicios** para agregar los servicios que pueden compartir datos empresariales:    
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-7.png)  
8. Seleccione **Guardar directiva**:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-8.png)  
9. Transcurridos unos segundos, la nueva directiva de DLP se mostrará en la lista de directivas de prevención de pérdida de datos:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-9.png)  
10. **Opcional** Envíe un correo electrónico o cualquier otra comunicación a su equipo para avisarle de que hay una nueva directiva de DLP en vigor.

Ya ha creado una directiva de DLP que permite que la aplicación comparta datos entre SharePoint y Saleforce, y bloquee el uso compartido de datos con otros servicios.  

**Nota**: Al agregar automáticamente un servicio al grupo de datos, se quita del otro grupo. Por ejemplo, si actualmente Twitter está en el grupo de datos **business data only** y no desea permitir que los datos empresariales se compartan con Twitter, basta con agregar el servicio Twitter al grupo **no business data allowed**. Esto quitará Twitter desde el grupo de datos "business data only".  

## <a name="data-sharing-violations"></a>Infracciones de uso compartido de datos
Suponiendo que ha creado la directiva DLP descrita anteriormente, si un usuario crea un flujo que comparte datos entre Salesforce (que está en el grupo de datos de **solo datos empresariales**) y Twitter (que está en el grupo de datos de **ningún dato empresarial permitido**), se le notificará al usuario que el flujo se ha **suspendido** debido a un conflicto con la directiva de prevención de pérdida de datos que creó.  
![crear flujo](./media/prevent-data-loss/10.png)  

Si los usuarios se ponen en contacto con usted acerca de flujos suspendidos, aquí hay algunas cosas a tener en cuenta:  

1. En este ejemplo, si hay una razón empresarial válida para compartir datos empresariales entre SharePoint y Twitter, puede editar la directiva DLP.  
2. Pida al usuario que modifique el flujo para cumplir con la directiva DLP.  
3. Pida al usuario que deje el flujo en estado suspendido hasta que se tome una decisión sobre el uso compartido de datos entre estas dos entidades.  

## <a name="find-a-dlp-policy"></a>Búsqueda de una directiva de DLP
### <a name="admins"></a>Administradores
Los administradores pueden utilizar la característica de búsqueda del Centro de administración para buscar directivas de DLP concretas.  

**NOTA** Los administradores deben publicar todas las directivas de DLP para que los usuarios de la organización las conozcan antes de crear flujos.

### <a name="makers"></a>Creadores
Si no tiene permisos de administrador y desea más información acerca de las directivas de DLP de su organización, póngase en contacto con el administrador de la misma. También puede obtener más información en el [tema de entornos de creadores](environments-overview-maker.md)  

**NOTA** Los administradores son los únicos que pueden editar o eliminar directivas de DLP.  

## <a name="edit-a-dlp-policy"></a>Edición de una directiva de DLP
1. Inicie el Centro de administración, para lo que debe especificar la siguientes URL: https://admin.flow.microsoft.com.  
2. Seleccione el vínculo **Data polices** (Directivas de datos) en el lado izquierdo.  
   ![Inicio de sesión](./media/prevent-data-loss/2.png)  
3. Busque en la lista de directivas de DLP existentes y seleccione el botón de edición que aparece junto a la directiva que desea editar:  
   ![Inicio de sesión](./media/prevent-data-loss/3.png)  
4. Realice los cambios que desee. Puede modificar el entorno o los servicios de los grupos de datos, por ejemplo.  
5. Seleccione **Guardar directiva** para guardar los cambios:  
   ![Inicio de sesión](./media/prevent-data-loss/create-policy-8.png)  

La directiva se ha actualizado. Para confirmar que se han realizado los cambios en la directiva, búsquela en la lista de directivas de prevención de pérdida de datos y revise sus propiedades.   

**Nota** Los administradores de entorno pueden ver las directivas de DLP que crean los administradores de inquilinos, pero no pueden editarlas.  

## <a name="delete-a-dlp-policy"></a>Eliminación de una directiva de DLP
1. Inicie el Centro de administración, para lo que debe especificar la siguientes URL: https://admin.flow.microsoft.com.  
2. Seleccione el vínculo **Data polices** (Directivas de datos) en el lado izquierdo.  
   ![Inicio de sesión](./media/prevent-data-loss/2.png)  
3. Busque en la lista de directivas de DLP existentes y seleccione el botón de eliminación que aparece junto a la directiva que desea eliminar:  
   ![Inicio de sesión](./media/prevent-data-loss/3-delete.png)  
4. Confirme que realmente desea eliminar la directiva, para lo que debe seleccionar el botón **Eliminar**:  
   ![Inicio de sesión](./media/prevent-data-loss/4.png)  

La directiva se ha eliminado. Para confirmar que la directiva no aparece en la lista de directivas de prevención de pérdida de datos, seleccione el vínculo **Data Policies** (Directivas de datos) de la izquierda y revise la lista de directivas.   

## <a name="dlp-policy-permissions"></a>Permisos de la directiva de DLP
Las directivas de DLP solo pueden crearlas y modificarlas los administradores de inquilinos y de entornos. Para más información acerca de los permisos, consulte el tema de los [entornos](environments-overview-admin.md).  

## <a name="next-steps"></a>Pasos siguientes
* [Más información acerca de los entornos](environments-overview-admin.md)  
* [Más información acerca de Microsoft Flow](getting-started.md)  
* [Más información acerca del Centro de administración](introduction-to-the-admin-center.md)  

