---
title: select标签如何设置提示功能
date: 2017-12-21 22:46:30
tags:
---
&emsp;&emsp;我们都知道**input**标签等设置提示是用**placeholder**属性，那么**select**标签该如何设置类似的提示功能呢？其实就是用一个option标签设置属性"**disabled selected hidden**"即可，如下代码：
```
<select>
	<option value="1" disabled selected hidden>1</option>/*具有类似提示功能*/
	<option value="2">2</option>
	<option value="3">4</option>
</select>
```