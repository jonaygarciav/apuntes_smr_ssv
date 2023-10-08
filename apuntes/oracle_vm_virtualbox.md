# Oracle VM VirtualBox

![][oracle_virtualbox_logo]

## ¿Qué es Oracle VM VirtualBox?

__VirtualBox__ es un software para virtualización, tambien conocido como hipervisor de tipo 2, que se utiliza para virtualizar OS dentro de nuestro ordenador, creando lo que se conoce como VM. Un hipervisor de tipo 2 se diferencia con los de tipo 1 en que necesita un sistema operativo para funcionar, a diferencia de los de tipo 1 en los que el propio hipervisor funciona sobre el hardware o máquina host.

Existen varios factores a tener en cuenta cuando necesitamos hacer uso de un hipervisor, pero generalmente VirtualBox, y los hipervisores de tipo 2 en general, se usan cuando no necesitamos destinar la máquina host al completo para realizar tareas de virtualización, por ejemplo, a la hora de probar software.

Para ejecutar VirtualBox no se necesita pagar ninguna licencia.

Su compatibilidad se extiende entre prácticamente todas las versiones de Windows, un gran número de versiones de macOS y otras tantas distribuciones de Linux, aunque también podremos encontrar perfiles para sistemas menos comunes como Solaris, OS/2, DOS, QNX, Novell, BeOS y otros sistemas operativos que queramos probar o utilizar sin tener que montar un equipo específicamente para ellos.

## ¿Para qué se utiliza Oracle VM VirtualBox?

VirtualBox sirve principalmente para virtualizar sistemas operativos que no podamos o no queramos ejecutar de forma nativa en nuestro equipo. Esto servirá también para trabajar sobre esos sistemas operativos con un relativamente amplio abanico de posibilidades, pues una de las principales virtudes de una VM es el aislamiento que ello proporciona.

Gracias a este aislamiento propio de las VMs, podemos crear por ejemplo un Sandbox y que consiste principalmente en un espacio de ejecución aislado donde podemos ejecutar aplicaciones de fuentes sin verificar o sospechosas.

Enlazando con este tipo de software, otro uso que le podemos dar a una VM es el de apoyarnos en términos de compatibilidad, y es que algunos programas determinados, aunque cuenten con protección contra su ejecución en máquinas virtuales, no pueden funcionar en versiones más modernas del sistema operativo para el que se diseñaron, así que este es un método en ocasiones imprescindible incluso para trabajar, como ocurre en ocasiones con los sistemas de diagnosis de vehículos, cuyo hardware acostumbra a estar diseñado para funcionar con una versión de Windows en específico.

## Requisitos de Oracle VM VirtualBox

Para ejecutar VirtualBox en tu máquina, necesitas:

* __Hardware x86__: cualquier procesador Intel o AMD reciente debería servir razonablemente potente.
* __Memoria RAM__: dependiendo de qué sistemas operativos invitados quieras ejecutar, necesitarás al menos 512 MB de RAM (pero probablemente más, y cuanto más, mejor). Básicamente, necesitarás lo que tu sistema operativo anfitrión necesita para funcionar cómodamente, más la  cantidad que necesita el sistema operativo invitado. Entonces, si quieres ejecutar Windows 8.1 en Windows 7, probablemente no disfrutarás mucho la experiencia con menos de 2 GB de RAM. Verifica los requisitos mínimos de RAM del sistema operativo invitado; a menudo se negarán a instalarse si se les da menos. A veces, en lugar de negarse, pueden presentar fallos. Por lo tanto, necesitarás esa cantidad solo para el invitado, más la memoria que tu sistema operativo normalmente necesita.
* __Espacio en el disco duro__: mientras que VirtualBox en sí es muy liviano (una instalación típica solo necesitará unos 30 MB de espacio en disco), las máquinas virtuales requerirán archivos bastante grandes en el disco para representar su propio almacenamiento en disco duro. Entonces, para instalar Windows 8, por ejemplo, necesitarás un archivo que fácilmente crecerá a varios 10 GB de tamaño.
* __OS anfitrión compatible__: Actualmente VirtualBox soporta Windows, muchas distribuciones de Linux, Mac OS X, Solaris y OpenSolaris. Consulta el manual del usuario de la versión de VirtualBox que estás usando para saber qué versiones son compatibles. Para la última versión de VirtualBox.

