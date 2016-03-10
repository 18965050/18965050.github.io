---
layout: post
title: "Storm Applied 读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [stream handler]
---
{% include JB/setup %}

![Storm Applied](/assets/attachment/img/storm-applied.png)

    Storm是个实时数据流处理框架, 其用于对数据进行实时处理,便于及时产生结果. 
    与Hadoop相比, Hadoop MapReduce是个数据批处理框架, 实时性不如Storm高
    通过此书阅读, 可以了解:
        (1) Storm组成部分: Topology, Tuple, Stream, Spout, Bolt
        (2) Stream分组,包括 Shuffle Group, FieldGroup, GlobalGroup等区别
        (3) Storm Topology设计原则及可靠性保证
        (4) Storm 集群组成: 包括ZK, Nimbus(master node), Supervisor(slave node), 以及节点内 work process, executor, task等概念及相互关系
        (5) Storm调优和内部结构
        ......
        
## 源码
[https://github.com/18965050/storm-applied.git](https://github.com/18965050/storm-applied.git "StormedApplied源码")

    
## 读书笔记
[https://github.com/18965050/storm-applied/wiki](https://github.com/18965050/storm-applied/wiki "StormedApplied读书笔记") 