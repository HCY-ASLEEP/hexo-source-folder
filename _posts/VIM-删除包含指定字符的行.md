---
title: VIM 删除包含指定字符的行
date: 2023-02-12 02:03:47
description: 高级操作喔
tags:
    - VIM
---

```bash
# 删除包含特定字符的行，匹配删除
:% g/abc/d

# 删除不包含特定字符的行
:% v/abc/d
:% g!/abc/d
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
