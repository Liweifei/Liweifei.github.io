---
title: css设置图片垂直居中
date: 2018-03-06 22:57:06
tags:
---
```
<!-- 1、在外部盒子设置 -->
	<div><img src="" alt=""></div>

	//如上html结构，则：
	div{
		display:table-cell;
		vertical-align:middle;
		text-align:center;//设置水平也居中
	}
	img{
		vertical:middle;
	}
```

