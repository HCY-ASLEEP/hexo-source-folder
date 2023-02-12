---
title: Arch Linux run sudo without passwd
date: 2023-02-11 13:03:02
description: Arch 免密 sudo
tags:
    - Arch
    - Linux
---

- 首先
    
    ```bash
    sudo visudo
    ```
    
- 然后编辑里面的内容

    ```bash
    myname ALL=(ALL) NOPASSWD: ALL
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
