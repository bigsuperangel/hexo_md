---
title: docker
date: 2018-10-15 10:56:40
tags: docker
---

`1. ` docker mysql 配置

```
docker search mysql
docker run --name some-mysql -p 3306:3306 -v /root/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=xxx -d mysql:5.5
docker image ls
docker exec -it some-mysql bash
#配置远程访问
mysql> grant all privileges on *.* to root@"%" identified by "password" with grant option; 
Query OK, 0 rows affected, 1 warning (0.04 sec)
mysql> flush privileges; 
Query OK, 0 rows affected (0.00 sec)
```
