---
title: ubuntu 固定ip设置
date: 2016-06-06 14:37:11
tags: [ubuntu,ip]
---

- 前面提到固定IP的上网方式主要是修改/etc/network/interfaces这个文件，配置IP、网关什么的，其实这里面还有个参数可以配置，那就是DNS了，对应的参数名为dns-nameservers，这里设置的优先级比resolv.conf高，也就是网络会从这里读取DNS配置，如果没配置才去看resolv.conf里面的设置，因此在这里面配置DNS更简单。


```
opback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto eth0
#iface eth0 inet dhcp

iface eth0 inet static

address 192.168.0.114
netmask 255.255.255.0
gateway 192.168.0.1

dns-nameservers 211.138.151.161
```


- 重启网络

```
sudo service networking restart 
或者
sudo /etc/init.d/networking restart

sudo ifconfig eth0 down 
sudo ifconfig eth0 up
```


