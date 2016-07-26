---
title: shadowsocks客户端配置
date: 2016-07-26 10:17:24
tags: [shadowsocks,linux,ubuntu]
---

### ubuntu 安装 shadowsocks

##### 一、pip 安装

- 安装python库

```
apt-get update
apt-get install python-pip
python-setuptools m2crypto
pip install shadowsocks
```

- 启动shadowsocks

A. 命令行启动
 
```
sslocal -s 11.22.33.44 -p 50003 -k "123456" -l 1080 -t 600 -m aes-256-cfb
```

B. 配置文件启动

```
sslocal -c /home/mudao/shadowsocks.json
```

```
{
"server":"11.22.33.44",
"server_port":50003,
"local_port":1080,
"password":"123456",
"timeout":600,
"method":"aes-256-cfb"
}
```
server  你服务端的IP
servier_port  你服务端的端口
local_port  本地端口，一般默认1080
passwd  ss服务端设置的密码
timeout  超时设置 和服务端一样
method  加密方法 和服务端一样

##### 二、shadowsocks-qt5 安装

在ubuntu上可以这样，通过PPA源安装，仅支持Ubuntu 14.04或更高版本。

```
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```

由于是图形界面，配置和windows基本没啥差别就不赘述了。经过上面的配置，你只是启动了sslocal 但是要上网你还需要配置下浏览器到指定到代理端口比如1080才可以正式上网。


