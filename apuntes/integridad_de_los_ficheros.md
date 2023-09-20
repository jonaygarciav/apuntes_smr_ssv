# Cómo comprobar la integridad de nuestros archivos con el hash

¿Cómo es posible saber fácilmente si el archivo que estoy recibiendo es legítimo? ¿Es posible saber si se ha corrompido mientras lo descargaba de Internet? Sí, es posible mediante su hash. El hash funciona como un código de identificación del dato con el cual estamos trabajando. Si llega a alterarse un determinado dato de origen, este código alfanumérico de salida se altera por completo. A continuación, te mostramos todo lo que necesitas saber y qué herramientas recomendamos para generar hashes cuando lo necesites.

## ¿Qué es un hash y para qué sirve?

Un hash es una función criptográfica que funciona solamente en un solo sentido, es decir, es un algoritmo matemático que transforma cualquier bloque de entrada de datos en una nueva serie de caracteres de salida con una longitud fija o variable. Por lo tanto, una función hash es el resultado de una función que se encarga de convertir un valor en otro. Un detalle muy importante es que, generalmente los hash proporcionan una salida de longitud fija, sin embargo, hay algoritmos de hash que están específicamente diseñados para «proteger» las contraseñas, y en este caso la longitud de la salida es variable.

Uno de los propósitos principales de dicha función hash, es el poder comprobar si un archivo se ha modificado o no. La huella hash de cada archivo es única, el hash genera una especie de código que sirve como una identificación del dato en cuestión. Además, con el hash de un determinado archivo no se puede recuperar el archivo original, por este motivo, una buena práctica de seguridad es almacenar los hashes de las contraseñas en las bases de datos, para que nadie pueda obtener la información en texto plano. No obstante, para crackear este «hash» lo que se hace es probar miles de combinaciones y comparar si los hashes son iguales.

Los hashes se utilizan para muchos usos, como los siguientes:

* __Comprobar la integridad de un archivo__: si hacemos la función hash de un archivo en cuestión y lo copiamos a otro ordenador o a cualquier otro sitio, si se vuelve a hacer la función hash de este archivo copiado, debe salir exactamente el mismo resultado que la función hash original. En cuanto en un archivo cambia un bit, la salida del hash que hayamos utilizado es completamente diferente. Por este motivo, es muy importante el hash en los protocolos seguros de cifrado, como el HTTPS o FTPES, donde se comprueba que efectivamente los datos no han sufrido ninguna variación en la comunicación. Los hash también son muy usados en el mundo forense informático, para realizar la cadena de custodia de un disco duro o una imagen de disco adecuadamente, y garantizar que no se ha modificado nada del contenido.
* __Guardar las contraseñas de forma segura__: si hacemos la función hash de una contraseña, y almacenamos el resultado de esta función hash en una base de datos, un posible atacante si accede a esta base de datos no podrá recuperar la contraseña. Debemos recordar que las funciones hash solamente van en un sentido, no se puede «revertir» una función hash, por lo que si un ciberdelincuente quiere crackear la contraseña, tendrá que hacer un ataque de fuerza bruta y diccionario, comparando el hash de cada contraseña probada con la contraseña que ha conseguido en la filtración.

Las funciones hash son muy importantes en el mundo de la seguridad informática, y también de las redes, porque nos permite comprobar la integridad de los datos transmitidos, no solamente los almacenados en un disco duro o unidad SSD. A continuación, os vamos a enseñar cómo comprobar la integridad de un archivo utilizando diferentes algoritmos de hash.

Las siglas de __SHA__ responden a _Secure Hash Algorithm_. Fue desarrollado por la NIST, que es la National Institute for Standards and Technology. Es uno de los algoritmos estandarizados más populares en la actualidad. Una de las ventajas es que ante el mínimo cambio en la integridad de los datos, el hash varía por completo. SHA2-256, por ejemplo, es un estándar que está siendo empleado a nivel nacional en los Estados Unidos, y actualmente se considera seguro. Éste se denomina tal cual ya que el hash que genera es de 256 bits de longitud.

No solamente puedes contar con los hashes de SHA2-256 y otros estándares para comprobar la integridad de los archivos. El que mencionamos, también tiene aplicación en protocolos populares de autenticación y encriptación: SSL, TLS, IPSec, SSH y PGP. En Linux y otros sistemas operativos, así como en aplicaciones que almacenan contraseñas en una base de datos, este algoritmo se utiliza para hashear las contraseñas, y almacenar dicho hash y no la contraseña en texto claro. La popular criptomoneda Bitcoin se vale de este algoritmo para verificar cada una de las transacciones que se da en su red.

## Tipos de hash

Estas funciones matemáticas, son tremendamente útiles para producir valores únicos. Su aplicación es válida dentro de muchas áreas diferentes dentro del mundo de la informática, donde se encuentra la seguridad, la criptografía y la verificación de la integridad de los datos. Pero esto no es algo que se haga con un solo tipo de hash, sino que nos podemos encontrar varios. Estos son:

