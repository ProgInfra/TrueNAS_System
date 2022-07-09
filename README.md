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
3) [Configure TrueNAS](./docs/configure.md).
4) [Configure Storage](./docs/storage.md).
5) [Configure Backup](./docs/backup.md).
6) [Configure Permissions with ACL and users](./docs/permissions.md).
7) [Configure SMB and NFS Share](./docs/shares.md).
8) Create some [Virtual Machine](./docs/vm.md) if you want.
9) Create some [Container](./docs/container.md) if you want.
10) [What you can do now ?](./docs/next.md).

### Server Access

- **SSH Access** : USER@192.168.X.X
  - **Username** : USER
  - **Password** : You have defined it !
- [TrueNAS Web UI](http://192.168.X.X) : Same credentials as SSH !

## Documentations

- [Ideas](./docs/ideas.md)
- [Configure](./docs/configure.md)
- [Storage](./docs/storage.md)
- [Backup](./docs/backup.md)
- [Permissions](./docs/permissions.md)
- [Shares](./docs/shares.md)
- [Virtual Machine](./docs/vm.md)
- [Container](./docs/container.md)
- [Next](./docs/next.md)

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
