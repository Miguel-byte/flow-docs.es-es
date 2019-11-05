---
title: Notas de la versión | Microsoft Docs
description: Problemas comunes y novedades de las versiones de Microsoft Flow
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
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548870"
---
# <a name="release-notes"></a>Notas de la versión
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Principales preguntas
1. Error en mi flujo. ¿Cómo corregirlo?
   
   1. Identifique el error. Para empezar, vaya al icono de notificaciones en la parte superior del portal web o seleccione la pestaña **actividad** en la aplicación móvil. Debería ver el flujo allí y puede seleccionarlo.
   2. Ahora está examinando los detalles del flujo. Busque el paso con el icono de exclamación rojo y debería ver el mensaje de error del flujo allí.
   3. En función del mensaje de error, debería poder **Editar** el flujo y corregirlo. [Obtenga más información sobre cómo solucionar errores comunes de flujo](fix-flow-failures.md).
2. ¿Cómo usar una condición avanzada o una expresión?
   
   * Obtenga información sobre cómo [Agregar condiciones](add-condition.md).
   * Si desea varios casos en un flujo, seleccione **Agregar condición** desde dentro de una condición existente.
   * Cree una expresión avanzada haciendo referencia [a una función en Logic apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. ¿Cómo funciona la concesión de licencias con Office 365?
   
   * Si es un usuario de Office 365, obtendrá acceso completo a través del plan de Microsoft Flow para Office 365. Para obtener más información, consulte los [planes de precios de Microsoft Flow](https://flow.microsoft.com/pricing/) .
   * Si es administrador, consulte la información sobre las [licencias de Microsoft Flow](organization-q-and-a.md), incluido con Office 365.

## <a name="known-issues"></a>Problemas conocidos
1. No se admiten listas de SharePoint en mis sitios y que no sean del tipo *lista personalizada* . Para solucionar este problema, cree una lista personalizada en un sitio de SharePoint estándar.
2. Los desencadenadores de archivo no se activarán para los archivos que se agregan dentro de las carpetas anidadas dentro de la carpeta que seleccione.

## <a name="whats-new"></a>Novedades

> [!IMPORTANT]
>
> **Presentación de las notas de la versión**
>
> ¿Se pregunta sobre las funcionalidades próximas y publicadas recientemente en Microsoft Flow?
>[Vea las notas de la versión de octubre de 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Hemos capturado todos los detalles, de un extremo a otro, de arriba a abajo, que puede usar para la planeación. Para obtener más información, revise [cada versión semanal](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) con las características y mejoras que contiene.
>
> Las notas de la versión anteriores a la versión 2018 de octubre permanecerán aquí para futuras referencias, pero todas las versiones nuevas solo se incluirán en las ubicaciones anteriores y no en esta página.

### <a name="release-2018-09-24"></a>Versión 2018-09-24

- **Acceso de administrador a ayuda y soporte técnico** : Abra vales de soporte técnico para Microsoft Flow en el centro de administración de Power Platform y proporcione detalles adicionales sobre el error del flujo de trabajo.
- **Comunidad de flujos rediseñado** : la búsqueda de lo que necesita es más fácil en la comunidad de Flow.
- **Mejoras en el conector de Microsoft Teams** : nuevos desencadenadores para Microsoft Teams para que pueda ejecutar un flujo cuando haya nuevos mensajes en un canal.
- **Más acciones de SharePoint** : hay nuevas acciones para mover archivos y mucho más en el conector de SharePoint.
- **Nuevos informes de análisis de administración** : Análisis de todo el entorno y el inquilino agregados al centro de administración de la plataforma de aplicaciones empresariales.
- **Integración de Power Query** : se está generando una experiencia de Power Query que permitirá a los responsables de dar forma a los mashups de datos de SQL Server.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) sobre esta versión.

### <a name="release-2018-08-31"></a>Versión 2018-08-31

- **Probar el flujo con datos de ejemplo** : Use los datos de ejemplo de los conectores para probar el flujo mientras lo crea desde el diseñador de Microsoft Flow. Al probar el flujo con datos de ejemplo, se confirma que el flujo se ejecutará según lo esperado cuando se implemente en producción.
- **Cinco nuevos conectores** : hemos agregado cuatro nuevos conectores de administración: Powerapps para fabricantes de aplicaciones, Power Platform para administradores, Powerapps para administradores, Microsoft Flow para administradores y Microsoft School Data Sync.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/test-data-management-connectors/) sobre esta versión.

### <a name="release-2018-08-24"></a>Versión 2018-08-24

- **Nuevas plantillas de sincronización de calendario** : nuevas plantillas de calendario que copian eventos entre Google Calendar y Office 365 o Outlook.com.
- **Compatibilidad con varios valores para SharePoint** : lectura y escritura para campos de varios valores en SharePoint que son tipos de elección, persona o búsqueda.
- **Enviar aprobaciones en nombre de otros usuarios de la organización** : Envíe aprobaciones en nombre de otros usuarios de la organización; por ejemplo, la persona que cargó el archivo en la lista de SharePoint, en lugar de la persona que creó el flujo.
- **Tipos de entrada de botón más** : los botones tienen dos nuevos tipos de entrada: número y sí/no.
- **Actualizaciones del conector** : un nuevo conector de NetDocuments, mejoras en los conectores de Azure y mucho más.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/button-types-more/) sobre esta versión.

### <a name="release-2018-08-02"></a>Versión 2018-08-02

El programa de vista previa Microsoft Flow es la manera de obtener acceso temprano a las próximas funcionalidades y actualizaciones de Microsoft Flow. Para obtener acceso temprano a las características más recientes, solo tiene que crear y usar un entorno en la región de vista previa.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/flow-preview-program/) sobre esta versión.

### <a name="release-2018-07-23"></a>Versión 2018-07-23

- **Compilar y ejecutar flujos desde Excel** : con el botón nuevo **flujo** (al que se tiene acceso desde la pestaña **datos** de la cinta de opciones), puede crear y desencadenar Automations desde Microsoft Flow en los datos de la tabla en Excel. Automatice el procesamiento de datos o la copia o importación de datos.
- **Crear un flujo de procesos empresariales** : un flujo de procesos empresariales es un nuevo tipo de flujo interactivo y con estado basado en el Common Data Service. Utilice estos nuevos flujos para definir un conjunto de fases y pasos para que las personas sigan. Pueden moverse hacia delante y hacia atrás según sea necesario.
- **Creación de un flujo para las tareas de Microsoft en Outlook Web App** : si alguien se \@menciona en Outlook Web App, verá un acceso directo para crear un flujo. Este flujo crea automáticamente tareas para la \@persona mencionada en Microsoft, en función del contenido del correo electrónico.
- **Compatibilidad con la vista de SharePoint** : el conector de SharePoint ahora admite la selección de una vista específica de SharePoint en desencadenadores y acciones. Esto filtra las columnas hasta solo los campos que se encuentran en la vista seleccionada.
- **Cuatro nuevos conectores** : se ha agregado Azure IOT central: una solución de IOT software como servicio (SaaS) muy escalable: encuesta 123, LMS365 y ProjectWise Design Integration.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) sobre esta versión.

### <a name="release-2018-06-29"></a>Versión 2018-06-29

