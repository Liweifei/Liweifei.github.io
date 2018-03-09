---
title: 关于hexo deploy出错问题
date: 2018-03-07 23:20:46
tags:
---
不知道为什么，本人2017年能hexo d能正常使用的，但是过了个年不行了。之后各种百度，终于找到了解决方法：
把**_config.yml**里面的  
"deploy:
&emsp;&emsp;type: git
&emsp;&emsp;repo: https://github.com/Liweifei/Liweifei.github.io.git
&emsp;&emsp;branch: master"  
**改为**
"deploy:
&emsp;&emsp;type: git
&emsp;&emsp;repo: git@github.com:Liweifei/Liweifei.github.io.git
&emsp;&emsp;branch: master"  
**重点是->repo: ？？？？**
