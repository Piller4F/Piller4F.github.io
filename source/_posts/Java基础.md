# Java基础快速入门
对Java的使用进行简单的梳理。

---
## Java简介
Java是由Sun Microsystems公司于1995年5月推出的Java面向对象程序设计语言和Java平台的总称。由James Gosling和同事们共同研发，并在1995年正式推出。
Java分为三个体系:  
- JavaSE
- JavaEE
- JavaME  

JavaSE就是标准版，包含标准的JVM和标准库，而JavaEE是企业版，它只是在JavaSE的基础上加上了大量的API和库，以便开发Web应用、数据库、消息服务等，JavaEE的应用使用的虚拟机和JavaSE的完全相同。 JavaME没有流行度，不建议学。  
Java的学习路线如下：
1. 首先掌握JavaSE，掌握Java语言本身、Java核心开发技术以及Java标准库的使用；
2. 如果继续学习JavaEE，那么Spring框架、数据库开发、分布式架构都是要学的；
3. 如果学习大数据开发，那么Hadoop、Spark、Flink这些大数据平台都是要学的；
4. 如果学习移动开发，就深入Android平台；

---
## JDK安装
1. Java程序必须运行在JVM上，第一件事情就是安装JDK。
![](https://i.loli.net/2020/06/16/T6sw8jdvucfKAXU.png)  
![](https://i.loli.net/2020/06/16/NTLBhwsfHC7Zjt5.png)  
2. 添加环境变量(注意改成自己的目录)
![](https://i.loli.net/2020/06/16/EoBLisy4DwQXWOH.png)  
- 新建系统变量`JAVA_HOME`
```
C:\Program Files\Java\jdk-14.0.1
```
![](https://i.loli.net/2020/06/16/Jqe6lU4VPyXDrNC.png)  
- 新建系统变量`CLASSPATH`
```
.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar; 
```
![](https://i.loli.net/2020/06/16/Y7MrfS8p9BHlgL4.png)  
- Path中添加
```
%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
```
![](https://i.loli.net/2020/06/16/EHf3r4UMJF5vCdL.png)  
使用java的常用命令，检测是否添加成功
```
java -version
```

## 第一个Java程序
1. 打开文本编辑器
```java
public class Hello {
	public static void main(String[] args) {
		System.out.println("Hello world!");
	}
}
```
在一个Java程序中能看到类似:
```java
public class Hello {
	...
}
```
的定义，这个定义被成为class(类)，这里的类名`Hello`，大小写敏感，使用`class`来定义一个类，`public`表面这个类是共有的，`Hello`是类的名字。
注意在类中我们定义了一个名为`main`的方法：
```java
public static void main(String[] args) {
	...
}
```
方法是可执行的代码块，一个方法除了方法名`main`，还有用`()`括起来的方法参数，这里`main`的方法又有一个参数，`String[]`使用`public`和`static`来修饰方法。  
方法中的每行代码有结束符`;`
```Java
System.out.println("Hello world!");
```
Java规定，某个定义的`main`是Java程序的入口方法，因此，Java程序总是从`main`开始执行。  
最终我们保存文件时，文件名必须为`Hello.java`因为要和我们定义的类名一致。
2. 如何运行Java程序
Java源码本质上是一个文本文件，我们需要先用`javac`把`Hello.java`编译成字节码文件`Hello.class`，然后用`java`命令执行这个字节码文件。  
第一步进入Hello.java的目录
```
javac Hello.java
java Hello
```
![](https://i.loli.net/2020/06/16/5Rm8jlTgIbCGrUD.png)  

## IntelliJ IDEA下载及安装教程(教程有很多，如果如下操作行不通，百度百度百度！)
1. [破解文件百度分流](https://pan.baidu.com/s/1soSy4eKId3z3xqxiKrxdxg )
提取码：4z00
2. 解压后如图  
![](https://i.loli.net/2020/06/16/zclmbnfxLpDsq9F.png)  
3. 安装(你如果不会就尽量和我配置的一样)
![](https://i.loli.net/2020/06/16/CVnF7rzsQxgLWEB.png)  
![](https://i.loli.net/2020/06/16/JMizG7sjedEqk5n.png)  
完成
4. 将该文件复制到IEDA安装的bin目录下
![](https://i.loli.net/2020/06/16/CHYTwJeN3ol9Dp7.png)  
5. 启动IDEA点击OK，接下来是主题，可以先跳过
![](https://i.loli.net/2020/06/16/qmvre1AcP6oCHfi.png)  
6. 按图中打开
![](https://i.loli.net/2020/06/16/4Vq1B8LjiXumps2.png)  
添加后save(注意要切换成自己的目录)

```
-javaagent:F:\IntelliJ IDEA 2019.3.3\bin\jetbrains-agent.jar
```
7. 关闭后打开
![](https://i.loli.net/2020/06/16/oKciM3yhfSIOdFT.png)  
只要是Licensed to XXX 就成功了
![](https://i.loli.net/2020/06/16/J9bBA3hCRVmtD5Z.png)  

## IntelliJ IDEA的使用
1. IDEA快速搭建Java开发环境  
配置JDK的方法如下
![](https://i.loli.net/2020/06/16/FctKezJhMfbRP3j.png)  
![](https://wx1.sbimg.cn/2020/06/16/11.png)  
![](https://i.loli.net/2020/06/16/B32bWeVQyuajlpv.png)  
![](https://i.loli.net/2020/06/16/wEXbO4yfrCcNxza.png)  
![](https://wx1.sbimg.cn/2020/06/16/15.png)  
2. 编写hello world!  
Create New Project  
![](https://wx1.sbimg.cn/2020/06/16/16.png)  
建立一个空的项目   
![](https://wx2.sbimg.cn/2020/06/16/17.png)  
![](https://wx2.sbimg.cn/2020/06/16/18.png)  
建立一个空类
![](https://wx2.sbimg.cn/2020/06/16/19.png)  
编写代码
```java
public class Hello {
    public static void main(String args[]) {
        System.out.println("hello world");
    }
}
```
ctrl+shift+10编译运行  
![](https://wx2.sbimg.cn/2020/06/16/20.png)  
