---
title: "Notas de la versión | Microsoft Docs"
description: Problemas comunes y novedades de las versiones de Microsoft Flow
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2017
ms.author: stepsic
ms.openlocfilehash: 37bab7ccd54ecc7976a42df2e215daa19916fc85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2017
---
# <a name="release-notes"></a>Notas de la versión
## <a name="top-questions"></a>Preguntas importantes
1. Error en el flujo. ¿Cómo puedo corregirlo?
   
   1. Identifique el error Empiece por ir al icono de notificaciones en la parte superior del portal web o seleccione la pestaña **Actividad** en la aplicación móvil. Aquí debería aparecer el flujo para que pueda seleccionarlo.
   2. Ahora puede ver los detalles del flujo. Busque el paso con el icono de exclamación rojo, donde debería ver el mensaje de error del flujo.
   3. Según el mensaje de error, debe poder **editar** el flujo y corregirlo. [Más información acerca de cómo solucionar errores comunes de flujo](fix-flow-failures.md).
2. ¿Cómo se puede usar una condición o fórmula avanzada?
   
   * Obtenga más información sobre la [incorporación de condiciones](add-a-condition.md).
   * Si desea que haya varios casos en un flujo, haga clic o pulse en **Agregar condición** desde dentro de una condición ya existente.
   * Cree una fórmula avanzada mediante la referencia a [una función de Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. ¿Cómo funciona la concesión de licencias con Office 365?
   
   * Los usuarios de Office 365 obtienen acceso completo a través del plan de Microsoft Flow para Office 365. Para más información, consulte el [plan de precios de Microsoft Flow](https://flow.microsoft.com/pricing/).
   * Si es administrador, consulte la información sobre [licencias de Microsoft Flow](organization-q-and-a.md), incluida con Office 365.

## <a name="known-issues-and-resolutions"></a>Problemas conocidos y soluciones
1. No se admiten listas de SharePoint en Mis sitios que no sean del tipo *Lista personalizada*. Para solucionar este problema, cree una lista personalizada en un sitio de SharePoint estándar.
2. Los desencadenadores no devuelven metadatos de documento de las bibliotecas de documentos de SharePoint.
3. Los flujos no pueden escribir en los campos de taxonomía de las listas de SharePoint. Se recomienda usar un campo de cadena simple hasta que se corrija este problema.
4. Los desencadenadores de archivo no se activarán para los archivos que se agreguen dentro de carpetas anidadas dentro de la carpeta que seleccione.

## <a name="whats-new"></a>Novedades
### <a name="release-2017-08-25"></a>Versión 2017-08-25
* **Propiedades de documentos y otras cuestiones relativas a SharePoint** - [lea y establezca las propiedades de la biblioteca de documentos de SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)y use campos adicionales, como vínculos, en el elemento de SharePoint.
* **Colecciones de Flow**: las colecciones de Flow son un conjunto de colecciones de plantillas organizado por rol o por vertical.
* **Volver a compartir botones**: si comparte botones con sus compañeros de trabajo, estos también pueden volver a compartirlos con otras personas.
* **Recopilar listas de botones**: defina las listas desplegables de opciones que pueden elegir los usuarios al pulsar el botón.
* **Siete conectores nuevos**: AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs y StaffHub. 
* **Mejoras en Slack y MySQL**: cree o combine de canales en Slack y puede escribir en bases de datos MySQL.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) acerca de esta versión.

### <a name="release-2017-08-02"></a>Versión 2017-08-02
* **Campos Write to Person, Choice and Lookup** (Escribir a persona, Opción y Búsqueda): las acciones Crear elemento y Actualizar elemento de SharePoint [ahora admiten la capacidad de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) configurar los campos Persona, Elección y Búsqueda.
* **Mayor configuración de las acciones**: ahora hay más control sobre la ejecución de desencadenadores y acciones, lo que incluye la configuración de las directivas de reintento y de la paginación.
* **Cuatro nuevos conectores**: ahora se pueden usar Azure File Storage, Elastic Forms, Plivo y Video Indexer.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) acerca de esta versión.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versión de 2017-07-27: actualización del segundo trimestre de Microsoft Flow
* **Importar y exportar**: importe y exporte soluciones de flujo entre entornos o de la fase de prueba a la de producción. 
* **Usar expresiones en acciones**: escriba expresiones en cualquier acción y obtenga ayuda en línea sobre cómo utilizarlas.
* **Crecer hasta Azure Logic Apps**: guarde los flujos como un recurso de Azure Logic Apps que se pueda implementar a través de Visual Studio o de Azure Portal.
* **Visibilidad de la administración**: Descargue el uso de Microsoft Flow en su inquilino para saber exactamente dónde y cómo se usan los flujos.
* **Flujos en Dynamics 365**: use flujos en de Dynamics 365 for Operations & Financials, Business Edition.
* **Buscar escenarios más fácilmente**: examine todo lo que el conector pueda hacer y, después, utilice cualquier desencadenador como punto de partida para generar flujos.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/q2-2017-update/) acerca de esta versión.

