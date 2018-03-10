---
title: "Habilitar Hyper-V en Windows 10"
toc: true
toc_label: "Tabla de contenidos"
toc_icon: "list-ul"
tags:
  - Virtualización
  - Hyper-V
  - Microsoft
  - Windows 10
header:
  image: /assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/header.png
  og_image: /assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/og.png
---

Continuamos con la serie de post dedicados a [Hyper-V](https://www.albertopc.com/blog/Que-es-Microsoft-Hyper-V/). En esta ocasión vamos a ver como podemos habilitarlo en Windows 10.

Existen varias maneras de hacer esto, en este caso vamos a hacerlo de 2 maneras:

* Panel de control de Windows 10 mediante interfaz gráfica
* PowerShell

Cabría destacar que no es necesario descargar ningún software adicional ya que Hyper-V está integrado en nuestro sistema y solo es necesario habilitarlo.

## Requisitos previos

Antes de proceder a habilitar la característica de Hyper-V es necesario comprobar una serie de requisitos que son indispensables:

* Tener una versión de Windows 10 Professional, Enterprise o Education de 64 bits. Las versiones Home de Windows 10 no tienen disponible la característica de Hyper-V.
* Procesador de 64 bits con soporte SLAT (Second Level Address Translation).
* Procesador con CPU con capacidad de virtualización. (VT-x en Intel y AMD-V en AMD).
* Tener activada la capacidad de virtualización en la BIOS.
* Un mínimo de 4 GB de memoria RAM.

Ahora vamos a pasar a comprobar cada uno de estos puntos.

### Comprobar versión de Windows 10

En primer lugar, vamos a comprobar que versión de Windows 10 tenemos en nuestro equipo en el caso de que la desconozcamos.

El primer paso es pulsar con el botón derecho del ratón sobre inicio y acceder a *Sistema*.

![Comprobar version de Windows 10 - Sistema]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/1 - Comprobar version W10 - sistema.png){: .align-center}

Ahora nos aparecerá otra ventana en la que seleccionaremos la opción *Acerca de* donde podremos ver las especificaciones del dispositivo y las especificaciones de Windows.

En las especificaciones del sistema vemos el tipo de sistema que tenemos, y comprobar si es de 64 bits. Más abajo encontramos las especificaciones de Windows donde podemos ver la edición de Windows 10 que tenemos instalada en nuestro equipo.

![Comprobar version de Windows 10 - version]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/2 - Comprobar version W10 - version.PNG){: .align-center}

### Comprobar si nuestro procesador tiene soporte SLAT

SLAT (Second Level Address Translation) es una tecnología a nivel de procesador que se encarga de traducir las direcciones de memoria virtuales de los sistemas operativos invitados que virtualizamos en direcciones de memoria físicas. Así, esta tecnología libera al sistema operativo invitado en la traducción de las direcciones de memoria, lo que conlleva a una mejora del rendimiento.

La tecnología SLAT la podemos encontrar tanto en procesadores Intel como en procesadores AMD, pero con diferente terminología. En procesadores Intel la podemos encontrar como EPT (Extended Page Tables, en español, Tablas de páginas extendidas) y en AMD como RVI (Rapid Virtual Indexing, en español, Indexado Rápido de Virtualización).

Una manera sencilla de comprobar si nuestro procesador tiene soporte SLAT es mediante la herramienta CoreInfo que nos proporciona Microsoft, la cual podemos descargar desde el siguiente enlace:

[Descargar CoreInfo](https://docs.microsoft.com/es-es/sysinternals/downloads/coreinfo)

Una vez nos hayamos descargado la herramienta la descomprimimos y accedemos a su ubicación mediante un CMD o una consola de PowerShell con privilegios de administrador.

Ya solo nos queda ejecutar el siguiente comando:

`coreinfo -v`

Se nos mostrará la información en la que veremos si nuestro procesador tiene soporte SLAT.

![Comprobar soporte SLAT]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/3 - Comprobar soporte SLAT.png){: .align-center}

### Comprobar si nuestro procesador tiene capacidades de virtualización

Para comprobar si nuestro procesador soporta las instrucciones de virtualización VT-x de Intel o AMD-v de AMD podemos hacerlo de varias maneras. Aquí vamos a ver 2 de ellas:

Podemos consultar nuestro modelo de procesador pulsando el botón derecho del ratón sobre el botón inicio y accediendo a *Sistema*, en la opción *Acerca de* podemos ver nuestro modelo de procesador.

![Comprobar modelo de procesador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/4 - comprobar modelo de procesador.png){: .align-center}

Una vez conozcamos nuestro modelo exacto podemos acceder a las plataformas online de [AMD](https://products.amd.com/es-es) e [Intel](https://ark.intel.com/es-es) y consultar las características buscando las tecnologías VT-x en caso de procesadores Intel, o AMD-v en caso de procesadores AMD.

Otra de las maneras que tenemos para hacer esta comprobación es mediante software de terceros como puede ser [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html). CPU-Z es un software gratuito que nos brinda una extensa información sobre nuestro procesador.

Una vez descargado e instalado, ejecutamos el programa y en la pestaña CPU tenemos la zona de *Instructions* que nos da información sobre todo el conjunto de instrucciones que soporta nuestra CPU, entre las cuales tendremos que buscar las instrucciones VT-x en caso de Intel o AMD-v en caso de que nuestro procesador sea AMD.

![Comprobar vt-x_amd-v]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/5 - Comprobar vt-x_amd-v.png){: .align-center}

