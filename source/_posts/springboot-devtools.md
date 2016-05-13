---
title: spring配置springboot-devtools来实现热启动
date: 2016-05-13 14:26:49
tags: [springboot, devtools ,java, ubuntu ,linux]
---

```
<build>
    <finalName>boot-web</finalName>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            <configuration>
                <fork>true</fork>
                <mainClass>org.boot.web.Application</mainClass>
                <layout>ZIP</layout>
            </configuration>
            <executions>
                <execution>
                    <goals>
                        <goal>repackage</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```


###### springboot devtools需要配置fock 为true才能正常运行

```
spring-boot :run
```

