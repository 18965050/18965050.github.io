---
layout: post
title: "ProHadoop读书笔记"
tagline: "Supporting tagline"
description: ""
category: big-data
tags: [batch process]
---
{% include JB/setup %}

![Pro-Hadoop](/assets/attachment/img/prohadoop.png)

        Hadoop是个非常大的生态圈. 围绕着大数据的处理, 衍生出非常多的处理框架和组件.
        Hadoop主要用于数据批处理应用.其核心是HDFS和MapReduce. 
        对于大数据处理这块, 我本身也是比较犹豫的, 毕竟平时搞的不是这块. 之前想阅读的是"Hadoop-The Definitive Guide 4th Edition", 但后来发现此书不适合于初学者, 而本书则更加合适些.
        此书阅读只涉及到了HDFS和基本MapReduce操作, 不涉及高阶的组件和框架. 
        此书是基于Hadoop 2.x YARN框架.
        通过此书阅读, 可以了解:
        (1) Hadoop组成部分及Hadoop1.x, Hadoop2.x 的主要组件
        (2) Hadoop环境搭建. 包括本地, 伪集群和集群方式
        (3) Hadoop 配置说明
        (4) Hadoop HDFS介绍及适用场景
        (5) MapReduce操作, 包括: 基本操作, Combiner, Partitioner, Total Sorting和 Secondary Sorting
        (6) Hadoop IO, 包括 Compression, Splitter, SequenceFile, MapFile和AVRO
        (7) 使用MRUnit进行MapReduce单元测试
        (8) Hadoop的监管手段
        ......
        
## 源码
[https://github.com/18965050/prohadoop.git](https://github.com/18965050/prohadoop.git "ProHadoop源码")

    
## 读书笔记
[https://github.com/18965050/prohadoop/wiki](https://github.com/18965050/prohadoop/wiki "ProHadoop读书笔记")
         
## 参考资料
[Hadoop 新 MapReduce 框架 Yarn 详解](https://www.ibm.com/developerworks/cn/opensource/os-cn-hadoop-yarn/ "Hadoop 新 MapReduce 框架 Yarn 详解")

[Hadoop HA on Yarn——集群配置](http://www.cnblogs.com/captainlucky/p/4654923.html "Hadoop HA on Yarn——集群配置")

[MapReduce:详解Shuffle过程](http://langyu.iteye.com/blog/992916 "MapReduce:详解Shuffle过程")