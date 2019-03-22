---
layout: post
title: "Learning Apache Kafka读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [MQ]
---
{% include JB/setup %}

![Learning-Apache-Kafka](/assets/attachment/img/learning-apache-kafka.png)

    Kafka是一个互联网级的消息中间件. 它支持过亿级的消息生成,消息, 且可无线扩展.它能严格确保消息在主题分区(Topic Partition)的FIFO顺序,以及至少一次(At Least Once)的消息丢失策略.
    Kafka使用Scala语言编写的,淘宝在其原理基础上进行了优化和扩展, 推出了Java版的RocketMQ
    通过此书阅读,可以了解:
        (1) 单节点, 单节点伪集群,多节点集群部署方式
        (2) ZooKeeper, Broker Server, Topic, Producer, Consumer的组件的概念和使用方式
        (3) 分区(partition),复制(replication)的概念和实现
        (4) Kafka Java API对生产者和消费者的使用
        (5) Kafka 系统监管
        ......
        
     2019-3-22日补充:
     Kafka历经这些年的发展, 自身的变化也很大. 比如更多的监控, EOS(Exact Once Semantics), 事务;
     另外, 还有Kafka Stream, Kafka Connect等等.这些已远非当年的文档能概括清楚的了
     
     目前, 公司的消息平台是在Kafka1.0.0基础上扩展的. 主要解决了如下问题:
     1. client端(producer, consumer)简化配置, 并支持多场景应用(sync,async,transaction)
     2. client和spring结合, 支持xml和annotation配置
     3. 扩展mirrormaker, 加强监控, 告警, 可用性
     4. 扩展kakfa-manager功能, 支持权限控制, fail message日志查询, 消息消费失败补充等  
        
## 源码
[https://github.com/18965050/learning-kafka.git](https://github.com/18965050/learning-kafka.git "LearningApachekafka源码")

    
## 读书笔记
[https://github.com/18965050/learning-kafka/wiki](https://github.com/18965050/learning-kafka/wiki "LearningApachekafka读书笔记")
