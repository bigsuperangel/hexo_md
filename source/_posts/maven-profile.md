---
title: 使用 Maven Profile 和 Filtering 打各种环境的包
date: 2016-09-12 17:15:17
tags: [maven,java,profile,package]
---

每个项目都会有多套运行环境（开发，测试，正式等等），不同的环境配置也不尽相同（如jdbc.url)，借助Jenkins和自动部署提供的便利，我们可以把不同环境的配置文件单独抽离出来，打完包后用对应环境的配置文件替换打包后的文件，其实maven已经给我们提供了替换方案：profile + filtering

1. 配置 resource 插件，启用filtering功能并添加属性到pom:

```
<project>
...
<build>
    <filters>
        <filter>src/main/filters-${active.profile}.properties</filter>
    </filters>
    <resources>
        <resource>
            <directory>src/main/resources</directory>
                <filtering>true</filtering>
        </resource>
    </resources>
</build>
<profiles>
    <profile>
        <id>dev</id>
        <properties>
            <active.profile>dev</active.profile>
        </properties>
        <!-- 把当前profile设置为默认profile，可以同时这是多个为默认-->
        <activation>
            <activeByDefault>true</activeByDefault>
        </activation>
    </profile>
    <profile>
        <id>test</id>
        <properties>
            <active.profile>test</active.profile>
        </properties>
    </profile>
    <profile>
        <id>product</id>
        <properties>
            <active.profile>product</active.profile>
        </properties>
    </profile>
...
</project>

```

2. 然后在src/main下新建三个文件：filters-dev.properties,filters-test.properties,filters-product.properties,文件内容如下（以filters-dev.properties为例):

```
pom.jdbc.url=jdbc:mysql://127.0.0.1:3306/dev
pom.jdbc.username=root
pom.jdbc.password=123456
```

3. 用 dev profile 打开发包mvn clean package -Pdev, 打包后jdbc.properties文件内容如下：

```
jdbc.url=jdbc:mysql://127.0.0.1:3306/dev
jdbc.username=root
jdbc.password=123456
```


