# TrueNAS System : VPN

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : VPN](#truenas-system--vpn)
  - [Table Of Contents](#table-of-contents)
  - [WireGuard](#wireguard)
  - [TailScale and HeadScale](#tailscale-and-headscale)

## WireGuard

[WireGuard](https://www.wireguard.com/) is great **VPN** to access to your **local networks**, services and server when you're outside your **home network**.

Manage **WireGuard** is simple but you need to generate or create manually your configuration files, there are a little app called [WireGuard Easy](https://github.com/wg-easy/wg-easy) that give you a good and simple **Web UI** to manage each access to your **VPN**.

On **TrueNAS Scale**, we'll install **WireGuard** as a **container apps**, so you need to setup some **requirements** before install it :

- **Bridge network** for each your apps (**ex**: br0)
- **Container Apps** initialized

Here is how to install it :

1) Go to **Apps**
2) Go to **Available Applications**, search **wg-easy** and click on install on the official **Truenas** version.
3) **Application Name** : Name that you want (**ex**: vpn)
4) **WG-Easy Configuration** :
   1) **Hostname or IP** : The Domain of IP of your public home network (**ex**: vpn.domain.net => Your box from internet)
   2) **Password for WebUI** : The password you want for the web UI
   3) **Clients IP Address Range** : Leave default
   4) **Clients DNS Server** : Leave default or change it if you want
5) **WG-Easy Environment** : You need to add some custom variable to configure the bridge network
   1) **WG_POST_UP** : `iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -o br0 -j MASQUERADE; iptables -A INPUT -p udp -m udp --dport 51820 -j ACCEPT; iptables -A FORWARD -i wg0 -j ACCEPT; iptables -A FORWARD -o wg0 -j ACCEPT;`
   2) **WG_PRE_UP** : `iptables -t nat -F; iptables -F;`
6) **Storage** : You can store if you want, but files are regenerated at each startup.
7) **Networking** :
   1) **WireGuard UDP Node Port for WG-Easy** : You have to change it to 51820 (because any other port won't work)
   2) **WebUI Node Port for WG-Easy** : You can use the port you want (**ex**: 51821)
   3) **Host Netowork** : Checked
8) **Resource Limits** : Configure these if you want
9) Click on save and wait for **deployment** to complete
10) Go to the web address of the **admin UI** : `http://192.168.1.X:51821`
11) Add a **new user** and **scan** with the **WireGuard** application on your **smartphone** the **QR Code**
12) Open the **UDP Port 51820** on your **network box / router** to allow it to connect to your **VPN** server
13) Try to **connect** to one of your server through the **VPN** with your **smartphone** on **5G network**
14) You've **done**, enjoy your **server** everywhere with internet !

## TailScale and HeadScale

TODO Upgrade of WireGuard
