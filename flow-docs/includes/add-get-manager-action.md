---
ms.openlocfilehash: 4df22afb64f96b89535d7c2536116d8ead2a48cc
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "64469649"
---
1. Seleccione **Nuevo paso** y, luego, **Agregar una acción**.
   
    ![nuevo paso](media/modern-approvals/select-sharepoint-add-action.png)
2. Escriba **obtener administrador** en el cuadro de búsqueda **Elegir una acción**.
3. Busque y, después, seleccione la acción **Office 365 Users - Get manager (V2)** (Usuarios de Office 365 - Obtener administrador [V2]).

    ![seleccionar usuarios de office](media/modern-approvals/add-get-manager-action.png)
4. Inserte el token **Created By Email** (Creado por correo electrónico) en el cuadro **Usuario (UPN)** en la tarjeta **Obtener administrador**.

    Esta acción obtiene el administrador de la persona que creó la solicitud de vacaciones en SharePoint.

    ![configuración de obtener administrador](media/modern-approvals/get-manager-card.png)

