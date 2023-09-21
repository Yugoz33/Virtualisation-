# tp1

Déterminer l'adresse MAC de vos deux machines :

```ip a```

node1 = link/ether 08:00:27:36:91:51          


node2 = link/ether 08:00:27:66:a0:03



Définir une IP statique sur les deux machines :


```sudo nano /etc/sysconfig/network-scripts/ifcfg-enp0s8```
ici je change l'ip et je met 192.168.56.121 et 192.168.56.122               


```sudo nmcli con reload ```
```sudo nmcli con up enp0s8 ```
