---
title: ubuntu 默认 root 密码
date: 2016-06-01 11:03:05
tags: [ubuntu,linux,root,pwd]
---

 安装完Ubuntu后忽然意识到没有设置root密码，不知道密码自然就无法进入根用户下。到网上搜了一下，原来是这麽回事。Ubuntu的默认root密码是随机的，即每次开机都有一个新的root密码。我们可以在终端输入命令 sudo passwd，然后输入当前用户的密码，enter，终端会提示我们输入新的密码并确认，此时的密码就是root新密码。修改成功后，输入命令 su root，再输入新的密码就ok了。

```
sudo passwd  #更改原来root密码
su root      #root帐号登陆
```


