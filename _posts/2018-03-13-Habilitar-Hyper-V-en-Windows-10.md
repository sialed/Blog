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
  image: /assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/header.png
  og_image: /assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/og.png
---

Continuemos con otro post dentro de la serie dedicados a [Hyper-V](https://www.albertopc.com/blog/Que-es-Microsoft-Hyper-V/). En esta ocasión, vamos a ver cómo podemos habilitarlo en Windows 10.

Existen distintas formas de llevarlo a cabo, pero en este caso nos centraremos principalmente en dos de ellas:

* Panel de control de Windows 10 mediante interfaz gráfica
* PowerShell

Cabría destacar que no es necesario descargar ningún software adicional ya que Hyper-V está integrado en nuestro sistema y solo es necesario habilitarlo.

## Requisitos previos

Antes de proceder a habilitar la característica de Hyper-V es necesario comprobar una serie de requisitos indispensables:

* Edición de Windows 10 Professional, Enterprise o Education de 64 bits. Las versiones Home de Windows 10 no tienen disponible la característica de Hyper-V.
* Procesador de 64 bits con soporte SLAT (Second Level Address Translation).
* Procesador con CPU con capacidad de virtualización. (VT-x en Intel y AMD-V en AMD).
* Capacidad de virtualización en la BIOS activa.
* Mínimo de 4 GB de memoria RAM.
* 
Analicemos a continuación estos requisitos previos.

### Comprobar edición de Windows 10

En primer lugar, comprobemos que versión de Windows 10 existe en nuestro equipo en el caso de que no la conozcamos.

Pulsamos con el botón derecho del ratón sobre inicio y acceder a *Sistema*.

![Comprobar version de Windows 10 - Sistema]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/1 - Comprobar version W10 - sistema.png){: .align-center}

Posteriormente, nos aparecerá otra ventana en la que seleccionaremos la opción *Acerca de* donde podremos ver las especificaciones del dispositivo y las especificaciones de Windows.

En las especificaciones del sistema, podemos observar el tipo de sistema que tenemos, y comprobar si es de 64 bits. Más abajo, se encuentran las especificaciones de Windows donde se ve la edición de Windows 10 que está instalada en nuestro equipo.

![Comprobar version de Windows 10 - version]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/2 - Comprobar version W10 - version.PNG){: .align-center}

### Comprobar si nuestro procesador tiene soporte SLAT

SLAT (Second Level Address Translation) es una tecnología a nivel de procesador que se encarga de traducir las direcciones de memoria virtuales de los sistemas operativos invitados que virtualizamos en direcciones de memoria físicas. De este modo, esta tecnología libera al sistema operativo invitado en la traducción de las direcciones de memoria, lo que conlleva a una mejora del rendimiento.

La tecnología SLAT la podemos encontrar tanto en procesadores Intel como en procesadores AMD, pero con diferente terminología. En procesadores Intel se presenta como EPT (Extended Page Tables, en español, Tablas de páginas extendidas) y en AMD como RVI (Rapid Virtual Indexing, en español, Indexado Rápido de Virtualización).

Una manera sencilla de comprobar si nuestro procesador tiene soporte SLAT, sería haciendo uso de la herramienta CoreInfo que nos proporciona Microsoft, la cual podemos descargar desde el siguiente enlace:

[Descargar CoreInfo](https://docs.microsoft.com/es-es/sysinternals/downloads/coreinfo)

Una vez descargada, la descomprimimos y accedemos a su ubicación mediante un CMD o una consola de PowerShell con privilegios de administrador.

Ya solo queda ejecutar el siguiente comando:

`coreinfo -v`

La información que confirmará si nuestro procesador tiene soporte SLAT será mostrada.

![Comprobar soporte SLAT]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/3 - Comprobar soporte SLAT.png){: .align-center}

### Comprobar si nuestro procesador tiene capacidades de virtualización

Para comprobar si nuestro procesador soporta las instrucciones de virtualización VT-x de Intel o AMD-V de AMD existen diversas maneras. Centrémonos en dos de ellas:

Es posible consultar nuestro modelo de procesador pulsando el botón derecho del ratón sobre el botón inicio y accediendo a *Sistema*. En la opción *Acerca de* es donde encontraremos indicado dicho modelo.

![Comprobar modelo de procesador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/4 - comprobar modelo de procesador.png){: .align-center}

Una vez conozcamos nuestro modelo exacto, se podrá acceder a las plataformas online de [AMD](https://products.amd.com/es-es) e [Intel](https://ark.intel.com/es-es) y consultar las características, buscando las tecnologías VT-x en caso de procesadores Intel, o AMD-V en caso de procesadores AMD.

Otra de las vías existentes para llevar a cabo esta comprobación es haciendo uso del software de terceros. Ejemplo de ello, [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html). CPU-Z es un software gratuito que nos brinda extensa información sobre nuestro procesador.

Una vez descargado e instalado, se ejecuta el programa. Es en la pestaña *CPU*, donde se encuentra la zona *Instructions* que presenta la información sobre todo el conjunto de instrucciones que soporta nuestra CPU, entre las cuales tendremos que buscar las instrucciones VT-x en caso de Intel, o AMD-V en caso de que nuestro procesador sea AMD.

![Comprobar vt-x_amd-v]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/5 - Comprobar vt-x_amd-v.png){: .align-center}

