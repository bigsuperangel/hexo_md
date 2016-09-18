---
title: Ubuntu下使用sysv-rc-conf管理服务
date: 2016-09-18 12:00:10
tags: [linux,ubuntu,rc,sysv-rc-conf]
---

### Ubuntu运行级别

```
0 停机

1 单用户，Does not configure network interfaces, start daemons, or allow non-root logins

2 多用户，无网络连接 Does not configure network interfaces or start daemons

3 多用户，启动网络连接 Starts the system normally.

4 用户自定义

5 多用户带图形界面

6 重启
```

### 以nexus为例，配置nexus开启自动启动

```
cp /opt/nexus/nexus-2.0.3/bin/nexus /etc/init.d/
update-rc.d nexus defaults 99 ##数字越大启动越靠后面，因为需要网络支持，所以启动靠后
```

### sysv-rc-conf管理启动项

```
sudo apt-get install sysv-rc-conf
sudo sysv-rc-conf
```


