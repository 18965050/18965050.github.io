---
layout: page
title: "Dubbo源码分析"
description: ""
---
{% include JB/setup %}

    Dubbo是淘宝开源的SOA框架, 它功能强大, 使用简单. 已被许多互联网公司采用, 完善和改造.
    Dubbo框架代码写得很好, 但注释和资料不足. 网上关于Dubbo的源码分析文档也不是很多,
    因此我特地用了3~4天的时间梳理了下Dubbo服务暴露和引用的流程. 便于今后对Dubbo进一步的
    深入理解和改造.

    另外, 公司内部的SOA框架(Hydra)借鉴了很多Dubbo的内容. 比如: 远程调用, 序列化反序列化, 注册中心的注册和查找等等
    后续有时间, 我也会将相应的文档补上.

    Dubbo框架内容庞大, 几天的时间只能梳理个主流程, 不能照顾到细枝末节, 有分析不对或含糊的地方还请多多指正.

[Dubbo源码分析文档](https://github.com/18965050/dubbo/wiki/Dubbo%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90 "Dubbo源码分析")
