---
title: hexo 配置themes相关submodule
date: 2017-08-02 10:04:50
tags: [git,submodule,hexo]
---

## 1. 添加themes submodule

```
git submodule add git@github.com:bigsuperangel/jacman.git themes/jacman
```

## 2. clone带submodule

```
git submodule init
git submodule update
```

## 3. 删除submodule

```
git rm --cached themes/jacman
rm .gitmodule
del .git/config submodule
```
