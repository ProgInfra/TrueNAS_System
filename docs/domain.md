# TrueNAS System : Domain

![Icon](../icon.png)

## Table Of Contents

- [TrueNAS System : Domain](#truenas-system--domain)
  - [Table Of Contents](#table-of-contents)
  - [Provider](#provider)
  - [TrueNAS](#truenas)

## Provider

First of all, you need to get a domain name in a good provider :

1) Search a provider compatible with DNS Challenge here at [Traefik Documentation](https://doc.traefik.io/traefik/https/acme/#dnschallenge), for us we use [Cloudflare](https://www.cloudflare.com/fr-fr/products/registrar/).
2) Buy a new Domain Name and register it with true information.
3) Create new Tokens for our server : (Go to **My Profile/API Tokens**)
   1) TrueNAS Custom Token (**Zone, Zone, Read** and **Zone, DNS, Edit**)
   2) (ONLY IF YOU USE TRAEFIK MANUALLY) Traefik Custom Tokens (One with **Zone, Zone, Read** and one with **Zone, DNS, Edit**)
4) Update DNS entries :
   1) Add a new entry : Type : A / Name : DATA.DOMAIN.NET / Content : 192.168.1.42 / No Proxy / TTL : Auto
   2) Add a new entry : Type : A / Name : *.DATA.DOMAIN.NET / Content : 192.168.1.42 / No Proxy / TTL : Auto
   3) (ONLY IF YOU USE TRAEFIK MANUALLY) Add a new entry for each service you need : Type : A / Name : SERVICE.DATA.DOMAIN.NET / Content : 192.168.1.43 / No Proxy / TTL : Auto

## TrueNAS

Next you have to connect your domain name on TrueNAS main interface : [Some Youtube Tutorial](https://www.youtube.com/watch?v=TJ5fDiDRcbU)

1) First of all, edit your **root** user and add an email to it.
2) Go to **Credentials/Certificates**.
3) Add a new **ACME DNS-Authenticators** :
   1) Name : cloudflare
   2) Authenticator : cloudflare
   3) API Token : Previous created Token for TrueNAS
4) Add a new **Certificate Signing Requests** :
   1) Name : csr
   2) Type : Certificate Signing Request
   3) Profiles : HTTPS RSA Certificate
   4) Key Type : RSA
   5) Key Length : 2048
   6) Digest Algorithm : SHA256
   7) Certificate Subject : Fill it with your information
   8) Subject Alternate Names : *.DOMAIN.NET (exemple : *.testy.net or *.games.testy.net)
   9) Next with default parameters and Save It
5) Click on the key on your **csr** : Create ACME Certificate :
   1) Identifier : cert
   2) Check Terms of service
   3) Let's Encrypt Production
   4) Select **cloudflare** on Authenticator
   5) Save it and generate a new certificate
6) Finally switch your default certificate and domain name to your new : DOMAIN.NET.net
