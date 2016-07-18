---
title: linux命令——scp 两台linux机器间文件或目录传输
date: 2016-07-18 10:40:10
tags: [linux,scp]
---

1. 从远程复制文件到本地目录。

> 说明：从192.168.120.204机器上的/opt/soft/的目录中下载nginx-0.5.38.tar.gz 文件到本地/opt/soft/目录中

```
$scp root@192.168.120.204:/opt/soft/nginx-0.5.38.tar.gz /opt/soft/
```

2. 从远程复制目录到本地目录。

> 说明：从192.168.120.204机器上的/opt/soft/中下载mongodb 目录到本地的/opt/soft/目录来。

```
$scp -r root@192.168.120.204:/opt/soft/mongodb /opt/soft/
```
 

3. 上传本地文件到远程目录。

> 说明：复制本地opt/soft/目录下的文件nginx-0.5.38.tar.gz 到远程机器192.168.120.204的opt/soft/scptest目录

```
$scp /opt/soft/nginx-0.5.38.tar.gz root@192.168.120.204:/opt/soft/scptest
```

4. 上传本地目录到远程目录。

> 说明：上传本地目录 /opt/soft/mongodb到远程机器192.168.120.204上/opt/soft/scptest的目录中去

```
$scp -r /opt/soft/mongodb root@192.168.120.204:/opt/soft/scptest
```

