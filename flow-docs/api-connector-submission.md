---
title: "Envío para certificación como conector de API | Microsoft Docs"
description: "Mediante la certificación de un conector, este estará disponible para todos los usuarios de Microsoft Flow, PowerApps y Logic Apps."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 7eb357458161ba398864604bfe8912636ddc4d39
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Envío de conectores para que los certifique Microsoft
Para que los conectores personalizados estén disponibles públicamente para todos los usuarios de Microsoft Flow, Azure Logic Apps y Microsoft PowerApps, envíe el conector a Microsoft para su revisión, validación y aprobación para su publicación. 

## <a name="certification-criteria"></a>Criterios de certificación
| Funcionalidad | Detalles | Necesario o recomendable |
| --- | --- | --- |
| Aplicación de software como servicio (SaaS) |Cubre un escenario de usuario que encaja bien con Logic Apps, Flow y PowerApps. |Necesario |
| Tipo de autenticación |La API debe ser compatible con OAuth2, Clave de API o Autenticación básica |Necesario |
| Soporte técnico |Debe proporcionar un contacto de soporte técnico para que los clientes puedan obtener ayuda |Necesario |
| Disponibilidad y tiempo de actividad |La aplicación tiene al menos un 99,9 % de tiempo de actividad. |Recomendable |
|  | | |

Aquellos que no sean partners de Microsoft o fabricantes de software independientes (ISV) y deseen certificar y liberar públicamente un conector, deben poseer el servicio subyacente o presentar derechos explícitos para usar la API.

Antes de conceder la certificación el conector se revisa en dos fases: 

1. Validación de funcionalidad
   
    Se evalúan los siguientes aspectos del conector personalizado:
   
   * Swagger no válido o errores de JSON en la sección de definición del Asistente para conector personalizado
   * Errores de runtime y de validación de esquema en la sección de pruebas del asistente
     
     Por tanto, todas las operaciones se prueban exhaustivamente en Flow, Logic Apps y PowerApps, por si hay algún error del cliente.
2. Validación de contenido
   
    Un conector bien escrito usa nombres descriptivos y descripciones en todas las entidades. La evaluación del archivo swagger se realiza para asegurarse de que todas las operaciones, parámetros de entrada y atributos de las respuestas contienen:
   
   * [Resumen](../logic-apps/custom-connector-openapi-extensions.md#summary)
   * [Descripción](../logic-apps/custom-connector-openapi-extensions.md#description)
   * [Información de visibilidad](../logic-apps/custom-connector-openapi-extensions.md#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>Designe y envíe su conector a Microsoft para su certificación
Para solicitar la certificación, siga estos pasos:

1. **Designación**
   
   1. [Envío de la designación](https://go.microsoft.com/fwlink/?linkid=848754)
   2. Firme el acuerdo de confidencialidad y el acuerdo de socio comercial que reciba. 
      Microsoft requiere estos contratos firmados antes de continuar. 
      A continuación, podemos comprobar si el conector cumple los criterios de certificación. 
   3. Si el conector se aprueba, Microsoft le proporcionará instrucciones para la incorporación.
2. **Revisión**
   
   1. Envíe esta información al contacto de nominación para su revisión:
      
      * El archivo OpenAPI que describe la API
      * El archivo de icono (.png o .jpg) que representa el conector. (El icono debe tener un logotipo aproximado de 160 píxeles dentro de un cuadrado de 230 píxeles. Se prefiere un logotipo blanco sobre un fondo de color.)
      * El color de la marca del icono en formato hexadecimal, que debe coincidir con el fondo de color del archivo de icono
      * Una cuenta de prueba para la validación
      * Un contacto de soporte técnico
   2. Si se necesita más información, nos pondremos en contacto con usted.
3. **Publicación**
   
    Tras validar el contenido y la funcionalidad del conector, se realiza una copia intermedia del conector para su implementación en todos los productos y regiones. Normalmente, el proceso de certificación e implementación tarda un máximo de 3 semanas.
   
    De forma predeterminada, todos los conectores se publican como "premium". 
    Si la aplicación se ha compilado con Azure, se puede solicitar que el conector aparezca como conector "estándar" disponible para todos los usuarios que tengan planes de Office 365 Enterprise. 
    Para más información, pregunte a su contacto de designación.

