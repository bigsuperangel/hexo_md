---
title: linux环境下修改hosts
date: 2016-07-11 10:54:41
tags: [linux,hosts,google]
---

> 在linux下替换hosts,上google

```
wget https://raw.githubusercontent.com/racaljk/hosts/master/hosts -qO /tmp/hosts && sudo sh -c 'cat /tmp/hosts > /etc/hosts'
```
