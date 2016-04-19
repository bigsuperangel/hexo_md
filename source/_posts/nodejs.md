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

#### - Linux/Unix/Mac 系统
- 新建一个 ~/.netrc 文件， 将 git 服务器， 用户名以及密码记录在这个文件， 如下所示：
***
	machine your-git-server
	login your-username
	password your-password
- 如果有多个 server 就重复上面的三行， 分别输入对应的服务器、 用户名和密码即可；
***
	machine git.oschina.net
	login xxx
	password xxx
#### - Windows 系统
- 在 Windows 平台上， 稍微麻烦一些， 但是也能实现, 需要先添加一个用户变量 %HOME%接下来在 %HOME% 变量指向的目录下新建一个名称为 _netrc 的文件， 内容与上面的一样， 将 git 服务器， 用户名以及密码记录在这个文件， 如下所示：
***
	machine your-git-server
	login your-username
	password your-password		
