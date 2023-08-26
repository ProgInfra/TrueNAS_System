# TrueNAS System : Container

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Container](#truenas-system--container)
  - [Table Of Contents](#table-of-contents)
  - [Description](#description)
  - [Init Apps](#init-apps)
  - [Add Community Catalogs : TrueCharts](#add-community-catalogs--truecharts)
  - [Install Traefik as main Ingress](#install-traefik-as-main-ingress)
  - [Install Apps from Catalogs](#install-apps-from-catalogs)
  - [Create a new Custom Apps](#create-a-new-custom-apps)
  - [Manually Launch Docker Compose](#manually-launch-docker-compose)

## Description

TrueNAS Scale contains a Container engine, with this you can setup some container, this is the best way to install some application.

There two possibility, the first, a Debian VM with Docker installed to run some container, and the TrueNAS way, we use the internal TrueNAS Container engine.

If you want to setup a Debian VM, you can go to the [VM documentation](./vm.md).

## Init Apps

First of all, you need to create a space to save all apps data :

1) Go to **Apps**
2) You need to **choose a pool for Apps**, choose a **data pool** for this.
3) Click on Choose and **wait** for the engine to be installed.

## Add Community Catalogs : TrueCharts

With just the official catalogs, we have a few apps, but not a lot, so we need to install the community catalogs :

1) Go to **Apps**
2) Click on **Manage Catalogs** and click on **Add Catalog**.
3) Use this documentation to add a new Catalog : [TrueCharts](https://truecharts.org/)
   1) **Catalog Name** : **truecharts**
   2) **Force Create** : Unchecked
   3) **Repository** : https://github.com/truecharts/catalog
   4) **Preferred Trains** : **stable**, **enterprise**, **operators**
   5) **Branch** : **main**
4) Wait the Catalogs to be loaded

## Install Traefik as main Ingress

To use Traefik, you need to setup properly the [domain](./domain.md).

> !!! Before install it, be careful to have port 80 and 443 changed by default on TrueNAS Admin Gui !!!

1) Go to **Apps**
2) Click on **Available Applications**, search "Traefik" and click on **install** on the app "Traefik Enterprise".
3) **Application Name** :
   1) **Application Name** : The name you want (ex: proxy)
   2) **Version** : Choose the one you want (latest available)
4) **Networking and Services** :
   1) Main Entrypoint Configuration : Don't change the port 9000
   2) web Entrypoint Configuration : Change 9080 to the port 80
   3) websecure Entrypoints Configuration : Change 9443 to the port 443
5) **Resources and Devices** :
   1) **CPU** : Choose the amount of CPU (ex: 500m)
   2) **RAM** : Choose the amount of RAM (ex: 1Gi)
6) **Middlewares (OPTIONAL)** : Here you can add some middleware to use for some apps
   1) **basicAuth** :
      1) Name = app-auth (MUST BE IN LOWERCASE !)
      2) Users = You can add some users if you want
7) Save it and launch your Traefik Ingress.

## Install Apps from Catalogs

If the apps you want is in the catalogs, you can install it :

1) Go to **Apps**
2) Click on **Available Applications** and click on **install** on the apps you want.
3) Choose all **parameters** you want to setup your **apps**.
4) **Application Name** :
   1) **Application Name** : The name you want
   2) **Version** : Choose the one you want
5) **Networking and Services** :
   1) **Service Type** : LoadBalancer to expose ports
   2) **Port** : Choose the port you want to expose (ex: 3000 to get to app with http://192.168.1.X:3000)
6) **Ingress** : If you have installed Traefik (to get url to access to service and HTTPS security)
   1) **Hosts** : Add one with the url you want : app.domain.net
   2) **TLS Settings** : Add one with the TrueNAS Scale certificate you've generated
7) **Resources and Devices** :
   1) **CPU** : Choose the amount of CPU
   2) **RAM** : Choose the amount of RAM
8) Save it and launch your app.

## Create a new Custom Apps

If you want, you can create your own apps, if it's not available in the main catalog :

1) Go to **Apps**
2) Click on **Launch Docker Image**
3) Choose all **parameters** you want to setup your **container**.
4) Click on save and wait for it to be **created** !

## Manually Launch Docker Compose

It's **not a good idea**, but you can **launch manually** a **Docker Compose file**, just copy or create your file on your **TrueNAS Server**, go to the **Shell** and run a **Docker Compose command** with it.