## Terminología útil

Al tratar con virtualización hay que familiarizarse con cierta terminología, especialmente los siguientes términos:

* __Sistema operativo anfitrión (Host OS)__: este es el SO del ordenador físico en el cual se instaló VirtualBox. Hay versiones de VirtualBox para Windows, macOS, Linux y hosts de Oracle Solaris.

* __Sistema operativo invitado (Guest OS)__: este es el SO que está corriendo dentro de la VM. Teóricamente, Oracle VM VirtualBox puede ejecutar cualquier SO x86 como DOS, Windows, OS/2, FreeBSD y OpenBSD.

* __Máquina virtual (VM)__: este es el entorno especial que VirtualBox crea para tu SO invitado mientras está en funcionamiento. En otras palabras, ejecutas tu SO invitado en una VM. Normalmente, una VM se muestra como una ventana en el escritorio de tu ordenador. Dependiendo de cuál de las diferentes interfaces de VirtualBox utilices, la VM podría mostrarse en modo de pantalla completa o de forma remota en otro ordenador. Internamente, VirtualBox trata a una VM como un conjunto de parámetros que especifican su comportamiento. Algunos parámetros describen configuraciones de hardware, como la cantidad de memoria y el número de CPUs asignadas. Otros parámetros describen la información del estado, como si la VM está en funcionamiento o guardada.
* __Complementos para invitados (Guest Additions)__: esto se refiere a paquetes de software especiales que se envían con VirtualBox pero diseñados para ser instalados dentro de una VM para mejorar el rendimiento del SO invitado y agregar características adicionales.

## Descripción de las características

A continuación, se muestra un breve resumen de las principales características de Oracle VM VirtualBox:

* __Portabilidad__: Oracle VM VirtualBox se ejecuta en un gran número de sistemas operativos host de 64 bits.

Oracle VM VirtualBox es un hipervisor denominado hosteado, a veces referido como hipervisor tipo 2. Mientras que un hipervisor de metal desnudo o tipo 1 se ejecuta directamente en el hardware, Oracle VM VirtualBox requiere un sistema operativo ya instalado. Por lo tanto, puede ejecutarse junto con aplicaciones existentes en ese host.

En gran medida, Oracle VM VirtualBox es funcionalmente idéntico en todas las plataformas host, y se utilizan los mismos formatos de archivo e imagen. Esto te permite ejecutar máquinas virtuales creadas en un host en otro host con un sistema operativo host diferente. Por ejemplo, puedes crear una máquina virtual en Windows y luego ejecutarla en Linux.

Además, las VM pueden importarse y exportarse fácilmente utilizando el Formato de Virtualización Abierta (OVF), un estándar de la industria creado para este propósito. Incluso puedes importar OVFs que fueron creados con otro software de virtualización.

* __Guest Additions__: carpetas compartidas, ventanas integradas, virtualización 3D, ... Las Guest Additions de Oracle VM VirtualBox es un paquete de software que se puede instalar dentro del OS invitado para mejorar su rendimiento y proporcionar integración y comunicación adicionales con el sistema host. Después de instalar las Guest Additions, una VM soportará el ajuste automático de resoluciones de video, ventanas integradas, gráficos 3D acelerados, entre otras características.

En particular, las Adiciones para Invitados proporcionan carpetas compartidas, que te permiten acceder a archivos en el sistema host desde dentro de una máquina invitada.