- **Solicitud de flujo de cierre de sesión integrado en SharePoint** : al seleccionar un archivo o un elemento en SharePoint, verá una nueva **solicitud de flujo de cierre de sesión** . Este flujo no requiere ninguna configuración ni configuración y envía una solicitud de cierre de sesión con un solo clic.
- **Dos nuevos conectores** : se ha agregado Cloud Connect Studio y PoliteMail.
- **Mejoras en el historial y** en la creación de una página: estamos actualizando la lista del historial de ejecuciones incluyendo los tiempos de ejecución exactos y la página crear agregando un nuevo vídeo del tutorial.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) sobre esta versión.

### <a name="release-2018-06-08"></a>Versión 2018-06-08

- Los **cmdlets de PowerShell** : los fabricantes de flujos y los administradores de inquilinos ahora pueden usar PowerShell para administrar sus flujos mediante programación.
- **Mejoras en el bot de flujo de equipos** : el bot de flujo en Microsoft Teams puede ejecutar botones de flujo y describir los flujos.
- **Tres nuevos conectores** : se ha agregado compatibilidad con Marketo, ElasticOCR y DynamicSignal. 
- **Información adicional de uso compartido** : se ha agregado información adicional al compartir o ejecutar flujos compartidos, para que sepa exactamente qué permisos recibirán otras personas.
- **Recorte automático de direcciones URL de SharePoint** : Cuando copie y pegue una dirección URL de SharePoint en el explorador, podría contener texto adicional más allá del sitio; este texto se quitará automáticamente para que pueda conectarse únicamente al sitio.
- **Documentación sobre solicitudes de RGPD** : hemos creado una guía completa y un conjunto de herramientas para que las organizaciones empresariales controlen las solicitudes de derechos de asunto de datos.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) sobre esta versión.

### <a name="release-2018-05-21"></a>Versión 2018-05-21

- **Flujos "propiedad de" las listas y bibliotecas de SharePoint** : los flujos que funcionan con listas y bibliotecas de SharePoint se pueden compartir con esas listas o bibliotecas. Por lo tanto, en lugar de compartirlos con personas o grupos, se comparten con todos los usuarios que tienen acceso a la lista. A medida que se agregan o quitan usuarios de la lista o biblioteca, su pertenencia cambia automáticamente en consecuencia.
- **Análisis de detalles de errores** : un nuevo informe incrustado que proporciona información sobre todos los errores que se producen dentro de un flujo.
- **Compartir flujos con grupos de office 365** : puede hacer que un grupo moderno de Office 365 sea el propietario de un flujo, y puede compartir flujos de botones con grupos de Office 365 para que cualquier usuario del grupo pueda ejecutar el flujo.
- **Mejoras del conector de SharePoint** : hay dos nuevas funcionalidades de conector de SharePoint: desencadenar flujos cuando se eliminen elementos o archivos y llamar a cualquier punto de conexión http que admita la API de REST de SharePoint.
- **Dos nuevos conectores** : compatibilidad agregada para Azure Data Factory y MailParser

[Lea más y formule preguntas](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) sobre esta versión.

### <a name="release-2018-05-01"></a>Versión 2018-05-01

- **Texto enriquecido en los mensajes de aprobación** : Use Markdown para dar formato a los detalles de aprobación que envíe.
- **Botones con varias entradas de selección** : botones de flujo de compilación que usan una lista de selección múltiple para recopilar más de un valor a la vez.
- **Trabajar con flujos más amplios** : la aplicación móvil Microsoft Flow ahora admite la vista horizontal y el diseñador web tiene una barra de desplazamiento horizontal.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) sobre esta versión.

### <a name="release-2018-04-12"></a>Versión 2018-04-12

- **Devolver datos a PowerApps desde** flujos de compilación de flujo a los que se puede llamar desde una aplicación compilada con PowerApps y devolver los datos a la aplicación. Use el diseñador de flujo de arrastrar y colocar de visual para compilar la lógica que necesita para las aplicaciones. 
- **Agregar varios registros a entradas de matriz** : se ha agregado un generador de listas a Microsoft Flow que se puede usar para agregar varios datos adjuntos a un correo electrónico, por ejemplo.
- **Probar flujos con datos ejecutados anteriormente** : se ha agregado un nuevo botón probar flujo al diseñador que le permite probar el flujo con datos del desencadenador de ejecuciones de flujo anteriores.
- **Nuevos campos de flujo de trabajo ()** : ahora puede acceder al nombre del entorno y al nombre para mostrar de flujo con la expresión de flujo de trabajo ().

[Lea más y formule preguntas](https://flow.microsoft.com/blog/return-data-to-powerapps/) sobre esta versión.

### <a name="release-2018-04-04"></a>Versión 2018-04-04

- Las **aprobaciones de las** aprobaciones de Common Data Service-moderno se basan en la versión más reciente del Common Data Service. Esto significa que puede crear flujos que lean el estado de las aprobaciones que envía o recibe con el conector de Common Data Service.
- **Buscar errores en aplicar a cada** : saltar directamente a los errores en los bucles de la vista de ejecución de flujo, incluso cuando hay cientos de elementos en el bucle.
- **Reasignar aprobaciones** : puede asignar cualquier aprobación que reciba a otra persona de su organización para delegar la aprobación en ellas. 
- **Listas de salas** : el conector de Office 365 Outlook agregó acciones para obtener los datos de la habitación de la organización.
- **Ver detalles de los botones de flujo** : al ejecutar un flujo que se ha compartido con usted, ahora puede ver todas las acciones que el flujo usa.
- **Región del Reino Unido** : ahora se pueden crear entornos para almacenar sus datos en Reino Unido.
- **Dos nuevos conectores** : se ha agregado compatibilidad con el administrador de AtBot y el centro de contenido de marketing.
- **Nueva página de aterrizaje de documentación** : se ha actualizado la página de aterrizaje de la documentación para tener contenido agrupado por quién es el principiante, un usuario intermedio o un experto. 

[Lea más y formule preguntas](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) sobre esta versión.

### <a name="release-2018-03-13"></a>Versión 2018-03-13

- **Historial de aprobación** : vea todas las solicitudes de aprobación que ha enviado, incluidas las respuestas, los comentarios que se enviaron y la hora exacta en que se produjeron.
- **Cuatro nuevos conectores** : se ha agregado Excel online (Business), Excel online (OneDrive), Azure SQL Data Warehouse y la calculadora de impuestos de Pitney Bowes.
- **Información sobre herramientas de contenido dinámico** : Mantenga el mouse sobre el contenido dinámico para ver dónde llegó desde dentro de las acciones y obtenga una vista previa de las expresiones sin abrir el editor de expresiones completo.
- **Control de simultaneidad** : habilite el control de simultaneidad para que un flujo determinado tenga solo una ejecución cada vez.
- **Reintento exponencial** : un nuevo tipo de directiva de reintentos que espacia los reintentos exponencialmente a lo largo del tiempo.
- **Conformidad** con la accesibilidad: se publican nuevos documentos de conformidad que describen cómo Microsoft Flow cumplir los estándares de accesibilidad.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/approval-history-accessibility/) sobre esta versión.

### <a name="release-2018-02-09"></a>Versión 2018-02-09

- **Alta disponibilidad de puerta de enlace** : cree clústeres de alta disponibilidad de puertas de enlace de datos locales, para mantener las conexiones al mismo tiempo que las máquinas virtuales.
- **Se ha mejorado aplicar a cada uno** : con el plan de flujo 1 o el plan de flujo 2 hasta 100.000 elementos en una sola ejecución y 50 acciones en paralelo en bucles de aplicar a cada. 

