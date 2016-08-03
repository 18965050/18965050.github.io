---
layout: page
title: "Python设计模式"
description: ""
---
{% include JB/setup %}

    对于从面向对象编程语言(比如C++, Java等)转入Python这种支持面向对象的脚本编程语言的程序员来说,
    一定会去研究设计模式在Python中的实现.
    虽然本质上来说, 设计模式是一种解决程序设计的惯用思维方式, 不受任何语言影响, 但不同语言的特性又
    决定了同一模式在不同语言中实现方式的差异.
    例如Python语言中的闭包, 装饰器, 函数作为一等公民, type等等特性决定了很多模式不需要通过类的继承
    或组合的形式来实现.
    github中 faif/python-patterns 项目对各种设计模式在python中的实现做了总结, 很值得我们学习下.
    我fork了此项目, 并对源码做了些调整, 使之在python3.5版本中可编译通过.

## 源码
[https://github.com/18965050/python-patterns.git](https://github.com/18965050/python-patterns.git "python-patterns源码")

## Wiki
[https://github.com/18965050/python-patterns/wiki](https://github.com/18965050/python-patterns/wiki "python设计模式")