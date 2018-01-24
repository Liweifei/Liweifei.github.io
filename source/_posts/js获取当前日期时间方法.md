---
title: js获取当前日期时间方法
date: 2017-12-25 22:36:48
tags:
---
&emsp;&emsp;**1，获取当前时间**
```
	var time=new Date().toLocaleTimeString();//返回形式：下午10:58:13
```
&emsp;&emsp;**2，获取完整年份**
```
	var year=new Date().getFullYear();
```
&emsp;&emsp;**3，获取当前月份**
```
	var month=new Date().getMonth()+1;//返回的是0-11,所以+1；
```
&emsp;&emsp;**4，获取当前月份共有多少天**
```
	var lastmonth_lastDate=new Date(new Date().getFullYear(),new Date().getMonth()+1,0);//返回上个月的最后一天
	var num=lastmonth_lastDate.getDate();//得到日期既是总数
	//第一个参数代表年份，先说第三个参数，第三个参数填0代表的是上一个月份的最后一天，也就是说这个月是12月（系统返回11，因为0-11），然后填0 意思是返回11月份的最后一天，也就是30号，所以这个时候第二个参数要+1，意思就是这个月是10月，我填11月，所以你返回10月的最后一天，最后一天也就意味着总数。最后配合获取日期数得到总数；
```
&emsp;&emsp;**5，获取当前日**
```
	var date=new Date().getDate();;//返回的是1-31；
```
&emsp;&emsp;**6，获取当前是星期几**
```
	var day=new Date().getDay()+1;//返回的是0-6，0代表星期天；
```
&emsp;&emsp;**7，获取当前小时**
```
	var hour=new Date().getHours();//返回的是0-23；
```
&emsp;&emsp;**8，获取当前分钟**
```
	var min=new Date().getMinutes();//返回的是0-59；
```
&emsp;&emsp;**9，获取当前秒**
```
	var sec=new Date().getSeconds();//返回的是0-23；
```