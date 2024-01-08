
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

























