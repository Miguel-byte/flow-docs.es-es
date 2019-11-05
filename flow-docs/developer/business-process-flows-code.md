---
title: Trabajar con flujos de procesos empresariales mediante código | MicrosoftDocs
description: Obtenga información sobre cómo trabajar con flujos de procesos empresariales mediante programación para crear procesos empresariales más eficientes y simplificados.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547728"
---
# <a name="work-with-business-process-flows-using-code"></a>Trabajar con flujos de procesos empresariales mediante código
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Un *flujo de procesos empresariales* le permite crear ventas, servicios y otros procesos empresariales más eficientes y simplificados. Crea una visualización del proceso empresarial mediante la colocación de controles especiales en la parte superior de los formularios de la entidad. A los usuarios se les guía a través de varias fases de los procesos de ventas, marketing o servicios hasta su finalización. Cada proceso admite varias fases y pasos. Puede Agregar o quitar pasos, cambiar el orden de las fases o agregar nuevas entidades al flujo de procesos empresariales.  
  
Las distintas instancias de flujo de procesos empresariales pueden ejecutarse simultáneamente en el mismo registro de entidad. Los usuarios pueden cambiar entre instancias de procesos empresariales simultáneos y reanudar su trabajo en una fase actual del proceso. 

En este tema se proporciona información sobre cómo se puede trabajar mediante programación con flujos de procesos empresariales.

> [!NOTE]
> No tiene que escribir código para trabajar con flujos de procesos empresariales. Para obtener información sobre el uso de la interfaz de usuario para crear y administrar flujos de procesos empresariales, consulte [información general sobre flujos de procesos empresariales](../business-process-flows-overview.md) .  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Requisitos previos para el flujo de procesos empresariales 

Las entidades y entidades personalizadas que tienen formularios de interfaz de usuario actualizados pueden participar en el flujo del proceso empresarial. Las entidades de interfaz de usuario actualizadas tienen la propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> establecida en `true`. 

Para habilitar una entidad para el flujo de procesos empresariales, establezca la propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> en `true`.

> [!IMPORTANT]
>  Habilitar una entidad para el flujo de procesos empresariales es un proceso unidireccional. No se puede invertir.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definir el flujo de procesos empresariales
  
Use el diseñador de flujo de proceso empresarial visual para definir un flujo de procesos empresariales. Más información: [creación de un flujo de procesos empresariales](../create-business-process-flow.md)

De forma predeterminada, se crea un registro de flujo de proceso empresarial en el estado `Draft`.  

