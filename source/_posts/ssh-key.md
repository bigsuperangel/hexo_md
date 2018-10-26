---
title: 生成ssh key
date: 2017-08-02 10:13:37
tags: [linux,ssh]
---

## 1. 如何生成ssh公钥

```
cd ~ #切换到git目录下
ssh-keygen -t rsa -C "xxxxx@xxxxx.com"  

# Generating public/private rsa key pair...
# 三次回车即可生成 ssh key
# 查看你的 public key，并把他添加到码云（Gitee.com） SSH key添加地址

cat ~/.ssh/id_rsa.pub
# ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC6eNtGpNGwstc....

ssh -T git@git.oschina.net
```

## 2. 配置多个git仓库

```
$ touch config

# window 与 linux 使用socks5代理有区别,一个用connect ,一个用nc

linux:
# github
Host github.com
	HostName github.com
	User     bigsuperangel
	PreferredAuthentications publickey
	IdentityFile ~/.ssh/github
	ProxyCommand nc -v -x 127.0.0.1:1080 %h %p

window:
# oschina
Host git.oschina.net
    HostName git.oschina.net
    PreferredAuthentications publickey
    User bigsuperyu
    IdentityFile ~/.ssh/id_rsa

# github
Host github.com
    HostName github.com
    User     bigsuperangel
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/github-rsa
    ProxyCommand connect -H 127.0.0.1:1080 %h %p
```

## 3. linux互信

```
ssh-copy-id -i id_rsa.pub root@host
ssh-copy-id -i id_rsa.pub -p port root@host
```

## 4. 相关问题

#### a. git fatal: early EOF fatal: index-pack failed

```
[core] 
packedGitLimit = 512m 
packedGitWindowSize = 512m 
[pack] 
deltaCacheSize = 2047m 
packSizeLimit = 2047m 
windowMemory = 2047m

I have tried this in /etc/ssh/ssh_config for Linux and Mac:
Host *
ServerAliveInterval 120
```


