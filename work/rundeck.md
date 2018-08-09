---
layout: page
title: "rundeck使用一些心得"
description: ""
---
{% include JB/setup %}

最近在搞jenkins+rundeck做应用的CI和CD. 下面是整理的一些rundeck使用上的心得

## 安装迁移
下面为从RUNDECK 2.10.7 ==> 3.0.1版本的迁移步骤.

**注意, 3.0.1版本如果使用mysql数据库,存在只能使用LATIN1字符集, 不支持UTF-8字符集的问题(https://github.com/rundeck/rundeck/issues/3797)**. 由此, 我们还是使用默认的H2
数据库

[从2.10.7升级到3.0.1](http://rundeck.org/docs/upgrading/upgrade-rundeck-2.11.x-to-rundeck-3.x.html)

## 权限配置
采用Runeck提供的JAAS来实现认证和登录. 最终目标为:
1. 支持公司LDAP域名登录认证
2. 支持配置的用户名/密码登录认证
3. 支持ACL权限分配

步骤如下:
1. `$RUNDECK_BASE/server/config/`目录下创建文件`jaas-multi.conf`((我们的路径为:/home/admin/rundeck)):

  ```yaml
  multiLoginModule {
        org.rundeck.jaas.jetty.JettyAuthPropertyFileLoginModule optional
        debug="true"
        storePass="true"
        file="/home/admin/rundeck/server/config/auth_realm.properties";
  
        com.dtolabs.rundeck.jetty.jaas.JettyCombinedLdapLoginModule optional 
        debug="true"
        contextFactory="com.sun.jndi.ldap.LdapCtxFactory"
        providerUrl="ldap://192.168.17.118/"
        bindDn="cn=ldapuser,cn=users,dc=focuschina,dc=com"
        bindPassword="mic66677777"
        authenticationMethod="simple"
        forceBindingLogin="true"
        userBaseDn="cn=users,dc=focuschina,dc=com"
        userRdnAttribute="sAMAccountName"
        userIdAttribute="sAMAccountName"
        userPasswordAttribute="unicodePwd"
        userObjectClass="user"
        roleBaseDn="cn=users,dc=focuschina,dc=com"
        roleNameAttribute="sAMAccountName"
        roleUsernameMemberAttribute="cn"
        roleMemberAttribute="member"
        roleObjectClass="group"
        cacheDurationMillis="300000"
        supplementalRoles="user"
        reportStatistics="true"
        timeoutRead="10000"
        timeoutConnect="20000"
        nestedGroups="false"
        storePass="true";
  
        org.rundeck.jaas.jetty.JettyRolePropertyFileLoginModule required 
        debug="true"
        useFirstPass="true"
        caseInsensitive="true"
        file="/home/admin/rundeck/server/config/role_realm.properties";
  
  };
  ```
  
  说明如下:
  a. 我们采用的是多级认证/鉴权模块登录方式
  
  b. LDAP认证类为`JettyCombinedLdapLoginModule`,不能是`JettyCachingLdapLoginModule `
  
  c. optional,requisite,required等关键词说明见 https://docs.oracle.com/javase/6/docs/api/javax/security/auth/login/Configuration.html
  
  c. 配置LDAP认证时, 注意userObjectClass配置为user
  
  d. LDAP认证模块中的supplementalRoles为用户默认的角色
  
  e. 上述配置了三个认证模块, 第一个为用户名/密码认证; 第二个为LDAP认证; 第三个作为授权(分配角色)用
  
  f. 使用`JettyRolePropertyFileLoginModule`必须要求前面登录模块`storePass="true"`, 且自身`useFirstPass="true"`, 这样可以使用上一个登录模块的认证信息
  
2. 创建给第一个LoginModule(`JettyAuthPropertyFileLoginModule`)使用的配置文件`auth_realm.properties`,配置如下:

  ```properties
  rundeck_admin_for_ci:passwordushouldnotuse,admin
  ```  
  
3. 创建给第三个LoginModule(`JettyRolePropertyFileLoginModule`)使用的配置文件`role_realm.properties`,配置如下:
  
  ```properties
  lvchenggang: -,admin
  rundeck_admin_for_ci:-,admin
  ```
  
  说明如下:
  
  a. 格式为`用户:密码,[角色列表]`
  
  b. 用户名即为第一个LDAP登录模块的用户名, 由于LDAP登录模块登录成功, 因此这里可以不需要密码, 用`-`(dummy password)代替
  
  c. rundeck默认的角色有admin, user, guest,apitoken(`$RUNDECK_BASE/etc`目录下的*.aclpolicy文件). 如果想自定义角色,及给角色分配权限, 可参考 http://rundeck.org/docs/administration/security/access-control-policy.html
  
3. 通过如下命令启动rundeck:
  ```bash
  java -Drundeck.jaaslogin=true -Dloginmodule.conf.name=jaas-multi.conf -Dloginmodule.name=multiLoginModule -jar rundeck-3.0.1-20180803.war
  ```

  说明如下:
  
  a. `-Dloginmodule.conf.name`参数值即为步骤1对应的文件名, 注意文件名前不要添加`server/confg/`路径
  
  b. `-Dloginmodule.name`需要保持和步骤1文件中的根名称一致