### <a name="release-2017-07-13"></a>Versión 2017-07-13
* **Mejora en la publicación de plantillas**: cualquier flujo que cree, junto con sus categorías, se puede publicar en la galería pública.
* **Obtener los eventos de Outlook Calendar**: una nueva acción que devuelve todos los eventos entre dos horas del calendario.
* **Nueva funcionalidad para dispositivos móviles**: ejecute flujos a petición y vuelva a enviar las ejecuciones con errores en la aplicación móvil.
* **Listas desplegables dinámicas en conectores personalizados**: cree listas desplegables dinámicas y desencadenadores de sondeo, y probar sus conectores personalizados.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) acerca de esta versión.

### <a name="release-2017-06-28"></a>Versión 2017-06-28
* **Actualización de la configuración de idioma**: puede personalizar el idioma y la región que usa Microsoft Flow en el menú de configuración.
* **Cinco nuevos conectores**: compatibilidad agregada con Adobe Creative Cloud, Bing Maps, Bing Search, JotForm y Freshservice.
* **Configuración de los tiempos de espera**: cambie las acciones de larga duración, como aprobaciones, ejecútelas antes de que se agote el "tiempo de espera" y el flujo continuará.
* **Incluir comentarios en Outlook en las aprobaciones**: cuando reciba una solicitud de aprobación, puede incluir comentarios sin salir de Outlook.
* **Identidad cromática para conectores personalizados**: ahora puede especificar un color para los conectores personalizados que se usará para los fondos.
* **Opción Guardar como para los flujos de equipo**: haga copias de los flujos, incluidos los flujos de equipo
* **Eliminación de la información de flujo**: al eliminar un flujo, se le mostrará la lista de todas las ejecuciones pendientes de dicho flujo.
* **Filtrado en la página de conectores**: busque los conectores que desee en la página de conectores y filtre por tipo de conector.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) acerca de esta versión.

### <a name="release-2017-06-19"></a>Versión 2017-06-19
Ahora puede ver el estado de todas las solicitudes de aprobación pendientes que ha enviado. Además, puede examinar y actuar directamente en todas las aprobaciones pendientes desde el dispositivo móvil.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) acerca de esta versión.

### <a name="release-2017-06-15"></a>Versión 2017-06-15
* **Conversión de contenido**: un nuevo conector que puede convertir contenido HTML en texto sin formato, útil para manejar correos electrónicos con formato HTML.
* **Tres nuevos conectores de base de datos**: agregue compatibilidad de solo lectura para MySQL, PostgreSQL y Teradata. Estos conectores se conectan a través de la puerta de enlace de datos local.
* **Otros tres conectores**: conéctese a Azure Application Insights, Calendly y Teamwork Projects.
* **Mejor visualización del control de errores**: los pasos que se ejecutan después de los errores se muestran ahora con flechas con puntos rojos para que pueda identificarlos fácilmente.
* **Ejecución del panel de detalles**: cuando se produce un error en un flujo, ahora hay un nuevo panel derecho que contiene algunos pasos útiles para saber cómo corregir el flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) acerca de esta versión.

### <a name="release-2017-06-04"></a>Versión 2017-06-04
* **Disponibilidad general para Windows Phone** - [La aplicación móvil de Microsoft Flow es ahora de disponibilidad general para Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Correos electrónicos al producirse errores de flujo**: reciba las notificaciones por correo electrónico si se produce un error en algún flujo. Estos mensajes de error se enviarán solo una vez por semana y el usuario puede activarlos o desactivarlos.
* **Acción de selección para tablas**: use la nueva acción de selección para cambiar el conjunto de columnas que se incluirán en las tablas.
* **Conector de Microsoft Forms**: Microsoft Forms es un nuevo elemento de Office 365 Educación que permite a los profesores y alumnos crear cuestionarios personalizados de forma rápida y sencilla, así como encuestas, registros y mucho más.
* **Plan de Office 365 Enterprise K1**: PowerApps y Microsoft Flow ahora se incluyen con el plan de Office 365 Enterprise K1 con ciertas cuotas.
* **Encabezados HTTP más sencillos**: al igual que la acción de selección, puede especificar un nombre y un valor de encabezado rellenando simplemente los cuadros de texto en la acción.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) acerca de esta versión.