* __Soporte de hardware integral__: entre otras características, Oracle VM VirtualBox soporta lo siguiente:

    * _Multiprocesamiento de Invitados (SMP)_: Oracle VM VirtualBox puede presentar hasta 32 CPUs virtuales a cada máquina virtual, independientemente de cuántos núcleos de CPU estén físicamente presentes en tu host.
    * _Soporte de dispositivos USB_: Oracle VM VirtualBox implementa un controlador USB virtual y te permite conectar dispositivos USB arbitrarios a tus máquinas virtuales sin tener que instalar drivers específicos del dispositivo en el host. El soporte USB no está limitado a ciertas categorías de dispositivos.
    * _Compatibilidad con hardware_: Oracle VM VirtualBox virtualiza una vasta gama de dispositivos virtuales, entre ellos muchos dispositivos que normalmente proporcionan otras plataformas de virtualización. Esto incluye controladores de disco duro IDE, SCSI y SATA, varias tarjetas de red virtuales y tarjetas de sonido, puertos serie y paralelos virtuales y un Controlador de Interrupción Programable Avanzado de Entrada/Salida (I/O APIC), que se encuentra en muchos sistemas informáticos. Esto permite la fácil clonación de imágenes de disco de máquinas reales e importación de máquinas virtuales de terceros en Oracle VM VirtualBox.
    * _Soporte completo de ACPI_: la __Interfaz de Configuración y Energía Avanzada (ACPI)__ está totalmente soportada por Oracle VM VirtualBox. Esto permite la fácil clonación de imágenes de disco de máquinas reales o máquinas virtuales de terceros en Oracle VM VirtualBox. Con su único soporte de estado de energía ACPI, Oracle VM VirtualBox incluso puede informar a los sistemas operativos invitados conscientes de ACPI sobre el estado de energía del host. Para sistemas móviles que funcionan con batería, el invitado puede así habilitar el ahorro de energía y notificar al usuario de la energía restante, por ejemplo, en modos de pantalla completa.
    * _Resoluciones multi-pantalla_: las VM de Oracle VM VirtualBox soportan resoluciones de pantalla muchas veces mayores que una pantalla física, permitiéndoles extenderse sobre un gran número de pantallas conectadas al sistema host.
    * _Soporte iSCSI incorporado_: esta característica única te permite conectar una máquina virtual directamente a un servidor de almacenamiento iSCSI sin pasar por el sistema host. La VM accede al objetivo iSCSI directamente sin el sobrecosto adicional que se requiere para virtualizar discos duros en archivos contenedores. Ver Sección 5.10, "Servidores iSCSI".
    * _Arranque de red PXE_: las tarjetas de red virtuales integradas de Oracle VM VirtualBox soportan completamente el arranque remoto usando el Entorno de Ejecución Preboot (PXE).
* __Instantáneas (Snapshots)__: Oracle VM VirtualBox puede guardar instantáneas del estado de la VM. Puedes retroceder en el tiempo y revertir la VM a cualquiera de esas instantáneas y empezar una configuración VM alternativa desde allí, creando efectivamente todo un árbol de instantáneas.
* __Grupos de VM__: Oracle VM VirtualBox proporciona una función de grupos que permite al usuario organizar y controlar máquinas virtuales colectivamente, así como individualmente. Además de los grupos básicos, es posible que cualquier VM esté en más de un grupo, y que los grupos estén anidados en una jerarquía. Esto significa que puedes tener grupos de grupos. En general, las operaciones que se pueden realizar en grupos son las mismas que las que se pueden aplicar a las VMs individuales: Iniciar, Pausar, Reiniciar, Cerrar (Guardar estado, Enviar apagado, Apagar), Descartar Estado Guardado, Mostrar en el Sistema de Archivos, Ordenar.
* __Visualización remota VM__: La Extensión de Escritorio Remoto de VirtualBox (VRDE) permite el acceso remoto de alto rendimiento a cualquier VM en ejecución. Esta extensión soporta el Protocolo de Escritorio Remoto (RDP) originalmente incorporado en Microsoft Windows, con adiciones especiales para el soporte completo de USB del cliente.

El VRDE no depende del servidor RDP que está integrado en Microsoft Windows. En su lugar, el VRDE está conectado directamente a la capa de virtualización. Como resultado, funciona con sistemas operativos invitados distintos de Windows, incluso en modo texto, y no requiere soporte de aplicación en la VM.

## Sistemas Operativos Anfitriones Soportados (Host OS)

Actualmente, Oracle VM VirtualBox se ejecuta en los siguientes sistemas operativos anfitriones:

* __Windows hosts (64-bit)__:

    * Windows 8.1
    * Windows 10
    * Windows 11 21H2
    * Windows Server 2012
    * Windows Server 2012 R2
    * Windows Server 2016
    * Windows Server 2019
    * Windows Server 2022

