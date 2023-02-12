---
title: Debian Nvidia 驱动
date: 2022-10-23 13:25:51
tags:
	- Debian
	- Nvidia
	- Linux
---
最重要的一点，去 bios 那里关闭 secure boot 先！<!--more-->

更新

```bash
sudo apt install nvidia-driver
```

重启

```bash
sudo reboot
```

验证是否安装成功

```bash
nvidia-smi
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
