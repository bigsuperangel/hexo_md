---
title: linux下`alsamixer`配置
date: 2018-12-03 14:41:38
tags: [ubuntu,alsamixer]
---

```
# 安装alsa相关应用：
sudo apt install alsa-base alsa-utils alsa-oss alsa-tools

#查看系统中的声卡：
cat /proc/asound/cards

sudo alsamixer
#其中，Master和PCM是必须打开的，Master和PCM声道默认是静音的，标记是MM。用左右方向键选择设置项，按M健来修改为OO或开启调节，上下键调节音量大小。

sudo alsactl store #保存配置
cat /var/lib/alsa/asound.state #查看配置生效的内容
```
