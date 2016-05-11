---
title: nginx相关配置
date: 2016-05-06 11:22:30
tags: [nginx,linux]
---

> nginx 配置80端口转向，间接启用tomcat，不需要用authbind

```
server {
  listen 80;
  server_name bigsuperangel.ngrok.cc;  # 写上你的虚拟主机域名

  location /{
    proxy_pass http://127.0.0.1:8080/;  # 写上要转发到的地址，可以是http也可以是https，注意不要遗漏了最后的斜杠
    proxy_pass_header Set-Cookie;                           # 带cookie转发
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

  }
}
```
