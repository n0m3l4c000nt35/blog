---
layout: "../../../../layouts/HackingLayout.astro"
title: "Reconocimiento"
description: "Herramientas para usar y acciones a llevar a cabo en la fase de reconocimiento."
---

---

### [nmap](/blog/hacking/herramientas/nmap)

```shell
sudo nmap -p- -sS --open --min-rate 5000 -n -Pn 192.168.0.10 -oG openPorts
```
