# Python3概述
## Python简介
Python是一个高层次的结合了解释性、编译性、互动性和面向对象的脚本语言。  
Python的设计具有很强的可读性，相比其它语言经常使用英文关键字，其它语言的一些标点符号，它具  
有比其它语言更具有特殊语法结构。
- Python是一种解释型语言：这意味着开发过程中没有了编译这个环节。类似于PHP和Perl语言。
- Python是交互式语言：这意味着，可以在一个Python提示符`>>>`后直接执行代码。
- Python是面向对象语言：这意味着Python支持面向对象的风格或代码封装在对象的编程技术。
- Python是初学者的语言：Python对初级程序员而言，是一种伟大的语言，它支持广泛的应用程序开发，从简单的文字处理到WWW浏览器再到游戏。

---
## Python的发展历史
Python是由Guido van Rossum在八十年代末和九十年的初，在荷兰国家数学和计算机科学研究所设计出来的。
Python本身也是由诸多其它语言发展而来的，这包括ABC、Modula-3、C、C++、Algol-68、SmallTalk、Unix sheII和其它的脚本语言等等。
像Perl语言一样，Python源代码同样遵循GPL(GNU General Public License)协议。
现在Python是由一个核心开发团队在维护，Guido van Rossum仍然占据着至关重要的作业，指导其进展。
Python2.7被确定为最后一个Python2.x版本，除了支持Python2.x语法外，还支持部分Python3.1语法。

---
## Python特点
- 易于学习：Python有相对较少的关键字，结构简单，和一个明确定义的语法，学习起来更加简单。
- 易于阅读：Python代码定义的更清晰。
- 易于维护：Python的成功在于它的源代码是相当容易维护的。
- 一个广泛的标准库：Python的最大优势之一是丰富的库，跨平台的，在UNIX，Windows和Mac兼容性很好。
- 互动模式：互动模式的支持，您可以从终端输入执行带代码并获得结果的语言，互动的测试和调试代码片段。
- 可移植：基于其开源的特性，Python已经被移植(也就是使其工作)到许多平台。
- 可扩展：如果你需要一段运行很快的关键代码，或者是想编写一些不愿开发的算法，你可以使用C或C++完成那段程序，从Python程序中调用。
- 数据库：Python提供所有主要的商业数据库的接口。
- GUI编程：Python支持GUI可以创建和移植到许多系统调用。
- 可嵌入：你可以将Python嵌入到C/C++程序，让你的程序的用户获得“脚本化”的能力。

---
# Python环境搭建
## Python下载(版本3.7.4)
1. [下载官网](https://www.python.org/downloads/)
![](https://i.loli.net/2020/06/16/6uoVyFaWPUE1bv4.png)
![](https://i.loli.net/2020/06/16/aR2Hq4fWMmenGZP.png)
2. 添加环境变量方法一
win+r输入cmd(注意分号之后为你的py的安装目录)
```
path=%path%;C:\Users\Piller4F\AppData\Local\Programs\Python\Python37
```
3. 添加环境变量方法二
右击我的电脑**属性**  
点击**高级系统设置**
选择**高级**点击**环境变量**
![](https://i.loli.net/2020/06/16/BrU2McPKOfHQIht.png)
选择**Path**双击,添加自己的python安装目录
![](https://i.loli.net/2020/06/16/fN94AGlz7kXn6aJ.png)
![](https://i.loli.net/2020/06/16/movbA2EdWwnqVCS.png)
4. 测试Python是否安装完毕
```
python
```
![](https://i.loli.net/2020/06/16/2C9MZJpo8NdYeP5.png)

---
# Python的使用
## 运行Python
1. 命令行直接运行
```
python
```
Python命令行参数：
| 选项 | 描述 |
| ---- | ---- |
| -d   | 在解析时显示调试信息 |
| -O   | 生成优化代码(.pyp)文件 |
| -S   | 启动时不引入查找Python路径的位置 |
| -V   | 输出Python版本号 |
| -X   | 从1.6版本之后基本内建的异常已过时 |
| -c cmd | 执行Python脚本，并将运行结果作为cmd字符串 |
| file | 在给定的python文件执行python脚本 |
2. 命令行脚本
```
python script.py
```
3. 集成开发环境:**PyCharm**  

## PyCharm的安装及使用
1. [下载地址](https://www.jetbrains.com/pycharm/download/#section=windows)  
2. 具体流程如下  
![](https://i.loli.net/2020/06/16/mghZ7Ks8oOyIu9e.png)
![](https://i.loli.net/2020/06/16/pgm8R5JW7dSfB1j.png)
![](https://i.loli.net/2020/06/16/7XFu1h6yYRnMBVv.png)  
3. 建立一个py项目
```
print("hello world")
```
ctrl+shift+F10就会运行
![](https://i.loli.net/2020/06/16/rHBl2Ahn6exDSTF.png)
![](https://i.loli.net/2020/06/16/ryigjt2ewShnP4f.png)
![](https://i.loli.net/2020/06/16/qRvHnhs5MJzLQON.png)  
完成