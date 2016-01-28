---
layout: page
title: "如何在Github创建个人博客"
description: ""

---
{% include JB/setup %}

  网上有很多如何在github上创建个人博客的教程,我根据别人的经验,花了一天的时间,终于搭建出了自己的博客(^_^).先将整个流程分享给大家.

- 安装git,并会基本的git操作命令.这个不多说了,还没有使用过git的同学们可参考[廖雪峰的git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000 "廖雪峰的git教程") 

- 在github上注册账号并添加本机公钥. 还没有github账号的同学可访问[git官网](http://www.github.com git官网),上面有详细的说明步骤

- github仓储分用户仓储和项目仓储. 我们在上面创建个人仓储.

![github-create-user-repo](../assets/attachment/img/work/buildlog/github-create-user-repo.png)

注意仓储选择`public`,当然, 你也可以选择创建`README.md`文件

- 由于个人博客上面都是静态网页, 但写html实在是太麻烦了({>~<}),还好markdown是一个不错的选择.但我们需要一个将mardown文件转换为html的工具, 这个就是**jekyll**了.幸好github pages也是支持jekyll的. 我们需要先安装ruby, 因为jekyll是ruby的一个插件(*gem*). [rubyInstaller下载地址](http://www.ruby-lang.org/en/downloads/ "ruby下载地址")
	
- 创建环境变量$RUBY_HOME,并将$RUBY_HOME/bin添加到$PATH环境变量中

- (<font color="orange">可选</font>)安装DevKit, DevKit可在windows环境中运行Unix命令,类似minggw.( [DevKit下载地址](https://github.com/oneclick/rubyinstaller/downloads/  "DevKit下载地址") ). 下载解压并进入解压目录, 运行

	ruby dk.rb init

	ruby dk.rb install
	
- 由于众所周知的原因, 需要为ruby gem更换来源,否则下载不了gem

	gem sources --remove https://rubygems.org/ --add https://ruby.taobao.org/

	gem sources -l
		
- 安装jekyll gem

	gem install jekyll

  安装完成后, 运行命令`jekyll serve --watch`. 并在浏览器中访问 http://localhost:4000 

- 找个jekyll模板, 我使用的是 [jekyll-boostrap模板](https://github.com/plusjade/jekyll-bootstrap.git "jekyll-boostrap模板"), 主题选用的是 [the-program主题](https://github.com/jekyllbootstrap/theme-the-program.git "the-program主题") 

	git clone https://github.com/plusjade/jekyll-bootstrap.git

	cd jekyll-bootstrap

	rake theme:install git="https://github.com/jekyllbootstrap/theme-the-program.git"

- jekyll-boostrap 0.3.0 版本有个小bug: 找不到相应主题下的样式表文件(*style.css*), 可将_config.yml配置项:

	ASSET_PATH : false  修改为
	
	ASSET_PATH : /assets/themes/the-program
  
  来解决. 
  至此, 个人博客的基本模板就完成了. `git push` 到github上, 访问 [github账户].github.io 就可以看到了(^_^).