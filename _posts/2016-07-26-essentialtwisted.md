---
layout: post
title: "Twisted Network Programming Essential读书笔记"
tagline: "Supporting tagline"
description: ""
category: python
tags: [python]
---
{% include JB/setup %}

![Twisted Network Programming Essential](/assets/attachment/img/twisted-network-programming-essential.png)

    Twisted是Python中的一个异步网络编程框架, 地位类似于Java中的Netty.和Python的其他网络框架不同(比如gevent基于协程),
    Twisted使用异步回调的方式来处理网络事件. 学好Twisted会让我们很方便的写出网络通讯的例子.
    通过阅读此书, 你可以了解:
    (1) Twisted框架的一些概念及使用. 比如 Transport, Protocol, ProtocolFactory
    (2) Deferred的使用, Deferred链的调用规则
    (3) twistd工具的使用及如何基于插件开发
    (4) 日志服务, 异步数据库访问API
    (5) trial及Twisted单元测试
    (6) Twisted中的线程及子进程
    .....

## 源码
**实例代码已做了修改, 适配Python3.5的版本**
[https://github.com/18965050/twisted-network-programming-essentials-examples.git](https://github.com/18965050/twisted-network-programming-essentials-examples.git "TwistedNetworkProgrammingEssential源码")


## 读书笔记
[https://github.com/18965050/twisted-network-programming-essentials-examples/wiki](https://github.com/18965050/twisted-network-programming-essentials-examples/wiki "TwistedNetworkProgrammingEssential读书笔记")

## 推荐阅读
[https://github.com/likebeta/twisted-intro-cn](https://github.com/likebeta/twisted-intro-cn "Twisted Intro 中文翻译版")

