# tp1

Déterminer l'adresse MAC de vos deux machines :

```ip a```

node1 = MAC 08:00:27:36:91:51          
IP = 192.168.56.101

node2 = MAC 08:00:27:66:a0:03

IP = 192.168.56.101


Définir une IP statique sur les deux machines :


```sudo nano /etc/sysconfig/network-scripts/ifcfg-enp0s8```
```
Node1 :
NAME=enp0s8
DEVICE=enp0s8

BOOTPROTO=static
ONBOOT=yes

IPADDR=192.168.56.121
NETMASK=255.255.255.0
```
```
Node2 :
NAME=enp0s8
DEVICE=enp0s8

BOOTPROTO=static
ONBOOT=yes

IPADDR=192.168.56.122
NETMASK=255.255.255.0
```

```sudo nmcli con reload ```                                               


```sudo nmcli con up enp0s8 ```


```ip a```

```
Node1
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:36:91:51 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.121/24 brd 192.168.56.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe36:9151/64 scope link
       valid_lft forever preferred_lft forever
```

```
Node2
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:66:a0:03 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.122/24 brd 192.168.56.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe66:a003/64 scope link
       valid_lft forever preferred_lft forever
```