* __MD5__: Fue una de las funciones más utilizadas, debido a que podía producir hashes de 128 bits. Salió a la luz en 1991, y se ha utilizado ampliamente para la seguridad de contraseñas y verificaciones de seguridad para la integridad de archivos. En cambio, cuenta con vulnerabilidades en su diseño, que hacen que hoy en día se considere inseguro. Por lo cual no se recomienda su utilización.
* __SHA-1__: Este algoritmo es capaz de producir hashes de 160 bits. Ha sido muy utilizado para la seguridad y verificación de archivos, pero también ha caído en desuso debido a diferentes vulnerabilidades que presentaba.
* __SHA-2__: En este caso estamos ante un grupo de algoritmos, los cuales pueden producir hashes de diferentes longitudes. Tenemos 224, 256, 384 y 512 bits respectivamente. Esta ha reemplazado en gran medida a MD5 y SHA-1, como una opción mucho más segura. Es muy utilizado en la verificación de contraseñas e integridad.
* __SHA-3__: Este algoritmo es capaz de producir hashes de 224, 256, 384 y 512 bits. Y es actualmente uno de los algoritmos aprobados por el Instituto Nacional de los Estándares y Tecnología (NIST) de Estados Unidos. Es considerado muy seguro, por lo cual también es ampliamente utilizado.

## Ejemplo práctico 1

Por ejemplo, imaginemos que hemos descargado un archivo llamado alpine-standard-3.18.3-x86_64.iso ubicado en la URL:

[https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso](https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso)


Este archivo se encuentra ubicado en la carpeta Descargas de nuestro directorio personal y queremos calcular su hash y compararlo con el que se encuentra en la página web para comprobar la integridad del archivo, por lo tanto, debemos abrir un Terminal (CTRL+ALT+T) y ejecutar los siguientes comandos:

```bash
$ cd Descargas

$ ls -l
total 193536
-rw-rw-r-- 1 jonay jonay 198180864 ago  7 14:13 alpine-standard-3.18.3-x86_64.iso

$ sha256sum alpine-standard-3.18.3-x86_64.iso 
badeb7f57634c22dbe947bd692712456f2daecd526c14270355be6ee5e73e83e  alpine-standard-3.18.3-x86_64.iso
```

La clave SHA-256 se encuentra en el archivo que se puede descargar en la URL:

[https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso.sha256](https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso.sha256)

cuyo contenido es el siguiente:

```bash:alpine-standard-3.18.3-x86_64.iso.sha256
# Contenido del fichero alpine-standard-3.18.3-x86_64.iso.sha256
badeb7f57634c22dbe947bd692712456f2daecd526c14270355be6ee5e73e83e  alpine-standard-3.18.3-x86_64.iso
```

Por lo tanto, podemos concluir que el archivo se ha descargado correctamente de la página web. En caso de que no coincidieran las claves, sería necesario volver a descargar el archivo hasta que las claves hash coincidan.

## Ejemplo práctico 2

En este ejemplo, descargaremos en nuestro ordenador, aparte del fichero con extensión ISO llamado alpine-standard-3.18.3-x86_64.iso, el archivo con la clave hash llamado alpine-standard-3.18.3-x86_64.iso.sha256:

* [https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso](https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso)
* [https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso.sha256](https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso.sha256)

Descargaremos estos archivos desde la línea de comandos utilizando el comando wget:

```bash
$ cd Descargas

$ wget https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso
$ wget https://dl-cdn.alpinelinux.org/alpine/v3.18/releases/x86_64/alpine-standard-3.18.3-x86_64.iso.sha256

$ ls -l
total 193544
-rw-r--r-- 1 jonay jonay 198180864 ago  7 14:13 alpine-standard-3.18.3-x86_64.iso
-rw-r--r-- 1 jonay jonay       100 ago  7 14:13 alpine-standard-3.18.3-x86_64.iso.sha256
```

El archivo alpine-standard-3.18.3-x86_64.iso.sha256 es un archivo de texto y podemos ver su contenido desde la terminal utilizando el comando cat:

```bash
$ cat alpine-standard-3.18.3-x86_64.iso.sha256
badeb7f57634c22dbe947bd692712456f2daecd526c14270355be6ee5e73e83e  alpine-standard-3.18.3-x86_64.iso
```

Ahora utilizaremos el hash almacenado en el archivo sh almacenado en el archivo alpine-standard-3.18.3-x86_64.iso.sha256 , para verificar la integridad del archivo alpine-standard-3.18.3-x86_64.iso que hemos descargado:

```bash
$ cat alpine-standard-3.18.3-x86_64.iso.sha256 | sha256sum --check
alpine-standard-3.18.3-x86_64.iso: La suma coincide
```

Por lo tanto, podemos concluir que el archivo se ha descargado correctamente de la página web. En caso de que no coincidieran las claves, sería necesario volver a descargar el archivo hasta que las claves hash coincidan.

> Nota: Esta es una manera más limpia de comprobar la integridad de un archivo, utilizando la opción --check con el comando sha256sum o sha512sum.

## Comandos

* _sha256sum_: calcula y comprueba el resumen del mensaje SHA256 de tipo SHA-2.
* _sha512sum_: calcula y comprueba el resumen del mensaje SHA512 de tipo SHA-2.
* _ls -l_: lista los archivos y carpetas del directorio en que nos encontramos actualmente.
* _wget_: permite descargar archivos de Internet.
* _cat_: muestra el contenido de un fichero de texto.

## Referencias

* [https://www.redeszone.net/tutoriales/seguridad/comprobar-integridad-archivos-hash/](https://www.redeszone.net/tutoriales/seguridad/comprobar-integridad-archivos-hash/)
* [https://linuxmint-installation-guide.readthedocs.io/es/latest/verify.html](https://linuxmint-installation-guide.readthedocs.io/es/latest/verify.html)
* [https://www.ochobitshacenunbyte.com/2023/01/03/como-generar-un-hash-sha-256-en-linux/](https://www.ochobitshacenunbyte.com/2023/01/03/como-generar-un-hash-sha-256-en-linux/)
