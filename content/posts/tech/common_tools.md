---
title: "常用工具脚本"
date: 2024-06-14T15:35:23+08:00
lastmod: 2024-06-14T15:35:23+08:00
author: ["Patick"]
keywords: 
- 
categories: 
- 
tags: 
- 
description: ""
weight:
slug: ""
draft: false # 是否为草稿
comments: true
reward: false # 打赏
mermaid: true #是否开启mermaid
showToc: true # 显示目录
TocOpen: true # 自动展开目录
hidemeta: false # 是否隐藏文章的元信息，如发布日期、作者等
disableShare: true # 底部不显示分享栏
showbreadcrumbs: true #顶部显示路径
cover:
    image: "" #图片路径例如：posts/tech/123/123.png
    caption: "" #图片底部描述
    alt: ""
    relative: false
---

# MAC 14.2.1

## 刷新dns
```bask
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder 
```
## 设置dns
```bash
networksetup -setdnsservers Wi-Fi 140.205.81.23 8.8.8.8 114.114.114.114
```



