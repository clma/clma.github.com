---
layout: post
title: "Hello, Jekyll"
description: "Use Jekyll to Create Blog, based of the Jekyll Bootstrap Foundation."
category: tools
tags: [Jekyll, Jekyllbootstrap]
---
{% include JB/setup %}

使用Jekyll搭建Blog，基于[Jekyll Bootstrap](http://jekyllbootstrap.com)框架修改。

## Jekyll

### Jekyll快速入门

参考[Jekyll 快速入门](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)，

1. 在Github仓库上，创建新的仓库：`USERNAME.github.com`
2. 安装使用Jekyll-Bootstrap

<pre><code>git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.com
cd USERNAME.github.com
git remote set-url origin git@github.com:USERNAME/USERNAME.github.com.git
git push origin master
</code></pre>

### Windows中配置Jekyll
1. 需要安装`Ruby`和`DevKit`
2. 配置过程及可能遇到问题，参考：[Windows中配置Jekyll](http://fangge-sun.blog.163.com/blog/static/4895625720142315473777/)

	$ gem install jekyll

### Jekyllbootstrap主题
Jekyll-Bootstrap使用`rake tasks`实现了它的大部分功能。主题包的安装和切换也可以使用`rake`完成。从[Jekyllbootstrap主题](http://jekyllbootstrap.com/usage/jekyll-theming.html)获取主题，下载到`_theme_packages`目录下。

#### 安装主题
	
	$ rake theme:install name="THEME-NAME"

主题安装目录：`.\_includes\themes`

#### 切换主题

	$ rake theme:switch name="the-program"

切换主题名称为安装目录下主题名称。


### Jekyll中文问题处理

参考[Jekyll中文问题处理](http://nepshi.com/2012-10-08/chinese-characters-in-jekyll/)

1. 修改Jekyll的`convertible.rb`文件，让其使用`UTF-8`编码读文件；

    self.content = File.read(File.join(base, name), :encoding => "utf-8");

2. md/html文件都使用`UTF-8无BOM格式编码`保存。

Jekyll 使用'`gem install Jekyll`'安装后，目录为：

	D:\Ruby200\lib\ruby\gems\2.0.0\gems\jekyll-2.1.0

### Jekyll使用

#### 本地运行Jekyll

	$ cd USERNAME.github.com
	$ jekyll serve
	
#### 写文章

	$ rake post title="Hello，Jekyll！"

#### 创建页面

	$ rake page name="about.md"
	$ rake page name="pages/about.md"
	$ rake page name="pages/about"	# 创建文件：./pages/about/index.html

#### 发布
	
	$ git add .
	$ git commit -m "Add new Content"
	$ git push origin master
