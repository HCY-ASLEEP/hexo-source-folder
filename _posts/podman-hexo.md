---
title: Podman hexo
date: 2023-02-11 10:38:59
description: 将 hexo 容器化便于迁移
tags:
    - Podman 
    - Hexo
---

- "hexo s" 在本地运行预览的端口是 4000

    ```bash
    podman run -it --name=hexoenv -p 4000:4000 -v /home/hcy/Gateway/hexo_blogs:/home/devenv/hexo/source hexoenv /bin/bash 
    ```
- 只需要把 source 文件夹暴露出来给 host 就行了

- 为了多端同步，推送不用 "hexo d" ， 而是手动将 public 下的内容推到 github.io 那里


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
