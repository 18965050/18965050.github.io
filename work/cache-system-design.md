---
layout: page
title: "基于多数据源的分布式缓存系统设计方案"
description: ""

---
{% include JB/setup %}

    这是在目前redis分布式sharding方案codis基础上做的一个设计方案稿,
    并加入了对数据持久化的支持.
    codis采用go语言编写, 并且修改了redis的版本, 加入了对slot原子操作的支持,
    确实是大牛之作, 而本方案意在使用Java语言来实现相同的功能.

[设计文档](https://github.com/18965050/cache-system-design "设计文档")