* __macOS hosts (64-bit)__:

    * 10.15 (Catalina)
    * 11 (Big Sur)
    * 12 (Monterey)

> Nota: Es necesario hardware Intel. Existe un paquete de instalación disponible para macOS/Arm64, para sistemas que utilizan una CPU de Apple. Con este paquete, puedes ejecutar algunos sistemas operativos invitados para CPUs Intel x86/x64 en una emulación.

* __Linux hosts (64-bit)__:

    * Ubuntu 18.04 LTS, 20.04 LTS y 22.04
    * Debian GNU/Linux 10 ("Buster") y 11 ("Bullseye")
    * Oracle Linux 7, 8 y 9
    * CentOS/Red Hat Enterprise Linux 7, 8 y 9
    * Fedora 35 y 36
    * Gentoo Linux
    * SUSE Linux Enterprise Server 12 y 15
    * openSUSE Leap 15.3

> Nota: se debería poder usar Oracle VM VirtualBox en la mayoría de los sistemas basados en el kernel de Linux 2.6, 3.x, 4.x o 5.x utilizando el instalador de Oracle VM VirtualBox o haciendo una instalación manual. Sin embargo, las distribuciones de Linux formalmente probadas y soportadas son aquellas para las que VirtualBox ofrece un paquete dedicado.

> Nota: hay que tener en cuenta que los sistemas operativos anfitriones basados en Linux 2.4 ya no están soportados.

* __Anfitriones Oracle Solaris (solo 64-bit)__:

    * _Oracle Solaris 11.4_

## VirtualBox Manager

__VirtualBox Manager__ es la interfaz de usuario para Oracle VM VirtualBox. Puedes usar el VirtualBox Manager para crear, configurar y administrar tus máquinas virtuales. Cuando inicias Oracle VM VirtualBox, se muestra la ventana del VirtualBox Manager.

La siguiente figura muestra el VirtualBox Manager, mostrando la pantalla de bienvenida la primera vez que inicias Oracle VM VirtualBox:

![][virtualbox_manager01]

La siguiente figura muestra la ventana del VirtualBox Manager, después de crear VMs, es decir, muestra cómo podría lucir el VirtualBox Manager después de haber creado algunas VMs:

![][virtualbox_manager02]

Los principales componentes de la ventana del VirtualBox Manager son los siguientes:

* __La lista de VMs__: el panel izquierdo de la ventana del VirtualBox Manager muestra todas tus VMs. Si aún no has creado ninguna VM, esta lista estará vacía.

* __El panel de Detalles__: el panel de la derecha muestra las propiedades de la VM actualmente seleccionada. Si aún no tienes ninguna VM, el panel mostrará un mensaje de bienvenida.

Los botones en la barra de herramientas del panel de Detalles se pueden usar para crear y trabajar con máquinas virtuales.

* __Visor de Ayuda__: una ventana que muestra temas de ayuda sensibles al contexto para las tareas del VirtualBox Manager.

### La Lista de Máquinas

La lista de VMs en el panel izquierdo se llama la lista de VMs.

Se pueden utilizar los siguientes métodos para controlar y configurar las máquinas virtuales en la lista de máquinas:

* Haz clic derecho en el nombre de la máquina virtual para mostrar opciones del menú.
* Haz clic en el menú Herramientas de Máquina, a la derecha del nombre de la máquina virtual.
* Haz clic en un botón en la barra de herramientas del panel de Detalles.

### El Panel de Detalles

El Panel de Detalles muestra la información de configuración de una máquina virtual que está seleccionada en la lista de máquinas. El panel también incluye una barra de herramientas para realizar tareas.

La siguiente figura muestra el Panel de Detalles del VirtualBox Manager de una VM, incluyendo la barra de herramientas.

![][virtualbox_manager03]

El panel de detalles incluye lo siguiente:

* __Barra de herramientas del VirtualBox Manager__: Una barra de herramientas en la parte superior del panel de detalles contiene botones que te permiten configurar la VM seleccionada o crear una nueva VM.

