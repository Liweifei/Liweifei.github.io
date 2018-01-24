---
title: js跨域传递信息和操作dom
date: 2018-01-23 22:08:16
tags:
---
### 1、什么是跨域？
&emsp;&emsp;不同协议（http/https）、不同域名（.com/.cn）或者是不同端口号（80/88），只要有一个不同就是跨域。
### 2、浏览器是否允许跨域？
&emsp;&emsp;javaScript出于安全考虑，不允许跨域读取数据或者是调用其它页面的对象。
### 3、解决方法（两个域的页面都是自己开发或者经过同意可允许跨域）？
&emsp;&emsp;HTML5的**postMessage**（ie8+），自己测试通过。
&emsp;&emsp;**（1）**在主域A.html（也就是另外一个域的页面想要跨域操作的这个页面）进行消息发送监听，如下代码：
```
	window.addEventListener("message",function(event){
		//event是对象，里面包含发来的数据event.data等
		//对其它窗口（域）下发来的信息
		if(event.data.type=="addPane"){
			//可以通过发送过来的数据的类型进行判断，符合才执行
			console.log("跨域执行输出")
		}
	
	})
```
<!-- more -->
&emsp;&emsp;**（2）**
在另一个域B.html进行消息发送，如下代码：
```
	document.body.onclick=function(){
		top.postMessage("addPane","http://192.168.1.168/project/A.html");
		//注意：
		//这里用top.postMessage，不用window.postMessage（具体我也不太懂）
		//前一个数据是要发送的数据
		//后一个数据就是要匹配跨域发送到的地址，必须对上，我们上面说在A.html中监听，所以假设A.html的地址在这里，（localhost测试时就输入localhost对应的地址就可以了）
	}
```