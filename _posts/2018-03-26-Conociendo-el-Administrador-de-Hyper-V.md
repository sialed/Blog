---
title: "Conociendo el Administrador de Hyper-V"
tags:
  - Virtualización
  - Hyper-V
  - Microsoft
  - Windows 10
header:
  image: /assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/header.png
  og_image: /assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/og.png
---

Tras seguir las indicaciones suministradas en el post anterior, y una vez hayamos [habilitado Hyper-V]( https://www.albertopc.com/blog/Habilitar-Hyper-V-en-Windows-10/) en Windows, tendremos a nuestra disposición el administrador de Hyper-V, el cual nos permite gestionar las máquinas virtuales mediante una interfaz gráfica.

El administrador de Hyper-V puede encontrarse como una aplicación más del sistema, por ello, accederemos a él mediante el menú inicio y *Herramientas Administrativas*.

![Administrador Hyper-V en menu inicio]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/1-adminsitrador_menu_inicio.PNG){: .align-center}

Cuando iniciamos el administrador de Hyper-V nos encontramos con una aplicación con un aspecto similar a este:

![Administrador Hyper-V]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/2-administrador_hyper_V.PNG){: .align-center}

Como se puede observar, la aplicación está dividida en varias secciones, la cuales será descritas a lo largo del post.

Comencemos analizando la aplicación desde la parte izquierda de la misma, donde encontramos el administrador en sí mismo y los servidores a los que tenemos acceso desde él, en este caso, es nuestro propio equipo.

![Servidores Administrador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/3-servidores_adminsitrador.png){: .align-center}

Aquí, se encuentra una lista de todos los servidores sobre los que tenemos control desde el administrador de Hyper-V, como veremos en otras ocasiones, es posible conectarse a servidores Hyper-V para controlar las máquinas virtuales que se estén ejecutando de manera remota.

Analicemos ahora la zona central del administrador, la cual, está subdividida en 3 zonas:

![Zona central Administrador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/4-zona_central.PNG){: .align-center}

* Máquinas Virtuales: aquí se muestra una lista de todas nuestras máquinas virtuales disponibles. La información proporcionada será sobre el estado de la máquina, el uso de CPU y la memoria que está siendo usa en tiempo real por cada máquina en el momento de ejecutarse.
* Puntos de control: aquí se podrá ver una lista de puntos de control o snapshot que hayamos realizado, con los que podremos restaurar la máquina a un punto anterior.
* Información sobre la máquina virtual: Asta zona nos dará una información adicional sobre la máquina virtual seleccionada. Disponemos de 3 pestañas para filtrar esta información. Resumen, que nos muestra la fecha de creación de la máquina, su versión de configuración o la generación de la máquina. Memoria, muestra información sobre la memoria asignada a la máquina y la que se encuentra en uso mientras se ejecuta. Funciones de red, muestra los adaptadores de red de los que dispone la máquina y las direcciones IP asignadas a cada uno de los adaptadores.

Pasemos a la parte derecha del administrador. Esta zona se divide en dos, una superior, dedicada a la configuración del servidor actual en el que se está actuando y una zona inferior, dedicada a la configuración de la máquina seleccionada o a realizar tratamientos con los puntos de control, según se seleccione.

![Zona derecha Administrador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/5-zona_derecha.PNG){: .align-center}

Como se observa en la imagen, si seleccionamos una máquina de las disponibles en la lista, la zona inferior permite realizar una serie de acciones, entre ellas, conectarse a la máquina, modificar la configuración, eliminar la máquina, crear un punto de control o cambiarle el nombre entre otras.

Cuando seleccionamos un punto de control, estas opciones enunciadas previamente cambian, y nos permiten aplicar el punto de control. Con ello se puede volver a ese punto anterior, exportar un punto de control como una máquina virtual o eliminar un punto de control concreto o incluso subárboles de los puntos de control.

![Zona derecha Administrador]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-26-Conociendo-el-Administrador-de-Hyper-V/6-opciones_punto_de_control.PNG){: .align-center}

Esta es la estructura predeterminada del administrador de Hyper-V, la cual se puede modificar eliminando columnas, si se desea una interfaz más simple.

Espero que os haya sido de ayuda para entender de manera básica como se distribuye la información y las opciones en la interfaz del administrador. Lo iremos tratando en los siguientes posts según vayamos usando sus opciones, incluso se dedicará algún post a algún aspecto concreto a destacar.

Os animo a comentar cualquier duda o sugerencia y a compartirlo.

Un saludo y hasta el próximo post.