La barra de herramientas incluye los siguientes botones:

   * _Nuevo_: crea una nueva VM y la añade a la lista de máquinas.
   * _Añadir_: Agrega una VM existente a la lista de máquinas.
   * _Configuración_: muestra la ventana de Configuración de la VM, permitiéndote realizar cambios en la configuración.
   * _Descartar_: para una VM en ejecución, descarta el estado guardado de la VM y la apaga.
   * _Mostrar/Iniciar_: para una VM en ejecución, "Mostrar" muestra la ventana de la VM. Para una VM detenida, "Iniciar" muestra opciones para encender la VM.

La opción _Configuraciones_ permite modificar algunas configuraciones de la VM.

> Nota: si una VM está en ejecución, algunas configuraciones no se pueden modificar. Debes detener la máquina virtual primero para cambiar la configuración.

La _Ventana de vista previa_ muestra una pequeña ventana con una muestra de la VM: podemos usar la ventana de vista previa para verificar una VM ha terminado de arrancar.

Los mensajes de notificación pueden aparecer en un panel deslizante en el lado derecho del panel de detalles, llamado _Centro de Notificaciones_.


VirtualBox Manager proporciona dos tipos de herramientas para los usuarios, para permitirte realizar tareas comunes fácilmente.

* __Herramientas globales__: estas herramientas se aplican a todas las máquinas virtuales. En el panel izquierdo de la ventana de VirtualBox Manager, haz clic en el icono de Menú en el banner de Herramientas ubicado sobre la lista de máquinas. Se muestra el menú de Herramientas globales.

A continuación se muestra la figura del menú de Herramientas Globales:

![][virtualbox_manager04]

* __Herramientas de Máquina__: estas herramientas se aplican a una VM específica. Una lista desplegable te permite seleccionar entre las siguientes herramientas globales:

    * _Bienvenida_: muestra el mensaje de bienvenida del VirtualBox Manager. La barra de herramientas del VirtualBox Manager también está incluida, para permitirte comenzar a usar Oracle VM VirtualBox.
    * _Extensiones_: muestra la herramienta del Gestor de Paquetes de Extensión. Esta herramienta se utiliza para instalar y desinstalar los paquetes de extensión de Oracle VM VirtualBox.
    * _Medios_: muestra la herramienta del Gestor de Medios Virtuales. Esta herramienta se utiliza para administrar las imágenes de disco utilizadas por Oracle VM VirtualBox.
    * _Red_: muestra la herramienta del Gestor de Red. Esta herramienta se utiliza para crear y configurar algunos tipos de redes utilizadas por Oracle VM VirtualBox.
    * _Nube_: muestra la herramienta del Editor de Perfil de Nube. Esta herramienta se utiliza para configurar conexiones a un servicio en la nube, como Oracle Cloud Infrastructure.
    * _Actividades_: muestra la herramienta de Resumen de Actividad de VM. Esta herramienta se utiliza para monitorear el rendimiento y el uso de recursos de las máquinas virtuales.

Para ver las Herramientas de Máquina, en la lista de máquinas en el panel izquierdo de la ventana del VirtualBox Manager, selecciona una VM y haz clic en el ícono de Menú a la derecha del nombre de la VM. Se muestra el menú de Herramientas de Máquina.

A continuación se muestra el menú de Herramientas de Máquina de una VM:

![][virtualbox_manager05]

El menú herramientas de máquina cuenta con las siguientes opciones:

   * _Detalles_: muestra el panel de Detalles para la máquina virtual seleccionada.
   * _Instantáneas_: muestra la herramienta de Instantáneas. Esta herramienta te permite ver y administrar instantáneas para la VM.
   * _Registros_: muestra la herramienta del Visor de Registros. Esta herramienta te permite ver y buscar registros del sistema para la VM.
   * _Actividad_: muestra la página de Actividad de VM del diálogo de Información de Sesión. Este diálogo te permite ver y analizar métricas de rendimiento para la VM.
   * _Administrador de Archivos_: muestra la herramienta del Administrador de Archivos de Control del Invitado. Esta herramienta te permite administrar archivos en el sistema invitado.

## Crear nuestra primera VM

El Administrador de VirtualBox incluye asistentes que te permiten completar tareas fácilmente. Ejemplos de tales tareas son cuando creas una nueva VM.

