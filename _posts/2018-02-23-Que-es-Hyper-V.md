---
title: "¿Qué es Hyper-V?"
header:
  image: /assets/images/posts/2018-02-23-Que-es-Hyper-V/header.jpg
  og_image: /assets/images/posts/2018-02-23-Que-es-Hyper-V/og.jpg
---

Hay muchas ocasiones en la que nos es necesario utilizar varias máquinas para ejecutar varios sistemas operativos, o simular algún tipo de infraestructura. En muchos de estos casos, no disponemos del número de máquinas físicas que necesitamos para esos fines, por lo que gracias a Hyper-V podremos ejecutar varios sistemas operativos como máquinas virtuales en Windows.

Hyper-V nos proporciona virtualización de hardware, por lo que nos permite ejecutar varios sistemas operativos en el mismo equipo físico y mantener estos sistemas aislados entre sí. Además de esto podremos crear discos duros virtuales, conmutadores virtuales y demás dispositivos que se podrán agregar a nuestras máquinas virtuales.

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-02-23-Que-es-Hyper-V/arquitectura_hyperv.png)

Como vemos en la imagen Hyper-V se ejecuta directamente sobre el hardware real de nuestra máquina. Esto es una ventaja ya que nos permite un mayor rendimiento y una mayor escalabilidad. Sobre Hyper-V ya sí encontramos ejecutándose tanto al sistema operativo host, que hay referencia a nuestro propio sistema Windows 10 o Windows Server, como a los sistemas que virtualizamos.

Las máquinas se ejecutan de manera totalmente aisladas unas de otras y esto es una gran ventaja ya que si se produce un error en una de ellas ninguna otra se verá afectada.

En Hyper-V podemos virtualizar un gran número de sistemas operativos diferentes, admite tanto versiones de Windows, Linux como de FreeBSD.

Un punto importante es que virtualizar no nos exime de seguir la política de licencias de cada uno de los sistemas operativos invitados.