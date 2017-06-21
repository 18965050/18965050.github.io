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

## 参考资料
 网上有一些storm的学习资料很值得学习下, 尤其是介绍storm 消息可靠性的保证

 [Storm入门教程：前言](http://os.51cto.com/art/201308/408733.htm "Storm入门教程：前言")

 [Storm入门教程：构建Topology](http://os.51cto.com/art/201308/408739.htm "Storm入门教程：构建Topology")

 [Storm入门教程：安装部署步骤详解](http://os.51cto.com/art/201309/411003.htm "Storm入门教程：安装部署步骤详解")

 [Storm入门教程：消息的可靠处理](http://os.51cto.com/art/201312/422572.htm "Storm入门教程：消息的可靠处理")

 [Storm入门教程：一致性事务](http://os.51cto.com/art/201312/422577.htm "Storm入门教程：一致性事务")

 [Storm应用系列](http://blog.csdn.net/xeseo/article/category/1831495 "Storm应用系列")