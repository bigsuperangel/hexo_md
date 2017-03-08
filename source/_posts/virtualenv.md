---
title: virtualenv
date: 2017-03-08 14:50:24
tags: [python,virtualenv]
---

VirtualEnv可以方便的解决不同项目对类库的依赖问题，这里讲下windows上如何安装virtualenv。

**1. 安装 `virtualenv`**
![5643975ae128412eaf43f35fff5c1dd7.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/5643975ae128412eaf43f35fff5c1dd7.png)

**2. 为项目安装虚拟环境**
![e357d5fb8428418bb14f2b43ebd05dcf.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/e357d5fb8428418bb14f2b43ebd05dcf.png)

**3. 启动虚拟环境中，为项目安装所需类库**
在windows中，启动虚拟环境使用命令：your_env_dir\Scripts\activate，激活虚拟环境后，在cmd窗口的命令前面将出现，表示目前处于虚拟环境中。
![77990833b53d46299e2d486bd00b460a.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/77990833b53d46299e2d486bd00b460a.png)

**4. 在虚拟环境中进行开发**
A.在项目目录下，创建一个flask_demo.py的文件，用来演示用flask创建一个应用。


```
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_flask():
  return 'hello flask!'

    if __name__ == '__main__':
      app.run()
```


B.在虚拟环境中执行该应用：
![d552521b25144f02bbd12a1753c954bb.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/d552521b25144f02bbd12a1753c954bb.png)
C.在浏览器中验证该应用：
![dc3fa4e4fb7d4abcacc8744b6b81555e.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/dc3fa4e4fb7d4abcacc8744b6b81555e.png)

**5. 离开虚拟环境，使用deactivate命令**
![820b2fa7c7554ea59d2e7b5bdb8f9704.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/820b2fa7c7554ea59d2e7b5bdb8f9704.png)
发现命令行前面已经没有了<env>

**6. 在系统环境中，我们并没有安装flask类库，可以对比在系统环境中和虚拟环境中的脚本运行效果：**
![b44caaea05fc48728b6adf1919b39b2c.png](http://olrtj18qs.bkt.clouddn.com/file/2017/3/b44caaea05fc48728b6adf1919b39b2c.png)

> 总结：virtualenv虚拟环境为每个项目隔离了一套运行类库，不同的项目在各自的虚拟环境中使用不同的类库，避免了将所有类库都安装到系统环境中导致的不同项目需要不同（版本）类库的问题，项目与项目之间的类库依存不再成为问题。