[Lea más y formule preguntas](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sobre esta versión.

### <a name="release-2018-01-29"></a>Versión 2018-01-29

- **Flujo dentro de Microsoft Teams** : desde los equipos, puede crear y administrar flujos, revisar las aprobaciones recibidas y enviadas e iniciar flujos directamente dentro de la aplicación de escritorio Teams o en Teams.Microsoft.com- [Obtenga más información aquí](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notificaciones de edición compartidas** : cada vez que un colega cambie un flujo de trabajo, recibirá una notificación por correo electrónico que le informa de quién ha cambiado el flujo.
- **Nuevas expresiones** : se han agregado dos nuevos conjuntos de expresiones: uno para analizar las direcciones URL y otro para trabajar con objetos JSON.
- **Tres nuevos conectores** : esta semana hay dos nuevos conectores de Plumsail: Plumsail SP y Plumsail, y un nuevo conector a kintone.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sobre esta versión.

### <a name="release-2018-01-17"></a>Versión 2018-01-17

- **Información de Perfil de office 365** : se han agregado nuevas acciones al conector de usuarios de Office 365 que funcionan con los perfiles de usuario y las fotos.
- **Anexar a variables de cadena** : puede Agregar cadenas dentro de bucles para crear tablas u otras listas.
- **Conector de infobip** : infobip es un servicio que permite la comunicación de nivel empresarial, incluidas las llamadas de voz y la activación en SMS entrante.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/o365-profile-infobip/) sobre esta versión.

### <a name="release-2017-12-20"></a>Versión 2017-12-20

Microsoft Flow Analytics ahora está disponible en todas las regiones Microsoft Flow, lo que significa que puede obtener más información sobre el estado de los flujos que se ejecutan dentro de su entorno.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sobre esta versión.


### <a name="release-2017-12-14"></a>Versión 2017-12-14

- **Mejoras del conector de Outlook** : puede guardar un correo electrónico como un archivo ". eml", responder a las invitaciones de calendario automáticamente y desencadenar flujos cuando se menciona en un subproceso de correo electrónico.
- **Mejoras en las conexiones** : Microsoft Flow recuerda las conexiones usadas más recientemente y muestra todos los conectores que se acaban de agregar.
- **Cinco nuevos conectores** : se han agregado Azure Container instances, Azure Kusto, metatask, Microsoft to-do y Plumsail Documents.
- **Mejoras de http** : la acción http admite ahora la codificación fragmentada.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/outlook-connector-more/) sobre esta versión.

### <a name="release-2017-12-05"></a>Versión 2017-12-05

El panel de inicio de Microsoft Flow ya está disponible en todas las regiones. Este panel permite agregar valores a un flujo cuando se ejecuta dentro de la biblioteca de documentos o lista de SharePoint.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sobre esta versión.


### <a name="release-2017-11-28"></a>Versión 2017-11-28

- Metadatos **administrados** : leer y escribir en columnas de SharePoint que usan los metadatos administrados (también conocidos como Taxonomía).
- **Anexar a matrices** : agregue elementos al final de las matrices usando una nueva acción de anexar a variable de matriz.
- **Tago** : un nuevo conector a Tago, que proporciona una conexión fácil de dispositivos electrónicos con datos externos para impulsar decisiones más inteligentes mediante el análisis contextual.
- **iPhone x** : una nueva versión de la aplicación Microsoft Flow que usa la pantalla completa en el iPhone x y que tiene una mejora de velocidad para las cargas de imágenes.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/managed-metadata-tago/) sobre esta versión.

### <a name="release-2017-11-09"></a>Versión 2017-11-09

- **Integración de onedrive para la empresa** : [ahora hay un botón de flujo dentro de OneDrive para la empresa](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) que puede crear o desencadenar flujos en archivos o carpetas seleccionados.
- **Desencadenadores de Planner** : inicia los flujos cuando se crea una nueva tarea, cuando se le asigna una tarea o cuando se completa una.
- **Datos adjuntos de SharePoint** : trabajar con datos adjuntos en elementos de lista de SharePoint: enumerar, descargar, agregar o eliminar datos adjuntos.
- **Conector de administración de Flow** : cree flujos que automaticen la administración de otros flujos en su entorno (por ejemplo, agregue permisos automáticamente a los flujos).
- **Cuatro nuevos conectores** : se ha agregado Azure Custom Vision Service, D & B Optimizer, Enadoc y Derdak SIGNL4. 
- **Más acciones del conector** : ejecutar consultas SQL, obtener desencadenadores de correo electrónico más rápidos, usar cualquier método con HTTP con Azure ad, etc.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sobre esta versión.

### <a name="release-2017-11-02"></a>Versión 2017-11-02

- **Registro de auditoría** : los eventos de auditoría de Microsoft Flow ahora están disponibles en Office 365 centro de seguridad y cumplimiento para todos los inquilinos.
- **Correcciones del widget de flujo** : se ha corregido un problema en la aplicación móvil de Flow que hacía que los botones no se cargaran en el widget.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/security-and-compliance-center/) sobre esta versión.

### <a name="release-2017-10-19"></a>Versión 2017-10-19

- Se **aplican anidadas a cada** : puede Agregar aplicar a cada acción, filtrar y seleccionar en otras acciones de cada contenedor.
- **Acciones de fecha y hora** : nuevas acciones para obtener horas locales, agregar, restar o dar formato a los tiempos.
- **Cuatro nuevos conectores** : se ha agregado Content Moderator, Docparser, Microsoft Kaizala y Pitney Bowes Data Validation.
- **Experiencia de conexión mejorada** : notificaciones en el portal de Microsoft Flow cuando una conexión se interrumpe y detalles de conexión más completos.
- **Recopilación en marcha** : una nueva colección de plantillas para [los trabajadores en marcha](https://flow.microsoft.com/collections/onthego/).
- **Entradas del botón de dirección de correo electrónico** : recopilar direcciones de correo electrónico de los usuarios cuando ejecutan botones.
- **Entradas de botón de archivo** : Obtenga archivos cargados, como fotos, de los usuarios cuando ejecuten botones.
- **Primera ejecución e inicio de sesión automático** : se han mejorado las experiencias de primera ejecución en la aplicación móvil, incluido el inicio de sesión automático.
- **Desencadenadores de Microsoft Forms más rápidos** : los formularios desencadenarán flujos mucho más rápido que antes (antes una hora).
- **Entradas de botón entre sesiones** : los botones que se desencadenan en el teléfono móvil recordarán las entradas anteriores.
- **Fuente de actividad móvil** : fuente de actividades mejorada para incluir resúmenes de ejecución más detallados y detalles de solución de problemas.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/nested-apply-to-each/) sobre esta versión.

### <a name="release-2017-10-03"></a>Versión 2017-10-03

- **Todo debe aprobar** : requerir una solicitud de aprobación enviada a más de una persona para que todos los usuarios que recibieron la solicitud lo aprueben.
- **Nuevas acciones de OneDrive para la empresa** : genere archivos PDF para los archivos almacenados en OneDrive para la empresa y otras cuatro acciones nuevas.
- **Conector de Apache Impala** : Apache Impala (incubación) es la base de datos analítica nativa de código abierto para Apache Hadoop.
- **Agregar descripciones de flujo** : proporcione las descripciones de los flujos, de modo que cuando los comparta, los compañeros de trabajo puedan ver un resumen del flujo.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sobre esta versión.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versión 2017-09-25: actualización del tercer trimestre para Microsoft Flow

