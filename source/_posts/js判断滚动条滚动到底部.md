---
title: js判断滚动条滚动到底部
date: 2018-01-02 23:22:23
tags:
---
&emsp;&emsp;判断依据：内容实际高度==滚动的距离+可视区域的高度？如果相等代表滚动到了底部。代码如下：
```
var scrollBox = document.getElementById("scrollBox");
var trueH = scrollBox.scrollHeight, //内容高度
scrollTop = scrollBox.scrollTop; //滚动高度
clientH = scrollBox.clientHeight;//可视区域的高度
if(trueH==(scrollTop+clientH)){
	alert("滚动到了底部")
}
```