# Oracle VirtualBox

![][oracle_virtualbox_logo]

## ¿Qué es VirtualBox?

__VirtualBox__ es un software para virtualización, tambien conocido como hipervisor de tipo 2, que se utiliza para virtualizar OS dentro de nuestro ordenador, creando lo que se conoce como VM. Un hipervisor de tipo 2 se diferencia con los de tipo 1 en que necesita un sistema operativo para funcionar, a diferencia de los de tipo 1 en los que el propio hipervisor funciona sobre el hardware o máquina host.

Existen varios factores a tener en cuenta cuando necesitamos hacer uso de un hipervisor, pero generalmente VirtualBox, y los hipervisores de tipo 2 en general, se usan cuando no necesitamos destinar la máquina host al completo para realizar tareas de virtualización, por ejemplo, a la hora de probar software.

Para ejecutar VirtualBox no se necesita pagar ninguna licencia.

Su compatibilidad se extiende entre prácticamente todas las versiones de Windows, un gran número de versiones de macOS y otras tantas distribuciones de Linux, aunque también podremos encontrar perfiles para sistemas menos comunes como Solaris, OS/2, DOS, QNX, Novell, BeOS y otros sistemas operativos que queramos probar o utilizar sin tener que montar un equipo específicamente para ellos.

## ¿Para qué se utiliza VirtualBox?

VirtualBox sirve principalmente para virtualizar sistemas operativos que no podamos o no queramos ejecutar de forma nativa en nuestro equipo. Esto servirá también para trabajar sobre esos sistemas operativos con un relativamente amplio abanico de posibilidades, pues una de las principales virtudes de una VM es el aislamiento que ello proporciona.

Gracias a este aislamiento propio de las VMs, podemos crear por ejemplo un Sandbox y que consiste principalmente en un espacio de ejecución aislado donde podemos ejecutar aplicaciones de fuentes sin verificar o sospechosas.

Enlazando con este tipo de software, otro uso que le podemos dar a una VM es el de apoyarnos en términos de compatibilidad, y es que algunos programas determinados, aunque cuenten con protección contra su ejecución en máquinas virtuales, no pueden funcionar en versiones más modernas del sistema operativo para el que se diseñaron, así que este es un método en ocasiones imprescindible incluso para trabajar, como ocurre en ocasiones con los sistemas de diagnosis de vehículos, cuyo hardware acostumbra a estar diseñado para funcionar con una versión de Windows en específico.

## Requisitos de VirtualBox

Para ejecutar VirtualBox en tu máquina, necesitas:

* __Hardware x86__: cualquier procesador Intel o AMD reciente debería servir razonablemente potente.
* __Memoria RAM__: dependiendo de qué sistemas operativos invitados quieras ejecutar, necesitarás al menos 512 MB de RAM (pero probablemente más, y cuanto más, mejor). Básicamente, necesitarás lo que tu sistema operativo anfitrión necesita para funcionar cómodamente, más la  cantidad que necesita el sistema operativo invitado. Entonces, si quieres ejecutar Windows 8.1 en Windows 7, probablemente no disfrutarás mucho la experiencia con menos de 2 GB de RAM. Verifica los requisitos mínimos de RAM del sistema operativo invitado; a menudo se negarán a instalarse si se les da menos. A veces, en lugar de negarse, pueden presentar fallos. Por lo tanto, necesitarás esa cantidad solo para el invitado, más la memoria que tu sistema operativo normalmente necesita.
* __Espacio en el disco duro__: mientras que VirtualBox en sí es muy liviano (una instalación típica solo necesitará unos 30 MB de espacio en disco), las máquinas virtuales requerirán archivos bastante grandes en el disco para representar su propio almacenamiento en disco duro. Entonces, para instalar Windows 8, por ejemplo, necesitarás un archivo que fácilmente crecerá a varios 10 GB de tamaño.
* __OS anfitrión compatible__: Actualmente VirtualBox soporta Windows, muchas distribuciones de Linux, Mac OS X, Solaris y OpenSolaris. Consulta el manual del usuario de la versión de VirtualBox que estás usando para saber qué versiones son compatibles. Para la última versión de VirtualBox.


[oracle_virtualbox_logo]: ./img/oracle_virtualbox/oracle_virtualbox_logo.png "Oracle VirtualBox Logo"