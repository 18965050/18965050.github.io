---
layout: page
title: "统一认证授权管理系统"
description: ""
---
{% include JB/setup %}

    最近几个月都在开发统一认证授权管理系统, 终于完工了. 我们的系统具有:
    1. 基于CAS的SSO登录认证
    2. 支持普通web应用(前后端不分离)及SPA应用(前后端分离)的认证和鉴权
    3. 基于shiro的权限和鉴权管理
    4. 后端二级数据缓存(redis+guava cache),前端数据缓存以及基于websocket的数据实时同步和页面更新
    5. 基于redis的分布式共享session, 支持请求级别和操作级别的session同步
    6. docker应用部署


## [wiki]
[https://github.com/18965050/authz/wiki](https://github.com/18965050/authz/wiki "authz相关文档")
