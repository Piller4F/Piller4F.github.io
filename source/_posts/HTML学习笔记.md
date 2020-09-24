# 初始HTML
对于HTML的基础知识进行了简单的梳理。
---
## 一、HTML简介
```html
<!DOCTYPE html>          
<html>
	<head>
		<meta charset="utf-8">
		<title>html学习</title>
	</head>
	<body>
		<h1>标题</h1>
		<p>段落</p>
	</body>
</html>
```
- \<!DOCTYPE html> 声明为HTML5文档
- \<html> 元素是HTML页面的根元素
- \<head> 元素包含了文档的(meta)数据，```<meta charset="utf-8">```定义网页的编码格式为utf-8
- \<title> 元素描述了文档的标题
- \<body> 元素包含页面内容
- \<h1> 元素定义了一个标题
- \<p> 元素定义了一个段落
---
## 二、什么是HTML?
HTML是一种描述网页的语言
- HTML不是一种编程语言，而是一种标记语言
- 标记语言是一套标记标签
- HTML文档包含HTML标签和文本内容
---
## 三、HTML标签
HTML标记标签通常被称为HTML标签。
- HTML中的标签是由**尖括号**包围的关键词，例如\<html>
- HTML中通常标签是**成对**出现的，例如\<b>和\</b>
- 标签对中第一个为开始标签，第二个为结束标签
```
<标签>内容</标签>
```
--- 
## 四、HTML元素
通常来说"HTML标签"和"HTML"标签元素是一个意思。
但是严格的讲一个HTML元素需包含开始标签和结束标签
```
<p>段落</p>	
```
---
## 五、Web浏览器
Web浏览器是用于读取HTML文件，并进行网页显示。
浏览器不是直接显示HTML标签，而是将标签决定的展现方式来显示给用户。
---
## 六、HTML的网页结构
>\<html>
>>\<head>
>>>\<title>标题\</title>  
>>
>>\</head>
>>
>>\<body>
>>>\<h1>标题\</h1>  
>>>\<p>段落\</p>
>>
>>\</body>
>
>\</html>
---
## 七、HTML版本
| 版本      | 发布时间 |
| --------- | ------  |
| HTML      | 1991    |
| HTML+     | 1993    |
| HTML2.0   | 1995    |
| HTML3.2   | 1997    |
| HTML4.0.1 | 1999    |
| XHTML1.0  | 2000    |
| HTML5     | 2012    |
| XHTML5    | 2130    |

---
## 八、<!DOCTYPE>声明
\<!DOCTYPE>声明有助于浏览器中正确的显示网页。
DOCTYPE声明不区分大小写，例如：
```
<!DOCTYPE html>
<!DOCTYPE HTML>
<!DOCTYPE hTML>
<!DOCTYPE htML>
```
---
## 九、通用声明
### HTML
```
<!DOCTYPE html>
```
### HTML4.01
```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```
### XGTHTML1.0
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```
---
## 十、中文编码
目前在大部分浏览器中，直接输出中文难免会出现乱码，此时我们需要在头部声明字符编码为UTF-8或GBK
```html
<!DOCTYPE html>          
<html>
	<head>
		<meta charset="utf-8">
		<title>html学习</title>
	</head>
	<body>
	</body>
</html>
```