---
layout: post
title: "ActiveMQ In Action 读书笔记"
tagline: "Supporting tagline"
description: ""
category: java
tags: [MQ]
---
{% include JB/setup %}

![Learning-Apache-Kafka](/assets/attachment/img/activemq-in-action.png)

    ActiveMQ是一个遵循JMS规范的Java消息中间件, 被广泛应用于企业消息系统中. MQ是应用解耦的利器, 其对于异构系统的集成, 系统解耦, 扩展, 重构等都意义重大
    通过此书阅读,可以了解:
        (1) JMS规范(producer, consumer, provider, message, domain)及组成部分
        (2) connector, 包括transport-connector和network-connector
        (3) 消息持久化(KahaDB, AMQ, JDBC, Memory)
        (4) 认证和授权
        (5) Java编程实现(POJO, XML)及结合Spring
        (6) broker主从集群方式及集群中的消息处理
        (7) broker的高级特性(consumer通配符, producer组合destination, advisory message, virtual topic, retroactive consumer等等)
        (8) client的高级特性(exclusive consumer, message group, stream, BlobMessage, scheduler message等等)
        (9) 性能提升及调优手段
        (10) 监控和管理手段
        ......
        
##源码
[https://github.com/18965050/activemq-in-action.git](https://github.com/18965050/activemq-in-action.git "ActiveMQ In Action源码")

    
##读书笔记
[https://github.com/18965050/activemq-in-action/wiki](https://github.com/18965050/activemq-in-action/wiki "ActiveMQ In Action读书笔记")  
