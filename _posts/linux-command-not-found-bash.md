---
title: Linux 环境变量配置错误处理
date: 2022-10-23 13:25:51
tags:
	- Bash
	- Linux
---
Linux 环境变量配置出错后，提示command not found<!--more-->

处理方法：

```bash
export PATH=$PATH:/usr/bin:/usr/sbin:/bin:/sbin
```

这样处理后，临时生效环境变量，然后修改配置错误的文件例如.bash_profile   /etc/profile .bashrc 等，修改后，执行source生效正确的环境变量

```bash
source /etc/profile --根据实际情况修改后面的文件路径
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
