# TrueNAS System

![Icon](./icon.png)

[Nas icons created by Freepik - Flaticon](https://www.flaticon.com/fr/icones-gratuites/nas)

## Table Of Contents

- [TrueNAS System](#truenas-system)
  - [Table Of Contents](#table-of-contents)
  - [Description](#description)
  - [Access](#access)
  - [Getting Started](#getting-started)
    - [Server Access](#server-access)
  - [Documentations](#documentations)
  - [Development](#development)
    - [Requirements](#requirements)
    - [Docsify](#docsify)
  - [Contributing](#contributing)
  - [Licence](#licence)

## Description

TrueNAS Installation and Configuration.

This project contains all documentations to setup a complete **TrueNAS System** to init a new storage or/and compute server.

We will use **TrueNAS Scale** based on **Debian** as main operating system, we have a complete **Docker** as Container engine and **ZFS** as storage filesystem.

## Access

- **Development (Local)** :
  - [TrueNAS System Docs Development](http://localhost:6007)
- **Production (Local)** :
  - [TrueNAS System Docs Production](http://localhost:6007)
- **Production** :
  - [TrueNAS System Docs Production](https://proginfra.gitlab.io/truenas_system)

## Getting Started

1) First of all you need a **machine** to build this **server**, choose and build your server with this project : [Server Build](https://proginfra.gitlab.io/server_build/#/)
2) With your machine, you can now install the **operating system** : **[TrueNAS Scale](https://www.truenas.com/truenas-scale/)**. You need to install the system with a **USB Boot Key**, download the iso on the official website and see this [documentations](https://progdevlab.gitlab.io/dyntools/#/docs/global/boot) to create this Key.
3) To install **TrueNAS**, you need also to check in your **BIOS** if you have **Virtualization** and **WakeOnLan** activated (If you try it with **VirtualBox**, you need to use **fixed size** for each **disk** and **Bridged Adapter** for the **network**).
   1) Enter "1" to enter in the install setup
   2) Select "1 Install/Upgrade"
   3) Press **SPACE** to select one or two drive to install the system on it and press **ENTER** (two drive can give you an high availability system installation !)
   4) Enter a password : **BE CAREFUL** because the keybord is in **QWERTY** by default
   5) Choose your boot type
   6) Wait for the finish of the installation
   7) Reboot and eject the installation media
   8) Wait the final installation and configuration process
   9) Now you can access the TrueNAS Admin Panel with the IP displayed on the terminal.
4) [Configure TrueNAS](./docs/configure.md).
5) [Configure Storage](./docs/storage.md).
6) [Configure Backup](./docs/backup.md).
7) [Configure Permissions with ACL and users](./docs/permissions.md).
8) [Configure SMB and NFS Share](./docs/shares.md).
9) [What you can do now ?](./docs/next.md).
10) Create some [Virtual Machine](./docs/vm.md) if you want.
11) Create some [Container](./docs/container.md) if you want.
12) Configure [Domain](./docs/domain.md) if you want.
13) Configure [VPN](./docs/vpn.md) if you want.

### Server Access

- **SSH Access** : root@192.168.X.X
  - **Username** : root
  - **Password** : You have defined it !
- [TrueNAS Web UI](http://192.168.X.X) : Same credentials as SSH !

## Documentations

- [Ideas](./docs/ideas.md)
- [Configure](./docs/configure.md)
- [Storage](./docs/storage.md)
- [Backup](./docs/backup.md)
- [Permissions](./docs/permissions.md)
- [Shares](./docs/shares.md)
- [Next](./docs/next.md)
- [Virtual Machine](./docs/vm.md)
- [Container](./docs/container.md)
- [Domain](./docs/domain.md)
- [VPN](./docs/vpn.md)

## Development

If you want you can **develop** this repository :

1) You need to install the [Requirements](#requirements)
2) You can develop on [Docsify](#docsify)

### Requirements

We use **Docker** :

- Docker
- Docker Compose

### Docsify

```bash
cd docsify

# Development
docker-compose -f docker-compose.dev.yml up

# Production
docker-compose up --build
```

## Contributing

See [CONTRIBUTING](./CONTRIBUTING.md) for more information.

## Licence

This project is licensed under the terms of the MIT license.

See [LICENSE](./LICENCE.md) for more information.
