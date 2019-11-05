---
title: Cree un bucle de aprobación con el Common Data Service | Microsoft Docs
description: Cree una entidad, un flujo y una aplicación que funcionen conjuntamente para que los revisores puedan aprobar o rechazar los archivos agregados a Dropbox.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4f58e5b3095769349e71e9ba8b203ea678981391
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546846"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Cree un bucle de aprobación mediante Microsoft Flow y Microsoft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
El Common Data Service puede proporcionarle una manera de compilar flujos que tengan información almacenada en una base de datos independiente de un flujo. El mejor ejemplo de esto es con aprobaciones. Si almacena el estado de la aprobación en una entidad, el flujo puede funcionar encima.

En este ejemplo, creará un proceso de aprobación que se inicia cuando un usuario agrega un archivo a Dropbox. Cuando se agrega el archivo, aparece información sobre él en una aplicación, donde un revisor puede aprobar o rechazar el cambio. Cuando el revisor aprueba o rechaza el cambio, se envía el correo de notificación y se eliminan los archivos rechazados de Dropbox.

Al seguir los pasos de esta sección, compilará:

* una **entidad personalizada** que contendrá información sobre cada archivo agregado a Dropbox y si el estado del archivo es aprobado, rechazado o pendiente.
* **flujo** que agrega información a la entidad personalizada cuando se agrega un archivo a Dropbox, envía correo cuando se aprueba o rechaza el archivo y elimina archivos rechazados. En estos pasos se muestra cómo crear este tipo de flujo desde cero, pero puede crear un flujo similar a partir de una plantilla.
* una **aplicación** en la que un revisor puede aprobar o rechazar archivos agregados a Dropbox. Usará PowerApps para generar esta aplicación automáticamente en función de los campos de la entidad personalizada.

**Requisitos previos**

