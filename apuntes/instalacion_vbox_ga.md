# Instalar VirtualBox Guest Additions

## Sistemas Debian

Instalar dependencias:

```bash
$ su -
# apt update
# apt install build-essential dkms linux-headers-$(uname -r)
```

Montar imagen de CD con las _VirtualBox Guest Additions_:

```
Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ...
```

Instalar _VirtualBox Guest Additions_:

```bash
# cd /media/cdrom0
# sh ./VBoxLinuxAdditions.run --nox11
```

Añadimos al grupo _vboxsf_ al usuario _alumno_ para que pueda utilizar _Carpetas compartidas_:

```bash
# usermod -aG vboxsf alumno
```

Reiniciar el sistema:

```bash
# reboot
```

Comprobar que las _VirtualBox Guest Additions_ se han instalado correctamente:

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```

## Sistemas Ubuntu y Linux Mint

Instalar dependencias:

```bash
$ sudo apt update
$ sudo apt install build-essential dkms linux-headers-$(uname -r)
```

Montar imagen de CD con las _VirtualBox Guest Additions_:

```
Menú _Dispositivos - Insertar imagen de CD de los complementos del invitado ...
```

Instalar _VirtualBox Guest Additions_:

```bash
$ sudo cd /media/alumno/VBox_GAs_7.0.12
$ sudo sh ./VBoxLinuxAdditions.run --nox11
```

Añadimos al grupo _vboxsf_ al usuario _alumno_ para que pueda utilizar _Carpetas compartidas_:

```bash
$ sudo usermod -aG vboxsf alumno
```

Reiniciar el sistema:

```bash
$ reboot
```

Comprobar que las _VirtualBox Guest Additions_ se han instalado correctamente:

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```

## Sistemas Fedora

Instalar dependencias:

```bash
$ sudo dnf update -y
$ sudo dnf install kernel-devel kernel-headers dkms gcc gcc-c++ make curl wget
```

Montar imagen de CD con las _VirtualBox Guest Additions_:

```
Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ...
```

Instalar _VirtualBox Guest Additions_:

```bash
$ cd /run/media/alumno/VBox_GAs_7.0.12
$ sudo sh ./VBoxLinuxAdditions.run --nox11
```

Añadimos al grupo _vboxsf_ al usuario _alumno_ para que pueda utilizar _Carpetas compartidas_:

```bash
$ sudo usermod -aG vboxsf alumno
```

Reiniciar el sistema:

```bash
$ reboot
```

Comprobar que las _VirtualBox Guest Additions_ se han instalado correctamente:

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```
