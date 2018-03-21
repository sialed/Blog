---
title: "¡Windows Server 2019 a la vista!"
tags:
  - Microsoft
  - Windows Server 2019
header:
  image: /assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/header.jpg
  og_image: /assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/og.jpg
---

Ayer día 20 de marzo de 2018, el equipo de Windows Server lanzaba la noticia de que Windows Server 2019 estaría disponible en la segunda mitad del año 2018. Aunque desde este momento se podría acceder a la preview build a través del [programa Insider](https://insider.windows.com/en-us/for-business-getting-started-server/).

## ¿Qué trae de nuevo Windows Server 2019?

Como comentan en el comunicado, Windows server 2019 se basa en la sólida base de Windows server 2016, el cual sigue teniendo una gran adopción por parte de las empresas.

Después de analizar lo que los clientes de Windows Server pedían, el estudio de la telemetría y hacía donde se desarrolla la industria, en este Windows Server 2019 se han mejorado cuatro temas fundamentalmente: Las infraestructuras híbridas, la seguridad, las plataformas de aplicaciones y las Infraestructuras hyperconvergentes (HCI).

### Escenarios de nubes híbridas

En estos últimos años la nube esta teniendo un gran crecimiento y las empresas cada día se apoyan más en soluciones cloud para mejorar su negocio, y sus modelos productivos se adaptan a estos nuevos servicios. Para la mayoría de las empresas un enfoque híbrido, que combina los entornos locales y la nube parece ser la mejor opción. La extensión de Active Directory en Azure, la sincronización de archivos y las copias de seguridad en la nube son algunos de los ejemplos que se pueden encontrar en las empresas a la hora de aprovechar los servicios cloud.

En la Microsoft Ignite de septiembre de 2017, se anunció la Technical Preview de [Proyect Honolulu](https://docs.microsoft.com/es-es/windows-server/manage/honolulu/honolulu), el cual estará disponible en Windows Server 2019 que facilitará la conexión y la gestión de las implementaciones de Windows Server a los servicios de Microsoft Azure mediante una plataforma vía web.

![Proyect Honolulu]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/1_Proyect_Honolulu.jpg){: .align-center}

### Seguridad

Para Microsoft la seguridad sigue siendo una prioridad. Según un [estudio]( https://cloud-platform-assets.azurewebsites.net/anatomy-of-a-breach/) de la propia Microsoft los incidentes de seguridad siguen creciendo rápidamente y muestra que los atacantes, de media, solo necesitan de 24 a 48 horas para penetrar en un entorno después de infectar la primera máquina. Además, pueden permanecer en el entorno sin ser detectados una media de 99 días.

El enfoque de seguridad de Microsoft tiene tres aspectos fundamentales: proteger, detectar y responder. En estas tres áreas Windows Server 2019 trae nuevas funciones.

En el aspecto de proteger, en Windows Server 2016 se presentaron las máquinas virtuales blindadas. Estas máquinas virtuales blindadas proporcionan funciones adicionales de seguridad como cifrados con Bitlocker, protección contra manipulaciones o cifrado automático del tráfico generado al realizar migraciones en vivo. En Windows Server 2019, las máquinas virtuales blindadas también admitirán máquinas virtuales Linux.

Tanto en los aspectos de detectar y responder, en Windows Server 2019, se incorpora Windows Defender Advanced Threat Protection (ATP) que brinda protección preventiva, detecta ataques y exploits zero day.

![Windows Defender Advanced Threat Protection (ATP)]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/2_ATP.png){: .align-center}

### Plataforma de aplicaciones

Uno de los aspectos importantes para el equipo de Windows Server es una satisfactoria experiencia de los desarrolladores. Por ello se han mejorado los contenedores de Windows Server y el Subsistema Linux (WSL).

Debido a la gran adopción desde la introducción de los contenedores en Windows Server 2016, el equipo de Microsoft entendió mediante los comentarios de la comunidad que un tamaño de imagen de contenedor más pequeño mejoraría la experiencia de los desarrolladores. Por ello, en Windows Server 2019, el objetivo del equipo es reducir el tamaño actual de Server Core a un tercio de su tamaño actual de 5 GB. Esto supondrá una reducción del 72% el tiempo de descarga de la imagen, optimizando el tiempo de desarrollo y el rendimiento.

También se está mejorando el soporte de Kubernetes, el cual se encuentra actualmente en versión beta, y en Windows Server 2019, se presentarán mejoras para los componentes de computación, almacenamiento y redes de un clúster de Kubernetes.

![Kubernetes]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/3_Kubernetes.png){: .align-center}

### Infraestructuras hyperconvergentes (HCI)

La infraestructura hyperconvergente es una de las últimas tendencias en la industria se servidores en la actualidad. Según IDC, el [mercado de HCI creció un 64%](https://thestack.com/data-centre/2017/06/26/hyperconverged-market-grows-64-over-2016/) en 2016.

Microsoft se asocia con proveedores de hardware líderes en la industria para proporcionar una solución HCI asequible y extremadamente robusta. En Windows Server 2019 se agregan capacidades de administración de implementaciones HCI junto con el Proyecto Honolulu, para simplificar la administración y las actividades cotidianas de entornos HCI.

![HCI Proyect Honolulu]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-21-¡Windows Server 2019 a la vista!/4_HCI.jpg){: .align-center}

Microsoft tiene mucho que compartir con nosotros sobre Windows Server 2019 en los próximos meses hasta la fecha de lanzamiento. Nos irán dando mas detalles sobre las áreas tratadas en el post.

Y nos recuerdan que si nos podemos esperar más a probar la nueva versión de Windows Server podemos hacerlo ya desde [la plataforma Insider](https://insider.windows.com/en-us/for-business-getting-started-server/).

Espero que el post os haya gustado y la información haya sido útil. Comentad que os parecen las novedades que veremos en Windows Server 2019 y nos vemos en el próximo post.

¡Un saludo!

- - -

Fuente: [Cloud Perspectives Blog]( https://cloudblogs.microsoft.com/windowsserver/2018/03/20/introducing-windows-server-2019-now-available-in-preview/)
