# TrueNAS System : Permissions

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Permissions](#truenas-system--permissions)
  - [Table Of Contents](#table-of-contents)
  - [Create Users and Groups](#create-users-and-groups)
  - [Configure ACL Permission](#configure-acl-permission)
  - [Next](#next)

## Create Users and Groups

First of all, you can create some **users** to access your **shared data**, **groups** are also great to give **permissions** to a amount of **users** :

1) Go to **Credentials/Local Users**
2) Click on **add** to add a new **User**
3) Write some **basic informations** like **full name**, **username** (lowercase)
4) Verify you have **Samba Authentication** checked
5) Click on **Save**, you have your user **created** !

If you want to create some groups, it's very simple :

1) Go to **Credentials/Local Groups**
2) Click on **add** to add a new **Group**
3) Choose a **name** for your **group** (lowercase)
4) Verify you have **Samba Authentication** checked
5) Click on **Save**, you have your group **created** !
6) Next to add some **users** to this **group**, you can **edit** your **user** to add it to the **group** or you can also **edit** the **group members** to add some **users** to this **group**.

## Configure ACL Permission

Now you have to setup some permission with ACL system to your dataset to configure access for users :

1) Go to **Storage**
2) Click on the **three vertical dots** on the left of a **dataset** you want to setup some **permission** and click on **view permission**.
3) Click on the **pen** to **edit dataset permissions**.
4) **Don't change anything** (or if your expert, you can XD), click on **set ACL**.
5) Select a **preset ACL** with some default value, **POSIX_RESTRICTED** is a **good way** to start.
6) If it's your **first ACL** for this **dataset**, you have to click on **Add Item** an choose a **mask** with **appropriate permissions**.
7) Click on **Add Item** and choose a **group** or **user** to grant some **permissions**, select permissions you want to add.
8) Check Apply **permissions recursively** and Apply **permissions** to **child datasets** if you want.
9) Finally click on **Save Access Control List** and you have setup your **permissions** !

## Next

You can [configure SMB and NFS Share](./shares.md).