Una definición de flujo de proceso empresarial se almacena en la entidad <xref:Microsoft.Dynamics.CRM.workflow> y la información de fase para el flujo de proceso empresarial se almacena en la entidad <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Activar flujo de procesos empresariales  
 Antes de poder usar el flujo de proceso, debe activarlo. Para activarla, debe tener el privilegio `prvActivateBusinessProcessFlow` para la entidad `Workflow`. Utilice el mensaje <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para establecer el estado del registro de entidad `Workflow` en `Activated`. Más información: [realización de operaciones especializadas mediante Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > También puede utilizar el diseñador de flujo de procesos empresariales para activar un flujo de procesos empresariales. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidad flujo de proceso empresarial 
 Una vez que se activa una definición de flujo de proceso empresarial cambiando el estado del registro de entidad `Workflow` correspondiente o mediante el diseñador de flujo de procesos empresariales, se crea automáticamente una entidad personalizada con el siguiente nombre para almacenar el negocio activado instancias de flujo de proceso: " *\<activesolutionprefix >* _ *\<uniquename >* ", donde UniqueName se deriva del nombre especificado.  
  
 Por ejemplo, si especificó "My Custom BPF" como el nombre de la definición de flujo de proceso empresarial y usa el publicador predeterminado (nuevo) para la solución activa, el nombre de la entidad personalizada que se crea para almacenar las instancias de proceso será "new_mycustombpf".  
  
 Si el valor `uniquename` no está disponible para una definición de flujo de proceso empresarial, por ejemplo, si el flujo de proceso empresarial se importó como parte de la solución de una versión anterior, el nombre predeterminado de la entidad personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  Los registros de flujo de proceso de negocio de ejemplo usan entidades del sistema para almacenar los registros de instancia de flujo de proceso empresarial correspondientes.  
>   
>  Sin embargo, las nuevas definiciones de flujo de procesos empresariales que cree utilizarán entidades personalizadas para almacenar sus registros de instancia, tal como se explicó anteriormente. 

Puede recuperar el nombre de la entidad de flujo de proceso empresarial mediante cualquiera de las siguientes maneras:

- **Mediante la interfaz de usuario**: Use la interfaz de usuario de personalización para ir a la entidad de flujo de proceso empresarial:

    ![](media/bpf-entity-name.png)
- **Mediante la API Web**: Use la siguiente solicitud:

    **Solicite**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Ante**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- Usar **el servicio de la organización**: Use el siguiente ejemplo de código:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> La propiedad <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> es `true` para las entidades de flujo de procesos empresariales. Puede recuperar todas las entidades de flujo de procesos empresariales en la instancia ejecutando la siguiente solicitud de API Web:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Administrar la seguridad de los flujos de procesos empresariales

La entidad personalizada que se crea automáticamente al activar un flujo de procesos empresariales para almacenar instancias de flujo de procesos empresariales se ajusta al modelo de seguridad estándar como para cualquier otra entidad personalizada en Common Data Service. Esto implica que los privilegios concedidos en estas entidades definen los permisos de tiempo de ejecución de los usuarios para los flujos de procesos empresariales.

La entidad flujo de proceso de negocio personalizada tiene ámbito de organización. Los privilegios de creación, recuperación, actualización y eliminación normales en esta entidad definen el permiso que los usuarios tendrían en función de sus roles asignados. De forma predeterminada, cuando se crea la entidad personalizada de flujo de procesos empresariales, solo se concede acceso a ella a los roles de seguridad de **Administrador del** sistema y de **Personalizador del sistema** , y debe conceder permisos explícitamente a la nueva entidad de flujo de proceso de negocio (para por ejemplo, **mi BPF personalizado**) para otros roles de seguridad según sea necesario.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Crear, recuperar, actualizar y eliminar registros de entidad de flujo de procesos empresariales (instancias de proceso)  
 La entidad personalizada que se crea automáticamente al activar una definición de flujo de proceso empresarial almacena todas las instancias de proceso para la definición de flujo de proceso empresarial. La entidad personalizada admite la creación y administración de registros mediante programación estándar mediante la API Web y el punto de conexión de CRM 2011.

> [!IMPORTANT]
> Cambiar a otra instancia de proceso para un registro de entidad solo se admite a través de la interfaz de usuario (cliente) o mediante programación con la información disponible en esta sección. Ya no puede usar el mensaje de `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> o <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) para cambiar mediante programación los procesos (establezca otro flujo de procesos empresariales como la instancia de proceso activa) para el registro de la entidad de destino. 

 Considere el ejemplo siguiente, donde tenemos un flujo de procesos empresariales entre entidades, "My Custom BPF", con 3 fases: S1: account, S2: account y S3: contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperar todos los registros (instancias) de una entidad de flujo de proceso de negocio
 Si el nombre de la entidad de flujo de proceso empresarial es "new_mycustombpf", use la siguiente consulta para recuperar todos los registros (instancias de proceso) de la entidad flujo de proceso empresarial:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

En este momento, es posible que no obtenga ninguna instancia de la respuesta, ya que no hay ninguna. Ejecute esta solicitud después de crear una instancia de la definición de flujo de proceso empresarial más adelante en este tema.

> [!NOTE]
> Para saber cómo recuperar el nombre de la entidad de flujo del proceso empresarial, consulte la sección anterior, la [entidad flujo de proceso empresarial](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Creación de un registro de entidad de flujo de proceso empresarial (instancia de proceso) 

Cree un registro de entidad de flujo de proceso empresarial (instancia de proceso) mediante programación si desea cambiar a otro flujo de procesos empresariales para un registro de entidad sin usar la interfaz de usuario. 

Para crear un registro de entidad de flujo de proceso empresarial, debe especificar los valores siguientes: 
- Asocie el registro de la entidad de flujo de procesos empresariales a un registro de entidad principal estableciendo la propiedad de navegación de un solo valor mediante la `@odata.bind` anotación. Para averiguar el nombre de la propiedad de navegación que apunta al registro de entidad principal de la definición de flujo de proceso empresarial, use el [documento $Metadata CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Asocie el registro de la entidad flujo de proceso empresarial a una fase válida especificada en la definición de flujo de proceso empresarial estableciendo la propiedad de navegación de un solo valor mediante la `@odata.bind` anotación. Para averiguar el nombre de la propiedad de navegación (normalmente `activestageid`) que apunta al registro provisional de la definición de flujo de proceso empresarial, use el [documento $Metadata CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Además, puede recuperar información sobre todas las fases de una definición de flujo de proceso empresarial mediante la siguiente solicitud de API Web, suponiendo que el identificador de la definición de flujo de proceso empresarial es 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Solicite**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Ante**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

A continuación, use la siguiente solicitud para crear una instancia de la definición de flujo de proceso empresarial para un registro de cuenta (ID. = a176be9e-9a68-E711-80e7-00155d41e206) y la fase activa establecida como la primera fase de la instancia de proceso, S1 (ID. = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Solicite**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Ante**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Tenga en cuenta que, si desea crear una instancia de la definición de flujo de proceso empresarial con el conjunto de la fase activa como una fase ***distinta*** de la primera fase, también debe proporcionar `traversedpath` en la solicitud. La ruta de acceso recorrida es la cadena delimitada por comas de identificadores de fase de proceso que representan las fases visitadas de la instancia de flujo de proceso de negocio. La solicitud siguiente crea una instancia de para un registro de cuenta (ID = 679b2464-71B5-E711-80f5-00155d513100) y un conjunto de fases activas como la segunda fase, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Actualización de un registro de entidad de flujo de proceso empresarial (instancia de proceso)

Puede actualizar una instancia de proceso para pasar a la fase siguiente o anterior, abandonar una instancia de proceso, reactivar una instancia de proceso o finalizar una instancia de proceso. 

#### <a name="stage-navigation"></a>Navegación por fases

Para ir a una fase diferente, debe actualizar un registro de instancia de proceso para cambiar su identificador de fase activo y, en consecuencia, actualizar la ruta de acceso recorrida. Tenga en cuenta que solo debe pasar a la etapa siguiente o anterior mientras actualiza una instancia de flujo de proceso empresarial.

Para realizar la navegación por fases, necesitará el identificador de la instancia de flujo de proceso empresarial que desea actualizar. Para recuperar todas las instancias del flujo de procesos empresariales, vea [recuperar todos los registros (instancias) de una entidad de flujo de proceso empresarial](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) anterior.

Suponiendo que el identificador de la instancia de proceso que quiere actualizar es dc2ab599-306d-e811-80ff-00155d513100, use la siguiente solicitud para actualizar la fase activa de S1 a S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Cambiar el estado de una instancia de proceso: anular, reactivar o finalizar 

Una instancia de proceso puede tener uno de los siguientes Estados: **activo**, **finalizado**o **anulado**. El estado viene determinado por los siguientes atributos en el registro de la instancia de proceso:

- **StateCode**: muestra el estado de la instancia de proceso.

    |valor|rótulo|
    |-----|-----|
    |0,1    |Active|
    |dimensional    |Inactiva|

- **StatusCode**: muestra información sobre el estado de la instancia de proceso.

    |valor|rótulo|
    |-----|-----|
    |dimensional    |Active|
    |dos    |Deja|
    |3    |Anuló|

Por lo tanto, para **anular** una instancia de proceso, use el siguiente conjunto de solicitudes para los valores de `statecode` y `statuscode` de forma adecuada:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Puede anular una instancia de proceso en cualquier fase.

Del mismo modo, para reactivar una instancia de proceso, reemplace los valores `statecode` y `statuscode` del código anterior por **0** y **1** , respectivamente.

Por último, para establecer el estado de una instancia de proceso como **terminado**, que solo es posible en la última fase de una instancia de proceso, reemplace los valores `statecode` y `statuscode` del código anterior por **0** y **2** , respectivamente.

#### <a name="cross-entity-navigation"></a>Navegación entre entidades

Para la navegación entre entidades en este ejemplo, debe establecer la fase activa de la instancia de proceso en la última fase, S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), actualizar la ruta de acceso recorrida en consecuencia y establecer un registro de contacto como el registro de la entidad principal según definición de flujo del proceso empresarial.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Eliminación de un registro de entidad de flujo de proceso empresarial (instancia de proceso)

Use la siguiente solicitud de API Web:

**Solicite**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Ante**

Si el registro existe, recibirá una respuesta normal con el estado 204 para indicar que la eliminación se realizó correctamente. Si no se encuentra la entidad, recibirá una respuesta con el estado 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Uso de mensajes RetrieveProcessInstances y RetrieveActivePath

Use el mensaje de `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para recuperar todas las instancias de flujo de proceso empresarial para un registro de entidad en todas las definiciones de procesos empresariales. Las instancias de flujo de procesos empresariales devueltas para una entidad se ordenan en función del atributo `modifiedon` de la instancia. Por ejemplo, la instancia de flujo de proceso de negocio modificada más recientemente será el *primer* registro de la colección devuelta. La instancia de flujo de proceso de negocio modificada más recientemente es la que está activa en la interfaz de usuario para un registro de entidad.  
  
Cada registro de instancia de flujo de proceso empresarial devuelto para un registro de entidad como resultado del uso del `RetrieveProcessInstances` mensaje almacena el identificador de la fase activa en el atributo `processstageid` que se puede usar para buscar la fase activa y, a continuación, se mueve a la fase anterior o siguiente. Para ello, primero debe buscar la ruta de acceso activa de una instancia de flujo de proceso empresarial y las fases disponibles en la instancia de flujo de proceso mediante el `RetrieveActivePath` mensaje (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> o <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Una vez que tenga la fase activa y la información de la ruta de acceso activa para una instancia de flujo de proceso de negocio, puede usar la información para pasar a una fase anterior o siguiente en la ruta de acceso activa. La navegación hacia delante de las fases debe realizarse en secuencia, es decir, solo debe avanzar a la siguiente fase de la ruta de acceso activa.   
  
 Para obtener el ejemplo completo en el que el código muestra el uso de estos dos métodos y la navegación por fases mediante el servicio de la [organización](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), vea [ejemplo: trabajar con flujos de procesos empresariales](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicar el flujo de procesos empresariales al crear un registro de entidad

En esta sección se proporciona información sobre el comportamiento predeterminado para aplicar flujos de procesos empresariales automáticamente a los nuevos registros de entidad creados en Common Data Service y cómo puede invalidarlo para aplicar un flujo de procesos empresariales de su elección para nuevos registros de entidad.

De forma predeterminada, para una entidad que tiene varios flujos de procesos empresariales definidos para ella, el sistema aplica un flujo de procesos empresariales al nuevo registro de entidad mediante la siguiente lógica de varios pasos:
1. Identifique todos los flujos de procesos empresariales aplicables al nuevo registro de entidad basado en el atributo **Workflow. PrimaryEntity** de los registros de definición de flujo de proceso empresarial.
2. Identifique las definiciones de flujo de proceso de negocio a las que el usuario actual tiene acceso. Para obtener información sobre cómo se determina y administra el acceso a un flujo de procesos empresariales, vea [administrar la seguridad de los flujos de procesos empresariales](#BPFSecurity) anteriormente en este tema.<br/>  
3. Todas las definiciones de flujo de procesos empresariales del sistema están sujetas a un pedido global por entidad. El orden del flujo de proceso empresarial se almacena en el atributo **Workflow. ProcessOrder** . Las definiciones de flujo de procesos empresariales de una entidad se ordenan en función de este orden y se selecciona la que tiene el menor valor de orden.
4. Por último, si el registro de entidad se crea a partir de una aplicación empresarial (módulo de aplicación), se aplica un nivel más de filtrado para elegir el flujo de proceso empresarial que se aplicará automáticamente al nuevo registro de entidad. Cuando se trabaja en una aplicación, los usuarios solo pueden acceder a las entidades pertinentes, los flujos de procesos empresariales, las vistas y los formularios a los que tienen acceso en virtud de los roles de seguridad asignados a la aplicación empresarial. 
    - Si la aplicación empresarial no contiene ningún flujo de procesos empresariales, el flujo de procesos empresariales se aplica como se explicó hasta el paso 3.
    - Si la aplicación empresarial tiene uno o más flujos de procesos empresariales, solo se aplicarán los flujos de procesos empresariales presentes en la aplicación. En este caso, cuando el usuario trabaja en un contexto de la aplicación empresarial, la lista de flujos de procesos empresariales del paso 3 se filtra más allá de las que forman parte de la aplicación empresarial que están presentes en el módulo de la aplicación y se ordenan según el orden de los procesos. 
    - Si no hay ningún flujo de procesos empresariales disponible en una aplicación empresarial para la entidad o en el que el usuario tiene acceso, no se aplica ningún flujo de procesos empresariales para el nuevo registro de entidad.

Puede invalidar la lógica predeterminada de los flujos de procesos empresariales que se aplican automáticamente a los nuevos registros de entidad. Para ello, establezca el atributo **ProcessId** de la entidad en uno de los siguientes valores al crear un nuevo registro de entidad:
- Establézcalo en **GUID. Empty** para omitir la configuración de un flujo de procesos empresariales para nuevos registros de entidad. Puede que desee hacerlo si está creando masivamente registros de entidad, pero no desea que se les aplique el flujo de procesos empresariales.
- Establézcalo en una entidad de flujo de proceso de negocio específica (como referencia de entidad). En este caso, el sistema aplicará el flujo de proceso empresarial especificado en lugar de la lógica predeterminada.

Si no establece un valor para el atributo **ProcessId** al crear un nuevo registro de entidad, el sistema aplicará la lógica predeterminada como se explicó anteriormente.

> [!NOTE]
> Invalidar la lógica predeterminada de los flujos de procesos empresariales que se aplican automáticamente a los nuevos registros de entidad solo se admite mediante programación. No se puede hacer con la interfaz de usuario.

## <a name="legacy-process-related-attributes-in-entities"></a>Atributos relacionados con los procesos heredados en entidades

Los atributos relacionados con los procesos heredados (como **ProcessId**, **StageId**y **TraversedPath**) en las entidades habilitadas para los flujos de procesos empresariales ya están desusados. La manipulación de estos atributos relacionados con los procesos heredados para los registros de entidad de destino no garantiza la coherencia del estado del flujo de procesos empresariales y ***no*** es un escenario admitido. La manera recomendada es usar los atributos de la entidad flujo de proceso empresarial como se explicó anteriormente en la sección [crear, recuperar, actualizar y eliminar registros de entidad de flujo de procesos empresariales (instancias de proceso)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) .

La única excepción a esto es modificar mediante programación el atributo **ProcessId** mientras se crea un registro de entidad para reemplazar la aplicación predeterminada del flujo del proceso empresarial al nuevo registro, tal como se explica en la sección anterior: [Apply Business flujo de proceso mientras se crea un registro de entidad](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Compatibilidad con la programación del lado cliente para flujos de procesos empresariales  
 Hay un objeto del lado cliente que se puede usar para interactuar con los flujos de procesos empresariales en los scripts de formulario. Los flujos de procesos empresariales desencadenan eventos del lado cliente cada vez que se aplica un proceso a un registro, se cambia la fase o se cambia su estado a `Active`, `Finished`o `Aborted`. Más información: [formContext. Data. Process (referencia de la API de cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de procesos, fases y pasos  
 Por entidad, el valor predeterminado para el número máximo de flujos de procesos empresariales activados es 10. Puede especificar un valor diferente mediante el atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Sin embargo, si el valor es mayor que 10, puede ver una disminución del rendimiento del sistema al cambiar procesos o abrir un registro que tenga un flujo de procesos empresariales asignado. Esto puede ser especialmente perceptible si los procesos abarcan varias entidades.  
  
 La configuración siguiente no se pueden personalizar:  
  
-   El número máximo de fases por entidad en el proceso es 30.  
  
-   El número máximo de pasos de cada fase es 30.  
  
-   El número máximo de entidades que pueden participar en el flujo de proceso es 5.  

