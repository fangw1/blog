---
title: "Mysql运维常用脚本整理"
date: 2024-08-01T11:25:01+08:00
lastmod: 2024-08-01T11:25:01+08:00
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



# Mysql运维常用脚本整理

```sql
    -- 查询表空间大小
    SELECT
        table_schema AS `Database`,
        table_name AS `Table`,
        ROUND((data_length + index_length) / 1024 / 1024 / 1024, 2) AS `Size`
    FROM
        information_schema.tables
    WHERE
        table_schema NOT IN ('information_schema', 'mysql', 'performance_schema', 'sys')
    ORDER BY
        `Size` DESC;

    -- 查询慢sql
    SELECT * FROM information_schema.PROCESSLIST
    WHERE COMMAND = 'Query' AND TIME > 1;

    -- 数据库用户配置权限
    -- 1查询数据库用户
    select user from mysql.user;
    -- 2创建用户
    CREATE USER ha_xx@'%' IDENTIFIED BY ‘ha_xx@P123123123’;

    -- 3查询某个用户的权限
    show grants for read_all_prd;
    -- 4给用户授权
    grant select,insert,update on ha_xx.table to read_all_prd@‘%’;