- **Integración más profunda de SharePoint en la primera versión** : hay un nuevo envío "en el mismo" para los flujos de revisión y un panel de flujo para recopilar entradas cuando se ejecuta un flujo para los inquilinos de primera versión.
- **Dynamics 365 apps** : Flow ahora está integrado en la interfaz de usuario para aplicaciones de Dynamics 365 como Dynamics 365 sales y Dynamics 365 Customer Service.
- **Centro de confianza de Microsoft** : Microsoft Flow aparece en el centro de confianza de Microsoft, que muestra certificaciones como HIPAA, ISO y SOC.
- **Análisis de uso** : cada flujo tiene un panel de Power BI insertado con análisis de uso básico.
- **Registro de auditoría en la primera versión** : todos los eventos de administración de flujos se registran en el centro de seguridad y cumplimiento de Office 365 para los inquilinos de primera versión.
- **Seis nuevos conectores** : se han agregado los grupos LinkedIn, Office 365, Skype empresarial, Adobe Sign, Bizzy y Azure log Analytics Data Collection.
- **Desencadenadores SQL** : ejecuta flujos cuando se agrega una nueva fila o se actualiza una fila en una tabla SQL.
- **Conectores personalizados** locales: los conectores personalizados ahora pueden usar la puerta de enlace de datos local para conectarse a los puntos de conexión internos de la red.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/q3-2017-update/) sobre esta versión.

### <a name="release-2017-09-21"></a>Versión 2017-09-21

- **Descargar el historial de flujos** : Descargue el historial de ejecución de un flujo como un archivo CSV para abrirlo en Excel.
- **Periodicidad avanzada** : las programaciones periódicas de compilación para desencadenar los flujos, por ejemplo, solo se desencadenan los días laborables.
- **IntelliSense** : al escribir expresiones, IntelliSense proporcionará sugerencias para los parámetros.
- **Cuatro nuevos conectores** : se han agregado conectores para Azure ad servicios http, Amazon Redshift, Azure Event Grid Publish y FlowForma.
- **Vínculos de uso compartido** : una nueva acción para generar vínculos que se puedan compartir para archivos de OneDrive o blobs Azure Storage.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/download-history-recurrence/) sobre esta versión.


### <a name="release-2017-08-25"></a>Versión 2017-08-25
* **Propiedades de documento y más para SharePoint** - [leer y establecer las propiedades](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)de la biblioteca de documentos de SharePoint y usar campos adicionales como vínculos al elemento de SharePoint.
* **Colecciones de flujo** : las colecciones de flujos son un conjunto de colecciones de plantillas organizadas por rol o por vertical.
* **ReCompartir botón** : cuando comparte botones con sus compañeros de trabajo, también pueden volver a compartirlos con otras personas.
* **Recopilar listas de botones** : defina las listas desplegables de opciones que los usuarios pueden elegir cuando puntean en el botón.
* **Siete nuevos conectores** : AWeber, Azure log Analytics, Azure tables, DocFusion365, Azure Event Grid, Azure Event hubs y StaffHub. 
* **Mejoras en el margen de demora y en MySQL** : cree o combine canales en el margen de demora y puede escribir en las bases de datos MySQL.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sobre esta versión.

### <a name="release-2017-08-02"></a>Versión 2017-08-02
* **Escribir en campos de persona, elección y búsqueda** : los elementos de creación y actualización de SharePoint [ahora admiten la capacidad de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) establecer campos de persona, elección y búsqueda.
* **Más opciones de configuración** de la acción: ahora hay más control sobre cómo se ejecutan los desencadenadores y las acciones, incluida la configuración de las directivas de reintento y la paginación.
* **Cuatro nuevos conectores** : ahora puede usar Azure File Storage, formatos elásticos, Plivo y video Indexer.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) sobre esta versión.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versión 2017-07-27: actualización del segundo trimestre para Microsoft Flow
* **Importar y exportar** : exportar e importar soluciones de flujo en entornos o desde pruebas hasta producción. 
* **Usar expresiones en acciones** : escriba expresiones en cualquier acción y obtenga ayuda en línea sobre cómo usarlas.
* **Aumente hasta Azure Logic apps** : Guarde los flujos como recursos de Azure Logic apps que se pueden implementar a través de Visual Studio o el Azure portal.
* **Visibilidad de administración** : Descargue el uso de Microsoft Flow en el inquilino para comprender exactamente dónde y cómo se usan los flujos.
* **Flujos en dynamics 365** : Use flujos dentro de Dynamics 365 para operaciones & Financials, Business Edition.
* **Busque escenarios más fácilmente** : Examine todo lo que puede hacer el conector y, a continuación, use cualquier desencadenador como punto de partida para la creación de flujos.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/q2-2017-update/) sobre esta versión.

### <a name="release-2017-07-13"></a>Versión 2017-07-13
* **Publicación de plantillas mejorada** : publique cualquier flujo que cree, junto con sus categorías, en la galería pública.
* **Obtener eventos en el calendario de Outlook** : una nueva acción para devolver todos los eventos entre dos horas del calendario.
* **Nueva funcionalidad móvil** : ejecute flujos a petición y vuelva a enviar las ejecuciones con errores en la aplicación móvil.
* **Listas desplegables dinámicas en conectores personalizados** : crear listas desplegables dinámicas, desencadenadores de sondeo y probar los conectores personalizados.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sobre esta versión.

### <a name="release-2017-06-28"></a>Versión 2017-06-28
* **Actualizar la configuración de idioma** : puede personalizar el idioma y la región que utiliza Microsoft Flow a través del menú configuración.
* **Cinco nuevos conectores** : se ha agregado compatibilidad con Adobe Creative Cloud, mapas de Bing, Bing Search, JotForm y Freshservice.
* **Configurar tiempos de espera** : cambie las acciones de ejecución prolongada, como las aprobaciones, ejecute antes de "tiempo de espera" y el flujo continúe.
* **Incluir comentarios en Outlook para aprobaciones** : cuando reciba una solicitud de aprobación, puede proporcionar comentarios sin salir de Outlook.
* **Colores de la marca de conector personalizado** : ahora puede especificar un color para los conectores personalizados que se usarán para el fondo.
* **Guardar como para flujos de equipo** : hacer copias de los flujos, incluidos los flujos de equipo
* **Eliminar información de flujo** : al eliminar un flujo, se mostrará la lista de todas las ejecuciones pendientes para ese flujo.
* **Filtrado en la página conectores** : Busque los conectores que desee en la página conectores y filtre por tipo de conector.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) sobre esta versión.

### <a name="release-2017-06-19"></a>Versión 2017-06-19
Ahora puede ver el estado de todas las solicitudes de aprobación pendientes que ha enviado. Además, puede examinar y actuar en todas las aprobaciones pendientes directamente desde el dispositivo móvil.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sobre esta versión.

### <a name="release-2017-06-15"></a>Versión 2017-06-15
* **Conversión de contenido** : un nuevo conector que puede convertir contenido HTML en texto sin formato, útil para administrar correos electrónicos con formato HTML.
* **Tres nuevos conectores de base de datos** : se ha agregado compatibilidad con solo lectura para MySQL, PostgreSQL y Teradata. Estos conectores se conectan a través de la puerta de enlace de datos local.
* **Otros tres conectores** : Conéctese a aplicación de Azure Insights, Calendly y trabajo en equipo.
* **Mejor visualización para el control de errores** : los pasos que se ejecutan después de los errores se muestran ahora con flechas de punto rojo para que pueda identificarlos fácilmente.
* **Panel de detalles** de la ejecución: cuando se produce un error en un flujo, ahora hay un nuevo panel derecho que contiene algunos pasos útiles para corregir el flujo.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) sobre esta versión.

