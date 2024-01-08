
🌞 Mettre en place la topologie dans GS3
reproduisez la topologie, configurez les IPs et les noms sur toutes les machines
une fois en place, assurez-vous donc que :

toutes les machines du réseau 1 peuvent se ping entre elles

```
[root@node1 ~]# ping 10.3.1.12
PING 10.3.1.12 (10.3.1.12) 56(84) bytes of data.
64 bytes from 10.3.1.12: icmp_seq=1 ttl=64 time=3.25 ms
64 bytes from 10.3.1.12: icmp_seq=2 ttl=64 time=2.67 ms
```
