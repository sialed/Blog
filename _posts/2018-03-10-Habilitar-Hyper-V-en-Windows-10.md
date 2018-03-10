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

El primer paso es pulsar con el botón derecho del ratón sobre inicio y acceder a Sistema.

![Comprobar version de Windows 10]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-03-10-Habilitar-Hyper-V-en-Windows-10/1 - Comprobar version W10 - sistema.png)

Ahora nos aparecerá otra ventana en la que seleccionaremos la opción “Acerca de” donde podremos ver las especificaciones del dispositivo y las especificaciones de Windows.

En las especificaciones del sistema vemos el tipo de sistema que tenemos, y comprobar si es de 64 bits. Más abajo encontramos las especificaciones de Windows donde podemos ver la edición de Windows 10 que tenemos instalada en nuestro equipo.
