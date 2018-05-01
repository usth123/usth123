---
title: jQuery基础及选择器
---
jQuery是快速、简洁的JavaScript库，是继Prototype之后又一个优秀的JavaScript代码库。jQuery设计的宗旨是“write Less，Do More”，即倡导写更少的代码，做更多的事情。它封装JavaScript常用的功能代码，提供一种简便的JavaScript设计模式，优化HTML文档操作、事件处理、动画设计和Ajax交互。

## jQuery Start

### ECMAScript与JavaScript的区别

``` bash
jQuery是一个流行的JS库
ECMAScript:脚本语言的国际Web标准，是一种开放的、国际上广为接受的脚本语言规范.它本身并不是一种脚本语言。JavaScript 是 ECMAScript 规范的一种实现。
JavaScript:一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言，内置支持类型。
```
-------

### jQuery选择器总结

#### 1.基本选择器

##### 1.1 id选择器
$("#Element") 选择id值为Element的元素，id值在文档中不能重复，因此根据id查找找到的是一个元素
```
例：
	HTML代码：
		<div id="box"><p>id="p1"</p></div>
		<div id="box1">id="box1"</div>
	jQuery代码:
		console.log($("#box1"));
```

##### 1.2 标签名选择器
$("Element") 标签名选择器，根据指定标签名选择元素
```
例：
	HTML代码：
		<div id="box"><p>id="p1"</p></div>
		<div id="box1">id="box1"</div>
	jQuery代码:
		console.log($("div"));
```

##### 1.3 类名选择器
$(".myclass") 类名选择器，选择class值为myclass的所有元素
```
例:
	HTML代码：
		<div class="box"><p>id="p1"</p></div>
		<div class="box">class="box"</div>
	jQuery代码:
		$(".box")

		结果：[<div class="box"><p>id="p1"</p></div>]
```

##### 1.4 * 通配符选择器
$("*")*选择器，匹配所有元素
```
例:
	HTML代码：
		<div>DIV</div>
		<span>SPAN</span>
		<p>P</p>
	jQuery代码:
		$("*")

	结果：[ <div>DIV</div>, <span>SPAN</span>, <p>P</p> ]
```
--------

#### 2.层级选择器

##### 2.1 >孩子选择器，在给定的父元素下匹配所有的子元素
$("div > p")在div下查找所有的p孩子元素
```
例:
		HTML代码：
			<div id="box"><p>id="p1"</p></div>
			<div id="box1">id="box1"</div>
		jQuery代码:
			$("div > p")

		结果：[<p>id="p1"</p>]

```

##### 2.2 +相邻兄弟选择器，在选择紧接在另一元素后的元素，且二者有相同父元素。
$("lable + input")查找与lable相邻的input元素
```
例：
		HTML代码:
			<form>
			  <label>Name:</label>
			  <input name="name" />
			  <fieldset>
			      <label>Newsletter:</label>
			      <input name="newsletter" />
			 </fieldset>
			</form>
			<input name="none" />
		jQuery代码:
			$("label + input")

		结果：[<input name="name"/>,<input name="newsletter" />]

```

##### 2.3 ~同胞选择器,选择的是所有相同的父元素中位于 某元素之后的所有 某元素
$("form ~ input")选则的是同一父元素下form元素之后所有的input元素
```
例：
		HTML代码:
			<form>
	  			<label>Name:</label>
	  			<input name="name" />
	  			<fieldset>
		    	  	<label>Newsletter:</label>
		     		<input name="newsletter" />
	 			</fieldset>
			</form>
			<input name="none" />
		jQuery代码:
			$("form ~ input")

		结果：[ <input name="none" /> ]

```
-------

#### 3.基本过滤选择器

##### 3.1 :first选择器 获取匹配指定元素的第一个元素
$("div :first") 获取第一个div
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :first")

	结果：[<div>AAA</div>]

```

##### 3.2 :last选择器 获取匹配指定元素的最后一个元素
$("div :last") 获取最后一个div
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :last")

	结果：[<div>DDD</div>]

```

##### 3.3 :eq(index)选择器 获取匹配指定元素的第index元素
$("div :eq(index)") 获取第index-1个div,index从0开始
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :eq(2)")

	结果：[<div>CCC</div>]

```

##### 3.4 :even匹配所有索引值为偶数的元素，从 0 开始计数
$("div :even") 获取奇数div
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :even")

	结果：[<div>AAA</div>,<div>CCC</div>]

```

##### 3.5 :lt(index)匹配所有索引值小于index的元素，从 0 开始计数
$("div :even") 获取偶数div
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :lt(1)")

	结果：[<div>AAA</div>]

```

##### 3.6 :gt(index)匹配所有索引值大于index的元素，从 0 开始计数
$("div :even") 获取偶数div
```
例：
	HTML代码：
		<div>AAA</div>
		<div>BBB</div>
		<div>CCC</div>
		<div>DDD</div>
	jQuery代码：
		$("div :gt(2)")

	结果：[<div>CCC</div>,<div>DDD</div>]

```
----------

#### 4.表单选择器

##### $("input") input选择器 选择所有的input
##### $(":text") 匹配input中的text
##### $(":password") 匹配密码框
##### $(":check") 匹配多选框
-----------

#### 5.子元素
##### E:nth-child(n) 从1开始计数匹配E元素父元素下的第n个E元素

