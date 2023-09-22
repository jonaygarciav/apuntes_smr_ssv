# Comprobar la integridad y la autenticidad de archivos mediante MD5, SHA-1 o SHA-2

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

Por ejemplo, imaginemos que entramos en la página de descarga de Debian [https://www.debian.org/download](https://www.debian.org/download) se encuentra los siguientes archivos:

* [https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.1.0-amd64-netinst.iso](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.1.0-amd64-netinst.iso)
* [https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS)

Para descargar estos archivos desde línea de comandos, abrimos un Terminal (CTRL+ALT+T) y utilizamos el comando __wget__:

```bash
$ cd Descargas

$ wget https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.1.0-amd64-netinst.iso
$ wget https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/SHA512SUMS
```

Estos archivos se encuentran ubicados en la carpeta _Descargas_ de nuestro directorio personal:

```bash
$ pwd
/home/jonay/Descargas

$ ls -la
total 642064
drwxr-xr-x 2 jonay jonay      4096 sep 22 08:23 .
drwxr-xr-x 3 jonay jonay      4096 sep 22 08:23 ..
-rw-r--r-- 1 jonay jonay 657457152 jul 22 13:30 debian-12.1.0-amd64-netinst.iso
-rw-r--r-- 1 jonay jonay       494 jul 22 17:49 SHA512SUMS
```

Para calcular el hash del archivo _debian-12.1.0-amd64-netinst.iso_ utilizamos el comando __sha512sum__:

```bash
$ sha512sum debian-12.1.0-amd64-netinst.iso 
9da6ae5b63a72161d0fd4480d0f090b250c4f6bf421474e4776e82eea5cb3143bf8936bf43244e438e74d581797fe87c7193bbefff19414e33932fe787b1400f  debian-12.1.0-amd64-netinst.iso
```

El archivo _SHA512SUMS_ contiene la clave hash del archivo _debian-12.1.0-amd64-netinst.iso_ entre otros:

```bash
$ cat SHA512SUMS 
9da6ae5b63a72161d0fd4480d0f090b250c4f6bf421474e4776e82eea5cb3143bf8936bf43244e438e74d581797fe87c7193bbefff19414e33932fe787b1400f  debian-12.1.0-amd64-netinst.iso
a75265fcbb50908b5b61d533d85893552a5a0c826050795368d17b632378da29effe2665804cbc52fe8a8f8142e389b07a369bc7a264fd454f562e47a4284e1a  debian-edu-12.1.0-amd64-netinst.iso
1d59635d33a3b31ebd31f13c8e2531625aa17310ae271e2b17215ea88c3daee8cd520491ec72870542cc9e5f4d633d63b6a1da2ddb81970daff1245224e881ce  debian-mac-12.1.0-amd64-netinst.iso
```

Lo que queremos es calcular el hash del archivo _debian-12.1.0-amd64-netinst.iso_ y compararlo con el que se encuentra dentro del fichero _SHA512SUMS_ para comprobar la integridad del archivo. Para ello, utilizamos el comando __sha512sum__ con la opción _--check_:

```bash
$ sha512sum --check SHA512SUMS
debian-12.1.0-amd64-netinst.iso: La suma coincide
sha512sum: debian-edu-12.1.0-amd64-netinst.iso: No existe el fichero o el directorio
debian-edu-12.1.0-amd64-netinst.iso: FAILED open or read
sha512sum: debian-mac-12.1.0-amd64-netinst.iso: No existe el fichero o el directorio
debian-mac-12.1.0-amd64-netinst.iso: FAILED open or read
```

> Nota: En el archivo _SHA512SUMS_ se encuentran los hash de los archivos _debian-12.1.0-amd64-netinst.iso_, _debian-edu-12.1.0-amd64-netinst.iso_ y _debian-mac-12.1.0-amd64-netinst.iso_ de los cuales solamente hemos descargado el primero, de ahí que aparezcan algunos errores en la terminal.

Por lo tanto, podemos concluir que el archivo se ha descargado correctamente de la página de descargas de Debian. En caso de que no coincidieran las claves, sería necesario volver a descargar el archivo hasta que las claves hash coincidan.


## Comprobar la autenticidad de los archivos


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

Firma de los ficheros:
* [Verificar la integridad y la autenticidad de la imagen de Linux Mint](https://linuxmint-installation-guide.readthedocs.io/es/latest/verify.html)
* [Verificar la autenticidad de las imágenes de Debian](https://www.debian.org/CD/verify)
