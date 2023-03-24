

[TOC]

## 1.1、简介

- Spring:春天—&gt;给软件行业带来了春天！ 
- 2002,首次推出了Spring框架的雏形：interface21框架！ 
- Spring框架即以interface21框架为基础，经过重新设计，并不断丰富其内涵，于2004年3月24日发布了1.0正式版。 
- Rod Johnson,Spring Framework创始人，著名作者。很难想象Rod Johnson的学历，真的让好多人大吃一惊，他是悉屋然学的博士，然而他的专业不是计算机，而是音乐学。 
- spring:理念：使现有的技术更加容易使用，本身是一个大杂烩，整合了现有的技术框架！

SSH：Struct2+Spring+Hibernate！ SSM： SpringMvc + Spring + Mybatis!

官网： [Spring Framework Documentation](https://docs.spring.io/spring-framework/docs/current/reference/html/)

网址： [Index of /spring-framework/docs/4.3.9.RELEASE/spring-framework-reference](https://docs.spring.io/spring-framework/docs/4.3.9.RELEASE/spring-framework-reference/)

官网下载地址： [repo.spring.io](https://repo.spring.io/ui/native/release/org/springframework/spring)

Github： [spring-projects/spring-framework: Spring Framework (github.com)](https://github.com/spring-projects/spring-framework)




![img](https://img-blog.csdnimg.cn/19950ead474643d4969fb2d100f52eda.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center) ![img](https://img-blog.csdnimg.cn/fe3657adcc8f4e2f87dae1a4448000c6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)![img](https://img-blog.csdnimg.cn/a5bef14200e149d5b249510468904464.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

导包：

 [Maven Repository: org.springframework » spring-webmvc (mvnrepository.com)](https://mvnrepository.com/artifact/org.springframework/spring-webmvc)


![img](https://img-blog.csdnimg.cn/7042be0866c24c93ade920c3a7193281.png)

```java
<!-- https://mvnrepository.com/artifact/org.springframework/spring-webmvc -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>5.3.16</version>
</dependency>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-jdbc</artifactId>
    <version>5.3.16</version>
</dependency>
```

## 1.2、优点

- Spring是一个开源的免费的框架（容器）！ 
- Spring是一个轻量级的、r非入侵式的框架！ 
- 控制反转(IOC)，面向切面编程(AOP)！ 
- 支持事务的处理，对框架整合的支持！

总结一句话：Spring就是一个轻量级的控制反转(IOC)和面向切面编程（AOP）的框架！

## 1.3、组成

 [Spring—七大核心模块 - 小白知浅 - 博客园 (cnblogs.com)](https://www.cnblogs.com/xiaobaizhiqian/p/7616453.html)


![img](https://img-blog.csdn.net/20180914091500764?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0h1YW5nMTE3ODM4Nzg0OA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**核心容器（Spring Core）**

核心容器提供Spring框架的基本功能。Spring以bean的方式组织和管理Java应用中的各个组件及其关系。Spring使用BeanFactory来产生和管理Bean，它是工厂模式的实现。BeanFactory使用控制反转(IoC)模式将应用的配置和依赖性规范与实际的应用程序代码分开。

**应用上下文（Spring Context）**

Spring上下文是一个配置文件，向Spring框架提供上下文信息。Spring上下文包括企业服务，如JNDI、EJB、电子邮件、国际化、校验和调度功能。

**Spring面向切面编程（Spring AOP）**

通过配置管理特性，Spring AOP 模块直接将面向方面的编程功能集成到了 Spring框架中。所以，可以很容易地使 Spring框架管理的任何对象支持 AOP。Spring AOP 模块为基于 Spring 的应用程序中的对象提供了事务管理服务。通过使用 Spring AOP，不用依赖 EJB 组件，就可以将声明性事务管理集成到应用程序中。

**JDBC和DAO模块（Spring DAO）**

JDBC、DAO的抽象层提供了有意义的异常层次结构，可用该结构来管理异常处理，和不同数据库供应商所抛出的错误信息。异常层次结构简化了错误处理，并且极大的降低了需要编写的代码数量，比如打开和关闭链接。

**对象实体映射（Spring ORM）**

Spring框架插入了若干个ORM框架，从而提供了ORM对象的关系工具，其中包括了Hibernate、JDO和 IBatis SQL Map等，所有这些都遵从Spring的通用事物和DAO异常层次结构。

**Web模块（Spring Web）**

Web上下文模块建立在应用程序上下文模块之上，为基于web的应用程序提供了上下文。所以Spring框架支持与Struts集成，web模块还简化了处理多部分请求以及将请求参数绑定到域对象的工作。

**MVC模块（Spring Web MVC）**

MVC框架是一个全功能的构建Web应用程序的MVC实现。通过策略接口，MVC框架变成为高度可配置的。MVC容纳了大量视图技术，其中包括JSP、POI等，模型来有JavaBean来构成，存放于m当中，而视图是一个街口，负责实现模型，控制器表示逻辑代码，由c的事情。Spring框架的功能可以用在任何J2EE服务器当中，大多数功能也适用于不受管理的环境。Spring的核心要点就是支持不绑定到特定J2EE服务的可重用业务和数据的访问的对象，毫无疑问这样的对象可以在不同的J2EE环境，独立应用程序和测试环境之间重用。

## 1.4、拓展

在Spring的官网有这个介绍：现代化的约ava开发！说白就是基于Spring的开发！


![img](https://img-blog.csdnimg.cn/8e907d5773e24e9d849a4b184f70cc06.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 1.5、常用依赖

```java
<dependencies>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>5.3.16</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
```

**SpringBoot**

- 一个快速开发的脚手架。 
- 基于SpringBoot可以快速的开发单个微服务。 
- 约定大于配置！

**SpringCloud**

- SpringCloud是基于SpringBoots实现的。

因为现在大多数公司都在使用SpringBooti进行快速开发，学习SpringBoot的前提，需要完全掌握Spring及SpringMVC!

**弊端：发展了太久之后，违背了原来的理念！配置十分繁琐，人称：“配置地狱！”**


1.UserDao接口 2.UserDaolmpl实现类 3.UserService业务接☐ 4.UserServicelmpl业务实现类

加配置


![img](https://img-blog.csdnimg.cn/99ddd523cdb74dadaa7988f8664d7008.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

接口

UserDao.java


![img](https://img-blog.csdnimg.cn/65c8d2832ef748838b5d3b8d79fdb765.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;

public interface UserDao {
   
    void getUser();
}
```

UserDaoImpl.java


![img](https://img-blog.csdnimg.cn/92e4fa3ec6da471fb1ee43e2a77c0c31.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;

public class UserDaoImpl implements UserDao{
   
    @Override
    public void getUser() {
   
        System.out.println("默认获取用户的数据");
    }
}
```

业务层

UserService.java


![img](https://img-blog.csdnimg.cn/c9f79c1c1eb74e29a279585bedfcd006.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.service;

public interface UserService {
   
    void getUser();
}
```

UserServiceImpl.java


![img](https://img-blog.csdnimg.cn/8628ec19970f4d6b94f770ecfe7ef610.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.service;

import com.blue.dao.UserDao;
import com.blue.dao.UserDaoImpl;

public class UserServiceImpl implements UserService{
   

    private UserDao userDao = new UserDaoImpl();

    @Override
    public void getUser() {
   
        userDao.getUser();
    }
}
```

MyTest.java


![img](https://img-blog.csdnimg.cn/bf4704529ad24c018532fde1a3733103.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;

import com.blue.service.UserService;
import com.blue.service.UserServiceImpl;

public class MyTest {
   
    public static void main(String[] args) {
   

        ///用户实际调用的是业务层，dao层他们不需要接触！
        UserService userService = new UserServiceImpl();

        userService.getUser();

    }
}
```

要获取其他业务的数据，如下：

UserDaoMysqlImpl.java


![img](https://img-blog.csdnimg.cn/7844c3bcc6444accb63029e018df61b0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;

public class UserDaoMysqlImpl implements UserDao{
   
    @Override
    public void getUser() {
   
        System.out.println("Mysql获取用户数据");
    }
}
```

则需要更改如下地方：

这动了源码，如果代码很长，则会复杂


![img](https://img-blog.csdnimg.cn/bbb61e3e5e81404b97a17167fa154b76.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/c3ea7ea1d8fd4c189f989f9d4b9be7a6.png)

在我们之前的业务中，用户的需求可能会影响我们原来的代码，我们需要根据用户的需求去修改原代码！

我们使用一个Set接口实现.已经发生了革命性的变化！

- 之前，程序是主动创建对象！控制权在程序猿手上！ 
- 使用了set注入后，程序不再具有主动性，而是变成了被动的接受对象！

UserServiceImpl.java


![img](https://img-blog.csdnimg.cn/44673551ad3b411c950406e03dd9d2aa.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.service;

import com.blue.dao.UserDao;
import com.blue.dao.UserDaoImpl;
import com.blue.dao.UserDaoMysqlImpl;

public class UserServiceImpl implements UserService{
   

    private UserDao userDao;

    //利用set进行动态实现值的注入
    public void setUserDao(UserDao userDao) {
   
        this.userDao = userDao;
    }

    @Override
    public void getUser() {
   
        userDao.getUser();
    }
}
```

MyTest.java


![img](https://img-blog.csdnimg.cn/2134884a992f452ea31d12577d51e3d0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;

import com.blue.service.UserService;
import com.blue.service.UserServiceImpl;

public class MyTest {
   
    public static void main(String[] args) {
   

        ///用户实际调用的是业务层，dao层他们不需要接触！
        UserServiceImpl userService = new UserServiceImpl();

        userService.setUserDao(new UserDaoMysqlImpl());
        userService.getUser();

    }
}
```

这种思想，从本质上解决了问题，我们程序猿不用再去管理对象的创建了。系统的耦合性大大降低~，可以更加专注的在业务的实现上！这是IOC的原型！

## 2.1、IOC本质控制反转

**IoC(Inversion of Control),是一种设计思想，DI(依赖注入)是实现Ioc的一种方法，**也有人认为DI只是oC的另一种说法。没有引oC的程序中，我们使用面向对象编程，对象的创建与对象间的依赖关系完全硬编码在程序中，对象的创建由程序自己控制，控制反转后将对象的创建转移给第三方，个人认为所谓控制反转就是：获得依赖对象的方式反转了。

采用XML方式配置Bean的时候，Bean的定义信息是和实现分离的，而采用注解的方式可以把两者合为一体，Bean的定义信息直接以注解的形式定义在实现类中，从而达到了零配置的目的。

**控制反转是一种通过描述(XML或注解)并通过第三方去生产或获取特定对象的方式。在Spring中实现控制反转的是IoC容器，其实现方法是依赖注入(Dependency Injection,Dl)。**


 [核心技术 (spring.io)](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#beans-basics)

### 测试一

新建模块


![img](https://img-blog.csdnimg.cn/2dee4b164193484d984cb3da1d69b2c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

beans.xml


![img](https://img-blog.csdnimg.cn/d13dad98b889497fb6246ac91e86a702.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/cb51bfa306b643a6a845a090d5c591a5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

MyTest.java


![img](https://img-blog.csdnimg.cn/0441505a3bdb4ef1a3ef335e8519ea48.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
ApplicationContext context = new ClassPathXmlApplicationContext("services.xml", "daos.xml");
```

结果：


![img](https://img-blog.csdnimg.cn/6ee749d1bfe3455ea8f32fa4e52eb5e7.png)

### 测试二

新建beans.xml

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-pPVkuRb6-1648559381967)(C:\Users\dlmu\AppData\Roaming\Typora\typora-user-images\image-20220329121647162.png)]

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="mysqlImpl" class="com.blue.dao.UserDaoMysqlImpl"/>
    <bean id="oracleImpl" class="com.blue.dao.UserDaoOracleImpl"/>

    <bean id="UserServiceImpl" class="com.blue.service.UserServiceImpl">
        <property name="userDao" ref="mysqlImpl"/>
    </bean>

    <!--
        ref:引Spring容器中创建好的对象
        value：具体的值，基本数据类型，！
    -->

</beans>
```


![img](https://img-blog.csdnimg.cn/cb31cc91d1214a0a90aa0f8829a11011.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.dao;


import com.blue.service.UserServiceImpl;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   

        ApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");

        UserServiceImpl userServiceImpl = (UserServiceImpl) context.getBean("UserServiceImpl");
        userServiceImpl.getUser();
    }
}
```

结果


![img](https://img-blog.csdnimg.cn/00dbb31621b142eabc836eedc4f886d9.png)

调用换这里


![img](https://img-blog.csdnimg.cn/4c4a7e3f4b684e4ba21bfc6978fedefc.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/84fc87da52234a1ca207656860dde31f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)



IOC核心是工厂模式，AOP核心是代理模式 ![img](https://img-blog.csdnimg.cn/9774a4356e8c49f2a89bb01f54da94aa.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_16,color_FFFFFF,t_70,g_se,x_16)

### 1.使用无参构造创建对象，默认！


![img](https://img-blog.csdnimg.cn/6a9e144affe04e8fa3fd410dfdfe9ec3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.pojo;

public class User {
   
    private String name;

    public User() {
   
        System.out.println("User的无参参构造！");
    }

    public String getName() {
   
        return name;
    }

    public void setName(String name) {
   
        this.name = name;
    }
    public void show(){
   
        System.out.println("name="+name);
    }
}
```


![img](https://img-blog.csdnimg.cn/2b05a9d18c014a35af7a052c1be9194e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="user" class="com.blue.pojo.User">
        <property name="name" value="blue"/>
    </bean>

</beans>
```


![img](https://img-blog.csdnimg.cn/c22dfce93d0445d9b627974a3d64158d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
import com.blue.pojo.User;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");

        User user = (User) context.getBean("user");
        user.show();
    }
}
```

### 2.假设我们要使用有参构造创建对象。


![img](https://img-blog.csdnimg.cn/b03574c6305c4c2e8295599acb845451.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.pojo;

public class User {
   
    private String name;

    public User(String name) {
   
        this.name = name;
    }

    public String getName() {
   
        return name;
    }

    public void setName(String name) {
   
        this.name = name;
    }
    public void show(){
   
        System.out.println("name="+name);
    }
}
```

#### 1、下标赋值


![img](https://img-blog.csdnimg.cn/7e63252bf95b431dab69c6824a50ab3a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="user" class="com.blue.pojo.User">
        <constructor-arg index="0" value="blueJava"/>
    </bean>

</beans>
```


![img](https://img-blog.csdnimg.cn/e977a8819983442280524d7640bd5d72.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
import com.blue.pojo.User;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");

        User user = (User) context.getBean("user");
        user.show();
    }
}
```


![img](https://img-blog.csdnimg.cn/2f871a401460409b9fb4dae05d7decfc.png)

#### 2、类型


![img](https://img-blog.csdnimg.cn/dd39db48c7944fa2bbed53640ff536ba.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<bean id="user" class="com.blue.pojo.User">
        <constructor-arg type="java.lang.String" value="blue"/>
    </bean>
```


![img](https://img-blog.csdnimg.cn/7086fe20fe4d43cf9a68e34e0287a7fa.png)

#### 3、参数名


![img](https://img-blog.csdnimg.cn/8de9714915a24807b778451038d711aa.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<bean id="user" class="com.blue.pojo.User">
        <constructor-arg name="name" value="blue"/>
    </bean>
```

总结：在配置文件加载的时候，容器中管理的对象就已经初始化了！


## 5.1、别名


![img](https://img-blog.csdnimg.cn/c2f2fe75f475484b9084a5a285fb5fe8.png)

## 5.2、Bean的配置

>id : bean 的唯一标识符，也就是相当于我们学的对象名<br> cLass ：bean 对象所对应的全限定名 ：包名＋类<br> name ：也是别名,而且name可以同时取多个别名

**UserT.java**

```java
package com.blue.pojo;

public class UserT {
   
    private String name;

    public UserT() {
   
        System.out.println("UserT的无参参构造！");
    }

    public String getName() {
   
        return name;
    }

    public void setName(String name) {
   
        this.name = name;
    }
    public void show(){
   
        System.out.println("name="+name);
    }
}
```


**beans.xml** ![img](https://img-blog.csdnimg.cn/76d628c742b0476897dffd6e547e6940.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<bean id="userT" class="com.blue.pojo.UserT" name="user2">
        
    </bean>
```


**test** ![img](https://img-blog.csdnimg.cn/181c6c71f864419eacbf12b882479457.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
import com.blue.pojo.UserT;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");

        UserT user = (UserT) context.getBean("user2");
        user.show();
    }
}
```


结果 ![img](https://img-blog.csdnimg.cn/1c4ec9157ab147d98a9d095c89c46abf.png)


![img](https://img-blog.csdnimg.cn/7a806dab689f4bf5bb285293dd40c092.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/328b39e602964d519f7c15c8e074f68c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 5.3、import

这个import，一般用于团队开发使用，他可以将多个配置文件，导入合并为一个

假设，现在项目中有多个人开发，这三个人复制不同的类开发，不同的类需要注册在不同的bean中，我们可以利用import将所有人的beans.xml合并为一个总的

- 张三 
- 李四 
- 王五 
- applicationContext.xml


使用的时候，直接使用总的配置就可以了 ![img](https://img-blog.csdnimg.cn/d702209f228f4470b4879c254dcab64b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_18,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/59b6d70426d94daf94c8ee9561e765d0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <import resource="beans.xml"/>
    <import resource="beans2.xml"/>
    <import resource="beans3.xml"/>

</beans>
```

**test**

```java
import com.blue.pojo.UserT;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");

        UserT user = (UserT) context.getBean("u2");
        user.show();
    }
}
```



![img](https://img-blog.csdnimg.cn/d8eafd439cb64c569c1824630c618361.png)

## 6.1、构造器注入

前面已经说过了

## 6.2、Set方式注入【重点】

依赖注入：Set注入！

- 依赖：bean对象的创建依赖于容器！ 
- 注入： 上bean对象中的所有属性，由容器来注入！

### 【环境搭建】

1. 复杂类型


![img](https://img-blog.csdnimg.cn/d0a8f1fb4d6d452b874d3a5464b99bc0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
package com.blue.pojo;

public class Address {
   

    private String address;

    public String getAddress() {
   
        return address;
    }

    public void setAddress(String address) {
   
        this.address = address;
    }
}
```

1. 真实测试对象


![img](https://img-blog.csdnimg.cn/c54212deb2904dd4bb37ea69e19d9eb8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class Student {
   

    private String name;
    private Address address;
    private String[] books;
    private List<String> hobbies;
    private Map<String,String> card;
    private Set<String> games;
    private String wife;
    private Properties into;
```

1. beans.xml


![img](https://img-blog.csdnimg.cn/82de994afec440c095dde7e3e9a22cb1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="student" class="com.blue.pojo.Student">
        <!-- 第一种，普通注入,value  -->
        <property name="name" value="blue"/>
    </bean>
</beans>
```


1. MyTest ![img](https://img-blog.csdnimg.cn/0ba52cc2646a42d6936e1bd45e9f6018.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class MyTest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");
        Student student = (Student) context.getBean("student");
        System.out.println(student.getName());
    }
}
```


结果： ![img](https://img-blog.csdnimg.cn/4514d12dfc074c508b1c2d03b320fec2.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 其他方式


![img](https://img-blog.csdnimg.cn/4118804b7b054ea0bed96b85373ebc62.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)




![img](https://img-blog.csdnimg.cn/44ccf36b941f4a73a7197026898f4b2d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/2d01c0e8211746beb2d7328774f9c96a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) address+ ![img](https://img-blog.csdnimg.cn/e117cde41e334f2ab0fd2c1560cf0860.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)



结果： ![img](https://img-blog.csdnimg.cn/ec5ce22fde3e41c4847f1a3ad024a40b.png) ![img](https://img-blog.csdnimg.cn/98318b694d8b4fb99b2b6dc8bc50b0c6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 6.3、拓展方式注入



我们可以使用P命令空间和C命令空间进行注入 官方解释： ![img](https://img-blog.csdnimg.cn/a15cf6ece1564db3829ca8dd1844866c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/598e01c33fb14872ba5811fcd4797e3d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

注意点：p命名和c命名空间不能直接使用，需要导入xml约束！

```java
xmlns:p="http://www.springframework.org/schema/p"
xmlns:c="http://www.springframework.org/schema/c"
```

### 标签P

```java
xmlns:p="http://www.springframework.org/schema/p"
```


![img](https://img-blog.csdnimg.cn/69381501d3b34614b02dd0a003b0b3b5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/4f3ff29b6d304f13830bbf182ca66cab.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:p="http://www.springframework.org/schema/p"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="user" class="com.blue.pojo.User" p:name="blue" p:age="18"/>
    
</beans>
```



加配置 ![img](https://img-blog.csdnimg.cn/dbeafd5aacaa472d805bc2f6c5294200.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) test： ![img](https://img-blog.csdnimg.cn/a972e0f25ab94058991ad13a7022ec02.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class MyTest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("userbeans.xml");
        User user = context.getBean("user", User.class);
        System.out.println(user);
    }
}
```


结果： ![img](https://img-blog.csdnimg.cn/cc9c65bccf0e42c0b80520b7e0d13fd0.png)

### 标签C

```java
xmlns:c="http://www.springframework.org/schema/c"
```


![img](https://img-blog.csdnimg.cn/024c8c03a7314d7daba45991827a90d4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class User {
   
    private String name;
    private int age;

    public User() {
   
    }

    public User(String name, int age) {
   
        this.name = name;
        this.age = age;
    }
```


![img](https://img-blog.csdnimg.cn/c9e7b88090ac47b6ba2a5a2bff3404eb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<bean id="user" class="com.blue.pojo.User" p:name="blue" p:age="18"/>

 <bean id="user" class="com.blue.pojo.User" c:age="18" c:name="blue"/>
```


![img](https://img-blog.csdnimg.cn/c7b7bc7fe8dd4632bc397de7f77ddd7a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 6.4、bean的作用域



![img](https://img-blog.csdnimg.cn/6014c6e096cf442ba77e64095160f166.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_16,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/36855905f63e4e768d809c3e600be19d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 1.单例模式（Spring默认机制）重点



单线程用![img](https://img-blog.csdnimg.cn/ddb6d9f1e42f4b7fb634d52a892083fe.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/a7df3273891645fba592bf279e326862.png)

### 2. 原型模式：



多线程用 每次从容器中get的时候，都会产生一个新对象！ ![img](https://img-blog.csdnimg.cn/6ef3190d35f544e994ccf101d6f1237d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/d6ec2b6667604133825ee287d6ed7520.png)

### 3. 其余的

其余的 request、session、application、这些个只能在web开发中使用到!


- 自动装配是Spring满足bean依赖一种方式！ 
- Spring会在上下文中自动寻找，并自动给bean装配属性！

在Spring中有三种装配的方式

1. 在xml中显示的配置 
2. 在java中显示配置 
3. 隐式 的自动装配bean【重要】

## 7.1、测试

### 1.环境搭建：一个人有两个宠物！！


![img](https://img-blog.csdnimg.cn/1247f8e935ff4f0cb0e3edc20db1fbe6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_12,color_FFFFFF,t_70,g_se,x_16)


**cat** ![img](https://img-blog.csdnimg.cn/1e9395148875444c8c08b89b5253cff6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class Cat {
   
    public void shout(){
   
        System.out.println("miao~");
    }
}
```



**dog** ![img](https://img-blog.csdnimg.cn/957da82bd2e94bcb937354cdcbd78b3f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) **people** ![img](https://img-blog.csdnimg.cn/52a5d7a2ac4c4a50b98dbe75fe07b29f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class People {
   
    
    private Cat cat;
    private Dog dog;
    private String name;
}
```


beans ![img](https://img-blog.csdnimg.cn/1bbc4a28d31b43168624a8058a16e8e4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="cat" class="com.blue.pojo.Cat"/>
    <bean id="dog" class="com.blue.pojo.Dog"/>

    <bean id="people" class="com.blue.pojo.People">
        <property name="name" value="blue"/>
        <property name="cat" ref="cat"/>
        <property name="dog" ref="dog"/>
    </bean>
</beans>
```


![img](https://img-blog.csdnimg.cn/070a7b47e01a4e3588d9726f841e282a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class MyTest {
   
    @Test
    public void test1(){
   
        ApplicationContext context = new ClassPathXmlApplicationContext("beans.xml");

        People people = context.getBean("people", People.class);
        people.getCat().shout();
        people.getDog().shout();
    }
}
```

## 7.2、ByName自动装配


byName:根据属性名和id匹配， byType：根据属性的类型和class匹配 全局唯一 ![img](https://img-blog.csdnimg.cn/b48211f4978642b683a08f854f52b712.png)

## 7.3、ByType自动装配


![img](https://img-blog.csdnimg.cn/d045e1420f964946b1ca71e14c579e40.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 小结：

- byname的时候，需要保证所有bean的id唯一，并且这个bean需要和自动注入的属性的set方法的值一致! 
- byType的时候，需要保证所有bean的class唯一，并且这个bean需要和自动注入的属性的类型一致！

## 7.4、使用注解实现自动装配


jdk1.5支持的注解，Spring2.5就支持注解了！ The introduction of annotation-based configuration raised the question of whether this approach is "better"than XML. ![img](https://img-blog.csdnimg.cn/45e4f917a7e24d51926c30259e296b18.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_17,color_FFFFFF,t_70,g_se,x_16) 要使用注解须知： 1.导入约束 context约束 2. 配置注解的支持：<context:annotation-config/>

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context
        https://www.springframework.org/schema/context/spring-context.xsd">

    <context:annotation-config/>

</beans>
```

### @Autowired


直接在属性上使用即可!也可以在set方式上使用! 使用Autowired我们可以不用编写Set方法了，前提是你这个自动装配的属性在IOC（Spring）容器中存在，且符合名字byname！  @Autowired会先根据类型进行注入，如果容器中有多个满足类型的实例，就会根据ID进行注入。并不是单纯只根据类型注入 ![img](https://img-blog.csdnimg.cn/32344cf3324b43409f8e25bb7cd4f7f9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class People {

    @Autowired
    private Cat cat;
    @Autowired
    private Dog dog;
    private String name;
}
```

如果@Autowired自动装配的环境比较复杂，自动装配无法通过一个注解@Autowired完成的时候、我们可以使用@Qualifier(value = "XXX")去配置@Autowired的使用，指定一个唯一的bean对象注入！

### @Nullable

科普:

```java
@Nullable   字段标记了这个注解，说明这个字段可以为nu11；
```

源码：

```java
public @interface Autowired {
   
    boolean required() default true;
}
```


![img](https://img-blog.csdnimg.cn/bd8e90f804484776add84299443a96de.png)

```java
public class People {
   

    @Autowired
    @Qualifier(value = "cat22")
    private Cat cat;
    @Autowired
    private Dog dog;
    private String name;
 
}
```

### @Resource


![img](https://img-blog.csdnimg.cn/cc9f2258b8aa40c99ccf125d68951d59.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 小结

@Resource和@ Autowired的区别

- 都是用来自动装配的，都可以放在属性字段上 
- @Autowired通过byType的方式实现，而且必须要求这个对象存在【常用】 
- @Resource默认通过byname的方式实现，如果找不到名字，则通过byType实现！如果两个都找不到的情况下，就报错！【常用】 
- 不同：Autowired通过byType的方式实现；Resource默认通过byname的方式实现



在Spring4之后，要使用注解开发，必须要保证 aaop的包导入了 ![img](https://img-blog.csdnimg.cn/8a93244e0f044bc196e6c7afce315b51.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_18,color_FFFFFF,t_70,g_se,x_16) 使用注解需要导入context约束，增加注解的支持！

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context
       http://www.springframework.org/schema/context/spring-context.xsd
       http://www.springframework.org/schema/aop
       http://www.springframework.org/schema/conaoptext/spring-aop.xsd">

    <!-- 开启注解的支持-->
    <context:annotation-config/>

</beans>
```


模块 ![img](https://img-blog.csdnimg.cn/968868481dac410d9d5f5a50ac06df72.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_12,color_FFFFFF,t_70,g_se,x_16)

## 1.bean


**applicationContext** ![img](https://img-blog.csdnimg.cn/a80e8f394a9b400d8b6ad19125ee4f6a.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 2. 属性如何注入


**user** ![img](https://img-blog.csdnimg.cn/64594da7c6ad473aa2f780a11276d683.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
@Component
public class User {
   
    public String name = "blue";
}
```

### @Component

组件，放在类上，说明这个类被Spring管理了，就是bean！


**test** ![img](https://img-blog.csdnimg.cn/d20555f057654799bc1a5cb33b05db08.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class MyTest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        User user = context.getBean("user", User.class);
        System.out.println(user.name);

    }
}
```


去掉名字内容，测试结果为null ![img](https://img-blog.csdnimg.cn/1e75e83d3373454fb3d4382c38e24676.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### @Value



![img](https://img-blog.csdnimg.cn/e7ef7e5c1239430f85c20be785724a93.png) ![img](https://img-blog.csdnimg.cn/8b185d03135d4059a872987d963f8180.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 3. 衍生的注解

@Component 有几个衍生注解，我们在web开发中，会按mvc三层架构分层

- dao 【@Repository】 
- service 【Service】 
- controller 【@Controller】

这四个注解功能都是一样的，都是代表将某个类注册到Spring中，装配Bean.




![img](https://img-blog.csdnimg.cn/9a4425a7b2504d6e9bf6e7e314b23672.png) ![img](https://img-blog.csdnimg.cn/bb88135bf7ef44d7bace4c5ce100ab2e.png) ![img](https://img-blog.csdnimg.cn/15a7f742381e4b639a335ed6a11f4165.png)

## 4.自动装配置

```java
@Autowired：自动装配通过类型。名字
	如果Autowired不能唯一自动装配上属性，则需要通过@Qualifier（va1ue="xxx"）
@Nullable ：字段标记了这个注解，说明这个字段可以为null；
@Resource ：自动装配通过名字。类型。
```

当一个类Class A中需要一个B类型的变量时 在声明变量时加上这个注解 spring会在容器中寻找有没有

## 5.作用域


![img](https://img-blog.csdnimg.cn/eb64b4a90abc41dea13a01080b572da7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
@Component
@Scope("prototype")
public class User {
   
    public String name;

    @Value("blue2")
    public void setName(String name) {
   
        this.name = name;
    }
}
```

## 6.小结

**xml与注解：**

- xml更加万能，适用于任何场合！维护简单方便 
- 注解 不是自己类使用不了，维护相对复杂！

**xml与 注解最佳实践：**

- xml 用来管理bean； 
- 注解只负责完成属性的注入； 
- 我们在使用的过程中，只需要注意一个问题：必须让注解生效，就需要开启注解的支持

```java
<!-- 指定要扫描的包，这个包下的注解就会生效-->
    <context:component-scan base-package="com.blue"/>
    <context:annotation-config/>
```


我们现在要完全不使用Spring的xml配置了，全权交给Java来做！


JavaConfig是Spring的一个子项目，在Spring4之后，它成为了一个核心功能！ ![img](https://img-blog.csdnimg.cn/c8513fc48eb348a7a7c43922d8145b93.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

注意：

1. 如果开启包扫描，加载配置类以后就可以通过反射拿到配置类中的对象了， 
2. @Bean 可以用于通过方法获取数据库连接池Connection这种对象 
3. @Bean只写在方法上，返回的是一个对象，但一般不获取已经在容器中的对象


![img](https://img-blog.csdnimg.cn/b12619e38ff34e23956180ca3f9aaaad.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_11,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/d69ab394c4874fc0af7b4c247dc8cc57.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
@Component
public class User {
   
    private String name;

    public String getName() {
   
        return name;
    }

    @Value("blue111")
    public void setName(String name) {
   
        this.name = name;
    }

    @Override
    public String toString() {
   
        return "User{" +
                "name='" + name + '\'' +
                '}';
    }
}
```


![img](https://img-blog.csdnimg.cn/8d1b429d75fb4424a4adbd40c3ca2722.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
@Configuration
@ComponentScan("com.blue.pojo")
public class BlueConfig {
   
    
    @Bean
    public User getUser(){
   
        return new User();
    }
}
```


![img](https://img-blog.csdnimg.cn/4a36e92bc01b4ec0befa38cd7cfe65d6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

方法 使用@configuration声明配置类时，有两种方法来生成Bean

1. 在配置类中定义一个方法，并使用@Bean注解声明 
2. 在User类上用@Component注解，并在配置类上@ComponentScan(“User类的路径”)，这样会自动扫描，getBean的时候使用的id就是类名小写（user） 
3. 如果两种方法都使用，会建两个对象，@Component建立的对象用getBean(“user”)获取，配置类中@Bean声明的用getBean(“getUser”)获取，这两个对象是不同的

这种纯Java的配置方式，在SpringBoot中随处可见！


**为什么要学习代理模式？**

因为这就是SpringAOP的底层！【SpringAOP和SpringMVC】

**代理模式的分类：**

- 静态代理 
- 动态代理


![img](https://img-blog.csdnimg.cn/e5ab24bfaf4f4552b790756e752159c3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 10.1、静态代理

**角色分析：**

- **抽象角色**：一般会使用接口或者抽象类来解决 
- **真实角色**：被代理的角色 
- **代理角色**：代理真实角色，代理真实角色后，我们一般会做一些附属操作 
- **客户**：访问代理对象的人！

### 代码步骤：

1.接口 ——Rent 2.真实角色——Host 3.代理角色——Proxy 4.客户端访问代理角色——Client


![img](https://img-blog.csdnimg.cn/e7ec6e25714d4fe9a763430fdecc212f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_11,color_FFFFFF,t_70,g_se,x_16)

### 1、测试-无中介

#### 抽象角色


![img](https://img-blog.csdnimg.cn/bec6eff28197484db976e4615a981d03.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_16,color_FFFFFF,t_70,g_se,x_16)

#### 真实角色


![img](https://img-blog.csdnimg.cn/70f203aa88524f33b2b2a900f4444030.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

#### 客户


![img](https://img-blog.csdnimg.cn/ffb8f9880d41429197dbbc9fdf5fa579.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 2、有中介


![img](https://img-blog.csdnimg.cn/0e2d96ab7dcf45038831422a40a460b7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)



![img](https://img-blog.csdnimg.cn/e13665ba04314f3dba5fc58ce515b561.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/36ea97e133974a9591e267bf60442648.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 小结

**代理模式的好处：**

- 可以使真实角色的操作更加纯粹！不用去关注一些公共的业务 
- 公共也就就交给代理角色！实现了业务的分工！ 
- 公共业务发生扩展的时候，方便集中管理！

**缺点：**

- 一个真实角色就会产生一个代理角色；代码量会翻倍开发效率会变低

## 10.2、加深理解


代码：对应08-dmeo02; 聊聊AOP ![img](https://img-blog.csdnimg.cn/eba26b4fb76149f19247f46d9d9973e5.png) **UserService**

```java
public interface UserService {
   
    public void add();
    public void delete();
    public void update();
    public void query();
}
```

**UserServiceImpl——真实对象**

```java
//真实对象
public class UserServiceImpl implements UserService{
   
    @Override
    public void add() {
   
        System.out.println("增加了一个用户");
    }

    @Override
    public void delete() {
   
        System.out.println("删除了一个用户");
    }

    @Override
    public void update() {
   
        System.out.println("修改了一个用户");
    }

    @Override
    public void query() {
   
        System.out.println("查询了一个用户");
    }
}
```


**UserServiceProxy——代理** ![img](https://img-blog.csdnimg.cn/e9d9a777a9ea4c7bad8a91dcca18c355.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class UserServiceProxy implements UserService{
   

    private UserServiceImpl userService;

    public void setUserService(UserServiceImpl userService) {
   
        this.userService = userService;
    }

    @Override
    public void add() {
   
        log("add");
        userService.add();
    }

    @Override
    public void delete() {
   
        log("delete");
        userService.delete();
    }

    @Override
    public void update() {
   
        log("update");
        userService.update();
    }

    @Override
    public void query() {
   
        log("query");
        userService.query();
    }

    //日志方法
    public void log(String msg){
   
        System.out.println("使用了"+msg+"方法");
    }
}
```

**加粗样式**Client

```java
public class Client {
   
    public static void main(String[] args) {
   
        UserServiceImpl userService = new UserServiceImpl();
        UserServiceProxy proxy = new UserServiceProxy();
        proxy.setUserService(userService);
        proxy.add();
    }
}
```


**结果：** ![img](https://img-blog.csdnimg.cn/fc34fd12c9514837bf8d38b722800c4e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


![img](https://img-blog.csdnimg.cn/44c01bbcc011439faa5b6dd5db033801.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 10.3、动态代理

动态代理和静态代理角色一样 动态代理的代理类是动态生成的，不是我们直接写好的！

动态代理分为两大类：基于接口的动态代理，基于类的动态代理

- 基于接口-JDK 动态代理【我们在这里使用】 
- 基于：cglib 
- java字节码实现：javasist

需要了解两个类：

- **Proxy**：代理， 
- **InvocationHandler**：调用处理程序，是由代理实例的调用处理程序实现的接口。





![img](https://img-blog.csdnimg.cn/1b7a3fb912564d8ca64f33b44273c0bb.png) **ProxyInvocationHandler** ![img](https://img-blog.csdnimg.cn/bedd99cd2b834610a236b88b3e7005c0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/8ec7a7d545f34b39973965b2458d27bf.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) **Client** ![img](https://img-blog.csdnimg.cn/4f31bbe417b241b1879b5046bca4cb9c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

```java
public class Client {
   
    public static void main(String[] args) {
   
        //真实角色
        Host host = new Host();

        //代理角色：现在没有
        ProxyInvocationHandler pih = new ProxyInvocationHandler();
        //通过调用程序处理角色 来处理我们要调用的接口对象
        pih.setRent(host);
        Rent proxy = (Rent) pih.getProxy();
        proxy.rent();
    }
}
```

### demo04——真正动态

```java
public class ProxyInvocationHandler implements InvocationHandler {
   
    //被代理的接口
    private Object target;

    public void setTarget(Object target) {
   
        this.target = target;
    }

    //生成得到代理类
    public Object getProxy(){
   
        return Proxy.newProxyInstance(this.getClass().getClassLoader(), target.getClass().getInterfaces(),this);
    }

    //处理代理实例，返回结果
    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
   
        log(method.getName());
        Object result = method.invoke(target,args);
        return result;
    }

    public void log(String msg){
   
        System.out.println("执行了"+msg+"方法");

    }

}
```

```java
package com.blue.demo04;

import com.blue.demo02.UserService;
import com.blue.demo02.UserServiceImpl;

public class Client {
   
    public static void main(String[] args) {
   
        //真实角色
        UserServiceImpl userService = new UserServiceImpl();

        //代理角色：现在没有
        ProxyInvocationHandler pih = new ProxyInvocationHandler();
        pih.setTarget(userService);

        //通过调用程序处理角色 来处理我们要调用的接口对象
        UserService proxy = (UserService) pih.getProxy();

        proxy.delete();

    }

}
```


![img](https://img-blog.csdnimg.cn/db6001819aac4439852ef0e0282af954.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 动态代理的好处：

- 可以使真实角色的操作更加纯粹！不用去关注一些 
- 公共的业务公共也就就交给代理角色！实现了业务的分工！ 
- 公共业务发生扩展的时候，方便集中管理！ 
- 一个动态代理类代理的是一个接口，一般就是对应的一类业务 
- 一个动态代理类可以代理多个类，只要是实现了同一个接口即可


## 11.1、什么是AOP

AOP(Aspect Oriented Programming)意为：面向切面编程，通过预编译方式和运行期动态代理实现程序功能的统一维护的一种技术。AOP是OOP的延续，是软件开发中的一个热点，也是Sping框架中的一个重要内容，是函数式编程的一种衍生范型。利用AOP可以对业务逻辑的各个部分进行隔离，从而使得业务逻辑各部分之间的耦合度降低，提高程序的可重用性，同时提高了开发的效率。


![img](https://img-blog.csdnimg.cn/dbf89b5f598e4640ba3c501378c7abfc.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 11.2、Aop在Spring中的作用

提供声明式事务；允许用户自定义切面

- 横切关注点：跨越应用程序多个模块的方法或功能。即是，与我们业务逻辑无关的，但是我们需要关注的部分，就是横切关注点。如日志，安全，缓存，事务等等… 
- 切面(ASPECT)：横切关注点被模块化的特殊对象。即，它是一个类。 
- 通知(Advice)：切面必须要完成的工作。即，它是类中的一个方法。 
- 目标(Target)：被通知对象。 
- 代理(Poy)：向目标对象应用通知之后创建的对象。 
- 切入点(PointCut)：切面通知执行的"地点"的定义。连接点(JointPoint):与切入点匹配的执行点。


![img](https://img-blog.csdnimg.cn/f1f6cdc795b0447cbc0fd661d353b156.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) SpringAOP中，通过Advice定义横切逻辑，Spring中支持5种类型的Advice：


![img](https://img-blog.csdnimg.cn/66dd262dcea14542afbf5e00c0c9a6c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 11.3、使用Spring实现Aop

【重点】使用AOP织入，需要导入一依赖包！

```java
<dependencies>
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjweaver</artifactId>
            <version>1.9.4</version>
        </dependency>
    </dependencies>
```

### 模块


![img](https://img-blog.csdnimg.cn/a678c4152c8f4e508b26afcecb3bafef.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_12,color_FFFFFF,t_70,g_se,x_16)

**service**

```java
public interface UserService {
   
    public void add();
    public void delete();
    public void update();
    public void select();
}
```

```java
public class UserServiceImpl implements UserService{
   

    @Override
    public void add() {
   
        System.out.println("增加了一个用户");
    }

    @Override
    public void delete() {
   
        System.out.println("删除了一个用户");
    }

    @Override
    public void update() {
   
        System.out.println("更新了一个用户");
    }

    @Override
    public void select() {
   
        System.out.println("查询了一个用户");
    }
}
```

### 方式一——使用原生Spring API接口【主要SpringAPI接口实现】



![img](https://img-blog.csdnimg.cn/f6c8c9d815ae4aaa8a8aea5471c64b79.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/281e205e49ee4b5aa629a88996134ee7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

#### Spring配置——applicationContext.xml


![img](https://img-blog.csdnimg.cn/bd1f834263d64537b58c513a214f6687.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) **test**

```java
import com.blue.service.UserService;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class MyTest {
   
    public static void main(String[] args) {
   
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        //动态代理代理的是接口
        UserService userService = context.getBean("userService", UserService.class);
        
        userService.add();
    }
}
```

### 方式二——自定义类【主要是切面定义】

```java
public class DiyPointCut {
   
    public void before(){
   
        System.out.println("=============方法执行前===========");
    }

    public void after(){
   
        System.out.println("=============方法执行后===========");
    }
}
```

```java
<!-- 方式二：自定义类   -->
    <bean id="diy" class="com.blue.diy.DiyPointCut"/>

    <aop:config>
        <!--   自定义切面，ref 要因用的类     -->
        <aop:aspect ref="diy">
            <aop:pointcut id="point" expression="execution(* com.blue.service.UserServiceImpl.*(..))"/>
            <!--  通知  -->
            <aop:before method="before" pointcut-ref="point"/>
            <aop:before method="after" pointcut-ref="point"/>
        </aop:aspect>
    </aop:config>
```


**结果：** ![img](https://img-blog.csdnimg.cn/0cfa58a0df324f6f9c0c4839988e3a36.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 方式三：使用注解方式实现AOP

```java
<!--    方式三-->
    <bean id="annotationPointOut" class="com.blue.diy.AnnotationPointCut"/>
    <!--开启注解支持-->
    <aop:aspectj-autoproxy/>
```

**AnnotationPointCut**

```java
package com.blue.diy;

import org.aspectj.lang.ProceedingJoinPoint;
import org.aspectj.lang.annotation.After;
import org.aspectj.lang.annotation.Around;
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Before;

@Aspect
public class AnnotationPointCut {
   
    @Before("execution(* com.blue.service.UserServiceImpl.*(..))")
    public  void before(){
   
        System.out.println("=============方法执行前===========");
    }

    @After("execution(* com.blue.service.UserServiceImpl.*(..))")
    public void after(){
   
        System.out.println("=============方法执行后===========");
    }

}
```




扩展： ![img](https://img-blog.csdnimg.cn/bef8fb6f66de49089fae7fbadb256390.png) ![img](https://img-blog.csdnimg.cn/a209398e7692431ba0ca6bb73c7c5801.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/f6c37be53df0481e9228eb655dfc751c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


步骤：

1. 导入相关jar包

- junit 
- mybatis 
- mysql数据库 
- spring相关的 
- aop织入 
- mybatis-.spring【new】

junit

```java
<dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>5.1.47</version>
        </dependency>
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>3.5.2</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>5.3.16</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>5.3.16</version>
        </dependency>
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjweaver</artifactId>
            <version>1.8.14</version>
        </dependency>
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
            <version>2.0.2</version>
        </dependency>
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.20</version>
        </dependency>

    </dependencies>
```

```java
<!--在build中配置resources,来防止我们资源导出失败的问题-->
    <build>
    <resources>
        <resource>
            <directory>src/main/resources</directory>
            <excludes>
                <exclude>**/*.properties</exclude>
                <exclude>**/*.xml</exclude>
            </excludes>
            <filtering>false</filtering>
        </resource>
        <resource>
            <directory>src/main/java</directory>
            <includes>
                <include>**/*.properties</include>
                <include>**/*.xml</include>
            </includes>
            <filtering>false</filtering>
        </resource>
    </resources>
    </build>
```

1. 编写配置文件 
2. 测试

## 12.1、回忆mybatis


![img](https://img-blog.csdnimg.cn/370a33135a904a299ed890d83bc791fe.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_12,color_FFFFFF,t_70,g_se,x_16)

### 1.编写实体类

```java
package com.blue.pojo;

import lombok.Data;

@Data
public class User {
   
    private int id;
    private String name;
    private String pwd;
}
```

### 2.编写核心配置文件

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">

<configuration>
    
    <typeAliases>
        <package name="com.blue.pojo"/>
    </typeAliases>
    
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT&amp;useUnicode=true&amp;characterEncoding=utf8&amp;useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="123456"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <mapper class="com.blue.mapper.UserMapper"/>
    </mappers>
</configuration>
```

### 3.编写接口

```java
package com.blue.mapper;

import com.blue.pojo.User;

import java.util.List;

public interface UserMapper {
    public List<User> selectUser();
}
```

### 4.编写Mapper.Xml

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="com.blue.dao.UserMapper">

    <select id="selectUser" resultType="com.blue.pojo.User">
        select * from mybatis.user
    </select>
    
</mapper>
```

### 5.测试

```java
import com.blue.mapper.UserMapper;
import com.blue.pojo.User;
import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;
import org.junit.Test;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

import static java.lang.System.in;

public class MyTest {
   

    @Test
    public void test() throws IOException {
   
        String resources = "mybatis-config.xml";
        InputStream in = Resources.getResourceAsStream(resources);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(in);
        SqlSession sqlSession = sqlSessionFactory.openSession(true);

        UserMapper mapper = sqlSession.getMapper(UserMapper.class);
        List<User> userList = mapper.selectUser();
        for (User user : userList) {
   
            System.out.println(user);
        }

        sqlSession.close();
    }
}
```



结果： ![img](https://img-blog.csdnimg.cn/400b71964e904dfb80b0707cbdda5f94.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) ![img](https://img-blog.csdnimg.cn/c212e7c872a54299ba6621a476969c13.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

## 12.2、Mybatis-spring

### 第一种方法


![img](https://img-blog.csdnimg.cn/ddd6226673f040bf811b0c0253025355.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_13,color_FFFFFF,t_70,g_se,x_16)

**spring-dao.xml**

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context
       http://www.springframework.org/schema/context/spring-context.xsd
       http://www.springframework.org/schema/aop
       http://www.springframework.org/schema/conaoptext/spring-aop.xsd">

    <!-- DataSource:使用 Spring的数据源 Mybatis的配置 c3p0 dbcp druid
    我们这里使 Spring 提供的 JDBC:org.springframework.jdbc.datasource
    -->
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT&amp;useUnicode=true&amp;characterEncoding=utf-8&amp;useSSL=false"/>
        <property name="username" value="root"/>
        <property name="password" value="123456"/>
    </bean>

    <!-- sqLSessionFactory-->
    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
    <!--  绑定Mybatis配置文件 -->
        <property name="dataSource" ref="dataSource"/>
        <property name="configLocation" value="classpath:mybatis-config.xml"/>
        <property name="mapperLocations" value="classpath*:com/blue/mapper/*.xml"/>
    </bean>

    <!--  SqLSessionTempLate:威是我M们使用sqLSession  -->
    <bean id="sqlSession" class="org.mybatis.spring.SqlSessionTemplate">
        <constructor-arg index="0" ref="sqlSessionFactory"/>
    </bean>

    <bean id="userMapper" class="com.blue.mapper.UserMapperImpl">
        <property name="sqlSession" ref="sqlSession"/>
    </bean>

</beans>
```

**UserMapperImpl**

```java
public class UserMapperImpl implements UserMapper{
   
    
    // 我们所有的操作，都使用sqlSession来执行，在原来，现在使用SqlSessionTemplate;
    private SqlSessionTemplate sqlSession;

    public void setSqlSession(SqlSessionTemplate sqlSession) {
   
        this.sqlSession = sqlSession;
    }

    @Override
    public List<User> selectUser() {
   
        UserMapper mapper = sqlSession.getMapper(UserMapper.class);
        return mapper.selectUser();
    }
}
```

**MyTest**

```java
public class MyTest {
   
    @Test
    public void test(){
   
        ApplicationContext context = new ClassPathXmlApplicationContext("spring_dao.xml");
        UserMapper userMapper = context.getBean("userMapper", UserMapper.class);

        for (User user : userMapper.selectUser()) {
   
            System.out.println(user);
        }
    }

}
```

结果：


![img](https://img-blog.csdnimg.cn/053f01f5c20143878f9e841c51fdbe2c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_19,color_FFFFFF,t_70,g_se,x_16)

### 第二种方法


![img](https://img-blog.csdnimg.cn/c16e9e740df344f688abc5f4f4c5f542.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_14,color_FFFFFF,t_70,g_se,x_16) **UserMapperImpl2**

```java
package com.blue.mapper;

import com.blue.pojo.User;
import org.mybatis.spring.support.SqlSessionDaoSupport;

import java.util.List;

public class UserMapperImpl2 extends SqlSessionDaoSupport implements UserMapper{
   

    @Override
    public List<User> selectUser() {
   
        return getSqlSession().getMapper(UserMapper.class).selectUser();
    }
}
```

**applicationContext.xml**

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context
       http://www.springframework.org/schema/context/spring-context.xsd
       http://www.springframework.org/schema/aop
       http://www.springframework.org/schema/conaoptext/spring-aop.xsd">

    <import resource="spring_dao.xml"/>
    
    <bean id="userMapper" class="com.blue.mapper.UserMapperImpl">
        <property name="sqlSession" ref="sqlSession"/>
    </bean>
    
    <bean id="userMapper2" class="com.blue.mapper.UserMapperImpl2">
        <property name="sqlSessionFactory" ref="sqlSessionFactory"/>
    </bean>

</beans>
```

```java
public class MyTest {
   
    @Test
    public void test(){
   
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        UserMapper userMapper = context.getBean("userMapper2", UserMapper.class);

        for (User user : userMapper.selectUser()) {
   
            System.out.println(user);
        }
    }

}
```


**结果：**![img](https://img-blog.csdnimg.cn/c3f263af5ab74c95be29cd98474af17e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)


**顺序：**![img](https://img-blog.csdnimg.cn/256d1900f62d415da7d9221823364356.png)


## 13.1、回顾事务

- 把一组业务当成一个业务来做；要么都成功，要么都失败！ 
- 事务在项目开发中，十分的重要，涉及到数据的一致性问题，不能马虎！ 
- 确保完整性和一致性；

**事务ACID原则：**

- 原子性 
- 一致性 
- 隔离性：多个业务可能操作同一个资源，防止数据损坏 
- 持久性：事务一旦提交，无论系统发生什么问题，结果都不会再被影响，被持久化的写到存储器中！

### spring-11-transaction


![img](https://img-blog.csdnimg.cn/896ec22cabcd4526a37be01aa845df19.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_13,color_FFFFFF,t_70,g_se,x_16) **粘过来** User、UserMapper、UserMapper.xml、UserMapperImpl、mybatis-config.xml、spring_dao.xml、applicationContext.xml


![img](https://img-blog.csdnimg.cn/7d9631f05b464447a371fafaa5de5331.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16) **UserMapperImpl**

```java
package com.blue.mapper;

import com.blue.pojo.User;
import org.mybatis.spring.SqlSessionTemplate;
import org.mybatis.spring.support.SqlSessionDaoSupport;

import java.util.List;

public class UserMapperImpl extends SqlSessionDaoSupport implements UserMapper{
   

    // 我们所有的操作，都使用sqlSession来执行，在原来，现在使用SqlSessionTemplate;
    @Override
    public List<User> selectUser() {
   
        UserMapper mapper = getSqlSession().getMapper(UserMapper.class);
        return mapper.selectUser();
    }
}
```

**applicationContext.xml**

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context
       http://www.springframework.org/schema/context/spring-context.xsd
       http://www.springframework.org/schema/aop
       http://www.springframework.org/schema/conaoptext/spring-aop.xsd">

    <import resource="spring_dao.xml"/>

    <bean id="userMapper" class="com.blue.mapper.UserMapperImpl">
        <property name="sqlSessionFactory" ref="sqlSessionFactory"/>
    </bean>


</beans>
```

**Mytest**

```java
public class Mytest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        UserMapper userMapper = context.getBean("userMapper", UserMapper.class);
        for (User user : userMapper.selectUser()) {
   
            System.out.println(user);
        }

    }
}
```

**结果：**


![img](https://img-blog.csdnimg.cn/7aa9caf93d55482cb6e98ab225213586.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_20,color_FFFFFF,t_70,g_se,x_16)

### 

**UserMapper 接口**

```java
public interface UserMapper {
   
    public List<User> selectUser();

    //添加一个用户
    public int addUser(User user);

    // 删除一个用户
    public int deleteUser(int id);
}
```

**User——主体**

```java
@Data
@AllArgsConstructor
@NoArgsConstructor
public class User {
   
    private int id;
    private String name;
    private String pwd;
}
```

**UserMapperImpl——实现方法**

```java
public class UserMapperImpl extends SqlSessionDaoSupport implements UserMapper{
   

    // 我们所有的操作，都使用sqlSession来执行，在原来，现在使用SqlSessionTemplate;
    @Override
    public List<User> selectUser() {
   
        User user = new User(5, "blue", "121334");
        UserMapper mapper = getSqlSession().getMapper(UserMapper.class);
        
        mapper.addUser(user);
        mapper.deleteUser(5);
        
        return mapper.selectUser();
    }

    @Override
    public int addUser(User user) {
   
        return getSqlSession().getMapper(UserMapper.class).addUser(user);
    }

    @Override
    public int deleteUser(int id) {
   
        return getSqlSession().getMapper(UserMapper.class).deleteUser(id);
    }
}
```

**UserMapper.xml——配置**

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<!--configuration核心配置文件-->
<mapper namespace="com.blue.mapper.UserMapper">

    <select id="selectUser" resultType="user">
        select * from mybatis.user;
    </select>

    <insert id="addUser" parameterType="user">
        insert into mybatis.user (id, name, pwd) values (#{id},#{name},#{pwd});
    </insert>

    <delete id="deleteUser" parameterType="int">
        delete from mybatis.user where id=#{id}
    </delete>

</mapper>
```

**Mytest**

```java
public class Mytest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        UserMapper userMapper = context.getBean("userMapper", UserMapper.class);
        for (User user : userMapper.selectUser()) {
   
            System.out.println(user);
        }

    }
}
```


**结果：** ![img](https://img-blog.csdnimg.cn/8737ae84b283470daafa792ab6e71f88.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_18,color_FFFFFF,t_70,g_se,x_16)

## 13.2、spring中的事务管理

- 声明式事务：AOP 
- 编程式事务：需要再代码中，进行事务的管理

### spring_dao.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/tx
       http://www.springframework.org/schema/tx/spring-tx.xsd
       http://www.springframework.org/schema/aop
       http://www.springframework.org/schema/aop/spring-aop.xsd">

    <!-- DataSource:使用 Spring的数据源 Mybatis的配置 c3p0 dbcp druid
    我们这里使 Spring 提供的 JDBC:org.springframework.jdbc.datasource
    -->
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT&amp;useUnicode=true&amp;characterEncoding=utf-8&amp;useSSL=false"/>
        <property name="username" value="root"/>
        <property name="password" value="123456"/>
    </bean>

    <!-- sqLSessionFactory-->
    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <!-- 绑定Mybatis配置文件 -->
        <property name="dataSource" ref="dataSource"/>
        <property name="configLocation" value="classpath:mybatis-config.xml"/>
        <property name="mapperLocations" value="classpath*:com/blue/mapper/*.xml"/>
    </bean>

    <!--  SqLSessionTempLate:威是我M们使用sqLSession  -->
    <bean id="sqlSession" class="org.mybatis.spring.SqlSessionTemplate">
        <constructor-arg index="0" ref="sqlSessionFactory"/>
    </bean>

<!--    <bean id="userMapper" class="com.blue.mapper.UserMapperImpl">-->
<!--        <property name="sqlSession" ref="sqlSession"/>-->
<!--    </bean>-->
    <!-- 配置声明事务   -->
    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>
    <!--  结合AOP实现事务的织入  -->
    <!-- 配置事务通知 -->
    <tx:advice id="txAdvice" transaction-manager="transactionManager">
        <tx:attributes>
            <tx:method name="add" propagation="REQUIRED"/>
            <tx:method name="delete" propagation="REQUIRED"/>
            <tx:method name="update" propagation="REQUIRED"/>
            <tx:method name="query" read-only="true"/>
            <tx:method name="*" propagation="REQUIRED"/>
        </tx:attributes>
    </tx:advice>

    <!--  配置事务切入  -->
    <aop:config>
        <aop:pointcut id="txPointCut" expression="execution(* com.blue.mapper.*.*(..))"/>
        <aop:advisor advice-ref="txAdvice" pointcut-ref="txPointCut"/>
    </aop:config>

</beans>
```

**Mytest**

```java
public class Mytest {
   
    public static void main(String[] args) {
   
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        UserMapper userMapper = context.getBean("userMapper", UserMapper.class);
        List<User> userList = userMapper.selectUser();

        for (User user : userList) {
   
            System.out.println(user);
        }

    }
}
```

**思考：为什么需要事务？**

- 如果不配置事务，可能存在数据提交不一致的情况下； 
- 如果我们不在SPRING中去配置声明式事务，我们就需要在代码中手动配置事务！ 
- 事务在项目的开发中十分重要，设计到数据的一致性和完整性问题，不容马虎！




重点掌握，最好可以用java写 ![img](https://img-blog.csdnimg.cn/21c6ccfa4f60419b99e5b7c9283ce00d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBALUJsdWUu,size_11,color_FFFFFF,t_70,g_se,x_16) **动态代理：反射** ![img](https://img-blog.csdnimg.cn/38a394cb74f24903bcd842e525a7d8b9.png)

