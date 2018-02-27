---
title: "¿Qué es Microsoft Hyper-V?"
tags:
  - Virtualizacion
  - Hyper-V
header:
  image: /assets/images/posts/2018-02-23-Que-es-Microsoft-Hyper-V/header.jpg
  og_image: /assets/images/posts/2018-02-23-Que-es-Microsoft-Hyper-V/og.jpg
---

Hay muchas ocasiones en las que nos es necesario utilizar varias máquinas para ejecutar varios sistemas operativos o simular algún tipo de infraestructura. En muchos de estos casos, no disponemos del número de máquinas físicas que necesitamos para esos fines, y es con Hyper-V con lo que podremos ejecutar varios sistemas operativos como máquinas virtuales en Windows.

Hyper-V nos proporciona virtualización de hardware, por lo que nos permite ejecutar varios sistemas operativos en el mismo equipo físico y mantener estos sistemas aislados entre sí. Además de esto, podremos crear discos duros virtuales, conmutadores virtuales y demás dispositivos que se podrán agregar a nuestras máquinas virtuales.

![alt]({{ site.url }}{{ site.baseurl }}/assets/images/posts/2018-02-23-Que-es-Hyper-V/arquitectura_hyperv.png)

Como vemos en la imagen, Hyper-V se ejecuta directamente sobre el hardware real de nuestra máquina. Esto es una ventaja, ya que nos permite un mayor rendimiento y una mayor escalabilidad. Sobre Hyper-V encontramos ejecutándose tanto el sistema operativo host, que hace referencia a nuestro propio sistema Windows 10 o Windows Server, como los sistemas que virtualizamos.

Las máquinas se ejecutan de manera totalmente aisladas unas de otras lo cual supone una gran ventaja, ya que si se produce un error en una de ellas, ninguna otra se verá afectada.

En Hyper-V podemos virtualizar un gran número de sistemas operativos diferentes, admite tanto versiones de Windows, Linux o de FreeBSD.

Cabría destacar que virtualizar no nos exime de seguir la política de licencias de cada uno de los sistemas operativos invitados.

Al virtualizar también tenemos algunas desventajas o limitaciones. Si queremos utilizar alguna aplicación con características especiales de hardware sobre un sistema virtualizado, es posible que no funcione de manera correcta, como ocurre con los controladores. Es posible que Hyper-V no gestione bien o no soporte este tipo de aplicaciones.

Al habilitar el módulo de Hyper-V, es posible que aplicaciones sensibles a latencia tengan ciertos problemas, debido a que el sistema operativo host también se ejecuta sobre la capa de virtualización de Hyper-V. Aunque este se verá menos afectado, ya que tiene acceso completo al hardware real de la máquina.

Bueno, esto ha sido un repaso por encima de lo que es Hyper-V, algunas de sus ventajas y desventajas. En próximos posts veremos cómo habilitarlo en sistemas Windows y como empezar a crear nuestras primeras máquinas virtuales con este potente software de virtualización.

Os animo a que comentéis vuestras dudas y sugerencias. ¿Conocías Hyper-V?, ¿Te parece interesante?

Un saludo y hasta el próximo post.