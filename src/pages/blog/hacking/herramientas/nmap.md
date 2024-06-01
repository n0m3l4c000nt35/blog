---
layout: "../../../../layouts/HackingLayout.astro"
title: "nmap"
description: "Utilidad gratuita y de código abierto para el descubrimiento de redes y auditorías de seguridad."
link: "https://nmap.org/"
---

## Descubrimiento de host

Escanear rango de red

```shell
sudo nmap 192.168.0.2/24 -sn
```

Escanear usando un archivo con una lista de direcciones IP

```shell
sudo nmap -sn -oA tnet -iL hosts.lst | grep for | cut -d" " -f5
```

Escanear múltiples direcciones IP

```shell
sudo nmap -sn -oA tnet 192.168.0.2 192.168.0.3 192.168.0.4 | grep for | cut -d" " -f5
```

Escanear múltiples direcciones IP definiendo el rango

```shell
sudo nmap -sn -oA tnet 192.168.0.2-4 | grep for | cut -d" " -f5
```

Escanear una dirección IP

```shell
sudo nmap 192.168.0.2 -sn -oA host
```

Escanear viendo todos los paquetes enviados y recibidos

```shell
sudo nmap 192.168.0.2 -sn -oA host -PE --packet-trace
```

Escanear obteniendo la razón por la que un puerto se encuentra en un estado particular

```shell
sudo nmap 192.168.0.2 -sn -oA host -PE --reason
```

Escanear deshabilitando solicitudes ARP

```shell
sudo nmap 192.168.0.2 -sn -oA host -PE --packet-trace --disable-arp-ping
```

Escanear puertos más comunes

```shell
sudo nmap 192.168.0.2 --top-ports=10
```

Escanear rastreando los paquetes

```shell
sudo nmap 192.168.0.2 -p 21 --packet-trace -Pn -n --disable-arp-ping
```

Escanear usando el escaneo Connect

```shell
sudo nmap 192.168.0.2 -p 443 --packet-trace --disable-arp-ping -Pn -n --reason -sT
```

Escanear puerto UDP

```shell
sudo nmap 192.168.0.2 -F -sU
```

Escanear versiones

```shell
sudo nmap 192.168.0.2 -Pn -n --disable-arp-ping --packet-trace -p 445 --reason  -sV
sudo nmap 192.168.0.2 -p- -sV
```

Escanear utilizando scripts

```shell
sudo nmap 192.168.0.2 -sC
sudo nmap 192.168.0.2 --script malware
sudo nmap 192.168.0.2 --script banner
```

Escanear agresivamente

```shell
sudo nmap 192.168.0.2 -p 80 -A
```

Escanear vulnerabilidades

```shell
sudo nmap 192.168.0.2 -p 80 -sV --script vuln
```
