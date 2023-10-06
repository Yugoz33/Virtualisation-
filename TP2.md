I. Routage

☀️ Configuration de router.tp2.efrei


ip a (node) 
```
[hugo@localhost ~]$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:80:70:2a brd ff:ff:ff:ff:ff:ff
    inet 10.2.1.1/24 brd 10.2.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe80:702a/64 scope link
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:b6:29:cb brd ff:ff:ff:ff:ff:ff
    inet 192.168.31.10/24 brd 192.168.31.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:feb6:29cb/64 scope link
       valid_lft forever preferred_lft forever


```

ip a (routeur)

```

[hugo@localhost network-scripts]$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:c8:94:15 brd ff:ff:ff:ff:ff:ff
    inet 10.2.1.254/24 brd 10.2.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fec8:9415/64 scope link
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:86:38:57 brd ff:ff:ff:ff:ff:ff
    inet 192.168.31.11/24 brd 192.168.31.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe86:3857/64 scope link
       valid_lft forever preferred_lft forever
4: enp0s9: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:db:c5:e0 brd ff:ff:ff:ff:ff:ff
    inet 192.168.128.131/24 brd 192.168.128.255 scope global dynamic noprefixroute enp0s9
       valid_lft 1631sec preferred_lft 1631sec
    inet6 fe80::8e81:a58c:b119:14eb/64 scope link noprefixroute
       valid_lft forever preferred_lft forever




```




```
[hugo@localhost ~]$ ping google.fr
PING google.fr (142.251.16.94) 56(84) bytes of data.
64 bytes from bl-in-f94.1e100.net (142.251.16.94): icmp_seq=1 ttl=128 time=100 ms
64 bytes from bl-in-f94.1e100.net (142.251.16.94): icmp_seq=2 ttl=128 time=98.4 ms
64 bytes from bl-in-f94.1e100.net (142.251.16.94): icmp_seq=3 ttl=128 time=104 ms
64 bytes from bl-in-f94.1e100.net (142.251.16.94): icmp_seq=4 ttl=128 time=99.9 ms
64 bytes from bl-in-f94.1e100.net (142.251.16.94): icmp_seq=5 ttl=128 time=99.7 ms
^C
--- google.fr ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4023ms
rtt min/avg/max/mdev = 98.413/100.415/103.797/1.807 ms

```
☀️ Configuration de node1.tp2.efrei


Ping de la Node au Router
```
[hugo@localhost network-scripts]$ ping 10.2.1.254
PING 10.2.1.254 (10.2.1.254) 56(84) bytes of data.
64 bytes from 10.2.1.254: icmp_seq=1 ttl=64 time=1.01 ms
64 bytes from 10.2.1.254: icmp_seq=2 ttl=64 time=1.72 ms
64 bytes from 10.2.1.254: icmp_seq=3 ttl=64 time=2.07 ms
64 bytes from 10.2.1.254: icmp_seq=4 ttl=64 time=4.14 ms
^C
--- 10.2.1.254 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3441ms
rtt min/avg/max/mdev = 1.011/2.233/4.135/1.161 ms


```

Ping internet depuis la node 1
```
[hugo@localhost network-scripts]$ ping google.com
PING google.com (142.250.179.110) 56(84) bytes of data.
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=1 ttl=127 time=28.9 ms
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=2 ttl=127 time=23.2 ms
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=3 ttl=127 time=27.5 ms
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=4 ttl=127 time=29.7 ms
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=5 ttl=127 time=27.4 ms
64 bytes from par21s20-in-f14.1e100.net (142.250.179.110): icmp_seq=6 ttl=127 time=28.1 ms
^C
--- google.com ping statistics ---
6 packets transmitted, 6 received, 0% packet loss, time 5023ms
rtt min/avg/max/mdev = 23.151/27.474/29.747/2.094 ms


```
Command Traceroute

```
[hugo@localhost network-scripts]$ traceroute 8.8.8.8
traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets
 1  _gateway (192.168.128.2)  2.746 ms  2.166 ms  1.976 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 9  * * *
10  * * *

```

















































































