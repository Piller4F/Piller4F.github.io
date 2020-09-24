# Maven简介

---
## 什么是Maven?
Maven是一个项目管理的综合工具。Maven提供了开发人员构建一个完整的生命周期框架。开发团队可以自动完成项目的基础工具建设，Maven使用的标准目录结构和默认构建生命周期。

## Maven是干什么的？
它是一个Apache的开源项目，主要服务于基于Java平台的项目构建、依赖管理和项目信息管理，为了不重复造车轮子。  
例如：两个项目A B，项目A需要依赖一些jar包，项目B也需要依赖这些jar包，那么此时如果都把jar包引入项目中，就是重复造轮子，我们应该将这些所有的jar包放入一个地方，需要用的时候过去取就行。

## 相同的项目结构
所有的Maven管理的Java项目都有着相同的项目结构
1. pom.xml用于维护当前项目使用了哪些jar包
2. 所以的java代码都放在src/main/java下面
3. 所以的测试代码都放在src/test/java下面

## 

## 下载Maven
1. [官网](http://maven.apache.org/download.cgi)
2. 图
3. 配置环境变量
- 新建系统变量:MAVEN_HOME 变量值:`C:\Maven\apache-maven-3.6.3`(填写自己的目录)
- 编辑系统变量:Path 添加变量值:`%MAVEN_HOME%\bin` 
4. 检验是否安装成功
`mvn -v`
