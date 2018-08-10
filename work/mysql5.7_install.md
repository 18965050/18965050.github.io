---
layout: page
title: "mysql5.7安装"
description: ""
---
{% include JB/setup %}

1. 下载[MySQL 5.7.22](https://dev.mysql.com/downloads/mysql/5.7.html#downloads "MySQL 5.7.22"),并放到`/usr/local`目录下

2. 登录安装机器,顺序执行如下命令

  ```bash
  yum install -y libaio
  groupadd mysql
  useradd -r -g mysql -s /bin/false mysql
  cd /usr/local
  tar -xvf mysql-5.7.22-el7-x86_64.tar.gz
  ln -s mysql-5.7.22-el7-x86_64 mysql
  cd mysql
  mkdir mysql-files
  chown mysql:mysql mysql-files
  chmod 750 mysql-files
  bin/mysqld --initialize --user=mysql
  bin/mysql_ssl_rsa_setup
  bin/mysqld_safe --user=mysql &
  cp support-files/mysql.server /etc/init.d/mysqld
  ```

3. 至此, mysql启动成功.可运行如下命令,加入系统service

  ```bash
  service mysqld status
  service mysqld start|stop
  
  chkconfig --add /etc/init.d/mysqld
  chkconfig mysqld on
  chkconfig --list
  ```

4. /etc/profile添加mysql环境变量

  ```bash
  export MYSQL_HOME=/usr/local/mysql
  export PATH=$PATH:${MYSQL_HOME}/bin:
  ```

5. 修改root初始密码
  - 在执行上述`bin/mysqld --initialize --user=mysql`命令时会得到一个root随机初始密码
  - 执行`bin/mysql -uroot -pxxx`登录
  - 执行`set password=password('ins1234');`修改root初始密码为`ins1234`

6. 拷贝[my.cnf](../assets/attachment/img/work/mysql-install/my.cnf "my.cnf") 到`/etc`目录下作为mysql默认配置

7. 允许root远程登录

  ```sql
  use mysql;
  grant all privileges  on *.* to root@'%' identified by "ins1234";
  flush privileges;
  select host,user from user; #可以看到root的host变更为%
  ```