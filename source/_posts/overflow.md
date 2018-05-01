title: overflow属性
---
### 说明
overflow:属性规定当内容溢出元素框时发生的事情.
---
### overflow的值
值      |描述
--------|:----------------------------------------------------|
visible |默认值。内容会显示在边框之外。
hidden  |边框内部正常显示，超出部分隐藏。
scroll  |超出部分隐藏，出现滚动条。
auto    |如果内容超出宽度，会出现滚动条，没超出正常显示，不出现滚动条。
inherit |从父元素继承overflow的值。
![overflow值](/img/images/overflow.png)
### 实例
#### 1.overflow:scroll
```
<html>
<head>
<style type="text/css">
	div 
		{
		background-color:#00FFFF;
		width:150px;
		height:150px;
		overflow: scroll;
	}
</style>
</head>

<body>
<p>如果元素中的内容超出了给定的宽度和高度属性，overflow 属性可以确定是否显示滚动条等行为。</p>

<div>
这个属性定义溢出元素内容区的内容会如何处理。如果值为 scroll，不论是否需要，用户代理都会提供一种滚动机制。因此，有可能即使元素框中可以放下所有内容也会出现滚动条。默认值是 visible。
</div>
</body>

</html>
```
----
#### 2.overflow:hidden
```
<html>
<head>
<style type="text/css">
	div 
	{
		background-color:#00FFFF;
		width:150px;
		height:150px;
		overflow: hidden
	}
</style>
</head>

<body>
	<p>如果元素中的内容超出了给定的宽度和高度属性，overflow 属性可以确定是否显示滚动条等行为。</p>
	<div>
	这个属性定义溢出元素内容区的内容会如何处理。如果值为 scroll，不论是否需要，用户代理都会提供一种滚动机制。因此，有可能即使元素框中可以放下所有内容也会出现滚动条。默认值是 visible。
	</div>
</body>

</html>
```
------
#### 3.overflow:auto
```
<html>
<head>
<style type="text/css">
	div 
	{
		background-color:#00FFFF;
		width:150px;
		height:150px;
		overflow: auto
	}
</style>
</head>

<body>
	<p>如果元素中的内容超出了给定的宽度和高度属性，overflow 属性可以确定是否显示滚动条等行为。</p>

	<div>
	这个属性定义溢出元素内容区的内容会如何处理。如果值为 scroll，不论是否需要，用户代理都会提供一种滚动机制。因此，有可能即使元素框中可以放下所有内容也会出现滚动条。默认值是 visible。
	</div>
</body>

</html>

```
------
### 浏览器支持
```
所有主流浏览器都支持 overflow 属性。
注释：任何的版本的 Internet Explorer （包括 IE8）都不支持属性值 "inherit"。
```

