---
layout: post
title: "Apache Zookeeper Essentials 读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [ distribute coordinate]
---
{% include JB/setup %}

![Apache-Zookeeper-Essentials](/assets/attachment/img/apache-zookeeper-essentials.png)

    Zookeeper是一个分布式协调系统.其主要应用在:
        (1) 配置管理
        (2) 分布式系统节点管理
        (3) 分布式队列, 屏障, 锁等实现
    通过此书阅读, 可以了解:
        (1) ZK单节点, 伪集群, 集群配置
        (2) ZK znode类型(persistent, ephemeral, sequential)及使用场景
        (3) watch和ACL机制
        (4) ZK Java API接口
        (5) ZK典型应用场景
        (6) ZK监控手段
        ......

    关于ZK在CAP理论中, 是偏向于CP的, 但网上有很多人对于ZK大规模的使用也存在异议. 主要问题在于:
    (1) 当跨机房部署时, 如果机房间通信存在问题,则机房server数量达不到quorum数量时会被全部丢弃
    (2) ZK对网络环境要求过高, 一旦网络环境不好进行Leader的重新选举会耗费大量时间
    (3) ZK扩容/缩容时, 需要手动修改配置.
    (4) 强一致性对于ZK集群的可用性会有较大的性能影响
    (5) 通知机制只要注册, 一定会接收相应的事件并处理, 没有过滤机制

    因此对于大规模的ZK使用, 一般都比较谨慎, 比如Dubbo在阿里内部使用时并没有用ZK做注册中心, 而是使用了数据库

## 源码
[https://github.com/18965050/ZookeeperEssentials.git](https://github.com/18965050/ZookeeperEssentials.git "ApacheZookeeperEssentials源码")

    
## 读书笔记
[https://github.com/18965050/ZookeeperEssentials/wiki](https://github.com/18965050/ZookeeperEssentials/wiki "ApacheZookeeperEssentials读书笔记")

[http://cailin.iteye.com/blog/2014486/](http://cailin.iteye.com/blog/2014486/ "zookeeper原理")

[https://github.com/alibaba/taokeeper](https://github.com/alibaba/taokeeper "TAOKeeper(zookeeper的监控报表系统)")



