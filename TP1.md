# tp1

Déterminer l'adresse MAC de vos deux machines :

```ip a```

node1 = link/ether 08:00:27:36:91:51          


node2 = link/ether 08:00:27:66:a0:03



Définir une IP statique sur les deux machines :


```sudo nano /etc/sysconfig/network-scripts/ifcfg-enp0s8```
```Node1 :
NAME=enp0s8
DEVICE=enp0s8

BOOTPROTO=static
ONBOOT=yes

IPADDR=192.168.56.121
NETMASK=255.255.255.0
```
```Node2 :
NAME=enp0s8
DEVICE=enp0s8

BOOTPROTO=static
ONBOOT=yes

IPADDR=192.168.56.122
NETMASK=255.255.255.0
```

```sudo nmcli con reload ```                                               


```sudo nmcli con up enp0s8 ```