### <a name="release-2017-05-23"></a>Versión 2017-05-23
* **Conector de Microsoft Teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) es un área de trabajo de Office 365 basado en chat que reúne a personas, conversaciones y contenido, junto con las herramientas que necesitan los equipos, para que puedan colaborar fácilmente para lograr objetivos superiores.
* **Widgets en iOS y Android**: los widgets de Microsoft Flow son accesos directos de botón que proporcionan una manera más rápida y sencilla de desencadenar los botones desde la pantalla principal.
* **Crear pasos de "control de errores"**: defina los pasos que se van a ejecutar después de que se produzca un error en una acción. Por ejemplo, obtener inmediatamente una notificación si un flujo no crea un registro en Dynamics 365.
* **Variables enteras y flotantes**: inicialice los contadores e increméntelos o redúzcalos en una ejecución de flujo para contar el número de veces que se ejecuta un conjunto de lógica determinado.
* **Página de detalles de flujo**: al seleccionar un flujo en la lista **Mis flujos**, verá una página con detalles de dicho flujo, como quién tiene acceso y el historial de ejecución.
* **Cuotas de ejecución de flujo para administradores**: ahora, los administradores pueden supervisar el uso de las ejecuciones de flujos en una organización con respecto a la cuota habitual de ejecuciones de una empresa y obtener un desglose de la cuota para saber qué licencias contribuyen a ella.
* **Mejoras en el desencadenador de solicitud HTTP**: use distintos métodos de HTTP y agregue segmentos de ruta al desencadenador de solicitud.
* **Dos conectores asociados**: ahora, Microsoft Flow puede conectarse a Parserr, un servicio de análisis de correo electrónico, y Cognito Forms, un servicio de formularios en línea.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/error-handling/) acerca de esta versión.

### <a name="release-2017-05-12"></a>Versión 2017-05-12
* **Integración con bibliotecas de documentos de SharePoint**: puede seleccionar cualquier archivo en una biblioteca de documentos y comenzar un flujo, por ejemplo, para enviarlo a su administrador para su aprobación, [y mucho más](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector de Microsoft Planner**: Microsoft Planner le permite reunir fácilmente los equipos, las tareas, los documentos y las conversaciones para obtener unos mejores resultados.
* **Vista de administración de licencias**: los administradores pueden ver todas las licencias de Microsoft Flow y PowerApps (tanto de la versión de evaluación como de la de pago) en el Centro de administración de Microsoft Flow.
* **Plan de la Comunidad de PowerApps**: el plan de la Comunidad de PowerApps es un plan gratis para que usuarios puedan explorar, aprender y desarrollar habilidades para PowerApps, Microsoft Flow y Common Data Service.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) acerca de esta versión.

### <a name="release-2017-05-09"></a>Versión 2017-05-09
* **Conector de Azure AD**: hay un nuevo conector para llevar a cabo acciones de administrador desde Microsoft Flow, incluida la creación de usuarios o su incorporación a grupos.
* **Mejoras de Office 365 Outlook**: los flujos se pueden desencadenar ya con los buzones de correo compartidos y el envío de un correo electrónico a un buzón compartido. También pueden establecer o leer las respuestas automáticas.
* **Disponible en Canadá**: ya puede crear los flujos en Canadá.
* **Creación de API y webhooks personalizados**: los desarrolladores de conectores personalizados pueden agregar desencadenadores a sus API personalizadas con webhooks.
* **Administración de los propietarios del flujo en el centro de administración**: los administradores de entornos pueden administrar propietarios de flujos en el centro de administración de Microsoft Flow.
* **Referencia a documentación sobre conectores**: ahora ya disponemos de una [completa referencia sobre conectores en docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dos servicios de asociados**: se publicaron dos nuevos servicios de asociados: Nexmo y Paylocity.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) acerca de esta versión.

### <a name="release-2017-04-27"></a>Versión 2017-04-27
* **Creación de flujos con pasos paralelos**: cree flujos con la ejecución en paralelo, lo que significa que dos o más pasos se pueden ejecutar al mismo tiempo.
* **Cinco nuevos servicios admitidos**: Approvals, Benchmark Email, Capsule CRM, LiveChat y Outlook Customer Manager.
* **Supervisión de reintentos para acciones**: Microsoft Flow volverá a realizar un reintento cuando haya errores con los servicios. Ahora puede consultar cuántos reintentos automáticos se han producido y los detalles de lo que ha ocurrido.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/parallel-actions/) acerca de esta versión.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versión de 2017-04-17 - Actualización del primer trimestre para Microsoft Flow
* **Experiencias modernas de aprobación**: cree flujos de trabajo donde los aprobadores pueden aprobar forma segura desde la misma aplicación móvil Microsoft Flow o en el centro de aprobaciones unificadas del sitio web de Microsoft Flow.
* **Disponibilidad general de flujos de equipo**: varias personas pueden poseer y administrar un flujo junto con flujos de equipo, que ahora están disponibles con carácter general.
* **Creación de conectores para Microsoft Flow**: cualquier persona puede enviar su propio conector de Microsoft Flow gratis para que lo use todo el mundo.
* **Un diseñador "a medida"**: en algunas plantillas, la nueva versión del diseñador presenta solo aquellos campos que son necesarios para crear un flujo, lo que simplifica la experiencia.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/q1-2017-update/) acerca de esta versión.

