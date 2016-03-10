---
layout: post
title: "Redis In Action读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [NoSQL]
---
{% include JB/setup %}

![Redis-In-Action](/assets/attachment/img/redis-in-action.png)

    Redis常常用来做分布式缓存系统. 其具有如下特点:
        (1) 访问速度快.可支持读写分离, 进一步提升写速度
        (2) 支持多达5种的数据结构,使用方便
        (3) 部署简单, 扩展方便, 尤其支持动态扩展
        (4) 目前只支持主从集群, 不支持分区(sharding). 但可通过一些客户端方式进行sharding.(3.0+的版本似乎已支持sharding了)
        (5) 可简单的当做消息中间件使用
    通过此书阅读,可以了解:
        (1) Redis 5种数据结构以及操作命令
        (2) Redis事务概念及相应命令
        (3) Redis的两种数据存储方案: 快照(snapshot)和AOF(append-only file)配置使用方式及使用场景
        (4) Redis数据压缩及性能诊断
        ......

## 源码
[https://github.com/18965050/redis-in-action.git](https://github.com/18965050/redis-in-action.git "Redis In Action源码")

    
## 读书笔记
[https://github.com/18965050/redis-in-action/wiki](https://github.com/18965050/redis-in-action/wiki "Redis In Action读书笔记") 