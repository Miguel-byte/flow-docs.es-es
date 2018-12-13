---
title: Información acerca de puertas de enlace de datos locales | Microsoft Docs
description: Información de referencia, acerca de la instalación y para la solución de problemas de las puertas de enlace de datos locales
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8baaf85ae07d2763886eb1ffda0141e4804cb630
ms.sourcegitcommit: 8a36a3211e76b2b1a4a3154bc41e12a87dc3c288
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53179826"
---
# <a name="understand-on-premises-data-gateways-for-microsoft-flow"></a>Información acerca de las puertas de enlace de datos locales de Microsoft Flow
Use la puerta de enlace de datos local con Microsoft Flow para establecer conexiones seguras con los orígenes de datos locales, como Microsoft SQL Server.

## <a name="installation-and-configuration"></a>Instalación y configuración
### <a name="prerequisites"></a>Requisitos previos
Mínimos:

* [.NET Framework 4.6](https://www.microsoft.com/download/details.aspx?id=48130)
* Versión de 64 bits de Windows 7 o Windows Server 2008 R2 (o posterior)

Recomendados:

* CPU de 8 núcleos
* 8 GB de memoria
* Versión de 64 bits de Windows Server 2012 R2 (o cualquier versión posterior)

Otras consideraciones relacionadas:

* No se pueden instalar puertas de enlace en un controlador de dominio.
* No se debe instalar una puerta de enlace en un equipo portátil que se pueda apagar, poner en suspensión o que no esté conectado a Internet,
* ya que su rendimiento puede verse negativamente afectado en una red inalámbrica.

## <a name="install-a-gateway"></a>Instalación de una puerta de enlace
> [!IMPORTANT]
> Las puertas de enlace de datos de Microsoft SharePoint admiten tráfico HTTP y HTTPS.
> 
> 

1. [Descargue el instalador](https://go.microsoft.com/fwlink/?LinkID=820931) y ejecútelo.
   
    ![Ejecutar el instalador](./media/gateway-reference/run-installer.png)
2. En la primera pantalla del Asistente para la instalación, seleccione **Siguiente** para confirmar el aviso acerca de la instalación de una puerta de enlace en un portátil.
   
    ![Pantalla de aviso](./media/gateway-reference/laptop-reminder.png)
3. Seleccione la ubicación de instalación.
4. Acepte los términos de uso y la declaración de privacidad.
5. Haga clic en **Instalar**.
   
    ![pantalla de ubicación](./media/gateway-reference/location.png)
6. En los cuadros de diálogo de **Control de cuentas de usuario**, seleccione **Sí** para continuar.
7. En la pantalla **Puerta de enlace de datos local**, escriba la dirección de correo electrónico de la cuenta que va a usar para iniciar sesión en la puerta de enlace, seleccione **Iniciar sesión** y complete el proceso de inicio de sesión.
   
    ![Inicio de sesión](./media/gateway-reference/sign-in.png)

## <a name="register-new-gateway-or-take-over-existing-gateway"></a>Registro de una puerta de enlace nueva o toma de control de una existente
1. Seleccione **Registrar una nueva puerta de enlace en este equipo** o **Migre, restaure o adquiera una puerta de enlace existente**y, después, seleccione **Siguiente**.
   
    ![Elegir nuevo o existente](./media/gateway-reference/new-existing.png)
2. Para configurar una puerta de enlace nueva, escriba un nombre en el cuadro **New on-premises data gateway name** (Nombre de nueva puerta de enlace de datos local), escriba una clave de recuperación en el cuadro **Clave de recuperación** y vuelva a escribirla en el cuadro **Confirmar clave de recuperación**. Seleccione **Configurar** y, luego, **Cerrar**.
   
    ![Configurar una puerta de enlace nueva](./media/gateway-reference/configure-new.png)
3. Especifique una clave de recuperación que contenga al menos ocho caracteres y guárdela en un lugar seguro. Necesitará esta clave si desea migrar, restaurar o asumir el control de su puerta de enlace.
4. Para migrar, restaurar o asumir el control de una puerta de enlace existente, especifique el nombre de la puerta de enlace y su clave de recuperación, seleccione **Configurar** y siga las instrucciones.
   
    ![Recuperar una puerta de enlace existente](./media/gateway-reference/recover-existing.png)

## <a name="restart-the-gateway"></a>Reinicio de la puerta de enlace
La puerta de enlace se ejecuta como un servicio de Windows y, al igual que cualquier otro servicio de Windows, se puede iniciar y detener de varias maneras. Por ejemplo, puede abrir un símbolo del sistema con permisos elevados en la máquina en que se ejecuta la puerta de enlace y, después, ejecutar cualquiera de estos comandos:

* Para detener el servicio, ejecute este comando:

```batchfile
    net stop PBIEgwService
```

* Para iniciar el servicio, ejecute este comando:

```batchfile
    net start PBIEgwService
```

## <a name="configure-a-firewall-or-proxy"></a>Configuración de un firewall o proxy
Para obtener información acerca de cómo proporcionar información del proxy a la puerta de enlace, consulte [Configuración de proxy para la puerta de enlace de datos local](https://powerbi.microsoft.com/documentation/powerbi-gateway-proxy/).

Para asegurarse de si el firewall o proxy, pueden bloquear las conexiones, ejecute el siguiente comando desde un símbolo del sistema de PowerShell. Este comando prueba la conectividad con Azure Service Bus. Este comando solo prueba la conectividad de la red, no afecta al servicio de servidor en la nube ni a la puerta de enlace. Ayuda a determinar si la máquina tiene conectividad con Internet.

```powershell
Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350
```

Los resultados deberían ser similares a la salida siguiente. Si el valor de **TcpTestSucceeded** no es *true*, es posible que algún firewall lo haya bloqueado.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Si desea ser exhaustivo, sustituya los valores de **ComputerName** y **Port** por los que aparecen en el apartado **Configurar puertos** de este mismo tema.

El firewall también puede bloquear las conexiones que Azure Service Bus establece con los centros de datos de Azure. En ese caso, incluirá en una lista blanca (desbloqueará) todas las [direcciones IP](https://www.microsoft.com/download/details.aspx?id=41653) de su región para dichos centros de datos.

## <a name="configure-ports"></a>Configuración de puertos
La puerta de enlace crea una conexión de salida con Azure Service Bus. Se comunica por los puertos de salida: TCP 443 (valor predeterminado), 5671, 5672 y 9350 a 9354. La puerta de enlace no requiere puertos de entrada.

Más información acerca de las [soluciones híbridas](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/).

| Nombres de dominio | Puertos de salida | Descripción |
| --- | --- | --- |
| *.analysis.windows.net |443 |HTTPS |
| *.login.microsoftonline.com |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Agentes de escucha en Service Bus Relay sobre TCP (requiere 443 para la adquisición del token de Access Control) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Se utiliza para probar la conectividad a Internet si no se puede acceder a la puerta de enlace. |

Si necesita incluir en la lista de permitidos direcciones IP, en lugar de dominios, puede descargar y usar la [lista de intervalos de direcciones IP del centro de datos de Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653). En algunos casos, las conexiones de Azure Service Bus se establecerán con la dirección IP, en lugar de con los nombres de dominio completo.

## <a name="sign-in-account"></a>Cuenta de inicio de sesión
Los usuarios iniciarán sesión con una cuenta profesional o educativa. Es la cuenta de su organización. Si se ha registrado para acceder a una oferta de Office 365, pero no ha especificado su correo electrónico profesional, podría ser similar a nancy@contoso.onmicrosoft.com. La cuenta, en un servicio en la nube, se almacena en un inquilino de Azure Active Directory (AAD). En la mayoría de los casos, el UPN de la cuenta de AAD coincidirá con la dirección de correo electrónico.

## <a name="windows-service-account"></a>Cuenta de servicio de Windows
La puerta de enlace de datos local está configurada para usar *NT SERVICE\PBIEgwService* para las credenciales de inicio de sesión de los servicios de Windows. De manera predeterminada, tiene el derecho de inicio de sesión como servicio. Esto se da en el contexto de la máquina en la que va a instalar la puerta de enlace.

No es la cuenta que se usa para conectarse a orígenes de datos locales ni la cuenta profesional o educativa con la que inicia sesión en los servicios en la nube.

## <a name="tenant-level-administration"></a>Administración de nivel de inquilino

No hay actualmente un único lugar donde los administradores de inquilinos puedan administrar todas las puertas de enlace que otros usuarios han instalado y configurado.  Si es usted un administrador de inquilinos, recomendamos que pida a los usuarios de su organización que lo agreguen como administrador para cada puerta de enlace que instalen. Esto le permite administrar todas las puertas de enlace de su organización a través de la página Configuración de puerta de enlace, o los [comandos de PowerShell](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
### <a name="general-questions"></a>Preguntas generales
**Pregunta:** ¿Qué orígenes de datos admite la puerta de enlace?
**Respuesta:**

* SQL Server
* SharePoint
* Oracle
* Informix
* Sistema de archivos
* DB2

**Pregunta:** ¿Se necesita una puerta de enlace para los orígenes de datos en la nube, como SQL Azure?
**Respuesta:** No. Una puerta de enlace solo se conecta a orígenes de datos locales.

**Pregunta:** ¿Cómo se denomina el servicio de Windows real?
**Respuesta:** En Servicios, la puerta de enlace se denomina **Servicio de Power BI Enterprise Gateway**.

**Pregunta:** ¿Hay conexiones de entrada con a la puerta de enlace desde la nube?
**Respuesta:** No. La puerta de enlace usa conexiones de salida con Azure Service Bus.

**Pregunta:** ¿Qué ocurre si bloqueo las conexiones de salida? ¿Qué necesito abrir?
**Respuesta:** Consulte los [puertos](gateway-reference.md#configure-ports) y hosts que utiliza la puerta de enlace.

**Pregunta:** ¿La puerta de enlace tiene que estar instalada en la misma máquina que el origen de datos?
**Respuesta:** No. La puerta de enlace se conectará al origen de datos con la información de conexión que se proporcionó. A este respecto, considere la puerta de enlace como una aplicación cliente. Solo será preciso que se pueda conectar con el nombre del servidor que se proporcionó.

**Pregunta:** ¿Cuál es la latencia para ejecutar consultas en un origen de datos desde la puerta de enlace? ¿Cuál es la mejor arquitectura?
**Respuesta:**  Para reducir la latencia de la red, instale la puerta de enlace lo más cerca posible del origen de datos. Si se puede instalar la puerta de enlace en el origen de datos real, se minimizará la latencia. Considere también los centros de datos. Por ejemplo, si el servicio utiliza el centro de datos del oeste de EE. UU. y tiene SQL Server hospedado en una máquina virtual de Azure, será conveniente que la máquina virtual de Azure se encuentre también en el oeste de EE. UU. Así se minimizará la latencia y se evitarán los cargos de salida en la máquina virtual de Azure.

**Pregunta:** ¿Hay requisitos relativos al ancho de banda de la red?
**Respuesta:** Se recomienda que la conexión de red tenga un buen rendimiento. Cada entorno es diferente y la cantidad de datos que se envían afectará a los resultados. El uso de ExpressRoute puede ayudarle a garantizar un nivel de rendimiento entre las instalaciones locales y los centros de datos de Azure.

Para determinar dicho rendimiento, se puede usar una herramienta de terceros, [Azure Speed Test](http://azurespeedtest.azurewebsites.net/).

**Pregunta:** ¿Se puede ejecutar el servicio de Windows de la puerta de enlace con una cuenta de Azure Active Directory?
**Respuesta:** No. El servicio de Windows debe tener una cuenta de Windows válida. De manera predeterminada, se ejecutará con el SID de servicio *NT SERVICE\PBIEgwService*.

**Pregunta:** ¿Cómo se envían los resultados a la nube?
**Respuesta:** Los resultados se envían mediante Azure Service Bus. Para más información, consulte el [funcionamiento](gateway-reference.md#how-the-gateway-works).

**Pregunta:** ¿Dónde se almacenan las credenciales?
**Respuesta:** Las credenciales que especifique para un origen de datos se cifran y almacenan en el servicio en la nube de la puerta de enlace. Las credenciales se descifran en la parte local de la puerta de enlace.

### <a name="high-availabilitydisaster-recovery"></a>Alta disponibilidad/recuperación ante desastres
**Pregunta:** ¿Existen planes para habilitar escenarios de alta disponibilidad con la puerta de enlace?
**Respuesta:** Sí, la alta disponibilidad [ya está disponible](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each).

**Pregunta:** ¿Qué opciones hay disponibles para la recuperación ante desastres?
**Respuesta:** Puede usar la clave de recuperación para restaurar o mover una puerta de enlace.

**Pregunta:** ¿Cuál es la ventaja de la clave de recuperación?
**Respuesta:** Proporciona una forma de migrar o recuperar la configuración de cualquier puerta de enlace.

### <a name="troubleshooting-questions"></a>Preguntas acerca de la solución de problemas
**Pregunta:** ¿Dónde están los registros de la puerta de enlace?
**Respuesta:** Consulte la sección [Herramientas](gateway-reference.md#tools) de este mismo tema, que encontrará más adelante.

**Pregunta:** ¿Cómo se pueden ver las consultas que se envían al origen de datos local?
**Respuesta:** Puede habilitar el seguimiento de consultas, que incluye las consultas que se envían. Cuando solucione el problema, no olvide devolverlo a su valor original. Si deje habilitado el seguimiento de consultas, los registros sean mayores.

También puede examinar las herramientas que tiene su origen de datos para realizar un seguimiento de las consultas. Por ejemplo, puede utilizar eventos extendidos o SQL Profiler para SQL Server y Analysis Services.

## <a name="how-the-gateway-works"></a>Funcionamiento de la puerta de enlace
![Funcionamiento](./media/gateway-reference/gateway-arch.png)

Cuando un usuario interactúa con un elemento que está conectado a un origen de datos local:

1. El servicio en la nube crea una consulta, junto con las credenciales cifradas del origen de datos, y envía la consulta a la cola para que la puerta de enlace la procese.
2. El servicio en la nube de la puerta de enlace analiza la consulta e inserta la solicitud en [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/).
3. La puerta de enlace de datos locales sondea Azure Service Bus para buscar las solicitudes pendientes.
4. La puerta de enlace obtiene la consulta, descifra las credenciales y se conecta a los orígenes de datos con dichas credenciales.
5. La puerta de enlace envía la consulta al origen de datos para su ejecución.
6. Los resultados se devuelven desde el origen de datos a la puerta de enlace y, luego, al servicio en la nube. A continuación, el servicio usa los resultados.

## <a name="troubleshooting"></a>Solución de problemas
### <a name="update-to-the-latest-version"></a>Actualización a la versión más reciente
Si la versión de la puerta de enlace no está actualizada, pueden aparecer muchos problemas. Asegúrese de usar la versión más reciente.  Si no ha actualizado la puerta de enlace recientemente, considere la posibilidad de instalar la versión más reciente y ver si puede reproducir el problema.

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Error: No se pudo agregar el usuario al grupo.  (-2147463168   PBIEgwService   Usuarios del registro de rendimiento   )
Este error puede producirse si se intenta instalar la puerta de enlace en un controlador de dominio que no sea compatible. Tendrá que instalar la puerta de enlace en una máquina que no sea un controlador de dominio.

## <a name="tools"></a>Herramientas
### <a name="collecting-logs-from-the-gateway-configurator"></a>Recopilación de registros del configurador de la puerta de enlace
Puede recopilar varios registros para la puerta de enlace. Empiece siempre con los registros.

1. Registros del instalador
   
    %localappdata%\Temp\On-premises_data_gateway_*.log
2. Registros de configuración
   
    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log
3. Registros del servicio de la puerta de enlace empresarial
   
    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log
4. Registros de eventos

Los registros de eventos de **On-premises data gateway service** están presentes en **Registros de aplicaciones y servicios**.

![Registros de eventos](./media/gateway-reference/event-logs.png)

### <a name="fiddler-trace"></a>Seguimiento de Fiddler
[Fiddler](http://www.telerik.com/fiddler) es una herramienta gratuita de Telerik que supervisa el tráfico HTTP.  Puede ver todo el funcionamiento del servicio de Power BI desde el equipo cliente. Puede aparecer errores y otra información relacionada.

