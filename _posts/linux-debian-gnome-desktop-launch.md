---
title: Gnome Desktop File 参考 
date: 2022-10-23 13:25:51
tags:
	- Gnome
	- Linux
---

eg:<!--more-->

```bash
[Desktop Entry]
Encoding=UTF-8
Name=Tabby
Comment=Tabby
Exec=/home/asleep/softwares/tabby/tabby/tabby %U
Icon=/home/asleep/softwares/tabby/tabby/tabby.svg
Terminal=false
StartupNotify=true
Type=Application
Categories=Application;Development;
StartupWMClass=tabby
```

需要改变的是 name，common，exec，icon，startupwmclass

.desktop 文件位于 /usr/share/application/ 下面

StartupWMClass

```bash
xprop | grep CLASS
```


<script src="https://giscus.app/client.js"
        data-repo="HCY-ASLEEP/HCY-ASLEEP.github.io"
        data-repo-id="R_kgDOISFjNg"
        data-category="Announcements"
        data-category-id="DIC_kwDOISFjNs4CUJyb"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="light"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>
