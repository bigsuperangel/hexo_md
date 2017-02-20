---
title: vscode相关配置操作小结
date: 2017-02-20 20:26:04
tags: [vscode,python]
---

## 1. vscode下python print 输出乱码

> 在task文件中加入环境变量，然后问题解决。

```
  "options": {
    "env":{
        "PYTHONIOENCODING": "UTF-8"
      }
  }
```

## 2. python 运行配置

```
{
    "version": "0.1.0",
    "command": "python",
    "windows": {
        "command": "D:\\develop\\running\\Python35\\python.exe" //python的安装路径
    },
    "isShellCommand": true,
    "args": [
        "${file}"
    ],
    "showOutput": "always",
    "options": {
        "env": {
            "PYTHONIOENCODING": "UTF-8"
        }
    }
}
```

