# Le TP 1 back to Back OG

## I. Basics

### ☀️ Carte réseau WiFi

```bash
ipconfig /all

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Intel(R) Wi-Fi 6 AX201 160MHz
   Adresse physique . . . . . . . . . . . : DC-46-28-B5-66-57
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::f9ad:14b2:37b4:90c2%29(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.74.93(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Bail obtenu. . . . . . . . . . . . . . : mercredi 2 octobre 2024 08:57:16
   Bail expirant. . . . . . . . . . . . . : vendredi 4 octobre 2024 08:54:37
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
   Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
   IAID DHCPv6 . . . . . . . . . . . : 165430824
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2C-0C-01-3A-04-7C-16-AC-F9-CA
   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```



- L'adresse MAC de votre carte Wifi : **DC-46-28-B5-66-57**
- L'adresse IP de votre carte Wifi : **10.33.74.93**
- Le masque de sous-réseau : **/20** & **255.255.240.0** 

### ☀️ Déso pas déso

- l'adresse de réseau du LAN auquel vous êtes connectés en WiFi : **10.33.64.0**
- l'adresse de broadcast : 	**10.33.74.254**
- le nombre d'adresses IP disponibles dans ce réseau : **4094**

### ☀️ Hostname

```bash
PS C:\Users\trist> hostname
MSI
PS C:\Users\trist>
```

(wouah le nom de merde)

### ☀️ Passerelle du réseau

```bash
Interface : 10.33.74.93 --- 0x1d
  Adresse Internet      Adresse physique      Type
  10.33.69.24           b8-1e-a4-8f-79-47     dynamique
  10.33.69.210          88-ce-43-20-fa-36     dynamique
  10.33.73.77           98-8d-46-c4-fa-e5     dynamique
  10.33.73.107          98-59-7a-ca-5f-67     dynamique
  10.33.77.160          c8-94-02-f8-ab-97     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique
```


- l'adresse IP de la passerelle du réseau : **10.33.74.254**
- l'adresse MAC de la passerelle du réseau : **7c-5a-1c-d3-d8-76**

### ☀️ Serveur DHCP et DNS




- l'adresse IP du serveur DHCP qui vous a filé une IP : **10.33.74.254**
- l'adresse IP du serveur DNS que vous utilisez quand vous allez sur internet : **8.8.8.8**

### ☀️ Table de routage

- dans votre table de routage, laquelle est la route par défaut :

``` bash
Destination réseau    Masque réseau  Adr. passerelle   Adr. interface Métrique
        ⭐  0.0.0.0          0.0.0.0     10.33.79. 254      10.33.74.93     30 ⭐
         10.2.1.0    255.255.255.0         On-link          10.2.1.1    281
         10.2.1.1  255.255.255.255         On-link          10.2.1.1    281
       10.2.1.255  255.255.255.255         On-link          10.2.1.1    281
         10.3.1.0    255.255.255.0         On-link          10.3.1.1    281
```

## II. Go further

### ☀️ Hosts ?

- faites en sorte que pour votre PC, le nom b2.hello.vous corresponde à l'IP 1.1.1.1

``` bash
PS C:\Users\trist> ping b2.hello.vous

Envoi d’une requête 'ping' sur b2.hello.vous [1.1.1.1] avec 32 octets de données :
Réponse de 1.1.1.1 : octets=32 temps=14 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=20 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=15 ms TTL=55
Réponse de 1.1.1.1 : octets=32 temps=15 ms TTL=55

Statistiques Ping pour 1.1.1.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 14ms, Maximum = 20ms, Moyenne = 16ms
```

``` bash
PS C:\Windows\System32\drivers\etc> type hosts
# Copyright (c) 1993-2009 Microsoft Corp.
#
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.
#
# This file contains the mappings of IP addresses to host names. Each
# entry should be kept on an individual line. The IP address should
# be placed in the first column followed by the corresponding host name.
# The IP address and the host name should be separated by at least one
# space.
#
# Additionally, comments (such as these) may be inserted on individual
# lines or following the machine name denoted by a '#' symbol.
#
# For example:
#
#      102.54.94.97     rhino.acme.com          # source server
#       38.25.63.10     x.acme.com              # x client host
        1.1.1.1         b2.hello.vous


# localhost name resolution is handled within DNS itself.
#       127.0.0.1       localhost
#       ::1             localhost
```

(oui je suis un fragile j'ai pas réussi à Edit par Shell)

### ☀️ Go mater une vidéo youtube et déterminer, pendant qu'elle tourne...



- l'adresse IP du serveur auquel vous êtes connectés pour regarder la vidéo : **91.68.245.15**
- le port du serveur auquel vous êtes connectés : **443**
- le port que votre PC a ouvert en local pour se connecter au port du serveur distant **63293**

### ☀️ Requêtes DNS

- à quelle adresse IP correspond le nom de domaine www.thinkerview.com


``` bash
PS C:\Windows\system32> nslookup www.thinkerview.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.thinkerview.com
Addresses:  ⭐ 2a06:98c1:3120::7
          2a06:98c1:3121::7
          188.114.96.7
          188.114.97.7 ⭐
```

- à quel nom de domaine correspond l'IP 143.90.88.12

``` bash
PS C:\Windows\system32> nslookup 143.90.88.12
Serveur :   dns.google
Address:  8.8.8.8

Nom :   ⭐ EAOcf-140p12.ppp15.odn.ne.jp ⭐
Address:  143.90.88.12

```

### ☀️ Hop hop hop

```bash
PS C:\Windows\system32> tracert www.ynov.com

Détermination de l’itinéraire vers www.ynov.com [104.26.10.233]
avec un maximum de 30 sauts :

  1     3 ms     1 ms     1 ms  10.33.79.254
  2     3 ms     1 ms     1 ms  145.117.7.195.rev.sfr.net [195.7.117.145]
  3     2 ms     2 ms     2 ms  237.195.79.86.rev.sfr.net [86.79.195.237]
  4     3 ms     2 ms     3 ms  196.224.65.86.rev.sfr.net [86.65.224.196]
  5    10 ms    10 ms    10 ms  164.147.6.194.rev.sfr.net [194.6.147.164]
  6     *        *        *     Délai d’attente de la demande dépassé.
  7    22 ms    17 ms    15 ms  162.158.20.240
  8    16 ms    16 ms    25 ms  104.26.10.233

Itinéraire déterminé.
```

### ☀️ IP publique

``` bash
PS C:\Windows\system32> nslookup myip.opendns.com resolver1.opendns.com
Serveur :   UnKnown
Address:  208.67.222.222

Réponse ne faisant pas autorité :
Nom :    myip.opendns.com
Address:  ⭐ 195.7.117.146 ⭐

```

## III. Le requin

### ☀️ Capture ARP

[Lien vers capture ARP](./captures/arp.pcapng)

### ☀️ Capture DNS

``` bash
PS C:\Windows\system32> nslookup youtube.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    youtube.com
Addresses:  2a00:1450:4007:818::200e
          142.250.179.110

```

[Lien vers capture DNS](./captures/dns.pcapng)

### ☀️ Capture TCP

[Lien vers capture TCP](./captures/tcp.pcapng)

