---
title: 解压版mysql安装
date: 2016-04-21 14:52:12
tags: [mysql,database]
---
### 环境配置
> MYSQL_HOME=D:\develop\database\mysql-5.6.20-winx64\bin


### mysql.ini
```
[mysqld]
设置字符集为utf8
loose-default-character-set = utf8
character-set-server = utf8
basedir = F:/mysql/mysql-5.6.20-winx64
datadir = F:/mysql/mysql-5.6.20-winx64/data 

[client]
#设置客户端字符集环境 
loose-default-character-set = utf8

[WinMySQLadmin]
Server = F:/mysql/mysql-5.6.20-winx64/bin/mysqld.exe
```
### 添加为系统服务
```
mysqld -install #进入mysql bin目录启动命令
mysqld -remove #删除服务
sc delete mysql #删除服务
```
***
### 修改密码
```
update mysql.user set password=PASSWORD('root') where User='root' 
flush privileges 
```

##### mysql解决远程不能访问的方法
```
GRANT ALL PRIVILEGES ON *.* TO 'myuser'@'%' IDENTIFIED BY 'mypassword' WITH GRANT OPTION;
```


