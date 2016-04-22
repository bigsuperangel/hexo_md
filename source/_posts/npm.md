---
title: npm
date: 2016-04-22 11:06:16
tags: [npm,nodejs]
---

### npm使用
> 设置国内代理
```
npm config set registry https://registry.npm.taobao.org
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

----
> Window使用
> 1. npm作为一个NodeJS的模块管理，之前我由于没有系统地看资料所以导致安装配置模块的时候走了一大段弯路，所以现在很有必要列出来记录下。我们要先配置npm的全局模块的存放路径以及cache的路径，例如我希望将以上两个文件夹放在NodeJS的主目录下，便在NodeJs下建立“node_global”及“node_cache”两个文件夹。我们就在cmd中键入两行命令：
```
npm config set prefix "D:\develop\nodejs\node_global"
npm config set cache "D:\develop\nodejs\node_cache"
```
> 2. 下面这一步非常关键，我们需要设置系统变量。进入我的电脑→属性→高级→环境变量。在系统变量下新建“NODE_PATH”,输入“D:\develop\nodejs\node_global\node_modules”
> 3. 由于改变了module的默认地址，所以用户变量都要跟着改变一下（用户变量PATH修改为刚才我们设置的全局模块存放路径），要不使用module的时候会导致输入命令出现“xxx不是内部或外部命令，也不是可运行的程序或批处理文件”这个错误。我使用的全局模块存放路径为D:\develop\nodejs\node-global（见上方设置的prefix值）， 我将它添加到我的变量PATH里面


---
> Linux使用
- 设置环境变量
```
vim /etc/profile 
export PATH="$PATH:/home/linyu/soft/node-v5.10.1-linux-x86/bin"
source /etc/profile  #设置生效
```



