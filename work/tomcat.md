---
layout: page
title: "Web应用服务器切换为Tomcat总结"
description: ""
---
{% include JB/setup %}

    最近在统一各个Web应用的Web服务器, 之前有的项目使用resin, 有的使用jetty, 还有的使用其他, 很不统一, 造成管理和维护困难. 
    经过技术选型及其他方面的考量, 最终确定使用Tomcat 8.5.X版本. 
    在切换的过程中, 遇到了不少问题, 也做了些优化. 现将此过程中的一些历程整理成文档,供后续参考


## [wiki]
[Tomcat相关总结文档](https://github.com/18965050/tomcat/wiki "Tomcat相关总结文档")
