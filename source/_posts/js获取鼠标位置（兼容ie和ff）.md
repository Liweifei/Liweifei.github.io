---
title: js获取鼠标位置（兼容ie和ff）
date: 2017-12-13 21:52:30
tags:
---
```
	//获取鼠标的y轴位置
	document.body.onmousemove=function(event){
		var y;
		var e=event || window.event;
		y=e.pageY?e.pageY:e.clientY+document.body.scrollTop-document.body.clientTop;//鼠标在可视区域的坐标+滚动条滚动的距离+border的高度
		return y;
	}
```
如上面代码，有两个点要注意：
&emsp;&emsp;**1**，evnet对象，因为ff中默认不带event对象，所以兼容event对象需要加上作为参数传递使用，否则会不识别。
&emsp;&emsp;**2**，e.pageX,ie中是没有这种方法的，所以为了兼容则等于后面的方法。