### <a name="release-2017-04-11"></a>Versión 2017-04-11
* **Nuevas acciones para compilar tablas y listas**: acciones de creación de nuevas tablas HTML, creación de tablas CSV y combinación que pueden procesar listas de elementos (en lugar del anterior método que se aplicaba de forma individual).
* **Inserción de pasos en cualquier lugar**: ahora puede insertar un nuevo paso en cualquier parte del flujo de trabajo sin necesidad de arrastrar y colocar.
* **Cuatro nuevos servicios**: Flow es ahora compatible con 10 to 8 Scheduling, Act!, Inoreader y Computer Vision API. Con Computer Vision API puede procesar imágenes para obtener el contenido de texto (proceso conocido como OCR) o etiquetar automáticamente las imágenes en función de su contenido.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) acerca de esta versión.

### <a name="release-2017-04-03"></a>Versión 2017-04-03
* **Versión Beta para Windows Phone**: la versión beta de la aplicación para Windows Phone está disponible para obtener una versión preliminar de la aplicación en su Windows Phone. [Más información](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/)
* **Muhimbi PDF**: ahora puede convertir archivos de Microsoft Word en PDF, agregar marcas de agua, combinar documentos y mucho más con Muhimbi PDF. [Más información](https://flow.microsoft.com/blog/convert-files-using-muhimbi/)
* **Desencadenar flujos desde botones físicos**: anunciamos asociaciones con dos de los principales productos en el espacio de los botones físicos: Flic, de Shortcut Labs, y Bttn, de The Button Corporation. [Más información](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versión 2017-03-22
* **Copia de su flujo**: ahora puede realizar una copia de su flujo para trabajar en versiones de borrador o duplicar un flujo que creó anteriormente.
* **Dos nuevos servicios**: se agrega compatibilidad con Toodledo, que permite administrar su lista de tareas mediante la creación y actualización de las tareas, y con Zendesk, que proporciona un servicio al cliente y admite una plataforma de tickets.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/make-a-copy/) acerca de esta versión.

### <a name="release-2017-03-15"></a>Versión 2017-03-15
* **Compartir botones con compañeros de trabajo**: ahora puede compartir los botones de flujo con otras personas, lo que ayuda a cualquier usuario corporativo a realizar tareas rápidas.
* **Desencadenar botones desde la pantalla principal**: los accesos directos a los botones de flujo en las pantallas principal y de bloqueo de los dispositivos móviles hacen que sea más rápido que nunca desencadenar un flujo.
* **Flujos de equipos en la aplicación Microsoft Flow**: ahora puede ver los flujos de otros propietarios de la aplicación Microsoft Flow para iOS o Android.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-sharing/) acerca de esta versión.

### <a name="release-2017-03-10"></a>Versión 2017-03-10
* **Mejor experiencia de conector personalizado**: ahora puede usar una colección Postman para crear un conector personalizado y editar, agregar y probar acciones.
* **Dos nuevos servicios**: se ha agregado compatibilidad con PowerApps Notifications y PivotalTracker.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) acerca de esta versión.

### <a name="release-2017-02-27"></a>Versión 2017-02-27
* **Desencadenar los botones de flujo**: ahora puede desencadenar los botones de flujo directamente desde el sitio web de Microsoft Flow. En la lista de flujos, simplemente seleccione el menú "..." y elija el comando Ejecutar ahora.
* **Cinco nuevos servicios**: se ha agregado compatibilidad con Oracle Database, Intercom, FreshBooks, LeanKit y WebMerge.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) acerca de esta versión.

### <a name="release-2017-02-21"></a>Versión 2017-02-21
* **Ver flujos de entorno**: los administradores de entorno ahora pueden ver la lista completa de todos los flujos dentro de un determinado entorno, así como habilitar, deshabilitar o eliminar flujos.
* **Dos nuevos servicios**: se ha agregado compatibilidad con Azure Automation y Basecamp 2.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) acerca de esta versión.

### <a name="release-2017-02-16"></a>Versión 2017-02-16
* **Cinco nuevos servicios**: se ha agregado compatibilidad con Azure Data Lake, Bitbucket (un servicio de hospedaje basado en web para proyectos que usan el control de revisión de GIT), Eventbrite, Infusionsoft y Pipedrive.
* **Autenticación HTTP personalizada**: en el diseñador de flujos ahora es posible usar la autenticación con puntos de conexión HTTP personalizados.
* **Analizar mensajes JSON**: puede analizar datos JSON procedentes del desencadenador Solicitud HTTP o devueltos desde la acción HTTP.
* **Filtrado de la ejecución de flujo**: filtrado mejorado para las ejecuciones de flujo, con opciones más específicas, incluida la visualización de los flujos en ejecución o las ejecuciones canceladas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) acerca de esta versión.

