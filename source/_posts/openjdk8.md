---
title: ubuntu15 以下安装 openjdk8
date: 2016-05-13 14:21:40
tags: [openjdk8,ubuntu]
---

- If you really want to use OpenJDK, you have to compile from source. There is not still any PPA for OpenJDK. It has been requested at  [https://bugs.launchpad.net/ubuntu/+bug/1297065](https://bugs.launchpad.net/ubuntu/+bug/1297065)

- **I recommend you to use Webup8 Oracle Java8 Installer**


```
sudo add-apt-repository ppa:webupd8team/java -y
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

- To automatically set up the Java 8 environment variables

```
sudo apt-get install oracle-java8-set-default
```

- Check it

```
java -version
```


##### So you have to wait to use OpenJDK8
