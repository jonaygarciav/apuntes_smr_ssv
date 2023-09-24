# ¿Qué es la Virtualización?

La __virtualización__ es un proceso que permite una utilización más eficaz del hardware físico y es la base del cloud computing.

La virtualización utiliza software para crear una capa de abstracción sobre el hardware del sistema que permite dividir los elementos de hardware de un sistema (procesadores, memoria, almacenamiento, etc.) en varios sistemas virtuales, comúnmente llamados máquinas virtuales (VM). Cada VM ejecuta su propio sistema operativo y se comporta como un ordenador independiente, aunque se esté ejecutando en una parte del hardware del sistema subyacente real.

De este modo, la virtualización permite una utilización más eficaz del hardware físico y una mayor rentabilidad de la inversión de hardware de una organización.

Hoy en día, la virtualización es una práctica estándar en la arquitectura de TI empresarial. También es la tecnología que impulsa la economía de cloud computing. La virtualización permite a los proveedores de cloud dar servicio a los usuarios con el hardware físico existente. Los usuarios del cloud pueden adquirir solo los recursos informáticos que necesitan y cuando los necesitan, y escalarlos de forma rentable a medida que crezcan sus cargas de trabajo.

Para obtener una visión general de cómo funciona la virtualización, consulte nuestro vídeo "En qué consiste la virtualización":


## Ventajas de la virtualización

La virtualización ofrece varias ventajas a los operadores de centros de datos y los proveedores de servicios:

* __Eficiencia de los recursos__: antes de la virtualización, cada servidor de aplicaciones necesitaba su propia CPU física dedicada: el personal de TI debía comprar y configurar un servidor independiente para cada aplicación que quería ejecutar (el personal de TI prefería una aplicación y un sistema operativo por ordenador por motivos de fiabilidad). Invariablemente, cada servidor físico estaba infrautilizado. En cambio, la virtualización del servidor permite ejecutar varias aplicaciones, cada una en su propia máquina virtual con su propio sistema operativo, en un único sistema físico (normalmente un servidor x86) sin sacrificar la fiabilidad. Esto permite utilizar al máximo la capacidad del hardware físico.
* __Gestión más sencilla__: la sustitución de sistemas físicos por máquinas virtuales definidas por software facilita el uso y la gestión de políticas escritas en software. De esta forma, puede crear flujos de trabajo de gestión de servicios de TI automatizados. Por ejemplo, las herramientas de despliegue y configuración automatizadas permiten a los administradores definir colecciones de máquinas virtuales y aplicaciones como servicios en plantillas de software. Como resultado, pueden instalar estos servicios sistemáticamente sin necesidad de la configuración manual lenta, complicada y propensa a errores. Los administradores pueden utilizar políticas de seguridad de virtualización para requerir determinadas configuraciones de seguridad basadas en el rol de la máquina virtual. Las políticas pueden incluso aumentar la eficiencia de los recursos al retirar las máquinas virtuales no utilizadas para ahorrar espacio y potencia.
* __Aprovisionamiento más rápido__: la compra, instalación y configuración de hardware para cada aplicación consume mucho tiempo. Siempre que el hardware ya esté instalado, el suministro de máquinas virtuales para ejecutar todas las aplicaciones es significativamente más rápido. Incluso puede automatizarlo utilizando software de gestión e incorporarlo en los flujos de trabajo existentes.
Para ver un análisis más detallado de los posibles beneficios, consulte "5 beneficios de la virtualización".

## Máquinas virtuales (VM)

Las __máquinas virtuales__ o __virtual machines__ (_VM_) son entornos virtuales que simulan un sistema físico en formato de software. Normalmente incluyen varios archivos que contienen la configuración de la VM, el almacenamiento de la unidad de disco duro virtual y algunas instantáneas de la VM que conservan su estado en un determinado momento.

Para obtener una visión general completa de las máquinas virtuales, consulte "¿Qué es una máquina virtual?"

## Hipervisores

Un __hipervisor__ o __hypervisor__ es la capa de software que coordina a las VMs. Sirve como interfaz entre la VM y el hardware físico subyacente, y garantiza que cada uno tenga acceso a los recursos físicos que necesita ejecutar: CPU, RAM, GPU, ... También se asegura de que las VMs no interfieran entre ellas afectando al espacio de memoria o los ciclos de cálculo del resto.

