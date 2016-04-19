---
title: nodejs
date: 2016-04-19 16:28:40
tags: nodejs
---

###  **About Setup**

#### - ubuntu
	curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
	sudo apt-get install -y nodejs
#### - yum
	yum -y install gcc make gcc-c++ openssl-devel wget python #下载并解压
	wget https://nodejs.org/dist/v4.2.1/node-v4.2.1-linux-x64.tar.gz
	tar zxvf node-v4.2.1-linux-x64.tar.gz  #在解压后文件夹里的bin文件夹中已经存在node以及npm，如果你进入到对应文件的中执行命令行一点问题都没有，说明是编译好的文件
	cd node-v4.2.1-linux-x64/bin
	ln -s/root/node-v4.2.1-linux-x64/bin/node /usr/bin/node
	ln -s/root/node-v4.2.1-linux-x64/bin/node /usr/local/bin/node
	ln -s/root/node-v4.2.1-linux-x64/bin/npm /usr/local/bin/npm
### **Git remember password**
设置记住密码（默认15分钟）
	git config --global credential.helper cache
设置记住密码（时间自定义）# 一小时有效期
	git config credential.helper 'cache --timeout=3600'
设置记住密码（长期有效）
	git config --global credential.helper store
