---
title: hexo使用说明
date: 2023-03-03 16:33:37
tags: [hexo,nodejs,npm,submodule]
---

### **Command**
```
hexo new <title> / hexo n <title> #生成文章，或者source\_posts手动编辑
hexo server / hexo s #本地发布预览效果
hexo generate / hexo g #生成public静态文件
hexo clean
hexo list <type>
hexo version
```
* * *
### **Build**
```
install nodejs
install npm 
npm install hexo-cli -g
npm install hexo --save
hexo init <folder>
cd <folder>
npm install
```
* * * 
### **Publish**
```
hexo clean
hexo d -g
hexo s --debug
```
* * * 
### **Themes submodule**
```
git clone git@github.com:bigsuperangel/hexo_md.git
git submodule init
git submodule update
```
* * * 
### **Update**
```
npm install -g hexo-cli
npm i -g npm-check-updates
ncu -u
npm install
```