---
title: hibernate连接mysql查询中文无效的问题
date: 2016-06-27 14:29:07
tags: [hibernate,mysql]
---

> 设置mysql的连接需要加上编码


```
jdbc:mysql://192.168.0.114:3306/fss?useUnicode=true&amp;characterEncoding=UTF-8
```
