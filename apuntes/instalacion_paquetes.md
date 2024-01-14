# Instalación de paquetes

## Instalación de paquetes en sistemas Debian

Instalación de paquetes que se encuentran en el repositorio:

```bash
# apt install git
```

Instalación de paquetes que no se encuentran en el repositorio:

```bash
# cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.deb>
# apt install ./<fichero>.deb
```

```bash
# cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.deb>
# dpkg -i ./<fichero>.deb
```

> Nota: Se recomienda utilizar apt ya que instala las dependencias del fichero .deb en caso de que las tenga.

## Instalación de paquetes en sistemas Ubuntu y Linux Mint

Instalación de paquetes que se encuentran en el repositorio:

```bash
$ sudo apt install git
```

Instalación de paquetes que no se encuentran en el repositorio:

```bash
$ cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.deb>
$ sudo apt install ./<fichero>.deb
```

```bash
$ cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.deb>
$ sudo dpkg -i ./<fichero>.deb
```

> Nota: Se recomienda utilizar apt ya que instala las dependencias del fichero .deb en caso de que las tenga.

## Instalación de paquetes en sistemas Fedora

Instalación de paquetes que se encuentran en el repositorio:

```bash
$ sudo dnf install git
```

Instalación de paquetes que no se encuentran en el repositorio:

```bash
$ cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.rpm>
$ sudo dnf localinstall ./<fichero>.deb
```

```bash
$ cd <carpeta/donde/se/encuentra/el/fichero/con/extension/.rpm>
$ sudo rpm -u ./<fichero>.deb
```

> Nota: Se recomienda utilizar dnf ya que instala las dependencias del fichero .deb en caso de que las tenga.
