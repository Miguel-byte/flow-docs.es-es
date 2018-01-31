---
title: Uso de Azure Active Directory con un conector personalizado | Microsoft Docs
description: "Aprenda a crear un conector personalizado para Azure Resource Manager con autenticación de Azure Active Directory."
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2016
ms.author: deonhe
ms.openlocfilehash: 791a44a681ef70ead495bf46623657b2b75cfb65
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2018
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-microsoft-flow"></a>Uso de Azure Active Directory con un conector personalizado en Microsoft Flow
Azure Resource Manager (ARM) le permite administrar los componentes de una solución en Azure: componentes como bases de datos, máquinas virtuales y aplicaciones web. Este tutorial muestra cómo habilitar la autenticación en Azure Active Directory, registrar una de las API de ARM como un conector personalizado y, a continuación, conectarse a él en Microsoft Flow. Esto resulta útil si desea administrar los recursos de Azure como parte de un flujo. Para más información sobre ARM, consulte la [introducción a Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="prerequisites"></a>Requisitos previos
* Una [suscripción de Azure](https://azure.microsoft.com/free/).
* Una [cuenta de Microsoft Flow](https://flow.microsoft.com).
* El [archivo OpenAPI de ejemplo](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json) utilizado en este tutorial.

## <a name="enable-authentication-in-azure-active-directory"></a>Habilitación de la autenticación en Azure Active Directory
En primer lugar, debemos crear una aplicación de Azure Active Directory (AAD) que llevará a cabo la autenticación cuando llame al punto de conexión de API de ARM.

1. Inicie sesión en [Azure Portal](https://portal.azure.com).  Si tiene más de un inquilino de Azure Active Directory, asegúrese de que ha iniciado sesión en el directorio correcto examinando el nombre de usuario en la esquina superior derecha.
   
    ![Nombre de usuario](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. En el menú de la izquierda, haga clic en **Más servicios**.  En el cuadro de texto **Filtro**, escriba **Azure Active Directory** y, a continuación, haga clic en **Azure Active Directory**.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    Se abre la hoja de Azure Active Directory.   
3. En el menú de la hoja de Azure Active Directory, haga clic en **Registros de aplicaciones**.
   
    ![Registros de aplicaciones](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. En la lista de aplicaciones registradas, haga clic en **Agregar**.
   
    ![Botón Agregar](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Escriba un nombre para la aplicación, deje **Aplicación web o API** seleccionado y, a continuación, para **URL de inicio de sesión** escriba `https://login.windows.net`.  Haga clic en **Crear**.  
   
    ![Nuevo formulario de aplicación](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Haga clic en la nueva aplicación de la lista.
   
    ![Nueva aplicación de la lista](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    Se abre la hoja Aplicación registrada.  Tome nota del **Id. de aplicación**.  Lo necesitará más adelante.
7. También se debe haber abierto la hoja Configuración.  En caso contrario, haga clic en el botón **Configuración**.
   
    ![Botón Configuración](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. En la hoja Configuración, haga clic en **URL de respuesta**. En la lista de direcciones URL, agregue `https://msmanaged-na.consent.azure-apim.net/redirect` y haga clic en **Guardar**.
   
    ![Direcciones URL de respuesta](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. De nuevo en la hoja Configuración, haga clic en **Permisos necesarios**.  En la hoja Permisos necesarios, haga clic en **Agregar**.
   
    ![Permisos necesarios](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    Se abre la hoja Agregar acceso de API.
10. Haga clic en **Seleccionar una API**. En la hoja que se abre, haga clic en la opción para Azure Service Management API y haga clic en **Seleccionar**.
    
    ![Selección de una API](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. Haga clic en **Seleccionar permisos**.  En *Permisos delegados*, haga clic en **Access Azure Service Management as organization users** (Acceder a Azure Service Management como usuarios de la organización) y, a continuación, haga clic en **Seleccionar**.
    
    ![Permisos delegados](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. En la hoja Agregar acceso de API, haga clic en **Listo**.
13. En la hoja Configuración, haga clic en **Claves**.  En la hoja Claves, escriba una descripción para la clave, seleccione un período de caducidad y, a continuación, haga clic en **Guardar**.  Se mostrará la nueva clave.  Tome nota del valor de clave ya que también lo necesitaremos más adelante.  Ahora puede cerrar Azure Portal.
    
    ![Creación de una clave](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-microsoft-flow"></a>Incorporación de la conexión en Microsoft Flow
Ahora que la aplicación AAD está configurada, vamos a agregar el conector personalizado.

1. En la [aplicación web de Microsoft Flow](https://flow.microsoft.com/), haga clic en el botón **Configuración** situado en la esquina superior derecha de la página (se parece a un engranaje).  A continuación, haga clic en **conectores personalizados**.
   
    ![Búsqueda de conectores personalizados](./media/customapi-azure-resource-manager-tutorial/finding-custom-apis.png)  
2. Haga clic en **Crear conector personalizado**.  
   
    Se le pedirá que especifique las propiedades de la API.  
   
   | Propiedad | Descripción |
   | --- | --- |
   | Nombre |En la parte superior de la página, haga clic en **Sin título** y asigne un nombre al flujo. |
   | Archivo OpenAPI |Vaya al [archivo OpenAPI de ARM de ejemplo](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json). |
   | Carga del icono de la API |Haga clic en **Cargar icono** para seleccionar un archivo de imagen para el icono. Cualquier imagen PNG o JPG de menos de 1 MB valdrá. |
   | Descripción |Escriba una descripción del conector personalizado (opcional). |
   
    ![Creación de un conector personalizado](./media/customapi-azure-resource-manager-tutorial/create-custom-api.png)  
   
    Seleccione **Continuar**.
3. En la siguiente pantalla, dado que el archivo OpenAPI utiliza nuestra aplicación de AAD para la autenticación, necesitaremos proporcionar a Flow cierta información acerca de esta aplicación.  En **Id. de cliente**, escriba el **Id. de aplicación** de AAD que anotó anteriormente.  Como secreto del cliente, use la **clave**.  Y, por último, para **URL de recursos**, escriba `https://management.core.windows.net/`.
   
   > [!IMPORTANT]
   > Asegúrese de incluir la URL de recursos exactamente como se escribió anteriormente, incluida la barra diagonal final.
   > 
   > 
   
    ![Configuración de OAuth](./media/customapi-azure-resource-manager-tutorial/oauth-settings.png)
   
    Después de escribir la información de seguridad, haga clic en la marca de verificación (**&#x2713;**) junto al nombre del flujo en la parte superior de la página para crear el conector personalizado.
4. El conector personalizado se muestra ya en los **conectores personalizados**.
   
    ![API disponibles](./media/customapi-azure-resource-manager-tutorial/list-custom-apis.png)  
5. Ahora que está registrado el conector personalizado, debe crear una conexión a este para utilizarlo en las aplicaciones y los flujos.  Haga clic en **+** a la derecha del nombre del conector personalizado y, a continuación, complete la pantalla de inicio de sesión.

> [!NOTE]
> El archivo OpenAPI de ejemplo no define el conjunto completo de operaciones de ARM y actualmente solo contiene la operación [List all subscriptions](https://msdn.microsoft.com/library/azure/dn790531.aspx) (Enumerar todas las suscripciones).  Puede editar este OpenAPI o crear otro archivo OpenAPI mediante el [editor OpenAPI en línea](http://editor.swagger.io/).
> 
> Este proceso se puede utilizar para tener acceso a cualquier API de RESTful autenticada con AAD.
> 
> 

## <a name="next-steps"></a>Pasos siguientes
Para más información acerca de cómo crear un flujo, consulte [Inicio de la compilación con Microsoft Flow](get-started-logic-flow.md).

Para realizar preguntas o hacer comentarios acerca de los conectores personalizados, [únase a nuestra comunidad](https://aka.ms/flow-community).

