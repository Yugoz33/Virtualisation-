
**🌞 Mettre en place la topologie dans GS3** ,
reproduisez la topologie, configurez les IPs 
et les noms sur toutes les machines
une fois en place, assurez-vous donc que :

toutes les machines du réseau 1 peuvent se ping entre elles

```
[root@node1 ~]# ping 10.3.1.12
PING 10.3.1.12 (10.3.1.12) 56(84) bytes of data.
64 bytes from 10.3.1.12: icmp_seq=1 ttl=64 time=3.25 ms
64 bytes from 10.3.1.12: icmp_seq=2 ttl=64 time=2.67 ms
```
toutes les machines du réseau 2 peuvent se ping entre elles

```
[root@node2 ~]# ping 10.3.2.11
PING 10.3.2.11 (10.3.2.11) 56(84) bytes of data.
64 bytes from 10.3.2.11: icmp_seq=1 ttl=64 time=3.44 ms
64 bytes from 10.3.2.11: icmp_seq=2 ttl=64 time=4.12 ms
```

toutes les machines du réseau 3 peuvent se ping entre elles

```
[root@routeur2 ~]# ping 10.3.100.1
PING 10.3.100.1 (10.3.100.1) 56(84) bytes of data.
64 bytes from 10.3.100.1: icmp_seq=1 ttl=64 time=1.86 ms
64 bytes from 10.3.100.1: icmp_seq=2 ttl=64 time=1.49 ms
```

le router1.tp3 doit avoir un accès internet normal
```
[root@routeur1 ~]# ping google.com
PING google.com (142.250.179.78) 56(84) bytes of data.
64 bytes from par21s19-in-f14.1e100.net (142.250.179.78): icmp_seq=1 ttl=128 time=15.9 ms
64 bytes from par21s19-in-f14.1e100.net (142.250.179.78): icmp_seq=2 ttl=128 time=17.2 ms
64 bytes from par21s19-in-f14.1e100.net (142.250.179.78): icmp_seq=3 ttl=128 time=15.4 ms
```

🌞 Mettre en place les routes locales
config a mettre dans node1.net1 et node2.net1
```
nano /etc/sysconfig/network-scripts/route-enp0s10

10.3.2.0/24 via 10.3.100.1
```

config a mettre dans routeur1
```
nano /etc/sysconfig/network-scripts/route-enp0s10

10.3.2.0/24 via 10.3.100.2
```

config a mettre dans node1.net2, node2.net2
```
nano /etc/sysconfig/network-scripts/route-enp0s3

10.3.1.0/24 via 10.3.100.2
```

config a mettre dans routeur2
```
nano /etc/sysconfig/network-scripts/route-enp0s3

10.3.1.0/24 via 10.3.100.1
```

🌞 Mettre en place les routes par défaut

prouvez avec un ping depuis node1.net1.tp3 que vous avez bien un accès internet

```
[root@node1 ~]# ping google.com
PING google.com (142.250.179.78) 56(84) bytes of data.
64 bytes from par21s19-in-f14.1e100.net (142.250.179.78): icmp_seq=1 ttl=127 time=18.6 ms
64 bytes from par21s19-in-f14.1e100.net (142.250.179.78): icmp_seq=2 ttl=127 time=19.6 ms
```


prouvez avec un traceroute depuis node2.net1.tp3 que vous avez bien un accès internet, et que vos paquets transitent bien par router2.tp3 puis par router1.tp3 avant de sortir vers internet

```
[root@node2 ~]# traceroute google.com
traceroute to google.com (172.217.20.174), 30 hops max, 60 byte packets
 1  _gateway (10.3.2.254)  5.071 ms  4.470 ms  4.340 ms
 2  10.3.100.1 (10.3.100.1)  4.217 ms  4.089 ms  2.886 ms
 3  192.168.190.2 (192.168.190.2)  2.785 ms  2.703 ms  2.600 ms
 4  * * *
```





















