---
layout: page
title: "使用Python编写的应用发布脚本"
description: ""
---
{% include JB/setup %}

    使用Python编写了一个应用发布的脚本, 可以实现:
    1.源码下载
    2.应用编译打包
    3.应用启动/停止/重启
    等功能

    这里简单记述下开发过程中的心得:
    使用python的虚拟环境(virtual enviromment)很方便.

    使用PyCharm的远程调试egg进行远程调试

    使用pip进行python egg下载安装时,从pypi下载很慢, 且经常由于网络原因报错, 可通过如下方式设置国内镜像:

        1. 在用户目录(~)下新建.pip文件夹

        2. 在.pip文件夹中新建pip.conf文件,内容如下:

        [global]
        index-url = http://mirrors.aliyun.com/pypi/simple
        [install]
        trusted-host = mirrors.aliyun.com


项目地址: [python应用发布脚本](https://github.com/18965050/python-RelaseScript.git "python应用发布脚本")