### Comprobar si la virtualización está activada

Una vez comprobado que nuestro sistema operativo y nuestro procesador cumplen con los requisitos necesarios para poder activar Hyper-V, toca confirmar si tenemos activada la virtualización.

Una manera sencilla en Windows 10 sería acceder al administrador de tareas mediante la combinación de teclas Ctrl+Alt+supr o haciendo uso del botón derecho del ratón sobre el menú inicio y *Administrador de tareas*.

En el momento en que accedamos al administrador de tareas, pulsamos en la pestaña *Rendimiento*, y a continuación pulsamos sobre *CPU* en la zona izquierda. Debajo de la gráfica se muestra la información relativa a si la virtualización está efectivamente habilitada. 

![Comprobar virtualizacion activada]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/6 - comprobar virtualizacion activada.png){: .align-center}

En caso de no estarla, habría que activarla mediante el acceso a la BIOS de nuestro equipo, siempre que ésta la soporte.

### Comprobar cantidad de memoria de nuestro equipo

Microsoft nos especifica que, para poder ejecutar Hyper-V de manera correcta, hemos de disponer de al menos 4 GB de RAM. Veamos, para aquellos que desconozcan la cantidad de memoria de la que disponen en su equipo, cómo averiguarla fácilmente. 

Accediendo al administrador de tareas, al igual que se indicó anteriormente mediante la pestaña *Rendimiento*, es posible verlo, sin embargo en este caso, pulsaremos sobre *Memoria*. Aquí podremos ver la cantidad y el tipo de memoria RAM de la que disponemos.

![Comprobar memoria ram]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/7 - Comprobar memoria ram.png){: .align-center}

Si se cumplen todos estos puntos, estás list@ para habilitar Hyper-V en tu equipo.

## Habilitar Hyper-V

Como se comentó al inicio de este post, Hyper-V es una característica integrada en Windows 10, por lo que no es necesario ninguna descarga ni instalación de software adicional por parte del usuario.

Para habilitar [Hyper-V](https://www.albertopc.com/blog/Que-es-Microsoft-Hyper-V/) existen varias opciones. En este caso, nos centraremos en dos de ellas: habilitación mediante el panel de control de Windows 10 a través de interfaz gráfica y habilitación desde una consola de PowerShell.

### Habilitar Hyper-V mediante el panel de control de Windows 10

Para habilitar Hyper-V mediante el panel de control es necesario hacer uso del botón derecho del ratón sobre el icono de inicio de Windows y acceder a *Aplicaciones y características*.

![Habilitar Hyper-v aplicaciones y caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/8 - habilitar hyper-v aplicaciones y caracteristicas.png){: .align-center}

En la nueva ventana que se abre accedemos a *Programas y características*

![Programas y caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/9 - Programas y caracteristicas.png){: .align-center}

Se abrirá una nueva ventana en la que tendremos que acceder a *Activar o desactivar las características de Windows*

![Activar o desactivar caracteristicas]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/10 - activar o descativar caracteristicas de windows.png){: .align-center}

Consecutivamente, aparecerá un listado de características disponibles en Windows dentro de las que debemos buscar Hyper-V y habilitarlo. Como se observa, junto a Hyper-V, se habilitan más servicios que nos permitirán la administración del hipervisor mediante interfaz gráfica y texto, haciendo uso de PowerShell.

![Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/11 - Hyper-V.PNG){: .align-center}

Finalmente, solo queda pulsar en Aceptar y empezará el proceso para habilitar Hyper-V. Una vez concluido, será necesario reiniciar el equipo para poder hacer uso de la nueva característica. 

### Habilitar Hyper-V mediante PowerShell

Para poder habilitar Hyper-V mediante PowerShell será necesario comenzar abriendo una consola de PowerShell como administrador e introducir el siguiente comando:

`Enable-WindowsOptionalFeature -Online -FeatureName:Microsoft-Hyper-V -All`

Una vez introducido el comando empezará el proceso de habilitar la característica de Hyper-V.

![Activar Hyper-V PowerShell]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/12 - Activar Hyper-v ps.PNG){: .align-center}

Una vez concluido, será de igual modo necesario reiniciar el equipo.

![Reiniciar PowerShell]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/13 - reiniciar ps.PNG){: .align-center}

Cabe destacar que, tanto si hemos habilitado Hyper-V mediante interfaz gráfica como por PowerShell, al volver a iniciar sesión después del reinicio habremos de encontrar entre nuestras aplicaciones el Administrador de Hyper-V.

![Administrador Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-13-Habilitar-Hyper-V-en-Windows-10/14- administrador hyper-v.PNG){: .align-center}

Hasta aquí el post, espero que os haya sido útil e interesante. En los próximos posts veremos cómo es la interfaz del Administrador de Hyper-V y comenzaremos a crear nuestras primeras máquinas virtuales.

No dudéis en comentar cualquier duda que os surja o cualquier sugerencia. 

Un saludo y hasta el próximo post.