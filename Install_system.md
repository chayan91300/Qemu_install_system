# Installation d'OS en dur à partir de Qemu vers un péripherique externes

## Installation des dépendances
```Bash
sudo apt install qemu-system-x86_64 -y
```
## Rechercher le nom de la clé USB
```Bash
lsblk
```
## Lancer l'installation
```Bash
sudo qemu-system-x86_64 -m 2048 -smp 2 -netdev user,id=network0 -device rtl8139,netdev=network0 -hda /dev/sdX -cdrom System.iso -boot d
```
* Clé USB : /dev/sdX
* ISO du systme : System.iso

## Tester le système

```Bash
sudo qemu-system-x86_64 -m 2048 -smp 2,sockets=1,maxcpus=2 -netdev user,id=network0 -device rtl8139,netdev=network0 -hda /dev/sdc -boot c
```
