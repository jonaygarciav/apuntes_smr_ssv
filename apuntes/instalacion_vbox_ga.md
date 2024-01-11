# Instalar VirtualBox Guest Additions

## Sistemas Debian

```bash
$ su -
# apt update
# apt install build-essential dkms linux-headers-$(uname -r)
```

_Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ..._

```bash
# cd /media/cdrom0
# sh ./VBoxLinuxAdditions.run --nox11
# usermod -aG vboxsf alumno
# reboot
```

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```

## Sistemas Ubuntu y Linux Mint

```bash
$ sudo apt update
$ sudo apt install build-essential dkms linux-headers-$(uname -r)
```

Menú _Dispositivos - Insertar imagen de CD de los complementos del invitado ..._

```bash
$ sudo cd /media/alumno/VBox_GAs_7.0.12
$ sudo sh ./VBoxLinuxAdditions.run --nox11
$ sudo usermod -aG vboxsf alumno
$ sudo reboot
```

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```

## Fedora

```bash
sudo dnf update -y
sudo dnf install kernel-devel kernel-headers dkms gcc gcc-c++ make curl wget
```

_Menú Dispositivos - Insertar imagen de CD de los complementos del invitado ..._

```bash
$ cd <TODO>
$ sudo sh ./VBoxLinuxAdditions.run --nox11
$ sudo usermod -aG vboxsf alumno
$ sudo reboot
```

```bash
$ lsmod | grep vbox
vboxguest              57344  0
```
