---
layout: post
title: "Netty In Action 读书笔记"
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
            (1) Bootstrap,ServerBootstrap启动Netty流程
            (2) Channel,ChannelPipeline,ChannelHandler(Inbound,Outbound),ChannelContext之间的关系
            (3) 如何使用Encoder,Decoder进行序列化和反序列化
            (4) Netty4的线程模型
            ......

##源码
[https://github.com/18965050/netty-in-action.git](https://github.com/18965050/netty-in-action.git "NettyInAction源码")


##读书笔记
[https://github.com/18965050/netty-in-action/wiki](https://github.com/18965050/netty-in-action/wiki "NettyInAction读书笔记")
