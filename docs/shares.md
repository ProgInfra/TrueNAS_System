# TrueNAS System : Shares

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Shares](#truenas-system--shares)
  - [Table Of Contents](#table-of-contents)
  - [SMB Share](#smb-share)
  - [NFS Share](#nfs-share)
  - [iSCSI Share](#iscsi-share)
  - [Next](#next)

## SMB Share

SMB alias CIFS is a great storage share protocol fully compatible with Windows and also with Linux, here is how to setup it :

First configure **SMB Server** :

1) Go to **Shares**
2) Click on the **three vertical dots** on the left of the Windows (SMB) Shares and click on Config Service.
3) Config the **NetBIOS Name** (displayed on your network) and **description**.
4) Click on **Save** and in **services**, **switch the toggle** to on for **running** and **check** the case **start automatically** for **SMB**.
5) Your **SMB server** is on !

Next you can configure **SMB Server** :

1) Go to **Shares**
2) Click on Add to configure a new shared folder.
3) Choose the folder you want to share, a name if you want and the purpose (Default share parameters is good and multi user is good too, some options are available).
4) Click on Save and you have your SMB Share Folder activated !

You can now connect to your shared folders with the SMB protocol, here some [documentations](https://progdevlab.gitlab.io/dyntools/#/docs/linux/smb).

## NFS Share

NFS is a great storage share protocol for Linux (or Windows Pro), but it's designed for server share more than personnal share, here is how to setup it :

First configure NFS Server :

1) Go to **Shares**

Next you can configure NFS Server :

1) TODO

You can now connect to your shared folders with the NFS protocol, here some [documentations](https://progdevlab.gitlab.io/dyntools/#/docs/linux/nfs).

## iSCSI Share

TODO

## Next

[What you can do now ?](./next.md)
