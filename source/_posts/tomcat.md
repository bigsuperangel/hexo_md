---
title: tomcat 命令启动关闭 
date: 2019-06-20 10:43:28
tags: [linux,tomcat]
---

```
netstat -anp | grep 8081 | awk '{printf $7}' | cut -d "/" -f 1
ps -ef | grep "/usr/local/tomcat/" | grep -v 'grep\|tail\|more\|bash\|le    ss'| awk '{print $2}'
```
