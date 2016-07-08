---
title: java 加解密
date: 2016-07-08 15:26:30
tags: [java,security]
---

> 在加解密类中引入

```
static {
	Security.addProvider(new BouncyCastleProvider());
}
```

```
<dependency>
	<groupId>org.bouncycastle</groupId>
	<artifactId>bcprov-jdk15</artifactId>
	<version>1.45</version>
</dependency>
```