Hay dos tipos de hipervisores:

* __Hipervisores de tipo 1__: interactúan con los recursos físicos subyacentes, sustituyendo por completo al sistema operativo tradicional. Suelen aparecer en escenarios de servidor virtual.

* __Hipervisores de tipo 2__: se ejecutan como una aplicación en un sistema operativo existente. Normalmente se utilizan en dispositivos de punto final para ejecutar sistemas operativos alternativos e implican una sobrecarga de rendimiento porque deben utilizar el sistema operativo del host para acceder y coordinar los recursos de hardware subyacentes.

![][hipervisores_tipo_1_y_2]

## Seguridad

La virtualización ofrece algunas ventajas de seguridad, por ejemplo:

* Las VMs infectadas con malware pueden retrotraerse a un punto en el tiempo (denominado __instantánea__ o __snapshot__) en el que la VM no estaba infectada y estaba estable.
* Se pueden suprimir una VM y volver a crear de manera más fácil.

> Nota: no siempre se puede desinfectar un sistema operativo virtualizado, ya que el malware a menudo está profundamente integrado en los componentes principales del sistema operativo.

La virtualización también presenta algunos problemas de seguridad, algunos de ellos son:

* Si un atacante compromete un hipervisor, es posible que posea todas las VMs y los sistemas operativos invitados. Como los hipervisores también permiten que las máquinas virtuales se comuniquen entre sí sin tocar la red física, puede ser difícil ver su tráfico y, por lo tanto, detectar la actividad sospechosa.

* Un hipervisor de tipo 2 en un sistema operativo de host también es susceptible de comprometer el sistema operativo del host.

## Tecnologías de Virtualización en fabricantes de procesadores Intel y AMD

Debido al gran uso que tienen las técnicas de virtualización por parte de empresas IT, para conseguir un óptimo rendimiento de sus equipos, los fabricantes de hardware se han visto prácticamente obligados a crear soluciones para sus plataformas que permitan un mejor aprovechamiento de los recursos hardware de las máquinas físicas por parte de las máquinas virtuales.

Es así como nacen las tecnologías de virtualización __VT-x__ por parte de la compañía _Intel_ y __AMD-V__ por parte de la compañía _AMD_. Estas tecnologías nos permiten, entre otras cosas:

* Abstraer de forma total las características técnicas del procesador para las máquinas virtuales. De esa forma el software de una máquina virtual se podrá ejecutar de forma nativa en la CPU dedicada de la máquina física. Para ello VT-x y AMD-V destinan físicamente parte de su CPU a la máquina virtual para que esta sea capaz de trabajar con él de forma directa.

* Abstraer la _memoria RAM_ de un equipo físico para que una máquina virtual la utilice.

* Abstraer los recursos gráficos de la GPU de un equipo físico para permitir la aceleración por hardware tal y como si estuviéramos en un equipo real.

Tanto VT-x como AMD-V son tecnologías que han de activarse en la BIOS del sistema.

A continuación, se muestra cómo activar la opción VT-x de Intel en una BIOS Phoenix, normalmente la opción VT-x aparece en la BIOS con el nombre de _Intel(R) Virtualization Technology_:

![][activar_vt-x_en_la_bios]

En caso de no tener la opción VT-X activada en la BIOS, al arrancar una VM en VirtualBox, nos aparecería el error _VT-x is not available_:

![][error_en_vbox_porque_vt-x_no_esta_disponible.png]

## Referencias:
* [¿Qué es la Virtualización?](https://www.ibm.com/es-es/topics/virtualization)

[hipervisores_tipo_1_y_2]: ./img/que_es_la_virtualizacion/hipervisores_tipo_1_y_2.png "Hipervisores tipo 1 y 2"
[activar_vt-x_en_la_bios]: ./img/que_es_la_virtualizacion/activar_vt-x_en_la_bios.png "Activar VT-X en la BIOS"
[error_en_vbox_porque_vt-x_no_esta_disponible.png]: ./img/que_es_la_virtualizacion/error_en_vbox_porque_vt-x_no_esta_disponible.**png** "Activar VT-X en la BIOS"
