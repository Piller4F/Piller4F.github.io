# SQL基础
什么是SQL？SQL是结构化查询语言的缩写，用来访问和操作数据库系统。SQL语句既可以查询数据库中的数据，也可以添加、更新和删除数据库中的数据，还可以对数据库进行管理和维护操作。不同的数据库，都支持SQL，这样，我们通过学习SQL这一种语言，就可以操作各种不同的数据库。

---
## 关系数据库概述
关系模型把数据看成是一个二维表格，任何数据都可以通过行号+列好来唯一确定，它的数据模型  看起来就是一个Excel表

|  序号  |  姓名   | 
| ----- | ------- |
|   1   |  XXX    |

## 数据类型
对于一个关系表，除了定义每一列的名称外，还需要定义每一列的数据类型。

| 名称 | 类型 | 说明 |
| ---  | ---- | --- |
| INT | 整形 | 4字节整数类型 |
| BIGINT | 长整型 | 8字节整数类型 |
| REAL | 浮点型 | 4字节浮点数 |
| DOUBLE | 浮点型 | 8字节浮点数 |
| DECIMAL(M,N) | 高精度小数 | 例如DECIMAL(20,10),一共20位,小数10位 |
| CHAR(N) | 定长字符串 | 存储指定长度字符串，CHAR(100)总是存储100个字符的字符串 |
| VARCHAR(N) | 变长字符串 | VARCHAR(100)可以存储0~100个字符的字符串 |
| BOOLEAN | 布尔类型 | 存储true或false |
| DATE  | 日期类型 | 存储日期例如,2020-06-17 |
| TIME | 时间类型 | 存储时间例如,18:59:59 |
| DATETIME | 日期和时间类型 | 例如,2020-06-17 18:59:59 |
注意: SQL语言关键字不区分大小写,但是针对不同的数据库，对于表名和列名，有的数据区分大小写，有的数据不区分大小写。

## 安装MySQL
1. [官网下载](https://dev.mysql.com/downloads/mysql/)
- 1
2. 不懂的话就一路next下去
3. 添加环境变量  
打开 Windows 环境变量设置, 新建变量名 MYSQL_HOME , 变量值为 MySQL 安装目录路径,这里为`C:\Program Files\MySQL\MySQL Server 8.0`环境变量的Path变量中添加;%MYSQL_HOME%\bin;使用指令`mysql -u root -p`输入密码,如果变为`mysql>`则成功。

## MySQL的简单使用

### 登陆到MySQL
命令行输入
```
mysql -u root -p
```
- -u:所要登录的用户名;
- -p:告诉服务器会使用一个密码登陆;
出现`mysql>`则成功

### 创建一个数据库
使用`create database`语句可完成对数据库的创建，创建命令的格式如下:
```
create database 数据库名 [其它选项]
```
假如我们需要创建一个名`sample`的数据库
```
create database sample character set gbk;
```
提示:`Query OK, 1 row affected (0.01 sec)`则成功。注意输入末端有`;`号，表明输入完毕。使用`show databases;`可以查看建立了哪些数据库。

### 选择所要操作的数据库
- 再登录数据库时指令
```
命令：mysql -D 数据库名 -h 主机名 -u 用户名 -p
```
- 登录后使用`use`命令
```
use 数据库名
```

### 创建数据库表
使用`create table`语句可完成对表的创建
```
create table 表名称(列声明);
```
以创建student表为例,表中存放学号(id)、姓名(name)、性别(sex)、年龄(age)、联系电话(tel)这些内容:  
```
create table students
(
	id int unsigned not null auto_increment primary key,
	name char(8) not null,
	sex char(4) not null,
	age tinyint unsigned not null,
	tel char(13) null default "-"
);
```
直接输入容易出错，因建立一个`createtable.sql`文件导入
```
mysql -D sample -u root -p < F:\MySQLPractice\createtable.sql
```
语句解释:
```
create table tablename(columns)为创建数据库表的命令，列的名称以及该列的数据类型将在括号中完成;
括号内声明了5列内容，id、name、sex、age、tel为列名称，后面跟的是数据类型描述，列与列之间用‘,’隔开;
以"id int unsigned not null auto-increment primary key"介绍
id:列名称
int:类型为int
not null:说明该值不为空
auto_increment:在列中使用,作用为当插入数据时列如果为NULL,会自动产生一个比显存更大的唯一标识符值;
primary key:表明该列是主键，本列的值唯一;
```