### <a name="release-2017-06-04"></a>Versión 2017-06-04
* **GA para Windows Phone** - [la aplicación móvil de Microsoft Flow se ha publicado para la disponibilidad general de Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Correos electrónicos sobre errores de flujo** : reciba una notificación por correo electrónico cuando se produzca un error en un flujo. Estos mensajes de correo electrónico de error solo se enviarán una vez a la semana, y el usuario podrá activarlo o desactivarlo.
* **Seleccionar acción para tablas** : Use la nueva acción seleccionar para cambiar el conjunto de columnas que se incluirán en las tablas.
* **Conector de Microsoft Forms** : Microsoft Forms es una nueva parte de Office 365 Education que permite a los profesores y estudiantes crear cuestionarios personalizados rápida y fácilmente, encuestas, cuestionarios, registros y mucho más.
* **Plan de office 365 Enterprise K1** : PowerApps y Microsoft Flow ahora se incluyen con el plan de Office 365 Enterprise K1 con ciertas cuotas.
* Los **encabezados HTTP son más sencillos** : al igual que la acción Select, puede proporcionar un nombre de encabezado y un valor de encabezado simplemente rellenando los cuadros de texto de la acción.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sobre esta versión.

### <a name="release-2017-05-23"></a>Versión 2017-05-23
* **Conector de Microsoft teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) es un área de trabajo basada en chat en Office 365 que reúne a personas, conversaciones y contenido, junto con las herramientas que necesitan los equipos, para que puedan colaborar fácilmente para lograr más.
* **Widgets en iOS y Android** : los widgets Microsoft Flow son accesos directos de botón que proporcionan una forma más fácil y rápida de desencadenar botones directamente desde la pantalla principal.
* **Crear pasos de "control de errores"** : defina uno o varios pasos para que se ejecuten después de que se produzca un error en una acción. Por ejemplo, reciba una notificación inmediatamente si el flujo no puede crear un registro en Dynamics 365.
* **Variables enteras y flotantes** : inicialice y aumente o reduzca los contadores dentro de una ejecución de flujo para contar el número de veces que se ejecuta un determinado conjunto de lógica.
* **Página de detalles de flujo** : al seleccionar un flujo en la lista **Mis flujos** , verá una página con detalles sobre el flujo, como quién tiene acceso y el historial de ejecución.
* **Cuotas de ejecución de flujo para administradores** : los administradores ahora pueden supervisar el uso de flujos en una organización contra la cuota de ejecución de la empresa común y obtener un desglose de la cuota para comprender qué licencias contribuyen a su cuota.
* **Mejoras en el desencadenador de solicitud HTTP** : usar diferentes métodos http y agregar segmentos de ruta de acceso para el desencadenador de solicitud.
* **Dos conectores de asociados** : Microsoft Flow ahora pueden conectarse al analizador, un servicio de análisis de correo electrónico y formularios de Cognito, un servicio de formularios en línea.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/error-handling/) sobre esta versión.

### <a name="release-2017-05-12"></a>Versión 2017-05-12
* **Integración de bibliotecas de documentos de SharePoint** : puede seleccionar cualquier archivo en una biblioteca de documentos y comenzar un flujo, por ejemplo, para enviarlo a su administrador para su aprobación, [y mucho más](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector de Microsoft Planner** : Microsoft Planner permite reunir fácilmente equipos, tareas, documentos y conversaciones para obtener mejores resultados.
* **Vista de administración de licencias** : los administradores pueden ver todas las licencias de Microsoft Flow y PowerApps (de prueba y de pago) en el centro de administración de Microsoft Flow.
* **Plan** de la comunidad de powerapps: el plan de la comunidad de powerapps es un plan gratuito que permite a los usuarios explorar, aprender y desarrollar habilidades para PowerApps, Microsoft Flow y Common Data Service.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) sobre esta versión.

### <a name="release-2017-05-09"></a>Versión 2017-05-09
* **Conector de Azure ad** : hay un nuevo conector para realizar acciones de administrador desde Microsoft Flow, incluida la creación de usuarios o su adición a grupos.
* **Mejoras de Office 365 Outlook** : los flujos se pueden desencadenar ahora mediante buzones compartidos y enviar correo a un buzón compartido. También pueden establecer o leer las respuestas automáticas.
* **Disponible en Canadá** : ahora puede crear flujos en Canadá.
* **Creación de webhooks de API personalizados** : ahora, los desarrolladores de conectores personalizados pueden agregar desencadenadores a sus API personalizadas con webhooks.
* **Administrar propietarios de flujos en el centro de administración** : los administradores del entorno pueden administrar los propietarios del flujo en el centro de administración de Microsoft Flow.
* **Referencia de documentación del conector** : ahora tenemos una [referencia de conector completa en docs.Microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dos servicios de asociados** : se lanzaron dos nuevos servicios de asociados: Nexmo y Paylocity.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) sobre esta versión.

### <a name="release-2017-04-27"></a>Versión 2017-04-27
* **Flujos de compilación con pasos paralelos** : crear flujos con ejecución en paralelo: es decir, puede tener dos o más pasos que se ejecuten exactamente al mismo tiempo.
* **Cinco nuevos servicios compatibles** : cinco nuevos servicios: aprobaciones, correo electrónico de prueba comparativa, CRM de cápsula, LiveChat y administrador de clientes de Outlook.
* **Supervisar reintentos para acciones** : Microsoft Flow volverá a intentarlo cuando haya errores con los servicios. Ahora vea cuántos reintentos automáticos se han producido y los detalles de lo que ha sucedido.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/parallel-actions/) sobre esta versión.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versión 2017-04-17: actualización del primer trimestre para Microsoft Flow
* **Experiencias de aprobación modernas** : cree flujos de trabajo donde los aprobadores puedan aprobar de forma segura desde dentro de la aplicación móvil de Microsoft Flow o el centro de aprobaciones unificadas en el sitio web de Microsoft Flow.
* **Disponibilidad general de flujos de equipo** : varias personas pueden poseer y administrar un flujo junto con los flujos de equipo, que ya están disponibles con carácter general.
* **Cree conectores para Microsoft Flow** : cualquiera puede enviar su propio conector de Microsoft Flow de forma gratuita para que lo use el resto del mundo.
* **Un diseñador "dieta"** : para determinadas plantillas, una nueva versión del diseñador solo presenta los campos necesarios para crear un flujo, lo que simplifica la experiencia.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/q1-2017-update/) sobre esta versión.

### <a name="release-2017-04-11"></a>Versión 2017-04-11
* **Nuevas acciones para compilar tablas y listas** : nueva crear tabla HTML, crear tabla csv y acciones de combinación que pueden procesar listas de elementos (en lugar de la anterior aplicación de solo aplicar a cada uno).
* **Insertar pasos en cualquier lugar** : ahora puede insertar un nuevo paso en cualquier lugar del flujo de trabajo sin necesidad de arrastrar y colocar.
* **Cuatro nuevos servicios** : Flow ahora admite la programación de 10 a 8, Act!, Inoreader y el Computer Vision API. Con el Computer Vision API puede procesar imágenes para obtener el contenido de texto (conocido como OCR) o etiquetar imágenes automáticamente en función de su contenido.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sobre esta versión.