### <a name="release-2017-02-06"></a>Versión 06-02-2017
* **Flujos de equipo**: los flujos de equipo permiten que varias personas posean y administren un flujo de forma conjunta y que, aunque cualquiera de ellas abandone la organización, los flujos creados se sigan ejecutando.
* **Uso compartido de conectores personalizados**: los conectores personalizados, como los flujos de equipo, se pueden compartir y administrar colectivamente dentro de una organización.
* **Compatibilidad con Gmail y LUIS**: conéctese a Gmail y a Language Understanding Intelligent Service de Azure Cognitive Services.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/team-flows/) acerca de esta versión.

### <a name="release-2017-01-30"></a>Versión 30-01-2017
* **Entradas de los botones de flujos**: los botones de flujos pueden recibir acciones de usuario en tiempo de ejecución, por lo que los creadores de flujos pueden definir la información que se pasa al pulsar el botón.
* **Tareas de Outlook y HelloSign**: el servicio Tareas de Outlook le permite administrar tareas, mientras que HelloSign permite proteger las firmas electrónicas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-user-inputs/) acerca de esta versión.

### <a name="release-2017-01-23"></a>Versión 2017-01-23
* **Buscar por servicio**: examine por servicio cuando agregue un desencadenador o una acción para ver todas las acciones de cada servicio.
* **Cambio de mayúsculas y minúsculas**: agregue bloques de cambios para tener varias ramas de lógica en paralelo.
* **Más acciones de correo electrónico**: nueva funcionalidad de los servicios Office 365 Outlook y Outlook.com para trabajar con mensajes de correo marcados.
* **Cinco nuevos servicios**: Conexión a sistemas de archivos locales o de red, el servicio de pago Stripe, IBM Informix, IBM DB2 y UserVoice.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/search-by-service/) acerca de esta versión.

### <a name="release-2017-01-14"></a>Versión 2017-01-14
* **Volver a enviar ejecuciones**: si tiene un flujo con un error y desea intentar corregirlo y ejecutarlo de nuevo, se puede volver a enviar esa ejecución.
* **Cancelación de ejecuciones**: cuando un flujo se queda bloqueado ya puede cancelar explícitamente la ejecución.
* **Dos nuevos servicios**: incorporación de compatibilidad con GoToTraining y GoToWebinar.
* **Conexión por teléfono móvil**: ya puede compartir plantillas directamente desde la aplicación móvil y se ha agregado un vínculo de descarga rápida de las aplicaciones de la parte superior del sitio web.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/managing-runs/) acerca de esta versión.

### <a name="release-2016-12-29"></a>Versión 2016-12-29
Microsoft Flow ahora admite DocuSign, para controlar firmas electrónicas y la administración de transacciones digitales, SurveyMonkey, para encuestas basadas en web, y la aplicación para tomar notas OneNote (solo cuentas empresariales).

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/final-2016-services/) acerca de esta versión.

### <a name="release-2016-12-20"></a>Versión 2016-12-20
* **Ejecutar ahora**: se puede enviar rápidamente un desencadenador recurrente
a petición (por ejemplo, si tiene un informe programado cada día, pero necesita que el informe se ejecute también **ahora**).
* **Seis nuevos servicios**: genere flujos que se conectan a MSN El Tiempo, Medium, Contactos de Google, Buffer, Harvest y TypeForm.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) acerca de esta versión.

### <a name="release-2016-12-14"></a>Versión 2016-12-14
Ahora puede sacar provecho de información valiosa al desencadenar un flujo de botón, como desde dónde se desencadenó el botón, quién lo hizo, a qué hora, etc.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) acerca de esta versión.

### <a name="release-2016-12-06"></a>Versión 2016-12-06
* **Introducción a aprendizaje guiado**: empiece a trabajar con un conjunto de cursos en secuencia que combinan vídeos y documentación para ayudarle a comprender las numerosas y eficaces funcionalidades de Microsoft Flow.
* **Dos nuevos servicios**: ahora los flujos pueden usar Freshdesk, una solución de soporte al cliente y GoToMeeting, una herramienta de reuniones en línea.
* **Compatibilidad con HTTP Webhook**: ahora un flujo puede ser un punto de conexión de webhooks que se registrará y anulará su registro automáticamente.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) acerca de esta versión.

