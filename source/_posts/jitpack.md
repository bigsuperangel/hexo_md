---
title: 利用jitpack.io发布Android、Java项目，通过gradle、maven方式引用
date: 2017-03-10 18:12:24
tags: [java,maven,jitpack]
---

### Android、Java项目开源
这里就仅仅介绍如何发布一个Android、Java的项目到 [jitpack.io](https://jitpack.io/) 。

#### 第一步：配置项目根目录的build.gradle

```
buildscript {
   repositories {
          jcenter()
   }

   dependencies {
       classpath 'com.android.tools.build:gradle:1.5.0'
       classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'//ADD
   }
}
```

#### 第二步：配置需要发布的Module Lib的build.gradle

```
apply plugin: 'java'
apply plugin: 'com.github.dcendents.android-maven'//ADD
```

#### 第三步：发布到github
这个参考网络上git教程

#### 第四步：创建Release版本
![aa86b3db62434b3faf2adc73a1c211c4.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/aa86b3db62434b3faf2adc73a1c211c4.png)
![d369db53afd74d338fcbaabea98f3627.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/d369db53afd74d338fcbaabea98f3627.png)
![8f027d11d86e4ba1ae2d554138a1026f.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/8f027d11d86e4ba1ae2d554138a1026f.png)

#### 第五步：到 [jitpack.io](https://jitpack.io/) 构建
![64d617943ba64d2f8b079606ccadd245.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/64d617943ba64d2f8b079606ccadd245.png)

#### 第六步：完成，即可通过gradle或maven引入发布的Lib
![3101ee3d460749989f948ea4300855ab.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/3101ee3d460749989f948ea4300855ab.png)

#### 第七步：添加仓库标识符
把这段Markdown代码放到README.md页面，需要根据项目地址修改。
![1a976650a6614ffb8359fb286b5bcfa0.png](//olrtj18qs.bkt.clouddn.com//file/2017/3/1a976650a6614ffb8359fb286b5bcfa0.png)

#### 第八步：通过gradle引用

```
<repositories>
  <repository>
      <id>jitpack.ioid</id>
      <url>https://jitpack.io</url>
  </repository>
</repositories>

<dependency>
  <groupId>com.github.bigsuperangel</groupId>
  <artifactId>hiwetoptools</artifactId>
  <version>3.3.0</version>
</dependency>
```

#### 示范代码
* https://github.com/bigsuperangel/hiwetoptools
* https://github.com/bigsuperangel/robot
