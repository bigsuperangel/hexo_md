---
title: Ubuntu下Tomcat绑定80端口
date: 2016-05-06 11:12:09
tags: [tomcat,authbind]
---

> 工作环境迁移到了Ubuntu,很多东西发生了变化,比如原先配置tomcat端口.只需要配置server.xml文件就可以了。但是在Ubuntu下，只修改了server.xml文件后发现无法访问到服务。起初以为是有别的进程占用了80端口，但是通过netstat -an | grep 80后并没有发现有进程在占用80,Google了一下，发现tomcat使用1023以下的端口时需要使用authbind来指定。

- authbind是GNU下的一个小工具，用于帮助系统管理员来为程序指定端口。如果你的机器没有安装authbind,那么首先要安装才可以: 
```
sudo apt-get install authbind
```

- 然后配置80端口: 
```
sudo touch /etc/authbind/byport/80
```

- 接下来再启动tomcat就可以访问到80的服务了:
```
sudo authbind --deep ./catalina.sh start
```

- 测试是否运行
```
sudo netstat -lnp | grep 80
```

> Enjoy Youself
