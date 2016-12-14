---
layout: post
title: "Netty In Action 读书笔记"
tagline: "Supporting tagline"
description: ""
category: java
tags: [network]
---
{% include JB/setup %}

![Netty-In-Action](/assets/attachment/img/netty-in-action.png)

        Netty是Java网络编程的经典框架.其统一了我们在进行BIO,NIO和AIO,以及TCP和UDP编程之间的差异.它使我们的开发精力主要放在业务协议实现,业务逻辑,序列化反序列化上,极大的减轻了在连接建立,读写模型,线程处理等方面的考虑
        Netty是Java的基础框架,其使用非常广泛. 比如淘宝Dubbo SOA框架, RocketMQ 消息框架等底层都是使用Netty来实现. 顺便说一句, 我们公司自己开发的SOA框架Hydra底层也是使用Netty来实现的. 
        Netty In Action是介绍Netty的经典书籍.
        通过此书阅读,可以了解:
            (1) ByteBuf相比于JDK NIO提供的ByteBuffer的有点所在
            (2) Bootstrap,ServerBootstrap启动Netty流程
            (3) Channel,ChannelPipeline,ChannelHandler(Inbound,Outbound),ChannelContext之间的关系
            (4) 如何使用Encoder,Decoder进行序列化和反序列化
            (5) Netty4的线程模型
            ......

## 源码
[https://github.com/18965050/netty-in-action.git](https://github.com/18965050/netty-in-action.git "NettyInAction源码")


## 读书笔记
[https://github.com/18965050/netty-in-action/wiki](https://github.com/18965050/netty-in-action/wiki "NettyInAction读书笔记")

## 备注
需要注意的是Netty3和Netty4的线程模型不一致. Netty3中, InBound事件均在IO线程中处理, 而OutBound事件在IO线程中执行,
而Netty4中统一了线程模型, InBound和OutBound线程均在EventLoop线程(IO线程)中执行. Netty3的线程模型
比较高效,因为可以使用线程池并行执行, 但由于InBound和OutBound模型不一致, 容易导致线程安全性问题或内存泄露
问题的发生. 而Netty4虽然是串行执行EventLoop线程的, 但ChannelPipeline在加载ChannelHandler的时候可指定业务EventExecutorGroup,
降低了串行执行ChannelHandler对性能的影响.

[Netty系列之Netty线程模型](http://www.infoq.com/cn/articles/netty-threading-model/ "Netty系列之Netty线程模型")

[Netty版本升级血泪史之线程篇](http://www.infoq.com/cn/articles/netty-version-upgrade-history-thread-part/ "Netty版本升级血泪史之线程篇")