### <a name="release-2016-11-23"></a>Versión 2016-11-23
* **Compatibilidad con alertas de Power BI**: convierte la información en acción gracias a la activación de flujos desde alertas de datos de Power BI.
* **Mejoras de aplicaciones móviles**: se ha agregado la capacidad de crear flujos desde cero, además de la experiencia ya existente de creación mediante plantillas. También se ha mejorado el rendimiento al ver las ejecuciones de los flujos.
* **Ocho nuevos servicios**: ahora puede conectarse a Azure Resource Manager, las colas de Azure, Chatter, Disqus, Azure DocumentDB, la API Cognitive Services Face, HipChat y Wordpress.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) acerca de esta versión.

### <a name="release-2016-11-15"></a>Versión 2016-11-15
* **Programa de asociados de Microsoft Flow**: Microsoft Flow tiene ahora un programa de asociados certificados para realizar conexiones y aprovechar las ventajas de la experiencia y los talentos de diferentes empresas con Microsoft Flow en todo el mundo.
* **Seis nuevos servicios**: también vamos a lanzar seis nuevos servicios esta semana: Asana, Campfire, EasyRedmine, JIRA, Redmine y Vimeo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) acerca de esta versión.

### <a name="release-2016-10-31---general-availability"></a>Versión 2016-10-31: disponibilidad general
* **Precios y licencias**: ya está disponible tanto de forma gratuita como de pago, además de estar incluido en Office 365 y Dynamics 365.
* **Centro de administración de Microsoft Flow**: preparado para la empresa con el nuevo Centro de administración. En el Centro de administración se pueden administrar los entornos de la organización.
* **Directivas de prevención de pérdida de datos**: los administradores pueden crear directivas de prevención de pérdida de datos para controlar el flujo de datos entre servicios.
* **Disponibilidad en Android**: la aplicación Microsoft Flow para dispositivos móviles ya está disponible tanto para iOS como para Android. La aplicación permite recibir notificaciones, supervisar la actividad e iniciar flujos pulsando un botón.
* **Nuevas experiencias de diseño**: ya se puede buscar en el contenido dinámico que se pasa paso a paso, lo que agiliza mucho la referencia a los datos que se desee.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/announcing-ga/) acerca de esta versión.

### <a name="release-2016-10-26"></a>Versión 2016-10-26
* **Flujos de botón**: hay innumerables operaciones que nos gustaría poder desencadenar en cualquier momento y lugar. Ahora, con los flujos de botón, es posible hacerlo con un solo clic un botón, y desde cualquier dispositivo móvil.
* **Anuncio de entornos**: los entornos son espacios diferenciados para almacenar y administrar los flujos de una organización. Los entornos están geolocalizados, lo que significa que los flujos, las aplicaciones y los datos empresariales de un entorno estarán en la región en que se encuentra el entorno.
* **Seis nuevos servicios**: se agrega compatibilidad con Bit.ly, Cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 for Financials, Instapaper y Pinterest.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/environments-for-makers/) acerca de esta versión.

### <a name="release-2016-10-16"></a>Versión 2016-10-16
* **Conectores personalizados con más tipos de autenticación**: los conectores personalizados ahora admiten la autenticación de clave de API y pueden autenticarse en cualquier servicio que admita la especificación OAuth 2.0 completa.
* **Tres nuevos servicios**: hemos agregado compatibilidad con Basecamp 3, Blogger y PagerDuty.
* **Mejoras del diseñador**: el rendimiento ha mejorado y ahora puede actualizar y reparar las conexiones directamente desde el menú "..." de cada acción; hemos agregado también un nuevo paso llamado Finalizar que puede usar para finalizar la ejecución de un flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/early-october-updates/) acerca de esta versión.

### <a name="release-2016-09-25"></a>Versión 2016-09-25
Ahora se pueden crear flujos en teléfonos móviles. Examine nuestra completa galería de plantillas, repase nuestra lista de servicios o seleccione la categoría de plantillas que desea ver con más detalle. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/mobile-creation/) acerca de esta versión.

### <a name="release-2016-09-22"></a>Versión 2016-09-22
* **Selector de personas de Microsoft Graph**: hay un nuevo selector de personas de Microsoft Graph integrado directamente en la interfaz de usuario de Microsoft Flow para ayudarle a elegir el contacto o la dirección de correo electrónico correctos.
* **Compatibilidad con Microsoft Dynamics AX**: ahora puede actuar sobre los datos de sus operaciones de Dynamics AX Online desde dentro de los flujos, desde crear nuevos registros a consultar los datos.
* **Dos nuevos servicios de asociados**: ahora puede usar appFigures o Insightly desde los flujos.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/more-september-updates/) acerca de esta versión.

