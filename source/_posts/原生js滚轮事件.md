---
title: 原生js滚轮事件
date: 2017-12-18 22:50:01
tags:
---
简述：滚轮事件只有firefox比较特殊，使用**DOMMouseScroll**; 其他浏览器使用**mousewheel**，简单代码如下：  
```
if (document.addEventListener){
	//Firefox监听,火狐浏览器监用DOMMouseScroll来监听			
	document.body.addEventListener("DOMMouseScroll",function(event){
		getEvent(event);
	})
}
document.body.addEventListener("mousewheel",function(event){
	//其它浏览器如谷歌用mousewheel来监听
	getEvent(event);
})
function getEvent(event){
	console.log(event.wheelDelta || event.detail);
	if(event.wheelDelta){//如果是mousewheel监听，则事件返回的是event.wheelDelta
		console.log(event.wheelDelta/120);//除以120是因为返回的值是120的倍数
	}else{
		console.log(event.wheelDelta/3);//Firefox返回值，除以3是因为返回的值是3的倍数
	}
}
```
**总结：**
&emsp;&emsp;**1**，**mousewheel**事件中的 “**event.wheelDelta**”属性值：返回的值，如果是**正值说明滚轮是向上滚动**，如果是**负值说明滚轮是向下滚动**；返回的值，均为 **120** 的倍数，即：幅度大小 = 返回的值 / 120。
&emsp;&emsp;**2**，**DOMMouseScroll**事件中的 “**event.detail**” 属性值：返回的值，如果是**负值说明滚轮是向上滚动**（与 “event.wheelDelta” 正好相反），如果是正值说明滚轮是向下滚动；返回的值，均为 3 的倍数，即：幅度大小 = 返回的值 / 3。