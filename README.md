# devops-DZ3.8

# Домашнее задание к занятию "3.8. Компьютерные сети, лекция 3"

>1. Подключитесь к публичному маршрутизатору в интернет. Найдите маршрут к вашему публичному IP
```bash
telnet route-views.routeviews.org
Username: rviews
show ip route x.x.x.x/32
show bgp x.x.x.x/32
```
### Ответ ###
```bash
route-views>show ip route 91.188.184.23
Routing entry for 91.188.184.0/24
  Known via "bgp 6447", distance 20, metric 0
  Tag 3267, type external
  Last update from 194.85.40.15 3d15h ago
  Routing Descriptor Blocks:
  * 194.85.40.15, from 194.85.40.15, 3d15h ago
      Route metric is 0, traffic share count is 1
      AS Hops 3
      Route tag 3267
      MPLS label: none
```
```bash
route-views>show ip route 91.188.184.23
BGP routing table entry for 91.188.184.0/24, version 2347352588
Paths: (23 available, best #4, table default)
  Not advertised to any peer
  Refresh Epoch 1
  3333 1103 12389 39153 8905
    193.0.0.56 from 193.0.0.56 (193.0.0.56)
      Origin incomplete, localpref 100, valid, external
      Community: 39153:10
      path 7FE0BBD4F318 RPKI State not found
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  4901 6079 3356 12389 39153 8905
    162.250.137.254 from 162.250.137.254 (162.250.137.254)
      Origin IGP, localpref 100, valid, external
      Community: 65000:10100 65000:10300 65000:10400
      path 7FE03D74A280 RPKI State not found
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  7018 3356 12389 39153 8905
    12.0.1.63 from 12.0.1.63 (12.0.1.63)
      Origin IGP, localpref 100, valid, external
      Community: 7018:5000 7018:37232
      path 7FE17DF3D088 RPKI State not found
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3267 39153 8905
    194.85.40.15 from 194.85.40.15 (185.141.126.1)
      Origin incomplete, metric 0, localpref 100, valid, external, best
      path 7FE019861080 RPKI State not found
      rx pathid: 0, tx pathid: 0x0
  Refresh Epoch 1
  20912 3257 28917 8905 8905 8905 8905
    212.66.96.126 from 212.66.96.126 (212.66.96.126)
      Origin incomplete, localpref 100, valid, external
      Community: 3257:4000 3257:8092 3257:50001 3257:50111 3257:54800 3257:54801 20912:65004
      path 7FE0180D41A8 RPKI State not found
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  1351 6939 12389 39153 8905
    132.198.255.253 from 132.198.255.253 (132.198.255.253)
      Origin IGP, localpref 100, valid, external
      path 7FE160A350A8 RPKI State not found
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  101 3356 12389 39153 8905
    209.124.176.223 from 209.124.176.223 (209.124.176.223)
      Origin IGP, localpref 100, valid, external
 --More-- 
```

>2. Создайте dummy0 интерфейс в Ubuntu. Добавьте несколько статических маршрутов. Проверьте таблицу маршрутизации.
### Ответ ###
```bash
 vk@vk-desktop:~$ sudo ip link add dummy0 type dummy
 vk@vk-desktop:~$ sudo ip addr add 10.0.29.0/24 dev dummy0
 vk@vk-desktop:~$ sudo ip link set dummy0 up
 vk@vk-desktop:~$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eno1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:22:4d:9a:2c:aa brd ff:ff:ff:ff:ff:ff
    altname enp0s25
    inet 192.168.1.106/24 brd 192.168.1.255 scope global dynamic noprefixroute eno1
       valid_lft 6235sec preferred_lft 6235sec
    inet6 fe80::f7b0:95f2:c528:a9bb/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:9d:0c:4e:31 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
4: dummy0: <BROADCAST,NOARP,UP,LOWER_UP> mtu 1500 qdisc noqueue state UNKNOWN group default qlen 1000
    link/ether 62:5f:40:07:4f:b4 brd ff:ff:ff:ff:ff:ff
    inet 10.0.29.0/24 scope global dummy0
       valid_lft forever preferred_lft forever
    inet6 fe80::605f:40ff:fe07:4fb4/64 scope link 
       valid_lft forever preferred_lft forever
```


>3. Проверьте открытые TCP порты в Ubuntu, какие протоколы и приложения используют эти порты? Приведите несколько примеров.
### Ответ ###
```bash
```


>4. Проверьте используемые UDP сокеты в Ubuntu, какие протоколы и приложения используют эти порты?
### Ответ ###
```bash
```


>5. Используя diagrams.net, создайте L3 диаграмму вашей домашней сети или любой другой сети, с которой вы работали.
### Ответ ###
```bash
```