### <a name="release-2017-04-03"></a>Versión 2017-04-03
* **Windows Phone beta** : el programa de la versión beta de la aplicación Windows Phone está disponible para obtener una vista previa de la aplicación en el Windows Phone. [Lea más](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **MUHIMBI PDF** : ahora puede convertir archivos de Microsoft Word en PDF, agregar marcas de agua, combinar documentos y mucho más con Muhimbi PDF. [Lea más](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Desencadenar flujos desde botones físicos** : anuncio de asociaciones con dos de los productos líderes en el espacio físico del botón: Flic by Shortcut Labs y BTTN by the Button Corporation. [Más información](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versión 2017-03-22
* **Realice una copia de su flujo** : ahora puede hacer una copia del flujo para trabajar en versiones de borrador o duplicar un flujo que haya creado en el pasado.
* **Dos nuevos servicios** : incorporación de compatibilidad con Toodledo: administre la lista de tareas pendientes mediante la creación y actualización de tareas, y zendesk, que proporciona un servicio de atención al cliente y una plataforma de vales de soporte técnico.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/make-a-copy/) sobre esta versión.

### <a name="release-2017-03-15"></a>Versión 2017-03-15
* **Compartir botones con compañeros de trabajo** : ahora puede compartir botones de flujo con otras personas, lo que facilita a los usuarios empresariales la realización de tareas rápidas.
* **Desencadenar botones desde la pantalla principal** : los accesos directos a los botones de flujo de las pantallas Inicio y de bloqueo de los dispositivos móviles hacen que sea más rápido que nunca desencadenar un flujo.
* **Flujos de equipo en la aplicación Microsoft Flow** : ahora puede ver los flujos que tienen otros propietarios en la aplicación Microsoft Flow para iOS o Android.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/button-sharing/) sobre esta versión.

### <a name="release-2017-03-10"></a>Versión 2017-03-10
* **Experiencia mejorada del conector personalizado** : ahora puede usar una colección Postman para crear un conector personalizado y editar, agregar y probar acciones.
* **Dos nuevos servicios** : se han agregado notificaciones de PowerApps y compatibilidad con PivotalTracker.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) sobre esta versión.

### <a name="release-2017-02-27"></a>Versión 2017-02-27
* **Desencadenar los botones de flujo** : ahora puede desencadenar botones de flujo directamente desde Microsoft Flow. Cuando examine la lista de flujos, simplemente seleccione el "..." y elija el comando ejecutar ahora.
* **Cinco nuevos servicios** : se ha agregado la compatibilidad con Oracle Database, Intercom, FreshBooks, LeanKit y webmerge.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sobre esta versión.

### <a name="release-2017-02-21"></a>Versión 2017-02-21
* **Ver flujos de entorno** : los administradores de entorno ahora pueden ver la lista completa de todos los flujos dentro de un entorno determinado, así como habilitar, deshabilitar o eliminar flujos.
* **Dos nuevos servicios** : se ha agregado Azure Automation y compatibilidad con Basecamp 2.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versión.

### <a name="release-2017-02-16"></a>Versión 2017-02-16
* **Cinco nuevos servicios** : se ha agregado compatibilidad con Azure Data Lake, Bitbucket (un servicio de hospedaje basado en web para los proyectos que usan el control de revisiones de Git), eventbrite, InfusionSoft y Pipedrive.
* **Autenticación http personalizada** : en el diseñador de flujos ahora es posible usar la autenticación con puntos de conexión HTTP personalizados.
* **Analizar mensajes JSON** : puede analizar datos JSON desde el desencadenador de solicitud HTTP o que se devuelven desde la acción http.
* **Filtrado de ejecución de flujo** : filtrado mejorado para ejecuciones de flujo, con opciones más específicas, como ver flujos en ejecución o ejecuciones canceladas.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versión.

### <a name="release-2017-02-06"></a>Versión 2017-02-06
* **Flujos de equipo** : los flujos de equipo permiten a varias personas poseer y administrar un flujo juntos y, si alguien deja una organización, los flujos creados pueden continuar ejecutándose.
* **Uso compartido de conectores personalizados** : los conectores personalizados, como los flujos de equipo, se pueden compartir y administrar colectivamente dentro de una organización.
* **Compatibilidad con gmail y Luis** : Conéctese a gmail y a Azure Cognitive Services "Language Understanding Intelligent Service.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/team-flows/) sobre esta versión.

### <a name="release-2017-01-30"></a>Versión 2017-01-30
* **Entradas del botón de flujo** : los botones de flujo ahora pueden recibir entradas de usuario en tiempo de ejecución, por lo que los autores de flujo pueden definir la información que se pasa al puntear en el botón.
* **Tareas de Outlook y HelloSign** : el servicio tareas de Outlook le permite administrar tareas y HelloSign habilita firmas electrónicas seguras.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/button-user-inputs/) sobre esta versión.

### <a name="release-2017-01-23"></a>Versión 2017-01-23
* **Buscar por servicio** : Explore por servicio cuando agregue un desencadenador o una acción para ver todas las acciones de cada servicio.
* **Cambiar mayúsculas y minúsculas** : agregue bloques switch para tener varias ramas de lógica paralela.
* **Más acciones de correo electrónico** : nueva funcionalidad de Office 365 Outlook y Outlook.com Services para trabajar con mensajes marcados.
* **Cinco nuevos servicios** : Conéctese a sistemas de archivos locales o de red, la franja de servicio de pago, IBM Informix, IBM DB2 y UserVoice.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/search-by-service/) sobre esta versión.

### <a name="release-2017-01-14"></a>Versión 2017-01-14
* Volver a **Enviar ejecuciones** : si se produce un error en un flujo y desea intentar corregirlo y ejecutarlo de nuevo, puede volver a enviar la ejecución con errores.
* **Cancelar ejecuciones** : cuando se bloquea un flujo, ahora puede cancelar explícitamente la ejecución.
* **Dos nuevos servicios** : se ha agregado compatibilidad con GoToTraining y GoToWebinar.
* **Vínculos móviles** : puede compartir plantillas directamente desde la aplicación móvil y se ha agregado un vínculo de descarga rápida para las aplicaciones en la parte superior del sitio Web.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/managing-runs/) sobre esta versión.

### <a name="release-2016-12-29"></a>Versión 2016-12-29
Microsoft Flow ahora admite DocuSign, para controlar la administración de firmas electrónicas y transacciones digitales; SurveyMonkey, para encuestas basadas en Web; y la aplicación de toma de notas de OneNote (solo cuentas empresariales).

[Lea más y formule preguntas](https://flow.microsoft.com/blog/final-2016-services/) sobre esta versión.

### <a name="release-2016-12-20"></a>Versión 2016-12-20
* **Ejecutar ahora** : ahora puede activar un desencadenador recurrente a petición; por ejemplo, si tiene un informe programado cada día, pero necesita que el informe se ejecute **ahora** también.
* **Seis nuevos servicios** : cree flujos que se conecten a MSN Weather, Medium, Google contacts, buffer, Harvest y TypeForm.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sobre esta versión.

### <a name="release-2016-12-14"></a>Versión 2016-12-14
Ahora puede aprovechar información valiosa al desencadenar un flujo de botones, como desde dónde se desencadenó el botón, quién, en qué momento, etc.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) sobre esta versión.

