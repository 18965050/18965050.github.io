---
layout: post
title: "Apache CXF WebService Development读书笔记"
tagline: "Supporting tagline"
description: ""
category: java
tags: [web service]
---
{% include JB/setup %}

![CXF WebService Development](/assets/attachment/img/cxf-webservice-development.png)

    CXF是一个Java WebService框架, 对Web服务规范的支持非常广泛. 包括JAX-WS, JAX-RS等. 与Spring的结合也十分的紧密.
    通过此书阅读, 可以了解:
        (1) WebService组成部分, WSDL文件结构
        (2) CXF内部结构, 包含总线(Bus), Front-End编程模型(标准WebService的Front-End, Simple Front-End等), WSDL服务模型, 数据绑定(JAXB, Aegis等), 传输协议(SOAP,HTTP,JMS等), 拦截器链(Phase, Inteceptor)等
        (3) 开发方式,包括Front-End(code-first, contract-first), Dynamic Client, Dispatch/Provider, Simple Front-End等
        (4) CXF支持的不同协议
        (5) Inteceptor Chain, Feature和Invoker
        (6) JAX-RS开发
        ......
        
## 源码
[https://github.com/18965050/ApacheCXFBook.git](https://github.com/18965050/ApacheCXFBook.git "Apache CXF WebService Development源码")

    
## 读书笔记
[https://github.com/18965050/ApacheCXFBook/wiki](https://github.com/18965050/ApacheCXFBook/wiki "Apache CXF WebService Development读书笔记") 