### Comprobar si la virtualización está activada

Una vez hayamos comprobado que nuestro sistema operativo y nuestro procesador cumplen con los requisitos necesarios para poder activar Hyper-V, toca comprobar si tenemos activada la virtualización.

Una manera sencilla en Windows 10 es acceder al administrador de tareas mediante la combinación de teclas Ctrl+Alt+supr o haciendo uso del botón derecho del ratón sobre el menú inicio y Administrador de tareas.

Una vez accedamos al administrador de tareas pulsamos en la pestaña *Rendimiento*, posteriormente pulsamos sobre CPU en la zona izquierda y debajo de la gráfica se nos muestra la información de si la virtualización está habilitada. 

![Comprobar virtualizacion activada]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/6 - comprobar virtualizacion activada.png){: .align-center}

En caso de no estarla debemos activarla accediendo a la BIOS de nuestro equipo, siempre que esta la soporte.

### Comprobar cantidad de memoria de nuestro equipo

Microsoft nos especifica que para poder hacer uno de Hyper-V debemos de disponer de al menos 4 GB de RAM. Para los que no sepan que cantidad de memoria disponen en su equipo vamos a verlo de una manera muy sencilla.

Accediendo al administrador de tareas como anteriormente mediante la pestaña *Rendimiento* podemos verlo, pero en este caso pulsaremos sobre *Memoria*. Aquí podremos ver la cantidad y el tipo de memoria RAM que disponemos.

![Comprobar memoria ram]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/7 - Comprobar memoria ram.png){: .align-center}

Si cumples todos estos puntos estas list@ para habilitar Hyper-V en tu equipo.

## Habilitar Hyper-V

Como comentaba al principio de este post Hyper-V es una característica integrada en Windows 10, por lo que no es necesario ninguna descarga ni instalación de software adicional por parte del usuario.

Para habilitar Hyper-V tenemos varias opciones y en este caso trataremos dos de ellas, mediante el panel de control de Windows 10 a través de interfaz gráfica y desde una consola de PowerShell.

### Habilitar Hyper-V mediante el panel de control de Windows 10

Para habilitar Hyper-V mediante el panel de control debemos hacer uso del botón derecho del ratón sobre el icono de inicio de Windows y acceder a *Aplicaciones y características*.

![Habilitar Hyper-v aplicaciones y caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/8 - habilitar hyper-v aplicaciones y caracteristicas.png){: .align-center}

En la nueva ventana que se nos abre accedemos a *Programas y características*.

![Programas y caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/9 - Programas y caracteristicas.png){: .align-center}

Se nos volverá a abrir una nueva ventana en la que tendremos que acceder a *Activar o desactivar las características de Windows*.

![Activar o desactivar caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/10 - activar o descativar caracteristicas de windows.png){: .align-center}

Ahora nos aparecerá un listado de características de Windows disponibles en las que debemos de buscar Hyper-V y habilitarlo. Como vemos junto con Hyper-V se nos habilitan más servicios que nos permitirán la administración del hipervisor mediante interfaz gráfica y texto haciendo uso de PowerShell.

![Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/11 - Hyper-V.PNG){: .align-center}

Solo nos queda pulsar en Aceptar y empezará el proceso para habilitar Hyper-V. Una vez concluido debemos reiniciar el equipo para hacer uso de la nueva característica.

### Habilitar Hyper-V mediante PowerShell

Para poder habilitar Hyper-V mediante PowerShell abre una consola de PowerShell como administrador e introduce el siguiente comando:

`Enable-WindowsOptionalFeature -Online -FeatureName:Microsoft-Hyper-V -All`

Una vez introducido el comando empezará el proceso de habilitar la característica de Hyper-V.

![Activar Hyper-V PowerShell]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/12 - Activar Hyper-v ps.PNG){: .align-center}

Una vez concluido el proceso se nos pedirá reiniciar el equipo.

![Reiniciar PowerShell]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/13 - reiniciar ps.PNG){: .align-center}

Tanto si hemos habilitado Hyper-V mediante interfaz gráfica como por PowerShell al volver a iniciar sesión después del reinicio deberemos encontrar entre nuestras aplicaciones el Administrador de Hyper-V.

![Administrador Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/14- administrador hyper-v.PNG){: .align-center}

Hasta aquí el post, espero que os haya sido útil e interesante. En los próximos posts veremos cómo es la interfaz del Administrador de Hyper-V y comenzaremos a crear nuestras primeras máquinas virtuales.

Comentad cualquier duda que os surja o cualquier sugerencia. 

Un saludo y hasta el próximo post.