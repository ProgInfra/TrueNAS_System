# TrueNAS System : Backup

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Backup](#truenas-system--backup)
  - [Table Of Contents](#table-of-contents)
  - [Description](#description)
  - [RSync](#rsync)
  - [Snapshots](#snapshots)
  - [RSync and Snapshots combination](#rsync-and-snapshots-combination)
  - [Cloud](#cloud)
    - [Backup to Cloud](#backup-to-cloud)
    - [Backup of Cloud](#backup-of-cloud)
    - [Minio](#minio)
  - [Duplicati](#duplicati)
  - [Next](#next)

## Description

When you use have some data, you want to **backup** them in case of problem with your disk. You can say "**RAID** can assure my data are **available**" and it's right, but **RAID IS NOT A BACKUP**, if you RAID is **corrupted** by a **virus** or a **ransomeware**, you can't resolve it without a **properly backup system**.

There are a lot of possibility to setup a **backup**, the best way if you have only **two disk** isn't a **RAID** but one disk for **data** and one disk for **backup**.

Now you have a disk or a volume to backup all your data in it, you can use different **system** and **software** do to this, use the method you want bellows.

> **Be careful** : **RAID IS NOT A BACKUP**, with a **RAID** you have more **read** or **write** capacity with **high availability**, you can lost one disk but if data are **corrupted**, **both disk are corrupted** !

## RSync

You can use **RSync** to copy data from one volume to another volume (with **SSH** or **local**), this copy can scan differences to copy just **missing** data. It's a **good way** if the system you want to backup **ins't ZFS**.

To setup it, here a **sample** :

1) Go to **Data Protection**
2) On **RSync Tasks**, click on **Add**
3) Select your **source** path, **destination** path, the **user** and **direction** for the **data** and a **schedule**.
4) You can choose some **options** if you want and click on **Save**.

## Snapshots

**Snapshots** is the best way to backup your **data**, you can setup some **snapshot** on each volumes in **ZFS periodically** and transfert these to the backup volumes, this way you have different **version** of your data that are **securely** on your **backup** disk.

To setup it, here a **sample** :

1) Go to **Data Protection**
2) On **Replication Tasks**, click on **Add**
3) Select your **source** location, **destination** location and check **recursive** (you can also setup some encryption if you want but save the key !).
4) You can choose the schedule and other options if you want and click on **Start Replication**.
5) Now you have schedule a replication of your data in your disk.

## RSync and Snapshots combination

You can also combine some **technologies** like **RSync** and **Snapshots**, first use RSync to **copy your data** in your Backup disk and finally setup a **snapshot system** on your Backup disk.

To do this use [RSync](#rsync) and setup some [Snapshots](#snapshots) on your backup disk.

## Cloud

### Backup to Cloud

TODO

### Backup of Cloud

TODO

### Minio

TODO https://www.truenas.com/docs/scale/scaleuireference/apps/minioclustersscale/

## Duplicati

If you want, you can use **Duplicati** to **backup all** your file, but you need to have access to these files through a **SMB** or **NFS** Share, because we haven't the **permission** to get access to each files.

To do this, you need to create a **VM** with **Docker** and the **Duplicati service** configured with **SMB** or **NFS** shares.

You can also configure it with the container engine in **TrueNAS** but you have to setup each volume as **SMB** or **NFS** shares.

## Next

You can [configure permissions with ACL and users](./permissions.md).
