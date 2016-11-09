---
layout: post
title: "Docker In Action 读书笔记"
tagline: "Supporting tagline"
description: ""
category: OPS
tags: [VM Container]
---
{% include JB/setup %}

![Docker-In-Action](/assets/attachment/img/docker-in-action.png)

        docker是近两年非常火的一项虚拟化技术. 其构建于namespace(资源隔离)和cgroup(资源审计和限制)
        两项技术之上. 实现了直接在物理机器中部署容器, 抛弃了虚拟机, 更细粒度的进行应用和资源的管理和监控.
        同时, docker技术也引燃了go语言在国内的流行.
        通过此书阅读,可以了解:
            (1) 什么是docker及其优势
            (2) 基本概念: image,container,repository
            (3) docker操作命令
            (4) 数据卷及共享
            (5) 网络访问
            (6) Dockerfile编写
            (7) docker-compose应用编排
            (8) docker-machine 对于docker环境管理
            (9) docker-harbor构建私有仓储
            (10) docker-swarm对于docker集群的部署管理

        ps: 在最近的项目中, 我已经试着使用docker构建了发布环境

## 读书笔记
[https://github.com/18965050/dockerinaction/wiki](https://github.com/18965050/dockerinaction/wiki "DockerInAction读书笔记")