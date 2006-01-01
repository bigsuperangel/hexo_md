---
title: ntpdate时间同步
date: 2016-05-04 11:59:05
tags: [ntpdate,ubuntu]
---

1.  安装ntpdate工具
``` 
sudo apt-get install ntpdate
```

2.  设置系统时间与网络时间同步
``` 
ntpdate cn.pool.ntp.org
```

3.  将系统时间写入硬件时间
``` 
hwclock –systohc
```

