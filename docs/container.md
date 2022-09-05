# TrueNAS System : Container

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Container](#truenas-system--container)
  - [Table Of Contents](#table-of-contents)
  - [Description](#description)
  - [Init Apps](#init-apps)
  - [Add Community Catalogs](#add-community-catalogs)
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

## Add Community Catalogs

With just the official catalogs, we have a few apps, but not a lot, so we need to install the community catalogs :

1) Go to **Apps**
2) Click on **Manage Catalogs** and click on **Add Catalog**.
3) Use this documentation to add a new Catalog : [TrueCharts](https://truecharts.org/)
   1) **Catalog Name** : **truecharts**
   2) **Force Create** : Unchecked
   3) **Repository** : https://github.com/truecharts/catalog
   4) **Preferred Trains** : **stable**
   5) **Branch** : **main**
4) Wait the Catalogs to be loaded

## Install Apps from Catalogs

If the apps you want is in the catalogs, you can install it :

1) Go to **Apps**
2) Click on **Available Applications** and click on **install** on the apps you want.
3) Choose all **parameters** you want to setup your **apps**.

## Create a new Custom Apps

If you want, you can create your own apps, if it's not available in the main catalog :

1) Go to **Apps**
2) Click on **Launch Docker Image**
3) Choose all **parameters** you want to setup your **container**.
4) Click on save and wait for it to be **created** !

## Manually Launch Docker Compose

It's **not a good idea**, but you can **launch manually** a **Docker Compose file**, just copy or create your file on your **TrueNAS Server**, go to the **Shell** and run a **Docker Compose command** with it.
