---
title: Aprenda a conectarse a sus datos mediante conexiones y puertas de enlace de datos locales | Microsoft Docs
description: Agregue o administre conexiones a SharePoint, SQL Server, OneDrive para la empresa, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive, etc.
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
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1de8602cc573e800d721b6b70222df49cf1577e3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544766"
---
# <a name="manage-connections-in-microsoft-flow"></a>Administrar conexiones en Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Si crea una conexión en Microsoft Flow, puede acceder fácilmente a los datos durante la compilación de un flujo. Microsoft Flow incluye conexiones usadas comúnmente, entre las que se incluyen SharePoint, SQL Server, Office 365, OneDrive para la empresa, Salesforce, Excel, Dropbox, Twitter y mucho más. Las conexiones se comparten con PowerApps, por lo que cuando se crea una conexión en un producto, la conexión se muestra en la otra.

Por ejemplo, puede usar una conexión para realizar estas tareas:

* Actualizar una lista de SharePoint.
* Obtenga datos de un archivo de Excel en su cuenta de OneDrive para la empresa o Dropbox.
* Envíe un correo electrónico en Office 365.
* Envíe un tweet.

Puede crear una conexión en varios escenarios, como los siguientes:

* Creación [de un flujo a partir de una plantilla](get-started-logic-template.md)
* Crear un [flujo desde](get-started-logic-flow.md) cero o actualizar un flujo existente
* Creación directa de una conexión en el [sitio web de Microsoft Flow][1]

En este tema se muestra cómo administrar las conexiones en el [sitio web de Microsoft Flow][1].

## <a name="add-a-connection"></a>Agregar una conexión
1. En el [sitio web de Microsoft Flow][1], inicie sesión con su cuenta profesional o de la organización.
2. Cerca de la esquina superior derecha, seleccione el icono de engranaje y, a continuación, seleccione **conexiones**.
   
    ![Seleccionar conexiones](./media/add-manage-connections/connections-menu.png)
3. Seleccione **crear conexión**.
4. En la lista de **conexiones disponibles**, seleccione la conexión que desea configurar, como SharePoint.
5. Seleccione el botón **crear conexión** y, a continuación, escriba sus credenciales para configurar la conexión.

Una vez configurada la conexión, aparece en **mis conexiones**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Conexión a los datos a través de una puerta de enlace de datos local
En el que se redactó este documento, SQL Server y SharePoint Server admiten la puerta de enlace de datos local. Para crear una conexión que use una puerta de enlace:

1. Siga los pasos descritos anteriormente en este tema para agregar una conexión.
2. En la lista de **conexiones disponibles**, seleccione **SQL Server**y, a continuación, active la casilla **conectar a través de la puerta de enlace de datos local** .
   
    ![Seleccionar puerta de enlace](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP, pero no tráfico HTTPS.
   > 
   > 
3. Proporcione las credenciales de la conexión y, a continuación, seleccione la puerta de enlace que desea usar.
   
    Para obtener más información, consulte [Administración de puertas de enlace](gateway-manage.md) y descripción de las puertas de [enlace](gateway-reference.md).
   
    Una vez configurada la conexión, aparece en **mis conexiones**.

## <a name="delete-a-connection"></a>Eliminar una conexión
1. Vaya a la página **mis conexiones** y seleccione el icono de la papelera para la conexión que desea eliminar.
   
    ![Eliminar conexión](./media/add-manage-connections/delete-connection.png)
2. Seleccione **Aceptar** para confirmar que desea eliminar la conexión.
   
    ![Confirmar eliminación](./media/add-manage-connections/delete-confirmation.png)

Cuando se elimina una conexión, se quita de PowerApps y Microsoft Flow.

## <a name="update-a-connection"></a>Actualizar una conexión
Puede actualizar una conexión que no funciona porque los detalles de la cuenta o la contraseña han cambiado.

1. En la página **mis conexiones** , seleccione el vínculo **comprobar contraseña** para la conexión que desea actualizar.
   
    ![Comprobar contraseña](./media/add-manage-connections/verify-password.png)
2. Cuando se le solicite, actualice la conexión con nuevas credenciales.

Cuando se actualiza una conexión, se actualiza para PowerApps y Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Solucionar problemas de una conexión
En función de las directivas de la organización, es posible que tenga que usar la misma cuenta para iniciar sesión en Microsoft Flow y crear una conexión a SharePoint, Office 365 o OneDrive para la empresa.

Por ejemplo, puede iniciar sesión en Microsoft Flow con *yourname@outlook.com* pero debe bloquearse al intentar conectarse a SharePoint con *yourname@contoso.com* . En su lugar, puede iniciar sesión en Microsoft Flow con *yourname@contoso.com* y podrá conectarse a SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
