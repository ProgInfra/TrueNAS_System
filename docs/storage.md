# TrueNAS System : Storage

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Storage](#truenas-system--storage)
  - [Table Of Contents](#table-of-contents)
  - [Config Pool](#config-pool)
  - [Next](#next)

## Config Pool

Now it's time to configure some Pool with ZFS and get each powerful ZFS functionalities :

1) Go to **Storage**
2) Click on **Create Pool**
3) Choose the name, check **encryption** if you want and click on **Suggest Layout** to get a good mapping of your disk or do it yourself (don't forget to save your encryption key !)
4) Go to **Tasks/S.M.A.R.T. Tests** and add a test for each disk (one short each day and one long each week)
5) Normally you have some Scrub tasks each week to verify and fix some error on disk.
6) Finally you can add some **Dataset** on your **pool** to create some **global folder** with all your data in it.

> A good practive is to **conserve** your **encryption keys** in a **account manager** (like **Bitwarden** or **Keepass**) and save it on **multiple support** (**local** and **Cloud**) to prevent from **key stole** or **system crash**.

## Next

You can [configure some backup](./backup.md).