### <a name="release-2016-12-06"></a>Versión 2016-12-06
* **Introducción a aprendizaje guiado** : Introducción a una colección secuenciada de cursos que emparejan vídeos con documentación para ayudarle a comprender las amplias y eficaces capacidades de Microsoft Flow.
* **Dos nuevos servicios** : los flujos ahora pueden usar Freshdesk, una solución de soporte al cliente y gotomeeting, una herramienta de reunión en línea.
* **Compatibilidad con webhook de http** : un flujo ahora puede ser un punto de conexión para los webhooks que se registrarán y anularán el registro automáticamente.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sobre esta versión.

### <a name="release-2016-11-23"></a>Versión 2016-11-23
* **Power BI la compatibilidad de alertas en el flujo** : Desactive los flujos de Power BI alertas de datos.
* **Mejoras en las aplicaciones móviles** : se ha agregado la capacidad de crear flujos desde cero, además de la experiencia ya existente de creación a partir de plantillas. También se ha mejorado el rendimiento al ver las ejecuciones de flujo.
* **Ocho nuevos servicios** : ahora puede conectarse a Azure Resource Manager, colas de Azure, chatter, Disqus, Azure Cosmos DB, Cognitive Services Face API, HipChat y WordPress.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sobre esta versión.

### <a name="release-2016-11-15"></a>Versión 2016-11-15
* **Microsoft Flow programa de asociados** : Microsoft Flow tiene ahora un programa de asociados certificado para realizar conexiones y aprovechar las ventajas de la experiencia y el talento de la empresa con Microsoft Flow en todo el mundo.
* **Seis nuevos servicios** : también lanzamos seis servicios esta semana: asana, Campfire, EASYREDMINE, Jira, Redmine y Vimeo.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) sobre esta versión.

### <a name="release-2016-10-31---general-availability"></a>Versión 2016-10-31: disponibilidad general
* **Precios y licencias** : ahora disponible en los planes gratis y de pago, además de los incluidos en Office 365 y Dynamics 365.
* **Centro de administración de Microsoft Flow** : listo para la empresa con el nuevo centro de administración. En el centro de administración puede administrar los entornos dentro de la organización.
* **Directivas de prevención de pérdida de datos** : los administradores pueden crear directivas de prevención de pérdida de datos para controlar el flujo de datos entre los servicios.
* **Disponibilidad de Android** : la aplicación de Microsoft Flow Phone ya está disponible para iOS y Android. La aplicación permite obtener notificaciones, supervisar la actividad e iniciar flujos con la pulsación de un botón.
* **Nuevas experiencias del diseñador** : ahora puede buscar en el contenido dinámico que se pasa del paso a paso, lo que hace que sea mucho más rápido hacer referencia a los datos que desea.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/announcing-ga/) sobre esta versión.

### <a name="release-2016-10-26"></a>Versión 2016-10-26
* **Flujos de botón** : hay innumerables operaciones que queremos que podamos desencadenar en cualquier momento y en cualquier lugar. Ahora, con los flujos de botón, puede hacer que se realicen en un solo clic de un botón, desde su dispositivo móvil.
* **Presentación de entornos** : los entornos son espacios distintos para almacenar y administrar los flujos de la organización. Los entornos están ubicados geográficamente, lo que significa que los flujos, las aplicaciones y los datos empresariales que residen dentro de un entorno estarán en la región donde se encuentra el entorno.
* **Seis nuevos servicios** : incorporación de compatibilidad con Bit.ly, Cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 para finanzas, Instapaper y Pinterest.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/environments-for-makers/) sobre esta versión.

### <a name="release-2016-10-16"></a>Versión 2016-10-16
* Los **conectores personalizados admiten más tipos de autenticación** : los conectores personalizados ahora admiten la autenticación de clave de API y pueden autenticarse en cualquier servicio que admita la especificación OAuth 2,0 completa.
* **Tres nuevos servicios compatibles** : hemos agregado compatibilidad con Basecamp 3, blogger y PagerDuty.
* **Mejoras** en el diseñador: rendimiento mejorado; ahora puede actualizar y reparar las conexiones directamente desde el "..." en cada acción y se ha agregado un nuevo paso llamado finalizar que puede usar para finalizar la ejecución de un flujo.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/early-october-updates/) sobre esta versión.

### <a name="release-2016-09-25"></a>Versión 2016-09-25
La creación del flujo ahora está disponible desde los teléfonos móviles. Examine nuestra amplia galería de plantillas, navegue por nuestra lista de servicios o seleccione una categoría de plantilla para profundizar. [Lea más y formule preguntas](https://flow.microsoft.com/blog/mobile-creation/) sobre esta versión.

### <a name="release-2016-09-22"></a>Versión 2016-09-22
* **Microsoft Graph selector de personas** : un nuevo selector de personas Microsoft Graph está integrado directamente en la interfaz de usuario de Microsoft Flow para ayudarle a elegir el contacto o la dirección de correo electrónico adecuados.
* **Compatibilidad con Microsoft Dynamics AX** : desde dentro de sus flujos, ahora puede realizar acciones en los datos de operaciones de Dynamics AX online, desde la creación de nuevos registros hasta la consulta de datos.
* **Dos nuevos servicios de asociados** : ahora usan appFigures o insightly desde los flujos.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/more-september-updates/) sobre esta versión.

### <a name="release-2016-09-14"></a>Versión 2016-09-14
* **Inserción en su sitio web o aplicación** : los desarrolladores ahora pueden insertar Microsoft Flow directamente en sus aplicaciones o sitios web para ofrecer a sus usuarios una forma sencilla de automatizar sus tareas profesionales o personales.
* **Usar un flujo como un punto de conexión http** : ahora puede usar un flujo como una API http. Hay un desencadenador denominado solicitud dentro de Flow y puede elegir responder a la solicitud entrante agregando una tarjeta de respuesta.
* **Compatibilidad con todo** el personal de TI proporciona perspectiva sobre todos los proyectos, en el trabajo y en casa.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/extend-web-site-application/) sobre esta versión.

### <a name="release-2016-09-01"></a>Versión 2016-09-01
Microsoft Flow ahora está disponible para todos los usuarios. inicialmente, abrimos la vista previa solo para las direcciones de correo electrónico proporcionadas por su trabajo o escuela, como las que se usan con Office 365 Business u Office 365 Enterprise. En la actualidad, anunciamos que la vista previa está oficialmente disponible, gratuita, para todos los usuarios, independientemente del correo electrónico que tenga. [Lea más y formule preguntas](https://flow.microsoft.com/blog/available-for-everyone/) sobre esta versión.

### <a name="release-2016-08-31"></a>Versión 2016-08-31
* Instrucciones **condicionales anidadas** : ahora puede Agregar una segunda condición (o tercera, etc.) dentro de otra.
* **Aplicar a cada** : un bucle Apply to Each permite controlar la lista que se repite.
* El bucle do- **Until-Until** permite repetir un paso hasta que se cumpla una determinada condición.
* **Filtrar matrices** : hay un solo paso de filtro nativo que puede asegurarse de que todos los elementos de la lista coincidan con alguna expresión que defina.
* **Variables de cadena de redacción** : ahora puede crear una variable de cadena.
* **Ámbitos** : los ámbitos son una manera sencilla de agrupar dos o más acciones.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/build-advanced-flows/) sobre esta versión.

