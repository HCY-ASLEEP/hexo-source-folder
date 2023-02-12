---
title: Nodejs 换源
date: 2022-10-23 13:25:51
tags:
	- Nodejs
---

由于 Node 的官方模块仓库网速太慢，模块仓库需要切换到阿里的源<!--more-->

```bash
npm config set registry https://registry.npm.taobao.org/
```

执行下面的命令，确认是否切换成功

```bash
npm config get registry
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