* __Modo Guiado__: este es el modo de visualización predeterminado. Los asistentes se muestran de la manera convencional, utilizando una serie de páginas con descripciones para guiar al usuario a través de los pasos de una tarea.
* __Modo Experto__: este modo de visualización está diseñado para usuarios más avanzados de Oracle VM VirtualBox. Todos los ajustes se muestran en una sola página, permitiendo una finalización más rápida de las tareas.

Haz clic en el botón en la parte inferior de la ventana del asistente para cambiar entre el Modo Guiado y el Modo Experto.

Haz clic en _Nueva_ en la ventana del Administrador de VirtualBox. Se muestra el asistente _Crear Máquina Virtual_ que nos guiará a través de los pasos necesarios para configurar una nueva máquina virtual (VM).

Los siguientes campos están disponibles en esta página del asistente:

* __Nombre__: un nombre para la nueva VM. El nombre que ingreses se mostrará en la lista de máquinas del Administrador de VirtualBox y también se usará para los archivos de la VM en el disco.
* __Carpeta__: la ubicación donde se almacenan las VMs en nuestro ordenador. Se muestra la ubicación de la carpeta predeterminada.
* __Imagen ISO__: selecciona un archivo de imagen ISO. El archivo de imagen se puede usar para instalar un SO en la nueva VM o se puede adjuntar a una unidad de DVD en la nueva VM.
* __Tipo y Versión__: estos campos se utilizan para seleccionar el SO que deseas instalar en la nueva VM.
* __Omitir Instalación Desatendida__: desactiva la instalación desatendida del SO invitado, incluso si se selecciona una imagen ISO que admite la instalación desatendida. En ese caso, la imagen ISO seleccionada se monta automáticamente en la unidad de DVD de la nueva VM, requiriendo de interacción del usuario para completar la instalación del SO.

> Nota: asegúrate de asignar a cada VM un nombre informativo que describa el SO y el software que se ejecuta en la VM.

> Nota: Asegúrate de que la ubicación de la carpeta tenga suficiente espacio libre, especialmente si piensas usar la función de instantáneas.

> Nota: si se selecciona una imagen ISO y Oracle VM VirtualBox detecta el sistema operativo para el ISO, los campos Tipo y Versión se completan automáticamente y se desactivan.

![][crear_vm01]

A continuación, entramos en el asistente _Crear Máquina Virtual_ en la sección _Hardware_, donde los siguientes campos están disponibles en esta página del asistente:

* __Memoria Base__: selecciona la cantidad de RAM que Oracle VM VirtualBox debe asignar cada vez que se inicie la VM. La cantidad de memoria seleccionada aquí se tomará de nuestra máquina anfitriona (Host) y se presentará al OS invitado (Guest OS).
* __Procesador(es)__: selecciona el número de procesadores virtuales para asignar a la VM.
* __Habilitar EFI__: esta opción la dejaremos desactivada.

> Nota: elige esta configuración con cuidado. La memoria que le das a la VM no estará disponible para tu sistema operativo anfitrión mientras la VM esté en funcionamiento, así que no especifiques más de lo que puedes prescindir. Por ejemplo, si tu máquina anfitriona tiene 4 GB de RAM y especificas 2048 MB como la cantidad de RAM para una VM en particular, solo te quedarán 2 GB para todo el otro software en tu anfitrión mientras la VM esté en funcionamiento. Si ejecutas dos VMs al mismo tiempo, se asignará aún más memoria para la segunda VM, que incluso puede no ser capaz de iniciarse si esa memoria no está disponible. Por otro lado, debes especificar tanto como tu sistema operativo invitado y tus aplicaciones requerirán para funcionar correctamente. Un sistema operativo invitado puede requerir al menos 1 o 2 GB de memoria para instalarse y arrancar. Para un rendimiento óptimo, puede ser necesario más memoria que esa. Asegúrate siempre de que el sistema operativo anfitrión tenga suficiente RAM restante. Si no queda suficiente RAM, el sistema podría intercambiar memoria excesivamente al disco duro, lo que efectivamente paralizaría el sistema anfitrión. Al igual que con otras configuraciones del asistente para crear máquinas virtuales, puedes cambiar esta configuración más tarde, después de haber creado la VM.

> Nota: no es recomendable asignar más de la mitad de los hilos totales del procesador de la máquina anfitriona.

![][crear_vm02]

