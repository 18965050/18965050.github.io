---
layout: post
title: "Using Flume 读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [ stream handler]
---
{% include JB/setup %}

![Using-Flume](/assets/attachment/img/using-flume.png)

    flume是Hadoop生态圈的一个组件, 大多用来进行:
        (1) 日志过滤, 分类, 集中处理
        (2) 蓄水池缓冲作用: 生产者消息生产 >> 消费者消息消费. 比如各种应用终端往NoSQL或Hadoop HDFS进行数据存取操作等
    通过此书阅读, 可以了解:
        (1) Flume Agent: Source, Channel, Sink之间的关系
        (2) Flume提供的各种Source, Channel,Sink,及其配置使用
        (3) Source的两种类型:轮询(Pollable)和事件驱动(EventDriven),及其适用场景
        (4) Source 拦截器(Inteceptor)和Channel 选择器(Replicate, Multiplex)
        (5) Source端事务和Sink端事务的处理流程
        
##源码
[https://github.com/18965050/usingflumecode.git](https://github.com/18965050/usingflumecode.git "UsingFlume源码")

    
##读书笔记
[https://github.com/18965050/usingflumecode/wiki](https://github.com/18965050/usingflumecode/wiki "UsingFlume读书笔记")   