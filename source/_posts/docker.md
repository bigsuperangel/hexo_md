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

`2. ` docker tomcat 配置

```
# tomcat8 给内网服务器使用
docker run --name tomcat8 -d \
	-v ~/web/tomcat8/webapps:/usr/local/tomcat/webapps \
	-v ~/web/tomcat8/logs:/usr/local/tomcat/logs \
	-v /etc/localtime:/etc/localtime:ro \
	-e TZ="Asia/Shanghai" \
	-p 8080:8080 tomcat:8.0

docker logs --tail=100 -f tomcat8
docker container stop tomcat8
docker container start tomcat8
```
