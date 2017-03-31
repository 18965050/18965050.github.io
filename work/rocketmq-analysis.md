---
layout: page
title: "RocketMQ源码分析"
description: ""
---
{% include JB/setup %}

    最近事比较多, 因此很久没更新博客了. 这是我抽时间看了下RocketMQ的源码并进行了分析的一些心得.
    相比于Kafka, RocketMQ在分布式部分做了简化, 但也增强了更多新的功能. 比如:
    1. PushConsumer和PullConsumer(Kafka只有Pull Consumer)
    2. 消费模式有集群模式和广播模式.广播模式可保证不同consumer,即便为同一consumerGroup,也可消费同一topic消息(Kafka中只能通过配置不同的consumerGroup来实现)
    3. 严格顺序消息消费(Kafka也支持)
    4. 事务消息(Kafka不支持)
    5. 消息过滤. RocketMQ支持两种方式的消息过滤:通过Tag或通过自定义的com.alibaba.rocketmq.common.filter.MessageFilter实现类来实现消息在broker上的过滤(Kafka不支持)
    6. 定时消息发送和定时拉取(Kafka不支持)
    7. 消息按key进行检索.这个有时很有用,可用于判断消息是否存在. (Kafka不支持)
    8. 消息同步和异步刷盘(FlushDiskType.SYNC_FLUSH和FlushDiskType.ASYNC_FLUSH),同步双写(BrokerRole.SYNC_MASTER),Kafka只有异步刷盘,没有同步双写功能,slave是从master上不断异步拉取commitLog数据

## 分析文档
[RocketMQ源码分析文档](https://github.com/18965050/RocketMQ/wiki "RocketMQ源码分析")

## 相关文档
阿里中间件团队专门有做过RocketMQ和Kafka的对比,并写了一系列的文章, 地址如下:

[RocketMQ与kafka对比（18项差异）](http://jm.taobao.org/2016/03/24/rmq-vs-kafka/ "RocketMQ与kafka对比（18项差异）")

[Kafka、RabbitMQ、RocketMQ消息中间件的对比 —— 消息发送性能](http://jm.taobao.org/2016/04/01/kafka-vs-rabbitmq-vs-rocketmq-message-send-performance/ "Kafka、RabbitMQ、RocketMQ消息中间件的对比 —— 消息发送性能")

[Kafka vs RocketMQ—— Topic数量对单机性能的影响 ](http://jm.taobao.org/2016/04/07/kafka-vs-rocketmq-topic-amout/ "Kafka vs RocketMQ—— Topic数量对单机性能的影响")

[Kafka vs RocketMQ——多Topic对性能稳定性的影响](http://jm.taobao.org/2016/04/20/kafka-vs-rocketmq-3/ "Kafka vs RocketMQ——多Topic对性能稳定性的影响")

[Kafka vs RocketMQ——单机系统可靠性](http://jm.taobao.org/%2F2016%2F04%2F28%2Fkafka-vs-rocktemq-4%2F "Kafka vs RocketMQ——单机系统可靠性")


