---
layout: page
title: "利用Prometheus打造业务监控系统"
description: ""
---
{% include JB/setup %}

    之前我们的监控系统主要使用的是zabbix和公司自研的UMC平台. 但这两个平台均只能对
    基础设施或基础指标进行监控, 对业务指标的监控并不强大. 
    
    最近我们改造成使用Prometheus+AlertManager+Grafana来进行业务监控, 并使用已经
    集成到SpringBoot中的micrometer构建监控指标, 目前效果良好. 
    
    同时, 也实现了对基础中间件的监控, 比如Druid, Dubbo, Tomcat, Redis等,
    相关代码在最新的oasis源码包中
    
## [wiki]
[Prometheus](https://github.com/18965050/prometheus "Prometheus业务监控")