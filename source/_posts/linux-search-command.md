---
title: linux搜索命令
date: 2016-06-06 15:58:37
tags: [linux,locate,find,grep]
---

1. locate 

```
/etc/updatedb.conf #locate配置文件筛选规则
locate file 
/var/lib/mlocate #筛选数据库
updatedb #更新数据库，以用来搜索最新的文件
```

2. whereis

```
whereis -b -m 
```

3. which

```
which ll  #会搜索文件别名
```

4. find

```
find / -name install.log
find /root -name "install.log*"
find /root -iname install.log #不区分大小写
find /root -nouser #搜索没有所有的文件
find /var/log/ -mtime +10  #查找10天前修改的文件

-10 10天以内
10 
+10 10天前

atime 
ctime
mtime 修改文件内容

find /root -size -25k
find /root -inum 22222 #通过i结点查找文件
-a and 
-o or
find /etc -size +20k -a -size -50k -exec ls -lh {} \

```

5. grep 

```
grep -i #不区别大小写
grep -v #取反
```


