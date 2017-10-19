---
title: "Compilación de un conector personalizado para una API web | Microsoft Docs"
description: "Aprenda a crear una ASP.NET Web API con autenticación de Azure Active Directory en Microsoft Flow."
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: sunayv
ms.openlocfilehash: b151724aa27cb5cf5f85809a69bd6947258eaee1
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="build-a-custom-connector-for-a-web-api-in-microsoft-flow"></a>Compilación de un conector personalizado para una API Web en Microsoft Flow
Este tutorial muestra cómo empezar a compilar una ASP.NET Web API, alojarla en Azure Web Apps, habilitar la autenticación de Azure Active Directory y, finalmente, registrar la ASP.NET Web API en Microsoft Flow. Una vez registrada la API, puede conectarse a ella y llamarla desde el flujo. 

## <a name="prerequisites"></a>Requisitos previos
* Una [suscripción de Azure](https://azure.microsoft.com/free/).
* Una [cuenta de PowerApps](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 o superior.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>Creación de una ASP.NET Web API e implementación en Azure
1. En Visual Studio, haga clic en **Archivo** > **Nuevo proyecto** para crear una aplicación web de C# ASP.NET.
   
    ![Nueva aplicación web](./media/customapi-web-api-tutorial/newwebapp.png)
2. Seleccione la plantilla **Web API**.  Deje la opción **Host en la nube** activada.  Haga clic en **Cambiar autenticación**.
   
    ![Nueva plantilla de proyecto web](./media/customapi-web-api-tutorial/new-web-api.png)
3. Seleccione **Sin autenticación** y, a continuación, haga clic en **Aceptar**.
   
    ![Sin autenticación](./media/customapi-web-api-tutorial/noauth.png)
4. Haga clic en **Aceptar** en el cuadro de diálogo **Nuevo proyecto de ASP.NET**.  Aparece el cuadro de diálogo Configurar Microsoft Azure Web App.
   
    ![Configurar Microsoft Azure Web App](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Seleccione su cuenta de Azure, escriba un **nombre de aplicación web** (o deje el valor predeterminado) y seleccione la **suscripción** de Azure.  Seleccione o cree un **plan de App Service** (una colección de Web Apps dentro de la suscripción).  Seleccione o cree un **grupo de recursos** (una agrupación de recursos de Azure dentro de la suscripción).  Seleccione la región donde se debe implementar Web Apps.  Si es necesario para la Web API, seleccione o cree un **servidor de base de datos** de Azure.  Por último, haga clic en **Aceptar**.
5. Cree la Web API.
   
   > [!NOTE]
   > Si no dispone actualmente de código preparado para una API Web, pruebe el tutorial [Getting Started with ASP.NET Web API 2 (C#)](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api) (Introducción a ASP.NET Web API 2 [C#]).
   > 
   > 
6. Para conectar la Web API a PowerApps, necesitaremos un archivo [Swagger](http://swagger.io/) que describa las operaciones.  Podría escribir un archivo OpenAPI por sí mismo mediante el [editor en línea](http://editor.swagger.io/), pero para este tutorial, va a utilizar una herramienta de código abierto denominada [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md).  Instale el paquete Nuget de Swashbuckle en el proyecto de Visual Studio haciendo clic en **Herramientas** > **Administrador de paquetes NuGet** > **Consola del Administrador de paquetes**  y, una vez aquí, escriba el comando `Install-Package Swashbuckle`.
   
    ![Paquete de instalación de Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
   > [!TIP]
   > Al ejecutar la aplicación de API Web después de instalar Swashbuckle, se generará un archivo OpenAPI en la dirección URL `http://<your root URL>/swagger/docs/v1`.  Una interfaz de usuario generada también está disponible en `http://<your root URL>/swagger`.
   > 
   > 
7. Cuando la Web API esté lista, publíquela en Azure. Para publicar desde Visual Studio, haga clic con el botón derecho en el proyecto web en el Explorador de soluciones, haga clic en **Publicar...** y, a continuación, siga las indicaciones del cuadro de diálogo Publicar.
8. Recupere el archivo JSON de OpenAPI yendo a `https://<azure-webapp-url>/swagger/docs/v1`.  Guarde el contenido como un archivo JSON.  Dependiendo del explorador, deberá copiar y pegar el texto en un archivo de texto vacío.   
   
   > [!IMPORTANT]
   > Un documento de OpenAPI con identificadores de operación duplicados no es válido. Si está utilizando la plantilla de C# de ejemplo, el identificador de la operación `Values_Get` se repite dos veces. Puede corregir esto cambiando una instancia a `Value_Get` y volviendo a publicar.
   > 
   > También puede descargar un archivo [OpenAPI de ejemplo](http://pwrappssamples.blob.core.windows.net/samples/webAPI.json) de este tutorial. Asegúrese de quitar los comentarios (a partir de `//`) antes de usarlo.
   > 
   > 

## <a name="set-up-azure-active-directory-authentication"></a>Configuración de la autenticación de Azure Active Directory
Ahora creará dos aplicaciones de Azure Active Directory (AAD) en Azure.  Para obtener un ejemplo de cómo hacerlo, consulte el [tutorial de Azure Resource Manager](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory).

> [!IMPORTANT]
> Ambas aplicaciones deben estar en el mismo directorio.
> 
> 

### <a name="first-aad-application-securing-the-web-api"></a>Primera aplicación de AAD: protección de la Web API
La primera aplicación de AAD se usa para proteger la Web API. Asígnele el nombre **webAPI**.  Siga los pasos del tutorial vinculados anteriormente (solo en la sección titulada "Habilitación de la autenticación en Azure Active Directory") con los siguientes valores:

* URL de inicio de sesión: `https://login.windows.net`
* URL de respuesta: `https://<your-root-url>/.auth/login/aad/callback`
* No se necesita ninguna clave de cliente.
* No es necesario delegar los permisos.
* **Importante** Anote el identificador de la aplicación.  Lo necesitará más adelante.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>Segunda aplicación de AAD: protección del conector personalizado y acceso delegado
La segunda aplicación de AAD se utiliza para proteger el registro de conectores personalizados y adquirir acceso delegado a la API Web protegida por la primera aplicación. Asígnele el nombre de **webAPI-customAPI**.

* URL de inicio de sesión: `https://login.windows.net`
* URL de respuesta: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Agregue permisos para tener acceso delegado a Web API.
* Necesitará el identificador de esta aplicación más adelante así que, anótelo.
* Genere una clave de cliente y almacénela en algún lugar seguro. Necesitaremos esta clave más adelante.

## <a name="add-authentication-to-your-azure-web-app"></a>Incorporación de autenticación a Azure Web App
1. Inicie sesión en [Azure Portal](https://portal.azure.com) y, a continuación, busque la instancia de Web App que implementó en la primera sección.
2. Haga clic en **Configuración** y, a continuación, seleccione **Autenticación / autorización**.
3. Active **Autenticación de App Service** y, a continuación, seleccione **Azure Active Directory**.  En la siguiente hoja, seleccione **Express**.  
4. Haga clic en **Seleccionar aplicación de AD existente** y seleccione la aplicación de AAD **webAPI** que creó anteriormente.

Ahora podrá usar AAD para autenticar la aplicación web.

## <a name="add-the-custom-connector-to-microsoft-flow"></a>Incorporación del conector personalizado a Microsoft Flow
1. Modifique el archivo OpenAPI para agregar el objeto `securityDefintions` y la autenticación de AAD utilizada para la instancia de Web App. La sección del archivo OpenAPI con la propiedad **host** debería tener este aspecto:

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "accessCode",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "tokenUrl" : "https://login.windows.net/common/oauth2/token",
        "scopes": {}
    }
},

// The rest of the OpenAPI follows...
```

1. Vaya a [Microsoft Flow](https://flow.powerapps.com) y agregue un conector personalizado como se describe en [Registro y uso de conectores personalizados en Microsoft Flow](register-custom-api.md).
2. Una vez que se ha cargado el archivo OpenAPI, el asistente detecta automáticamente que está usando la autenticación de AAD para la Web API.
3. Configure la autenticación de AAD para el conector personalizado.  
   
   * **Id. de cliente**: *el identificador de cliente de webAPI-CustomAPI*
   * **Secreto**: *la clave de cliente de webAPI-CustomAPI*
   * **URL de inicio de sesión**: `https://login.windows.net`
   * **ResourceUri**: *identificador de cliente de webAPI*
4. Haga clic en **Crear** y cree una conexión al conector personalizado.

## <a name="next-steps"></a>Pasos siguientes
Revise el [tutorial sobre conectores personalizados de Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

