# tp1
I. Most simplest LAN


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

Ensuite pour venir comfirmer le changement je vien faire un

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
Je vais Maintenant Ping Node1 vers Node2 puis l'inverse
```
Node1
[hugo@localhost ~]$ ping 192.168.56.122
PING 192.168.56.122 (192.168.56.122) 56(84) bytes of data.
64 bytes from 192.168.56.122: icmp_seq=1 ttl=64 time=1.82 ms
64 bytes from 192.168.56.122: icmp_seq=2 ttl=64 time=5.24 ms
64 bytes from 192.168.56.122: icmp_seq=3 ttl=64 time=2.01 ms
```

```
Node2
[hugo@localhost ~]$ ping 192.168.56.121
PING 192.168.56.121 (192.168.56.121) 56(84) bytes of data.
64 bytes from 192.168.56.121: icmp_seq=1 ttl=64 time=14.3 ms
64 bytes from 192.168.56.121: icmp_seq=2 ttl=64 time=1.34 ms
64 bytes from 192.168.56.121: icmp_seq=3 ttl=64 time=1.50 ms
```




II. Ajoutons un switch


 Voici les adresses Mac de mes 3 nodes
 
```
 Node 1 08:00:27:36:91:51 
 Node 2 08:00:27:66:a0:03
 Node 3 08:00:27:0c:eb:a7
```

```
Node3 :
NAME=enp0s8
DEVICE=enp0s8

BOOTPROTO=static
ONBOOT=yes

IPADDR=192.168.56.123
NETMASK=255.255.255.0


```

```sudo nmcli con reload ```                                               


```sudo nmcli con up enp0s8 ```


Je vais Maintenant Ping 
Node1 vers Node2 
Node2 vers Node3
Node1 vers Node3


``` 
Node1 vers Node2

```

```
Node2 vers Node3

```

```
Node1 vers Node3

```


III. Serveur DHCP