### <a name="release-2016-09-14"></a>Versión 2016-09-14
* **Inserción en su sitio web o aplicación**: los desarrolladores pueden insertar Microsoft Flow directamente en sus aplicaciones o sitios web para ofrecer a sus usuarios una manera sencilla de automatizar sus tareas profesionales o personales.
* **Usar un flujo como un punto de conexión HTTP**: ahora puede usar un flujo como una API HTTP. En Flow hay un desencadenador llamado Request (Solicitud) y puede elegir responder a la solicitud entrante agregando una tarjeta Response (Respuesta).
* **Compatibilidad con Todoist**: Todoist ofrece perspectiva sobre todos los proyectos, en el trabajo y en casa.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/extend-web-site-application/) acerca de esta versión.

### <a name="release-2016-09-01"></a>Versión 2016-09-01
Ahora, Microsoft Flow está disponible para todos. Inicialmente, la versión preliminar se abrió solo para las direcciones de correo electrónico de trabajo o escuela, como las usadas con Office 365 Business u Office 365 Enterprise. Hoy anunciamos que la versión preliminar está disponible oficialmente para todos los usuarios, de forma gratuita, independientemente de qué correo electrónico tengan. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/available-for-everyone/) acerca de esta versión.

### <a name="release-2016-08-31"></a>Versión 2016-08-31
* **Instrucciones condicionales anidadas**: ahora puede agregar una segunda condición dentro de otra, o una tercera o más.
* **Aplicar a cada**: el bucle ‘aplicar a cada’ permite controlar la lista en la que se repetirá la acción.
* **Hacer hasta**: el bucle ‘hacer hasta’ permite repetir un paso hasta que se cumpla una determinada condición.
* **Filtrar matrices**: un único paso de filtro nativo permite asegurarse de que todos los elementos de la lista coincidan con una expresión que defina.
* **Componer variables de cadena**: ahora puede componer una variable de cadena.
* **Ámbitos**: los ámbitos son una manera sencilla de agrupar dos o más acciones.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/build-advanced-flows/) acerca de esta versión.

### <a name="release-2016-08-27"></a>Versión 2016-08-27
* **Comentarios en pasos**: los comentarios permiten agregar notas a cada acción individual para recordar fácilmente lo que el flujo necesita.
* **Compatibilidad con Smartsheet**: esta semana agregamos compatibilidad para conectarse a Smartsheet. Smartsheet es un servicio que facilita la colaboración en hojas en la nube.
* **Mejoras en la interfaz de usuario durante la creación de flujos**: hemos centrado el nombre del flujo en el frente y hemos movido el botón de guardar a la parte superior de la página para facilitar el acceso.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) acerca de esta versión.

### <a name="release-2016-08-18"></a>Versión 2016-08-18
Ahora puede disfrutar de la nueva experiencia de listas modernas de SharePoint Online, que incluye la integración con Microsoft Flow. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) acerca de esta versión.

### <a name="release-2016-08-13"></a>Versión 2016-08-13
* **Visual Studio Team Services**: con Flow, ahora puede conectar VSTS a una gran variedad de servicios como Correo de Office 365, Slack, Trello y Wunderlist.
* **Mejoras de SharePoint**: las listas de SharePoint admiten diversos tipos de datos, desde objetos simples como líneas individuales de texto o fecha y hora, a objetos complejos tales como personas o grupos, búsqueda y opciones.
* **Probar las conexiones de O365 Outlook**: siempre que cree una nueva conexión a Office 365 Outlook, la probaremos para estar seguros de que está listo para usarla.
* **Control booleano**: también hemos agregado un control booleano para aclarar qué valores se deben especificar en los campos de entrada booleanos, por ejemplo Tiene datos adjuntos en el desencadenador Cada vez que reciba un correo electrónico.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) acerca de esta versión.

### <a name="release-2016-08-08"></a>Versión 2016-08-08
Versión preliminar pública de Microsoft Common Data Service integrado en Microsoft Flow. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) acerca de esta versión.

### <a name="release-2016-08-05"></a>Versión 2016-08-05
* **SharePoint local**: al igual que con SharePoint Online, puede crear flujos para las listas de SharePoint local y las bibliotecas de documentos, mediante plantillas predefinidas o partiendo de cero.
* **Burbujas de información en el diseñador**: para proporcionar información sobre las funcionalidades de cada desencadenador y acción, hemos agregado burbujas de información en cada paso del flujo.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) acerca de esta versión.

### <a name="release-2016-07-15"></a>Versión 2016-07-15
* **Cuatro nuevos servicios agregados**: conecte con Google Calendar, Google Tasks, YouTube y SparkPost.
* **Cambie el nombre de las acciones**: ahora, puede cambiar el nombre de estas acciones para diferenciarlas.
* **Retraso de diferentes períodos de tiempo**: ahora, puede seleccionar cualquier número de segundos, minutos, horas o días.
* **Explorador de carpetas más fácil de usar**: hemos simplificado el explorador de carpetas. Ahora, al seleccionar en el lado izquierdo, se elegirá esa carpeta y al seleccionar en el lado derecho, se abrirá la carpeta para que pueda elegir las subcarpetas.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) acerca de esta versión.

