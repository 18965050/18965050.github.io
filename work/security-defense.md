---
layout: page
title: "Web开发安全防范注意"
description: ""

---

##防止XSS(Cross Site Script)攻击
- 定义: 攻击者往Web页面里插入恶意html代码(或js脚本)，当用户浏览该页访问代码连接时，嵌入其中Web里面的html代码(或脚本)会被执行，从而达到恶意攻击用户的特殊目的
- 类型: 反射型(未存储在数据库中). 保存型(保存至数据库中)
- 解决手段: 转义HTML特殊字符. JSP可使用<c:out />标签(其有个属性 `escapeXml`, 默认为true.表示转义标签中的字符) 

##防止CSRF(Cross-site request forgery)攻击
- 定义: 用户在访问网站A情况下,会生成用户会话(session).当用户使用此会话访问攻击者网站B针对网站A提供的连接时,会话会被劫持.从而造成比如信息修改, 恶意支付等情况. 可通过下图说明:
![csrf攻击原理](../assets/attachment/img/work/security_defense/csrf_principle.png)
- 解决手段: 防止会话被劫持. 可通过网站自生成的_token参数是否匹配来解决 
<font color="red">有些网站, 用户未登录和登录情况下的会话权限相同(新一站不存在此情况),这样危害更严重. 在一些Java安全框架, 比如Spring-Security, Shiro等都会创建一新会话,防止登录前回话被劫持</font>

##防止SQL Injection攻击
- 定义: 将sql命令作为页面参数提交给server端,造成实际执行sql和预期sql不一致,从而引起信息泄露,数据篡改等恶意行为
- 解决手段: 使用Prepare Statement. 比如iBatis中通过井号(#)参数引用方式可预防此攻击.

##防止DDos(Distribute Denial-of-Service)攻击
- 定义: 恶意用户将多个计算机联合起来作为攻击平台,利用正常的访问请求,对网站进行攻击.阻塞网络带宽,消耗网站资源, 使正常用户无法正常访问.
- 解决手段: 应用部署各层应均有防DDos攻击的配置.越靠前的防御,效果越好. 
  这里我们只说下应用层的防御.目前我们采用的是:

	<font color="blue">单会话单位时间访问请求数限制(防请求过频)</font> <br />
	<font color="blue">单IP单位时间产生会话数限制(防页面打开数过多)</font>


##防止MITM(Man-In-the-Mirror)攻击 

(TBD...)