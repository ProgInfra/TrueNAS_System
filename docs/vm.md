# TrueNAS System : Virtual Machine

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Virtual Machine](#truenas-system--virtual-machine)
  - [Table Of Contents](#table-of-contents)
  - [Create new Virtual Machine](#create-new-virtual-machine)
  - [Fix](#fix)
    - [VNC Resolution Config](#vnc-resolution-config)
    - [Disk Management](#disk-management)
    - [Boot Configuration](#boot-configuration)

## Create new Virtual Machine

1) Go to **Virtualization** => **Add**
2) Operating System :
   1) Guest Operating System : Linux or Windows
   2) System Clock : Local (Windows) or UTC (Linux)
   3) Boot Method : UEFI
3) CPU and Memory :
   1) Virtual CPU : Choose the amount of CPU (1)
   2) Cores : Choose the amount of Core per CPU (4)
   3) Threads : Choose the amount of threads per core (1)
   4) Memory Size : 2048 MiB
4) Disk : Set what you want
5) Network Interface :
   1) Adapter Type : The one you want
   2) Attach NIC : br0 or other bridge
6) Installation Media : The iso you want to install
7) GPU : If needed
8) Confirm and save
9) Check or uncheck if you want to auto start your VM
10) Start it and go to **Display**
11) Install your system
12) Once install is complete and you have reboot, power off the VM, click on it, go to Devices and remove the device CDROM (with iso).
13) Then Start it and you can start to use it and configure it (you can also check fix bellows if you have some issues).

## Fix

### VNC Resolution Config

- CAREFULL ! Set VNC resolution to 800x600 to fix screen issue !
- Disabled "Delay VM Boot"

### Disk Management

- Remove Install CD for boot system

### Boot Configuration

**Access Setup** :

- Shell> exit
- Boot Maintenance Manager
- Boot From File
- Search for File : **grubx64.efi**

**Definitive Boot Setup** :

```bash
sudo -s
mkdir -p /boot/efi/EFI/BOOT
cp /boot/efi/EFI/debian/grubx64.efi /boot/efi/EFI/BOOT/bootx64.efi
poweroff
```