### <a name="release-2016-08-27"></a>Versión 2016-08-27
* **Comentarios en los pasos: los** comentarios facilitan la anotación de cada acción individual con notas para que pueda recordar fácilmente lo que necesita el flujo.
* **Compatibilidad con Smartsheet** : esta semana hemos agregado compatibilidad para conectarse a Smartsheet. Smartsheet es un servicio que facilita la colaboración en hojas en la nube.
* **Refinación de la interfaz de usuario al crear flujos** : hemos convertido el nombre del flujo en el centro y el botón Guardar en la parte superior de la página para facilitar el acceso.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) sobre esta versión.

### <a name="release-2016-08-18"></a>Versión 2016-08-18
Ahora puede obtener una vista previa de la nueva experiencia de listas modernas de SharePoint Online que incluye la integración de Microsoft Flow. [Lea más y formule preguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sobre esta versión.

### <a name="release-2016-08-13"></a>Versión 2016-08-13
* **Visual Studio Team Services** : con Flow, ahora puede conectar VSTS a una amplia variedad de servicios, como correo electrónico de O365, demora, Trello y Wunderlist.
* **Mejoras en SharePoint** : las listas de SharePoint admiten una variedad de tipos de datos de objetos simples como líneas individuales de texto y fecha y hora hasta objetos complejos como persona o grupo, búsqueda y elección.
* **Probar las conexiones de Outlook de o365** : cada vez que cree una nueva conexión de Office o365, la probaremos para asegurarse de que está lista para su uso.
* **Control booleano** : también hemos agregado un control booleano para aclarar qué valores debe especificar para los campos de entrada booleanos, como tiene datos adjuntos en el desencadenador cuando llega un nuevo correo electrónico.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sobre esta versión.

### <a name="release-2016-08-08"></a>Versión 2016-08-08
Versión preliminar pública de Microsoft Common Data Service integrado en Microsoft Flow. [Lea más y formule preguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) sobre esta versión.

### <a name="release-2016-08-05"></a>Versión 2016-08-05
* **SharePoint local** : al igual que con SharePoint Online, puede crear flujos en torno a las listas locales de SharePoint y a las bibliotecas de documentos mediante plantillas predefinidas o compilarlas desde cero.
* **Info-Bubbles en el diseñador** : para elaborar las capacidades de cada desencadenador y acción, se han agregado las burbujas de información sobre cada paso del flujo.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sobre esta versión.

### <a name="release-2016-07-15"></a>Versión 2016-07-15
* Se **agregaron cuatro nuevos servicios** : Conéctese a Google Calendar, Google Tasks, YouTube y SparkPost.
* **Cambiar el nombre** de las acciones: ahora, puede hacer que estas distintas acciones se separan si cambia su nombre.
* **Retraso en distintos períodos de tiempo** : ahora puede seleccionar cualquier número de segundos, minutos, horas o días.
* **Explorador de carpetas más fácil de usar** : se ha simplificado el explorador de carpetas. ahora, al seleccionar a la izquierda, se seleccionará esa carpeta y, si se selecciona a la derecha, se abrirá la carpeta para que pueda elegir las subcarpetas dentro de.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) sobre esta versión.

### <a name="release-2016-07-08"></a>Versión 2016-07-08
Conectividad local para Microsoft Flow mediante la puerta de enlace de datos local. Esto le permite establecer conexiones seguras a SQL Server e integrarlas con los flujos. [Lea más y formule preguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) sobre esta versión.

### <a name="release-2016-07-02"></a>Versión 2016-07-02
* **Compatibilidad con hojas** de cálculo de Google: en el pasado, hemos tenido la capacidad de usar Excel, así como Google Drive, pero esta semana estamos agregando compatibilidad nativa con hojas de Google.
* Comience a **trabajar más rápidamente desde plantillas** : también hemos realizado algunas optimizaciones para que pueda empezar a partir de plantillas. Ahora, puede seleccionar qué cuentas desea usar para una plantilla alineada a la derecha en la página de la plantilla.
* **Sin autorización de expiración para SharePoint y Office 365** : ahora, Microsoft Flow renovará automáticamente el acceso a los servicios basados en Azure Active Directory, de modo que todos los flujos seguirán funcionando a través de los cambios de contraseña.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/more-june-updates/) sobre esta versión.

### <a name="release-2016-06-20"></a>Versión 2016-06-20
* **Introducción a la nueva aplicación móvil para Microsoft Flow** -hoy, nos complace presentar otra parte importante de nuestra oferta: ahora hay una aplicación móvil disponible para su descarga en iOS (pronto en Android) que le ofrece la posibilidad de administrar, hacer un seguimiento y explorar su flujos de trabajo automatizados en cualquier momento y lugar.  
* **Inicio de sesión único** : hemos implementado el inicio de sesión único que le permite autenticarse en Microsoft Flow con otros servicios de Microsoft como Office 365.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sobre esta versión.

### <a name="release-2016-06-18"></a>Versión 2016-06-18
* **Nuevo servicio de correo** : ahora puede enviar correos electrónicos directamente desde Microsoft Flow, sin necesidad de conectarse a sus cuentas de correo electrónico personales o de trabajo dentro de Microsoft Flow.
* **Notificaciones en el portal** : ahora verá las notificaciones en la parte superior del portal siempre que algo se interrumpa con los flujos.
* **Toda la actividad en el portal** : ahora puede ver la actividad en todos los flujos haciendo clic en la nueva pestaña actividad en el sitio web de Flow.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) sobre esta versión.

### <a name="release-2016-05-27"></a>Versión 2016-05-27
* **Examinar plantillas por servicio** : ahora hay una forma de ver todos los servicios que se admiten (sin tener que iniciar sesión). Desde esta página puede ver una descripción de cada uno de los servicios y consultar las plantillas que tenemos para ese servicio.
* **Crear y usar conectores personalizados** : al igual que puede crear conectores personalizados en PowerApps, también puede conectarse a sus propias API directamente en Flow.Microsoft.com:
* **Prueba de los flujos antes de su finalización** : cada vez que se guarda un flujo, ahora se pueden ver los resultados de la ejecución del flujo activo en la página, si se realiza la acción de inicio.

[Lea más y formule preguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sobre esta versión.

### <a name="release-2016-05-07"></a>Versión 2016-05-07
Se han agregado dos nuevos servicios: Microsoft Project online y Mailchimp. [Lea más y formule preguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sobre esta versión.

### <a name="release-2016-04-27---public-preview"></a>Versión 2016-04-27: vista previa pública
Si ha usado flujos de lógica como parte de [Microsoft PowerApps](https://powerapps.microsoft.com), la versión de vista previa de Microsoft Flow ofrece varias características nuevas:

* Ahora puede examinar una galería de docenas de plantillas y ordenar por popularidad, nombre o fecha de publicación.
* Puede [publicar sus propias plantillas](publish-a-template.md) en la Galería después de personalizar un flujo.
* Puede ver el historial de todas las comprobaciones y ejecuciones del flujo.
* Al guardar un flujo, puede [verlo de forma inmediata](see-a-flow-run.md) simplemente realizando la acción del desencadenador.
* Tenemos una [nueva comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) para que pueda discutir sobre el flujo o [enviar sus ideas](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Pasos siguientes
Si tiene algún problema que no se haya tratado en estas notas de la versión o en las [preguntas más frecuentes](frequently-asked-questions.md), [Únase a nuestra comunidad](https://go.microsoft.com/fwlink/?LinkID=787467) para hacer preguntas o [ponerse en contacto con el soporte técnico](https://go.microsoft.com/fwlink/?LinkID=787479).

