---
title: gradle idea 设置hotswap
date: 2016-06-12 16:11:58
tags: [gradle,idea,hotswap]
---

```
apply plugin: 'jetty'
jettyRun {
    reload = "automatic"
    scanIntervalSeconds = 1
}



task watchfiles {
    inputs.files 'src'
    doLast {
        compileJava
    }
}

watchfiles.finalizedBy compileJava
```
