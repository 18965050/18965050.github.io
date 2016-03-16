---
layout: post
title: "跟我学Shiro 学习笔记"
tagline: "Supporting tagline"
description: ""
category: java
tags: [web security]
---
{% include JB/setup %}

![和我学Shiro](/assets/attachment/img/learning-shiro-with-me.png)

    Shiro是一个非常轻量级的Java安全框架(前身是jSecurity), 一般用于Web安全方面. 麻雀虽小,五脏俱全,Shiro中包含了安全管理(认证, 授权),
    会话管理(脱离于HttpSession的独立会话),缓存管理(独立的缓存框架,可对接其他缓存实现),各种Web 认证过滤器等等...
    开涛的"跟我学Shiro"(https://github.com/zhangkaitao/shiro-example)系列文章非常详细的介绍了Shiro的各个方面, 并扩展出了很多实际开发
    中可能会遇到的用例进行实例说明, 是非常棒的Shiro学习资料.
    通过阅读"跟我学Shiro"系列文章, 可以了解:
    (1) Shiro中的实体概念: Subject, AuthenticationToken(Principal, Credential), Realm 等等
    (2) 认证和授权流程: SecurityManager(Authenticator, Authorizer), AuthorizingRealm, CredentialsMatcher, AuthenticationStrategy等等
    (3) 会话管理: Session, SessionManager, SessionDAO等等
    (4) 缓存管理: Cache, CacheManager等等
    (5) Shiro如何与Web和Spring相结合: JSP标签, 注解, 认证FilterChain
    ......
    
## 源码
[https://github.com/zhangkaitao/shiro-example.git](https://github.com/zhangkaitao/shiro-example.git "跟我学Shiro源码")
    
## 读书笔记
[https://github.com/18965050/shiro-example/wiki](https://github.com/18965050/shiro-example/wiki "跟我学Shiro读书笔记")