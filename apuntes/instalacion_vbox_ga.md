# Instalar VirtualBox Guest Additions

## Sistemas Debian

Instalar dependencias:

```bash
$ su -
# apt update
# apt install build-essential dkms linux-headers-$(uname -r)
```

Montar ISO con las _VirtualBox Guest Additions_:

```
_Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ..._
```

Instalar _VirtualBox Guest Additions_:

```bash
# cd /media/cdrom0
# sh ./VBoxLinuxAdditions.run --nox11
# usermod -aG vboxsf alumno
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

Montar ISO con las _VirtualBox Guest Additions_:

```
Menú _Dispositivos - Insertar imagen de CD de los complementos del invitado ..._
```

Instalar _VirtualBox Guest Additions_:

```bash
$ sudo cd /media/alumno/VBox_GAs_7.0.12
$ sudo sh ./VBoxLinuxAdditions.run --nox11
$ sudo usermod -aG vboxsf alumno
$ sudo reboot
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

Montar ISO con las _VirtualBox Guest Additions_:

```
_Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ..._
```

Instalar _VirtualBox Guest Additions_:

```bash
$ cd <TODO>
$ sudo sh ./VBoxLinuxAdditions.run --nox11
$ sudo usermod -aG vboxsf alumno
$ sudo reboot
```

Comprobar que las _VirtualBox Guest Additions_ se han instalado correctamente:

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```
