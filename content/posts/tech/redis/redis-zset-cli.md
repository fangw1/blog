---
title: "Redis Zset操作"
date: 2024-06-20T11:04:28+08:00
lastmod: 2024-06-20T11:04:28+08:00
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
# Zet操作

```bash

# 查看zset有多少数据
ZCARD homemarket:realTimeTrans

# 输出zset数据详情
ZRANGE  homemarket:realTimeTrans 0 -1 withscores

# 移除指定元素
ZREMRANGEBYRANK homemarket:realTimeTrans 3 3

# 移除所有元素
ZREMRANGEBYRANK homemarket:realTimeTrans 0 -1


# 增加元素， 需要用双引号可以避免中文反序列化问题。时间-8小时
ZADD homemarket:realTimeTrans 1718789470278 "{\"@class\":\"xxx$TransVO\",\"type\":\"facPolicy\",\"transNo\":\"xx000000003\",\"transDate\":[\"java.util.Date\",\"2024-06-12T11:00:08.257+00:00\"],\"iconZh\":\"2024\x88\x86\",\"iconEn\":\"2024Policy\",\"premium\":\"xxx\"}"

```

参考：[菜鸟教程](https://www.runoob.com/redis/redis-sorted-sets.html)