### <a name="release-2016-07-08"></a>Versión 2016-07-08
Conectividad local para Microsoft Flow con la puerta de enlace de datos local. Esto permite establecer conexiones seguras a SQL Server e integrarlas con los flujos. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) acerca de esta versión.

### <a name="release-2016-07-02"></a>Versión 2016-07-02
* **Compatibilidad con Google Sheets**: en el pasado, podíamos usar Excel y Google Drive, pero esta semana hemos agregado compatibilidad nativa con Google Sheets.
* **Comience a trabajar más rápidamente con las plantillas**: también hemos optimizado la forma de comenzar a trabajar con las plantillas. Ahora, puede seleccionar qué cuentas desea usar para una plantilla directamente en la página de la plantilla.
* **Las autorizaciones no expiran para SharePoint y Office 365**: ahora, Microsoft Flow renovará automáticamente el acceso a los servicios basados en Azure Active Directory, por lo que todos los flujos seguirán funcionando incluso después de cambiar la contraseña.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/more-june-updates/) acerca de esta versión.

### <a name="release-2016-06-20"></a>Versión 2016-06-20
* **Presentación de la nueva aplicación móvil para Microsoft Flow**: hoy nos complace presentar otra pieza importante de nuestra oferta: una aplicación móvil que ya está disponible para su descarga en iOS (próximamente también en Android) y que ofrece la posibilidad de administrar, realizar seguimiento y explorar sus flujos de trabajo automatizados en cualquier momento y en cualquier lugar.  
* **Inicio de sesión único**: hemos implementado el inicio de sesión único que le permite autenticar Microsoft Flow en otros servicios de Microsoft, por ejemplo, Office 365.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) acerca de esta versión.

### <a name="release-2016-06-18"></a>Versión 2016-06-18
* **Nuevo servicio de correo**: ahora puede enviar correos electrónicos directamente desde Microsoft Flow sin necesidad de conectarse a sus cuentas de correo electrónico personales o de trabajo dentro de Microsoft Flow.
* **Notificaciones en el portal**: ahora verá las notificaciones en la parte superior del portal cada vez que algo vaya mal con los flujos.
* **Toda la actividad en el portal**: para ver la actividad de todos los flujos, ahora puede hacer clic en la nueva pestaña de actividad en el sitio web de Flow.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) acerca de esta versión.

### <a name="release-2016-05-27"></a>Versión 2016-05-27
* **Explorar plantillas por servicio**: ahora puede ver todos los servicios que admitimos, sin tener que iniciar sesión. En esta página puede ver una descripción de cada uno de los servicios y consultar las plantillas que tenemos para ese servicio.
* **Creación y uso de conectores personalizados**: igual que se crean conectores personalizados en PowerApps, también puede conectar con sus propias API directamente en flow.microsoft.com:
* **Probar los flujos antes de finalizar**: cada vez que guarde un flujo, ahora verá los resultados de la ejecución del flujo directamente en la página, si realiza la acción de inicio.

[Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) acerca de esta versión.

### <a name="release-2016-05-07"></a>Versión 2016-05-07
Dos nuevos servicios: Microsoft Project Online y Mandrill de Mailchimp. [Obtenga más información y envíe sus preguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) acerca de esta versión.

### <a name="release-2016-04-27---public-preview"></a>Versión 2016-04-27: versión preliminar pública
Si utiliza flujos de lógica como parte de [Microsoft PowerApps](https://powerapps.microsoft.com), la versión preliminar de Microsoft Flow ofrece varias características nuevas:

* Ahora puede examinar una galería de docenas de plantillas y ordenarlas por popularidad, nombre o fecha de publicación.
* Puede [publicar sus propias plantillas](publish-a-template.md) en la galería después de personalizar un flujo.
* Puede ver el historial de cada comprobación y ejecución de los flujos.
* Al guardar un flujo, puede [verlo en acción de inmediato](see-a-flow-run.md), solo tiene que realizar la acción del desencadenador.
* Tenemos una [nueva comunidad](http://go.microsoft.com/fwlink/?LinkID=787467), donde puede intercambiar información sobre Flow o [enviar sus ideas](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Pasos siguientes
Si tiene algún problema que no se haya incluido en estas notas de la versión o en la sección de [preguntas más frecuentes](frequently-asked-questions.md), [únase a nuestra comunidad](http://go.microsoft.com/fwlink/?LinkID=787467), donde puede realizar cualquier pregunta, o [póngase en contacto con el departamento de soporte técnico](http://go.microsoft.com/fwlink/?LinkID=787479).

