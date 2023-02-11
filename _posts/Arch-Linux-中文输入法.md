---
title: Arch Linux  中文输入法
date: 2023-02-11 13:06:55
description: 使用于大部分桌面？
tags:
    - Arch
    - Linux
---

Arch Linux可以安装安装fcitx5 实现输入中文，具体步骤如下

```bash
sudo pacman -S fcitx5-im 
sudo pacman -S fcitx5-chinese-addons
```

其中 fcitx5-chinese-addons 包含了大量中文输入方式：拼音、双拼、五笔拼音、自然码、仓颉、冰蟾全息、二笔等

然后在环境变量配置文件 /etc/environment 中添加如下内容


```bash
# /etc/environment
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
SDL_IM_MODULE=fcitx
```

然后配置自动启动，提供以下3种方法，第一个不行，试第2个，然后第3个

1. 如果支持XDG桌面环境，例如KDE,GNOME, Xfce,默认重启后即可

2. 在~/.config/autostart目录下添加fcitx-autostart.desktop文件，可以从目录etc/xdg/autostart中复制

3. 对于i3-wm,可以在配置文件~/.config/i3/config中添加如下代码
    
    ```bash
    # fcitx5
    exec_always --no-startup-id fcitx5
    ```

