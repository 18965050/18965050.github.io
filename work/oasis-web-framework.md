---
layout: page
title: "开源 OASIS Java Web 开发框架"
description: ""
---
{% include JB/setup %}

    OASIS是个我们自己定制的Web开发框架, 集成了SpingMVC+MyBatis+Tile+Shiro, 统一了Web开发的基本流程, 以及一些常用的功能.
    主要功能介绍如下:
    (1) Apache Tile页面模块化
    (2) MyBatis Generator深度定制; 支持生成文件(*Mapper.xml,*Mapper.java)和自定义文件(*DAO.xml,*DAO.java)分离,各种类型数据库的真正物理分页; 分页查询组件EasyList的实现; 基于注解的SQL查询条件及排序的支持.
    (3) 基于Shiro+Redis的分布式共享Session实现, 支持操作级和请求级的Session同步.
    (4) 独立的后端校验框架EasyValidator(https://github.com/18965050/EasyValidator)
    (5) 令牌拦截机制, 可一定程度预防CSRF攻击, 及防止表单重复提交
    (6) 滥用检查机制, 包括IP及Session的滥用检查, 黑白名单等.
    (7) Apache Commons和Google Guava工具类介绍说明


    OASIS的详细介绍可通过启动oasis-web-showcase项目(运行cn.xyz.chaos.examples.showcase.demo.ShowcaseServer)

## 项目地址
[https://github.com/18965050/oasis.git](https://github.com/18965050/oasis.git "OASIS Web Framework")
