---
title: maven 相关命令
date: 2016-08-24 11:27:37
tags: [maven,command,java]
---

```
##　You will need somewhere for your project to reside, create a directory somewhere and start a shell in that directory. On your command line, execute the following Maven goal:

mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

##　You may test the newly compiled and packaged JAR with the following command:
java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App

##　ignore test
mvn install -Dmaven.test.skip=true

## 按指定文件指定环境打包
mvn -B package --file pom_github.xml -P profile -Dmaven.test.skip=true

mvn dependency:tree
mvn install -X
```
