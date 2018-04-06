---
title: "Creación de máquinas virtuales en Hyper-V"
tags:
  - Virtualización
  - Hyper-V
  - Microsoft
header:
  image: /assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/header.png
  #overlay_image: /assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/header.png
  #overlay_filter: 0.5
  og_image: /assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/og.png
---

Seguimos con otro post relativo a Hyper-V. En este caso nos ocupa la creación de las máquinas virtuales, donde se verá las dos formas que existen de crearlas.

Para comenzar, se debe acceder al [Administrador de Hyper-V]( https://www.albertopc.com/blog/Conociendo-el-Administrador-de-Hyper-V/) desde la barra de menús mediante el botón *Acción* o desde el panel izquierdo de *Acciones*. En ambos lugares se pueden observar las dos opciones de creación.

![Administrador Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/1_AdministradorHyper-V.PNG){: .align-center}

En primer lugar, se aborda la opción de *Creación rápida…*, en la que se permite la creación de una máquina virtual con unas opciones de configuración predeterminadas y sin complicaciones para el usuario.

![Creación rápida máquina virtual]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/2_Creacion_rapida.png){: .align-center}

Como se observa, se ofrece un sistema operativo Windows 10 como opción por defecto para la creación de la máquina virtual, sin embargo, el usuario tiene la opción de seleccionar una imagen de instalación que posea de manera local.

Si se despliega *Más opciones* es posible el cambio de nombre con el que se identificará la máquina virtual en el Administrador de Hyper-V, además de permitir elegir el tipo de red con el que queremos unir nuestra máquina. Esto, se tratará en post futuros, por el momento el *Modificador predeterminado* proporciona una conexión a internet mediante la maquina host o anfitriona.

Una vez revisadas y modificadas estas opciones a gusto del usuario, se puede pulsar sobre *Crear máquina virtual*.

En el caso de haber elegido la imagen de Windows 10 que nos proporciona Hyper-V de manera predeterminada, comenzará la descarga y extracción de dicha imagen para la creación de la máquina virtual.

![Descarga Windows 10 creacion rapida]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/3_Descarga_Windows_10_creacion_rapida.png){: .align-center}

Una vez terminado el proceso se notificará al usuario.

![Creacion compretada creacion rapida]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/4_Creacion_Completada_creaccion_rapida.png){: .align-center}

Creada la máquina, el usuario, tiene la posibilidad de conectarse directamente a la máquina o editar su configuración. Si se selecciona esta opción, aparecerá una ventana como la que se muestra en la imagen inferior, en la que se puede cambiar la configuración de la máquina según las necesidades del usuario.

![Configuracion maquina creacion rapida]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/5_configuracion_maquina_creacion_rapida.png){: .align-center}

A continuación, se pasa a ver la creación de la máquina de una manera más personalizada. Para ello, como se ha visto anteriormente, se puede acceder mediante la barra de menús pulsando sobre la opción *Acción* &rarr; *Nuevo* &rarr; *Máquina virtual…*.

Si se procede de esta forma, aparecerá un asistente que guiará al usuario durante todo el proceso de creación de la máquina virtual. En este momento, es posible seguir el asistente o, por el contrario finalizarlo y la máquina virtual será creada con una configuración por defecto.

![Asistente creacion maquina virtual]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/6_asistente_creacion_maquina.PNG){: .align-center}

Si se decide continuar con el asistente, éste, comienza definiendo el nombre de la máquina virtual y la ubicación de los archivos de configuración de ésta. Se tiene la opción de almacenarla en la ubicación que se propone, o una personalizada activando la opción. Se advierte que, si se planea realizar puntos de control de la máquina, la ubicación que se elija ha de tener el espacio suficiente para almacenarlos.

![Definir noimbre y ubicacion de la maquina]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/7_nombre_y_ubicacion.PNG){: .align-center}

El siguiente paso del asistente permite seleccionar la generación de la máquina virtual. Se puede elegir entre *Generación 1* y *Generación 2*:

* **Generación 1**: permite la ejecución de sistemas operativos invitados de 32 y 64 bits y tiene un firmware basado en BIOS.

* **Generación 2**: solo ejecuta sistemas operativos invitados de 64 bits, tiene un firmware basado en UEFI y permite disponer de las últimas características de virtualización.

Es muy importante definir esta generación correctamente, ya que una vez creada la máquina **no es posible modificarla**, siendo básica para la correcta ejecución de los sistemas operativos invitados.


![Definir generación de la maquina virtual]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/8_generacion.PNG){: .align-center}

A continuación, se configurará la memoria de inicio. Esta es la cantidad de memoria física del host que la máquina reserva para su arranque. Posteriormente a la creación de la máquina, se puede configurar la memoria mínima y máxima de la que puede hacer uso. También está disponible la opción de que la máquina haga uso de la memoria dinámica, la cual permite a Hyper-V gestionar de manera automática la memoria que no se está usando, para repartirla entre las demás máquinas virtuales y el equipo anfitrión.

![Asignacion de memoria a maquina virtual]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/9_memoria.PNG){: .align-center}

Continuando, se pasa a la configuración de red. Existe la opción de mantener la máquina sin conexión o conectarla a una de las redes de las que se dispongan.

![Configuracion funciones de red]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/10_red.PNG){: .align-center}

El siguiente paso permite la configuración de un disco duro virtual. Disponemos de tres opciones de configuración:

* **Crea un disco duro virtual**: se crea un disco duro virtual nuevo para la máquina que se está configurando. Se puede definir un nombre, una ubicación y un tamaño. El tamaño será definido teniendo en cuenta el desempeño que vaya a realizar la máquina, con un máximo de 64 TB.

* **Usar un disco virtual existente**: se puede seleccionar un disco virtual que ya exista para la máquina que se está configurando.

* **Exponer un disco duro virtual más adelante**: mantener la máquina sin conectarle ningún disco duro y añadirlo posteriormente mediante las opciones de configuración de ésta.

![Conectar disco duro virtual]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/11_hdd.PNG){: .align-center}

Posteriormente, se encuentra la opción de configurar un medio de instalación, escogiendo entre las tres posibles acciones siguientes :

* **Instalar un sistema operativo mas tarde**: se configurará la forma de instalación de manera posterior a la creación de la máquina mediante las opciones de configuración de ésta.

* **Instalar un sistema operativo desde un archivo de imagen de arranque**: se realizará la instalación mediante un archivo de imagen ISO.

* **Instalar un sistema operativo desde un servidor de instalación en red**: la instalación se realizará a partir de una conexión de red a un servidor. Para esto, es imprescindible tener correctamente configurada una conexión de red.

![Opciones de instalacion]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/12_opciones_de_instalcion.PNG){: .align-center}

El último paso que ofrece el asistente, es un resumen de toda la configuración para la creación de la máquina virtual. Si se desea modificar alguna de las opciones, se puede volver a cualquier paso previo de la configuración desde la lista disponible ubicada a la derecha de la ventana.

![Resumen configuracion]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/13_resumen.PNG){: .align-center}

Una vez finalizado el asistente, la máquina será creada y se presentará en el listado del Administrador de Hyper-V.

![Maquina creada]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-04-06-Creacion-de-maquinas-virtuales-en-Hyper-V/14_maquina_creada.PNG){: .align-center}

Desde este momento, ya se tendría disponible la máquina para poder ejecutarla o acceder sus opciones de configuración, las cuales se verán en el próximo post de forma más exhaustiva.

Espero que el post sea de ayuda y ¡hasta la próxima!.

Un saludo.