# Spring boot入门

---
## 什么是Spring Boot
Spring Boot是由Pivotal团队提供的全新框架，其设计目的是用来简化新Spring应用的初始搭建以及开发过程。该框架使用了特定的方式进行配置，从而使开发人员不再需要定义样板化的配置。通俗的讲Spirng boot整合了所有的框架。  

## 使用Spring Boot有什么好处
方便、简单、快捷!平时如果我们需要搭建一个Spring Web项目的时候需要怎么做?
1. 配置web.xml加载Spring和Spring mvc
2. 配置数据库连接、配置Spring事物
3. 配置加载配置文件的读取，开启注释
4. 配置日志文件
5. 部署Tomcat测试
使用Spring Boot仅仅只需要非常少的几个配置就可以迅速方便的搭建起来一套Web项目或是构建一个微服务

## Spring Boot目录结构
根目录结构:com.example.project
```
com
  +- example
    +- myproject
      +- Application.java
      |
      +- domain
      |  +- Customer.java
      |  +- CustomerRepository.java
      |
      +- service
      |  +- CustomerService.java
      |
      +- controller
      |  +- CustomerController.java
      |
```
1. `Application.java`放在根目录下，用于框架配置
2. `domain`目录用于实体(Entity)与数据访问层(Repository)
3. `service`层用于业务类代码
4. `controller`负责页面访问控制