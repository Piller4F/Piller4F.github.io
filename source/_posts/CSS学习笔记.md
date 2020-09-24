# CSS 样式的学习
对于CSS样式进行简单的了解。
---
## 一、如何使用CSS
CSS是从HTML4开始使用的，作用是为了更好的渲染HTML元素。
CSS可以通过如下方式添加到HTML中：
- 内敛样式-在HTML中使用"style"**属性**
- 内部样式表-在HTML文档头部\<head>区域使用\<style>**元素**来包含CSS
- 外部引用-使用外部CSS**文件**
最好的方式为通过外部引用CSS文件  
---
## 二、内联样式
当特殊的样式需要应用个别元素时，就可以使用内联样式。方法是在相关的标签中使用  
样式属性。样式属性可以包含任何CSS属性。以下实例显示如何改变段落的颜色和左外  
边距。
```html
<p style="color:blue;margin-left:20px;">段落。</p>
```
<p style="border: 1px solid black;color:blue;margin-left:20px;">段落。</p>

--- 

## 三、HTML样式实例-背景颜色
背景颜色属性定义一个元素的背景颜色

```html
<body style="background-color:yello">
<h2 style="background-color:red">标题</h2>
<p style="background-color:green">段落</p>
</body>
```
<h2 style="border:1px solid black;background-color:red">标题</h2>
<p style="border:1px solid black;background-color:green">段落</p>

---

## 四、HTML样式实例-字体，字体颜色，字体大小
我们可以用font-family(字体)、color(颜色)，和font-size(字体大小)属性来定义字体的样式。

```html
<h1 style="font-family:verdanna;">标题</h1>
<p style="font-family:arial;color:red;font-size:20px">段落</p>
```
<h1 style="font-family:verdanna;">标题</h1>
<p style="font-family:arial;color:red;font-size:20px">段落</p>

---

## 五、HTML样式实例-文本对齐方式
使用text-align(文字对齐)属性指定文本的水平与垂直方式对齐：

```html
<h1 style="border:1px solid black;text-align:center;">文本居中对齐</h1>
<p style="border:1px solid black">段落</p>
```
<h1 style="border:1px solid black;text-align:center;">文本居中对齐</h1>
<p style="border:1px solid black">段落</p>

---

## 六、内部样式表
当单个文件需要特别样式时，就可以使用内部样式表。可以在\<head>部分通过\<style>标签定义内部样式表：

```html
<head>
	<style type="text/css">
		body {
			background-color:yello;
		}
		p {
			color:blue;
		}
	</style>
</head>
```

---

## 七、外部样式表
当样式需要被应用到很多页面的时候，外部样式表是理想的选择。使用外部样式表，就可以通过更改一个文件来改变整个站点的外观。

```html
<head>
	<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

---