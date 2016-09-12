---
layout: post
title: "Flask Web Development读书笔记"
tagline: "Supporting tagline"
description: ""
category: python
tags: [python]
---
{% include JB/setup %}

![Flask Web Development](/assets/attachment/img/flask-web-development.png)

    Flask是python中的一个web开发框架. 其核心只包括两个组件: werkzeug(WSGI)和jinjia2(Template),
    其他的功能均以插件的形式提供. 因此其框架本身很小, 但功能却十分的强大.
    本书的作者以实例的方式,循序渐进的方式介绍了Flask的功能, 包括:
    (1) 模板的使用
    (2) web请求响应, 请求路由, 请求钩子函数(类似于Servlet中的Filter和SpringMVC中的请求拦截器等)
    (2) 数据校验
    (3) 数据库访问, 迁移
    (4) 认证和授权
    (5) 大应用结构
    (6) 测试, 性能, 部署等等
    ......

    如果你想用Flask进行web开发, 此书确实是除了官方文档外, 值得一读的好书.

## 源码
[https://github.com/18965050/flasky.git](https://github.com/18965050/flasky.git "FlaskWebDevelopment源码")

这里要赞下作者, 每个知识点被打成了git中的tag, 使得代码获取和测试很方便


## 读书笔记
[https://github.com/18965050/flasky/wiki](https://github.com/18965050/flasky/wiki "FlaskWebDevelopment读书笔记")

