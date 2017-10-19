---
title: "Descripción de un conector personalizado con Postman | Microsoft Docs"
description: "Creación de una colección Postman para registrar los conectores personalizados"
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
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="describe-a-custom-connector-with-postman"></a>Descripción de un conector personalizado con Postman
[Postman](https://www.getpostman.com/) es una herramienta que sirve para realizar el desarrollo de API más rápido y sencillo. Este tutorial muestra cómo crear una colección Postman que, a continuación, puede utilizar para crear fácilmente [conectores personalizados](register-custom-api.md) en Microsoft Flow.

## <a name="prerequisites"></a>Requisitos previos
* Instale la [aplicación Postman](https://www.getpostman.com/apps).

## <a name="create-a-postman-collection"></a>Crear una colección Postman
Vamos a crear una colección Postman para [Text Analytics API](https://www.microsoft.com/cognitive-services/text-analytics-api) de Azure Cognitive Services. Esta API identifica el idioma, las opiniones y las frases clave del texto que se le pasa.

1. El primer paso para crear una colección Postman es crear una solicitud. Al crear la solicitud, puede establecer el verbo HTTP, la URL de solicitud, los parámetros de consulta o de ruta de acceso, los encabezados y el cuerpo. Para más información, consulte [Sending Requests](https://www.getpostman.com/docs/requests) (Envío de solicitudes) en la documentación de Postman. Como punto de conexión de Detect Language API, establezca los valores como se indica a continuación:
   
    ![Solicitud Postman](./media/postman-collection/request.png)
   
    Detalles de los parámetros y valores usados:
   
   | Parámetro | Valor |
   | --- | --- |
   | Verb |POST |
   | Request URL |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Params |numberOfLanguagesToDetect |
   | Authorization |“No Auth” |
   | Headers |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Body |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Haga clic en **Enviar** para realizar la solicitud y devolver la respuesta.
3. Haga clic en **Guardar** para guardar la solicitud en una colección Postman.
   
    ![Respuesta Postman](./media/postman-collection/request-response-save.png)
4. Proporcione un **nombre de solicitud** y una **descripción de solicitud** en el cuadro de diálogo **Guardar solicitud**. Usará estos valores en el conector personalizado.
   
    ![Postman, Guardar colección](./media/postman-collection/save-request-note.png)
   
    También puede guardar la respuesta en la solicitud. Los conectores personalizados solo admiten actualmente una única respuesta por solicitud. Si guarda varias respuestas por solicitud, se usa solo la primera de ellas.
   
    ![Postman, Guardar respuesta](./media/postman-collection/save-response.png)
5. Continúe con la creación de la colección Postman creando y guardando otras solicitudes y respuestas.
6. Una vez que se ha completado la creación de la colección Postman para todas las solicitudes y respuestas, exporte la colección.
   
    ![Postman, Exportar](./media/postman-collection/export.png)
7. Elija **Collection v1** como formato de exportación.
   
    ![Postman, Exportar](./media/postman-collection/export2.png)

Ahora ya puede usar esta colección Postman para crear un conector personalizado en Microsoft Flow.

> [!IMPORTANT]
> Al crear un conector personalizado a partir de una colección de Postman, asegúrese de quitar el encabezado `Content-type` de las acciones y los desencadenadores, ya que lo agregará automáticamente Microsoft Flow. Los encabezados de autenticación (por ejemplo, `Ocp-Apim-Subscription-Key`) deben definirse en la sección **Seguridad** y deben quitarse de las acciones y los desencadenadores. 
> 
> 

Para más información, consulte [Registro y uso de conectores personalizados en Microsoft Flow](register-custom-api.md).