* Regístrese en [Microsoft Flow](sign-up-sign-in.md) y [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Cree conexiones a Dropbox y Office 365 Outlook, como se describe en [administrar las conexiones](https://powerapps.microsoft.com/tutorials/add-manage-connections/) .

## <a name="build-the-entity"></a>Compilar la entidad
1. Inicie sesión en [powerapps.com](https://web.powerapps.com).
2. Si la barra de navegación izquierda no aparece de forma predeterminada, haga clic o pulse en el icono con tres líneas horizontales en la esquina superior izquierda.
   
    ![Abrir la barra de navegación izquierda](./media/common-data-model-approve/hamburger-icon.png)
3. En la barra de navegación izquierda, pulse o haga clic en **administrar**y, después, pulse o haga clic en **entidades**.
   
    ![Administrar entidades](./media/common-data-model-approve/manage-entities.png)
4. Si se le solicita, pulse o haga clic en **crear mi base de datos**.
   
    ![Crear base de datos](./media/common-data-model-approve/create-database.png)
5. Cerca de la esquina superior derecha, pulse o haga clic en **nueva entidad**.
   
    ![Crear entidad](./media/common-data-model-approve/new-entity.png)
   
    Si la ventana del explorador no está maximizada, este botón podría aparecer en un lugar diferente.
6. En **nombre de entidad**, especifique un nombre que no contenga espacios y que no tenga ninguna otra entidad en la base de datos.
   
    Para seguir este ejemplo exactamente, especifique **ReviewDropboxFiles**.
   
    ![Especificar nombre de entidad](./media/common-data-model-approve/entity-name.png)
7. En **nombre para mostrar**, especifique un nombre descriptivo.
   
    ![Especificar nombre para mostrar](./media/common-data-model-approve/display-name.png)
8. Pulse o haga clic en **siguiente**.
   
    ![Botón siguiente](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Agregar campos a la entidad
1. Cerca de la esquina superior derecha, pulse o haga clic en **Agregar campo**.
   
    ![Agregar campo](./media/common-data-model-approve/add-field.png)
2. En la fila en blanco que aparece en la parte inferior de la lista de campos, establezca las propiedades de un campo de **aprobador** . (Al establecer estas propiedades, puede cambiar a la columna siguiente presionando TAB).
   
   * En la columna **nombre para mostrar** , escriba **aprobador**.
   * En la columna **nombre** , escriba **ApproverEmail**.
   * En la columna **tipo** , haga clic o pulse en la opción **correo electrónico** .
   * En la columna **requerido** , active la casilla.
     
     ![Campo de aprobador](./media/common-data-model-approve/approver-field.png)
3. En la fila siguiente, establezca las propiedades de un campo de **Estado** :
   
   * En la columna **nombre para mostrar** , escriba **status**.
   * En la columna **nombre** , escriba **status**.
   * En la columna **tipo** , haga clic o pulse en la opción **texto** .
   * En la columna **propiedades** , deje el valor predeterminado.
   * En la columna **requerido** , active la casilla.
     
     ![Campo de estado](./media/common-data-model-approve/status-field.png)
4. En la fila siguiente, establezca las propiedades de un campo **FileID** :
   
   * En la columna **nombre para mostrar** , escriba identificador de **archivo**.
   * En la columna **nombre** , escriba **FileID**.
   * En la columna **tipo** , haga clic o pulse en la opción **texto** .
   * En la columna **propiedades** , deje el valor predeterminado.
   * En la columna **única** , active la casilla.
   * En la columna **requerido** , active la casilla.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Cerca del borde derecho, pulse o haga clic en los puntos suspensivos (...) del campo **FileID** y, después, pulse o haga clic en **establecer como campo de título**.
   
    ![Establecer campo de título](./media/common-data-model-approve/set-title-field.png)
6. Cerca de la esquina inferior izquierda, pulse o haga clic en **crear**.
   
    ![Crear una entidad](./media/common-data-model-approve/create-button.png)
7. opta Cuando vuelva a aparecer la lista de entidades, maximice la ventana del explorador si aún no está maximizada y, a continuación, haga clic o pulse en el encabezado de columna **tipo** . La lista se ordena con las entidades personalizadas, como la que acaba de crear, que aparecen en la parte superior.

## <a name="sign-in-and-create-a-flow"></a>Inicio de sesión y creación de un flujo
1. Abra el [portal de Microsoft Flow](https://flow.microsoft.com).
2. Maximice la ventana del explorador si aún no está maximizada y, después, haga clic o pulse **en iniciar sesión** cerca de la esquina superior derecha.
   
    ![Botón de inicio de sesión para Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. En el menú de la parte superior derecha, seleccione el entorno en el que creó la base de datos en powerapps.com.
   
    **Nota**: Si no selecciona el mismo entorno, no verá la entidad.
4. Cerca de la esquina superior izquierda, haga clic o pulse en **Mis flujos**.
   
    ![Botón Mis flujos](./media/common-data-model-approve/myflows-button.png)
5. Cerca de la esquina superior derecha, pulse o haga clic en **crear nuevo flujo**.
   
    ![Botón Crear nuevo flujo](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Iniciar al agregar un archivo
1. En el cuadro que contiene **Buscar más desencadenadores**, escriba o pegue **Dropbox**y, después, pulse o haga clic en **Dropbox-cuando se crea un archivo**.
   
    ![Crear desencadenador](./media/common-data-model-approve/create-trigger.png)
2. En **carpeta**, haga clic o pulse en el icono de carpeta y, a continuación, vaya a la carpeta donde se agregarán los archivos.
   
    ![Elegir carpeta](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Agregar datos a la entidad
1. Pulse o haga clic en **nuevo paso**y, a continuación, haga clic o pulse en **Agregar una acción**.
   
    ![Agregar una acción](./media/common-data-model-approve/add-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **Common Data Service**y, a continuación, haga clic o pulse en **Common Data Service-crear objeto**.
   
    ![Cree un objeto en la Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. En **la entidad**, escriba o pegue **revisar**y, a continuación, haga clic o pulse en **revisar archivos de Dropbox**.
   
    ![Elegir la entidad](./media/common-data-model-approve/choose-entity-flow.png)
4. En **título**, haga clic o pulse en el cuadro y, después, pulse o haga clic en **nombre de archivo** en la lista de tokens de parámetro para agregar ese token al campo.
   
    ![Agregar token de nombre de archivo](./media/common-data-model-approve/add-filename-token.png)
5. En **aprobador**, escriba o pegue la dirección de correo electrónico de la persona que va a revisar los archivos.
   
    **Nota**: para facilitar la prueba del flujo, especifique su propia dirección. Puede cambiarlo más adelante, cuando el flujo esté listo para su uso real.
   
    ![Agregar aprobador](./media/common-data-model-approve/add-approver.png)
6. En **Estado**, escriba o pegue **pendiente**.
   
    ![Agregar estado predeterminado](./media/common-data-model-approve/add-default-status.png)
7. En **identificador de archivo**, haga clic o pulse en el cuadro y, a continuación, haga clic o pulse en **identificador de archivo** en la lista de tokens de parámetro para agregar ese token al campo.
   
    ![Agregar token de identificador de archivo](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Comprobar si se ha revisado el archivo
1. En la acción **crear objeto** , haga clic o pulse en **nuevo paso**, haga clic o pulse en **más**y, a continuación, haga clic o pulse en **Agregar una tarea hasta**.
   
    ![Agregar do Until](./media/common-data-model-approve/add-do-until.png)
2. En la esquina superior izquierda de la acción **do Until** , haga clic o pulse en el cuadro que contiene **elegir un valor**.
   
    ![Elegir un valor](./media/common-data-model-approve/choose-value.png)
   
    **Nota**: Si la ventana del explorador no está maximizada, haga clic o pulse en el cuadro superior que contiene **elegir un valor**.
3. En **salidas de crear objeto**, pulse o haga clic en **Estado** para agregar ese token de parámetro al campo.
   
    ![Agregar token de estado](./media/common-data-model-approve/add-status.png)
4. Abra la lista cerca del centro de la acción **do Until** y, después, pulse o haga clic en **no es igual a**.
   
    ![Especificar no es igual a](./media/common-data-model-approve/is-not-equal.png)
5. En la esquina superior derecha de la acción **do Until** , escriba o pegue **pendiente** en el cuadro que contiene **elegir un valor**.
   
    ![Especificar el estado que se va a ver](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Nota**: Si la ventana del explorador no está maximizada, haga clic o pulse en el cuadro inferior que contiene **elegir un valor**.
6. Cerca de la parte inferior de la acción **do Until** , haga clic o pulse en **Agregar una acción**.
   
    ![Agregue una acción dentro de do Until](./media/common-data-model-approve/add-action-in-dountil.png)
7. En el cuadro que contiene **Buscar más acciones**, escriba **Common**y, después, haga clic o pulse en **Common Data Service-Get Object**.
   
    ![Obtener un objeto](./media/common-data-model-approve/get-object.png)
8. En **el espacio de nombres**, haga clic o pulse en la base de datos.
9. En **la entidad**, escriba o pegue **revisar**y, a continuación, haga clic o pulse en **revisar archivos de Dropbox**.
   
    ![Elegir entidad](./media/common-data-model-approve/choose-entity-flow.png)
10. En **ID. de objeto**, haga clic o pulse en el cuadro y, a continuación, haga clic o pulse en el token del parámetro del **identificador de archivo** para agregarlo al campo.
    
     ![Agregar identificador de objeto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Comprobar si el elemento se ha aprobado
1. En la acción **do-Until** , haga clic o pulse en **nuevo paso**y, a continuación, haga clic o pulse en **Agregar una condición**.
   
    ![Agregar condición](./media/common-data-model-approve/add-condition.png)
2. En la esquina superior izquierda de la condición, haga clic o pulse en el cuadro que contiene **elegir un valor**.
   
    ![Esquina superior izquierda de la condición](./media/common-data-model-approve/condition-upper-left.png)
   
    **Nota**: Si la ventana del explorador no está maximizada, haga clic o pulse en el cuadro superior que contiene **elegir un valor**.
3. En **salidas de obtener objeto**, haga clic o pulse en el token de parámetro de **Estado** para agregarlo al campo.
   
    ![Agregar estado a condición](./media/common-data-model-approve/add-status-to-condition.png)
4. En la esquina superior derecha de la condición, escriba o pegue **aprobado** en el cuadro que contiene **elegir un valor**.
   
    ![Compruebe si el estado está establecido en aprobado.](./media/common-data-model-approve/status-equals-approved.png)
   
    **Nota**: Si la ventana del explorador no está maximizada, escriba o pegue **aprobado** en el cuadro inferior que contiene **elegir un valor**.

## <a name="send-notification-mail"></a>Enviar correo electrónico de notificación
1. En **si es así, no haga nada**, haga clic o pulse en **Agregar una acción**.
   
    ![En caso afirmativo, agregue una acción.](./media/common-data-model-approve/if-yes-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **Enviar correo**y, a continuación, haga clic o pulse en **Office 365 Outlook-enviar un correo electrónico**.
   
    ![En caso afirmativo, enviar correo](./media/common-data-model-approve/if-yes-send-mail.png)
3. En **a**, escriba o pegue la dirección de la persona a la que desea notificar cuando se acepte un elemento.
   
    **Nota**: para facilitar la prueba del flujo, especifique su propia dirección. Puede cambiarla cuando el flujo esté listo para su uso real.
   
    ![Destinatario de aprobación](./media/common-data-model-approve/approval-recipient.png)
4. En **asunto**, haga clic o pulse en el cuadro y, a continuación, haga clic o pulse en el token del parámetro de **nombre de archivo** para agregarlo al campo.
   
    ![Especificar el nombre de archivo como el asunto del correo electrónico](./media/common-data-model-approve/subject-is-file-name.png)
5. En **cuerpo**, escriba o pegue **el elemento se ha aprobado.**
   
    ![Cuerpo de correo electrónico de aprobación](./media/common-data-model-approve/approval-body.png)
6. En **si no, no hacer nada**, repita los pasos 1-5 de este procedimiento, excepto especifique el cuerpo del mensaje de correo electrónico como **el elemento se ha rechazado.**
   
    ![Cuerpo del correo de rechazo](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Eliminar archivos rechazados
1. En los campos del correo de rechazo, haga clic o pulse en **Agregar una acción**.
   
    ![Agregar acción de eliminación](./media/common-data-model-approve/add-delete-action.png)
2. En el cuadro que contiene **Buscar más acciones**, escriba o pegue **Dropbox**y, a continuación, haga clic o pulse en **Dropbox-eliminar archivo**.
   
    ![Eliminar archivo de Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. En **archivo**, haga clic o pulse en el cuadro y, a continuación, haga clic o pulse en el parámetro token del **identificador de archivo** para agregarlo al campo.
   
    ![Identificar el archivo que se va a eliminar](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Guardar el flujo
1. En la parte superior de la pantalla, escriba o pegue un nombre para el flujo que está creando y, a continuación, haga clic o pulse en **Crear flujo**.
   
    ![guardar flujo](./media/common-data-model-approve/save-flow.png)
2. Pulse o haga clic en **cerrar** y, después, pulse o haga clic en **listo**.
3. En Dropbox, agregue al menos dos archivos a la carpeta que especificó: uno para probar la aprobación y otro para probar el rechazo.

## <a name="build-the-app"></a>compilar la aplicación
1. Inicie sesión en [powerapps.com](https://web.powerapps.com)y, después, pulse o haga clic en **nueva aplicación** cerca de la parte inferior de la barra de navegación izquierda.
   
    ![Creación de una aplicación en un explorador](./media/common-data-model-approve/new-app-button.png)
2. En el cuadro de diálogo que aparece, pulse o haga clic en la opción para abrir PowerApps Studio para Windows o PowerApps Studio para la Web.
3. Si ha abierto PowerApps Studio para Windows, haga clic o pulse en **nuevo** en la barra de navegación izquierda.
4. En **crear una aplicación a partir de los datos**, haga clic o pulse en **diseño de teléfono** en el icono de **Common Data Service** .
   
    ![Crear aplicación](./media/common-data-model-approve/afd-cdm.png)
5. En el cuadro de **búsqueda** , escriba o pegue **revisar**.
   
    ![Buscar una entidad](./media/common-data-model-approve/search-entities.png)
6. En **elegir una entidad**, haga clic o pulse en **revisar archivos de Dropbox**.
   
    ![Elegir una entidad](./media/common-data-model-approve/choose-entity.png)
7. Cerca de la esquina inferior derecha, haga clic o pulse en **conectar**.
   
    ![Botón conectar](./media/common-data-model-approve/connect-button.png)
8. Si aparece la pantalla inicial del paseo introductorio, realice el paseo para familiarizarse con PowerApps (o haga clic o pulse en **omitir**).
   
    ![Paseo introductorio](./media/common-data-model-approve/quick-tour.png)
   
    Siempre puede realizar el paseo más tarde haciendo clic o pulsando en el icono de signo de interrogación situado cerca de la esquina superior izquierda y, a continuación, haciendo clic o pulsando en **realizar el paseo introductorio**.
9. opta Cerca de la parte inferior de la pantalla, arrastre el control deslizante para aumentar el zoom de modo que la aplicación sea más fácil de ver.
   
    ![Control de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalización de la aplicación
1. En la barra de navegación derecha, haga clic o pulse en el diseño que incluye un encabezado y una descripción.
   
    ![Botón conectar](./media/common-data-model-approve/choose-layout.png)
2. En el **BrowseScreen**, haga clic o pulse justo debajo de la barra de búsqueda para seleccionar el control de cuadro de texto más grande.
   
    ![Seleccionar encabezado](./media/common-data-model-approve/select-header.png)
3. En el panel derecho, abra la lista inferior haciendo clic o pulsando en la flecha hacia abajo.
   
    ![Abrir desplegable](./media/common-data-model-approve/open-dropdown.png)
4. En la lista inferior, haga clic o pulse en **título** para mostrar el nombre de archivo de los archivos agregados.
   
    ![Establecer datos de encabezado](./media/common-data-model-approve/set-heading.png)
5. En el panel derecho, abra la lista superior y, después, pulse o haga clic en **Estado** para mostrar el estado de cada archivo.
   
    ![Establecer datos de cuerpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Probar la solución global
1. En PowerApps, abra el modo de vista previa haciendo clic o pulsando en el botón de reproducción situado cerca de la esquina superior izquierda.
   
    ![Abrir el modo de vista previa](./media/common-data-model-approve/open-preview.png)
2. En el primer archivo de la lista, pulse o haga clic en la flecha para mostrar los detalles de dicho archivo.
   
    ![Abrir pantalla de detalles](./media/common-data-model-approve/open-details.png)
3. En la esquina superior derecha, haga clic o pulse en el icono de lápiz para cambiar los detalles del archivo.
   
    ![Abrir pantalla de edición](./media/common-data-model-approve/edit-record.png)
4. En el cuadro **Estado** , escriba o pegue **aprobado**.
   
    ![Aprobar un archivo](./media/common-data-model-approve/change-status.png)
5. En la esquina superior derecha, haga clic o pulse en el icono de marca de verificación para guardar los cambios y volver a la pantalla de detalles.
   
    ![Guardar cambios](./media/common-data-model-approve/save-record.png)
   
    En unos minutos, recibirá un correo electrónico en el que se indicará que el archivo se ha aprobado.
6. En la esquina superior derecha, haga clic o pulse en el botón atrás para volver a la pantalla de exploración.
   
    ![Volver a la pantalla de exploración](./media/common-data-model-approve/back-arrow.png)
7. Para el otro archivo de la lista, pulse o haga clic en la flecha para mostrar los detalles de dicho archivo.
   
    ![Abrir pantalla de detalles](./media/common-data-model-approve/open-details.png)
8. En la esquina superior derecha, haga clic o pulse en el icono de lápiz para cambiar los detalles del archivo.
   
    ![Abrir pantalla de edición](./media/common-data-model-approve/edit-record.png)
9. En el cuadro **Estado** , escriba o pegue **rechazado** (o cualquier cosa excepto **aprobado**, incluido **aprovado** o **approobado**).
   
    ![Rechazar archivo](./media/common-data-model-approve/reject-file.png)
10. En la esquina superior derecha, haga clic o pulse en el icono de marca de verificación para guardar los cambios y volver a la pantalla de detalles.
    
     ![Guardar cambios](./media/common-data-model-approve/save-record.png)
    
     En unos minutos, recibirá un correo electrónico en el que se indicará que el archivo se ha rechazado y el archivo se eliminará de Dropbox.

