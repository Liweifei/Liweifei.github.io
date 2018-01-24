---
title: 如何使用hexo+github创建个人博客
date: 2017-12-11 22:31:10
tags:
---
一篇关于如何使用hexo+github制作个人博客的小文章！直接进入正题！

**1. 什么是hexo？**
&emsp;&emsp;**[Hexo](https://hexo.io/)**是一个基于Nodejs快速简洁高效的博客框架（即它是博客速成工具）,它的文章编写采用**[markdown](https://www.appinn.com/markdown/)**语法，后期还可以部署到**[github](https://github.com/)**中使得你的博客可以直接访问。

<!-- more -->

**2. 环境配置**（以下为必须步骤）
&emsp;&emsp;安装**[node](https://nodejs.org/en/)**一路安装即可）
&emsp;&emsp;作用：用来生成静态页面的

&emsp;&emsp;GitHub（必须）

&emsp;&emsp;安装Git（必须）
&emsp;&emsp;作用：git仓库，管理项目，这里是把本地的hexo内容提交到github上去.

**3. 安装hexo**
``` bash
$ npm install hexo-cli -g
```

**4. 初始化hexo**
&emsp;&emsp;4.1 在任意一个文件夹中：**hexo init**（或者：**hexo init blog**）
&emsp;&emsp;4.2 进入这个文件夹：**cd blog**
&emsp;&emsp;4.3 初始化：**hexo init**(注意文件夹中不能有其它文件)
&emsp;&emsp;4.4 生成静态文件：**hexo generate**（或者：**hexo g**）
&emsp;&emsp;4.5 启动：**hexo server**（或者：**hexo s**）
&emsp;&emsp;4.6 在localhost:4000能够访问表示已经成功了

**5. hexo部署到Github**
5.1 建立仓库（Repository）：仓库名必须为：**"你的github的id".github.io**
5.2 修改_config.yml文件，来建立关联，命令（注意后面的三个有单个空格，格式限制），如下：
&emsp;deploy:

&emsp;&emsp;type: git

&emsp;&emsp;&emsp;repo: https://github.com/Liweifei/Liweifei.github.io.git

   branch: master
5.3 执行安装**hexo deploy**：**npm install hexo-deployer-git --save**
5.4 安装好之后执行配置命令：**hexo deploy**
5.5 在浏览器输入：http://liweifei.github.io/ 能访问表示成功了
5.6之后每次部署的步骤可以是：
&emsp;**hexo clean**

&emsp;&emsp;**hexo generate**

&emsp;&emsp;&emsp;** hexo deploy**