A continuación, entramos en el asistente _Crear Máquina Virtual_ en la sección _Disco Duro virtual_, donde los siguientes campos están disponibles:

* __Crear un Disco Duro Virtual Ahora__: crea una nueva imagen de disco duro virtual vacía, ubicada en la carpeta de la máquina VM. Introduce las siguientes configuraciones:
    * _Tamaño del Disco_: usa el deslizador para seleccionar un tamaño máximo para el disco duro en la nueva VM.
    * _Reservar Tamaño Completo_: esta configuración determina el tipo de archivo de imagen utilizado para la imagen del disco. Selecciona esta configuración para usar un archivo de tamaño fijo para la imagen del disco. Deselecciona esta configuración para usar un archivo asignado dinámicamente para la imagen del disco.
* __Usar un Archivo de Disco Duro Existente__: te permite seleccionar un archivo de imagen de disco existente para usar con la nueva VM. La lista desplegable presentada en la ventana muestra todas las imágenes de disco que son conocidas por Oracle VM VirtualBox. Estas imágenes de disco están actualmente adjuntas a una VM o han estado adjuntas a una VM.
* __No Agregar un Disco Duro Virtual__: la nueva VM se crea sin un disco duro.

> Nota: para evitar que tu disco duro físico en el sistema operativo host se llene, Oracle VM VirtualBox limita el tamaño del archivo de imagen. Pero el archivo de imagen debe ser lo suficientemente grande como para contener el contenido del sistema operativo invitado y las aplicaciones que deseas instalar. Para un invitado Windows o Linux, probablemente necesitarás varios gigabytes para cualquier uso serio.

Los diferentes tipos de archivos de imagen se comportan de la siguiente manera:

* __Archivo asignado dinámicamente__: este tipo de archivo de imagen solo aumenta de tamaño cuando el invitado realmente almacena datos en su disco duro virtual. Por lo tanto, este archivo es pequeño inicialmente. A medida que la unidad se llena de datos, el archivo crece al tamaño especificado.
* __Archivo de tamaño fijo__: este tipo de archivo de imagen ocupa inmediatamente el espacio especificado, incluso si solo una fracción de ese espacio de disco duro virtual está realmente en uso. Aunque ocupa mucho más espacio, un archivo de tamaño fijo incurre en menos sobrecarga y, por lo tanto, es ligeramente más rápido que un archivo asignado dinámicamente.

![][crear_vm03]

A continuación, entramos en el asistente _Crear Máquina Virtual_ en la sección _Resumen_, donde se muestra la configuración para la VM. Si no estamos satisfecho con alguna de las configuraciones, podemos usar el botón Atrás para volver a la página correspondiente y modificar la configuración.

Para crear la VM hacemos click en el botón _Finalizar_. La VM se muestra en la lista de máquinas en el lado izquierdo de la ventana del Administrador de VirtualBox, con el nombre que ingresamos en la primera página del asistente.

![][crear_vm04]

[oracle_virtualbox_logo]: ./img/oracle_vm_virtualbox/oracle_virtualbox_logo.png "Oracle VirtualBox Logo"
[virtualbox_manager01]: ./img/oracle_vm_virtualbox/virtualbox_manager01.png "VirtualBox Manager 01"
[virtualbox_manager02]: ./img/oracle_vm_virtualbox/virtualbox_manager02.png "VirtualBox Manager 02"
[virtualbox_manager03]: ./img/oracle_vm_virtualbox/virtualbox_manager03.png "VirtualBox Manager 03"
[virtualbox_manager04]: ./img/oracle_vm_virtualbox/virtualbox_manager04.png "VirtualBox Manager 04"
[virtualbox_manager05]: ./img/oracle_vm_virtualbox/virtualbox_manager05.png "VirtualBox Manager 05"
[crear_vm01]: ./img/oracle_vm_virtualbox/crear_vm01.png "Crear VM 01"
[crear_vm02]: ./img/oracle_vm_virtualbox/crear_vm02.png "Crear VM 02"
[crear_vm03]: ./img/oracle_vm_virtualbox/crear_vm03.png "Crear VM 03"
[crear_vm04]: ./img/oracle_vm_virtualbox/crear_vm04.png "Crear VM 04"