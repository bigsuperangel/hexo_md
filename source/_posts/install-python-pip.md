---
title: centos6升级python2.7
date: 2018-12-14 12:08:17
tags: [linux,python,pip]
---

### 1. upgrade python2.7
```
wget https://gitee.com/bigsuperyu/git-test/raw/master/python2.7_for_centos6.sh
bash python2.7_for_centos6.sh
```

### 2. install pip
```
curl https://bootstrap.pypa.io/get-pip.py | python
ln -s /usr/local/bin/pip /usr/bin/pip
pip -V
```
### 3. install mycli
```
pip install mycli
```


