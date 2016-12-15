---
layout: page
title: "Pigeon源码分析"
description: ""
---
{% include JB/setup %}

    Pigeon是公司Hydra服务化框架的底层通讯框架, 其实现参考了淘宝Dubbo的底层通讯实现.这也是为何我在 <<Dubbo源码分析>> 一文中没有分析远程服务调用具体实现的原因. 

	分析并熟悉Pigeon框架对于如何使用Netty通讯框架,自定义协议,序列化/反序列化等方面都具有积极的指导意义.

[Pigeon源码分析文档](https://github.com/18965050/dove/wiki/%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90 "Pigeon源码分析")


谈谈使用Netty开发协议的一些步骤及注意点:

1. 当然首先应该根据业务需求确定协议结构

2. 根据协议结构固定住请求(req),响应(res)对象的结构

3. Netty开发时, 注意ChannelHandler的顺序

    a. 如果是InBound, 则ChannelHandler的顺序一般为: Decrypt Handler-->Decoder Handler-->HeartBeat Hander-->Req构建Handler-->协议处理Handler

    b. 如果是OutBound, 则ChannelHandler的顺序一般为:Encrypt Handler-->Encoder Handler-->HeartBeat Hander-->Res构建Handler-->协议处理Handler  (注意调用顺序为反序)

    其中, Codec部分(Encoder,Decoder)可以考虑采用多种序列化方式(JDK,JSON,XML,Protobuf,Avro等等)

4. Netty4的线程模型中, InBound和OutBound事件均在EventLoop线程(及IO线程)中处理, 需要注意避免耗时操作导致线程阻塞

5. 同步调用一般通过Future.get()来实现阻塞同步调用, 异步调用则通过Callback方式进行

6. 如果ChannelHandler无状态, 可考虑在ChannelHandlerContext中共享(@Shareable)

7. 特定方法调用分两种情况:

    a. 类固定, 方法指定, 则req信息中需包含方法信息(方法签名, 参数等), server端通过反射实现

    b. 类和方法均指定, 则req信息中需包含类和方法信息(类,方法签名, 构造器,参数等),server端同样通过反射实现

8. 注意维护已建立的server和client的Channel连接(保存, 动态更新),便于后续做路由,负载均衡,监控等处理