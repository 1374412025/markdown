[TOC]

# 1、MySQL

JavaEE:企业级java开发，weib
前端（页面：展示，数据！）
后台（连接点：链接数据库JDBC，链接前端(控制，控制视图跳转，给前端传递数据)
数据库（存数据，Txt，Excel，word）

> 操作系统，数据
>
> 
>
> 结构与算法

数据库是所有软件系统中最核心的存在DBA

## 1.1、数据库分类

**关系型数据库（SQL）**

- MySQL，Oracle，Sql Server，DB2，SQLite
- 通过表和表之间，行和列之间的关系进行数据存储，学院信息表...

**非关系数据库（NoSQL）**

- Redis、MongDB
- 非关系数据库，对象存储，通过对象的自身的属性来决定

**DBMS（数据库管理系统）**

- 数据库管理啥软件，科学有效的管理我们的数据。维护和获取数据
- MySQL、数据库管理系统

## 1.2、MySQL简介

**关系型数据库管理系统**、
前世：瑞典MySQL AB公司
今生：属于Oracle旗下产品
**MySQL是最好的 RDBMS(Relational Database Management System**应用软件之一、开软的数据库软件
体积小、速度快、总体拥有成本低，招人成本低，
中小型网站、或者大型网站，集群！
**官网：[https://www.mysql.com](https://www.mysql.com/)**
**官网下载地址：[https://dev.mysql.com/downloads/mysql/5.7.html](https://dev.mysql.com/downloads/mysql/5.7.html)**

安装建议: 尽量**不要使用exe**,会走注册表（win+R--regedit--HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL
用压缩包

## 1.3、MySQL安装

1. 下载ZIP文件

2. 解压放在环境目录下`D:\language_envir`

3. 添加环境变量
  
- 在环境变量--系统环境变量--Path中新增刚解压文件的bin路径
     `D:\language_envir\Mysql\mysql-5.7.40\bin`
   
- 在`D:\language_envir\Mysql\mysql-5.7.40`下新建`my.ini`配置文件,内容如下

```java
[mysqld]
#设置3306端口
port = 3306 
# 设置mysql的安装目录
basedir=D:\language_envir\Mysql\mysql-5.7.40\
# 设置mysql数据库的数据的存放目录
datadir=D:\language_envir\Mysql\mysql-5.7.40\data\
#跳过密码验证
skip-grant-tables
```
- **启动管理员模式下的CMD**,**切换到bin目录**
  **`cd /d D:\language_envir\Mysql\mysql-5.7.40\bin`**
  - **安装mysql服务**：输入 `mysqld -install`，返回`Service successfully installed.``
  - **初始化数据文件**：再输入 `mysqld --initialize-insecure --user=mysql`。查看目录，发现base文件夹建好，为初始数据库
  - **启动mysql**：输入`net start mysql`   启动成功，
    用命令 `mysql -u root -p` ，不输入密码直接回车，进入
  - **修改密码**：`update mysql.user set authentication_string=password('123456') where user='root' and Host='localhost';` 
  - **刷新权限**：`flush privileges;`
  
- **重新修改**·ini·配置文件，注解掉skip.
- **重启mysql服务**:  cmd中`exit`或者`ctrl+z，回车`退出mysql
  - `net stop mysql`
  - `net start mysql`
- **重新进入mysql**
  - `mysql -u root -p`,在输入密码
  - 或者`mysql -u root -p密码`

## 1.4、SQLyog安装

sqlyog可视化操作软件

下载地址：[https://github.com/webyog/sqlyog-community/wiki/Downloads](https://github.com/webyog/sqlyog-community/wiki/Downloads)

打开安装包，一直下一步(中途可以设置安装路径)
运行程序，**选择语言，点击新建**

<img src="https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557896.png" alt="新建" style="zoom:80%;" />

**然后启动服务**
![启动服务](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557715.png)

**输入用户名和密码**
![用户名](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557011.png)

**进入界面完成**

## 1.5、SQLyog使用

​	1、**创建数据库school**，右击左边目录创建数据库
![创建数据库](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557632.png)

```sql
CREATE DATABASE `school`CHARACTER SET utf8 COLLATE utf8_general_ci; 
//每一个sqlyog操作，本质上对应了一个sql语句，历史记录可见
```

2、**创建一张表student**

> 字段：id，name，age

<img src="https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557429.png" alt="创建表" style="zoom:100%;" />

```sql
CREATE TABLE `school`.`student` ( `id` INT(10) NOT NULL COMMENT '学员id', `name` VARCHAR(100) NOT NULL COMMENT '学员姓名', `age` INT(3) NOT NULL COMMENT '学员年龄', PRIMARY KEY (`id`) ) ENGINE=INNODB CHARSET=utf8 COLLATE=utf8_general_ci; 
```

3、 **查看表**
目录右击表，打开表，可以直接在null处添加，添加后点击右侧工具栏刷新，保存修改
<img src="https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557492.png" style="zoom:80%;" />

勾选后可以删掉

## 1.6、链接数据库

命令行连接

```mysql
mysql -u 用户名 -p 密码	-- 连接数据库
mysql -u root -p 123456

-- 修改密码
update mysql.user set authentication_string=password('123456') where user='root' and Host='localhost';

-- 刷新权限
flush privileges;
-----------------------------------------------------------------------
-- 所有的语句都以  ;  结尾
mysql> -- 以下为SQL语句

show databases;-- 查看所有数据库	show databases/tables;

use school; -- 切换数据库	 use 数据库名
Database changed --返回

show tables; -- 查看该数据库中所有表

describe student; -- 查看表中数据 	describe 表名

create database westos; -- 创建一个数据库

exit; -- 退出连接

-- 注释(SQL的本身注释)
/*注释内容(SQL的多行注释)
多行注释内容	
*/

```

数据库XXX语言(CRUD增删改查！)CV程序员 API程序员 CRUD程序员
DDL	定义
DML	操作
DQL	查询	--核心
DCL	控制

# 2、操作数据库

**操作数据库  >  操作数据库中的表 >  操作数据库中表的数据**

==mysql关键字不区分大小写==

## 2.1、操作数据库

SQL语句以	`;`	开始和结束

1、 创建数据库

```mysql
CREATE DATABASE [IF NOT EXISTS] 数据库名字;
```

2、删除数据库

```mysql
DROP DATABASE [IF EXISTS] 数据库名字;
-- 同理删除表
```

3、使用数据库

```mysql
-- tab 键上面，如果你的表名或者字段名是一个特殊字符，就需要``
USE `数据库名字`;
```

4、查看数据库

```mysql
SHOW DATABASES --查看所有数据库
```

记住关键字	

## 2.2、数据库的列的数据类型

> 数值	

- tinyint	十分小的数据	    1Byte 	-127\~127（unsigned后0\~256)th 
- smallint 	较小的数据  	  2Byte
- mediumint 	中小等数据   3Byte
- **int				标准的整数     4Byte**      常用的    int
- bigint		较大的数据 	  8Byte
- float			浮点数    		4Byte
- **double**    	浮点数    		8Byte(精度问题)
- decimal		**字符串形式的浮点数**	金融计算的时候一般使用decimal

> 字符串	
>
> \

- char			字符串固定大小的	0~255
- **varchar		可变字符串				0~65535	常用的变量  String**
- tinytext		微型文本					2^8~1
- **text				文本							2^16~1		保存大文本	**

> 时间日期

java.util.Date

- date		YYYY-MM-DD,日期格式
- time 		HH:	mm:	ss ，时间格式
- **datatime   YYYY-MM-DD	HH:mm:ss 最常用的时间格式**      
- **timestamp    时间戳   utc的格式，检索时区并转换，1970.1.1到现在的毫秒!**   
- year    年份表示 

[timestamp和datatime区别](https://cloud.tencent.com/developer/article/1541699)

| 类型      | 占据字节 | 表示形式            | 范围                                                         | 时区                                                         | 默认     |
| --------- | -------- | ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------- |
| datatime  | 8Byte    | yyyy-mm-dd hh:mm:ss | '1000-01-01 00:00:00.000000' to '9999-12-31 23:59:59.999999' | 不会进行时区的检索.存什么拿到的就是什么。                    | NULL     |
| timestemp | 4Byte    | yyyy-mm-dd hh:mm:ss | '1970-01-01 00:00:01.000000' to '2038-01-19 03:14:07.999999' | 以utc的格式储存， 它会自动检索当前时区并进行转换。如果储存时的时区和检索时的时区不一样，那么拿出来的数据也不一样。 | 当前时间 |

timestamp翻译为汉语即"时间戳"，它是当前时间到 Unix元年(1970 年 1 月 1 日 0 时 0 分 0 秒)的秒数。对于某些时间的计算，如果是以 datetime 的形式会比较困难，假如我是 1994-1-20 06:06:06 出生，现在的时间是 2016-10-1 20:04:50 ，那么要计算我活了多少秒钟用 datetime 还需要函数进行转换，但是 timestamp 直接相减就行。

> null

- 没有值,未知
- ==注意，不要使用

## 2.3、==数据库的字段属性==

==**Unsigned**==

- 无符号的整数
- 声明了该列不能声明为负数

==**zerofill**==

- 0填充的
- 不足的位数、使用0来填充，int(3),5-----005

==**自增**==		**auto-increment**

- 通常理解为自增，自动在上一条记录的基础上+1(默认)
- 通常用来设计唯一的主键——index，必须是整数类型
- 可以自定义设计主键自增的起始值和步长

==**非空**==	not null	null

- 假设设置为not null ，如果不赋值，会报错
- 假设设置为Null，如果不填值，默认就是null

==**默认**==

- 设置默认的值！
- sex，默认值为男，如果不指定该列的值，则会默认男

```java
/*每一个表都必须存在以下五个字段，表示一个记录存在的意义
id			主键
`version`	乐观锁
is_delete	伪删除
gmt_create 创建时间
gmt_update 修改时间
*/
```

## ==2.4、创建表==

**格式**

```sql
-- 英文 () , `` '' ;五种符号
-- auto_increment自增   comment '注释'   primary key(`主键`) default '默认'
CREATE TABLE [IF NOT EXISTS] `表名`(
	`字段名` 列的类型 [属性] [索引] [注释],
    `字段名` 列的类型 [属性] [索引] [注释],
    ...
    `字段名` 列的类型 [属性] [索引] [注释]
)[表类型] [字符集设置] [注释];
```

```sql
DROP TABLE IF EXISTS `school`.`student`;
CREATE TABLE IF NOT EXISTS `student`(
   `id` INT(4) NOT NULL AUTO_INCREMENT COMMENT '学号',
   `name` VARCHAR(30) NOT NULL DEFAULT '匿名' COMMENT '姓名',
   `pwd` VARCHAR(20) NOT NULL DEFAULT '123456' COMMENT '密码',
   `sex` VARCHAR(2) NOT NULL DEFAULT '女' COMMENT '性别',
   `birthday` DATETIME NOT NULL COMMENT '出生日期',
   `address` VARCHAR(100) DEFAULT NULL COMMENT '家庭住址',
   `email` VARCHAR(50) DEFAULT NULL COMMENT '邮箱',
   PRIMARY KEY (`id`) -- 主键
	
)ENGINE=INNODB DEFAULT CHARSET=utf8 COLLATE=utf8_general_ci; 
```

**常用命令**

```sql
-- 查看创建数据库的语句
SHOW CREATE DATABASE  `表名字`;
-- 查看创建表的语句
SHOW CREATE TABLE  `表名字`;
 -- 显示表的结构
DESC student;
-- 删除表
DROP TABLE [IF EXISTS] `表名字`;
```

## 2.5、表的类型

INNODB				MYISAM	
ARCHIVE 	BLACKHOLD	CSV	MEMORY

|              | MYISAM | INNODB        |
| ------------ | ------ | ------------- |
| 事务支持     | 不支持 | 支持          |
| 数据行锁定   | 不支持 | 支持          |
| 外键约束     | 不支持 | 支持          |
| 全文索引     | 支持   | 不支持        |
| 表空间的大小 | 较小   | 较大，约为2倍 |

常规使用操作

- MYISAM  节约空间，速度较快
- INNODB  安全性高，事务的处理，多表多用户操作



> **数据在物理空间存在的位置**

所有的数据库文件都在`data`目录下，一个文件夹对于一个数据库
本质还是文件的存储！



> **MySQL引擎在物理文件上的出区别**

- **INNODB**  在数据库表中只有一个`*.frm`文件、以及上级目录下的`ibdata1`文件

- **MYISAM**对于文件

  - `*.frm`     表结构的定义文件
  - `*.MYD`     数据文件(data)
  - `*.MYI`     索引文件(index)

  

> **设置数据库表的字符集编码**

- 建表尾部`CHARSET=utf8`不设置的话，会使mysql的默认字符集编码`Latin1`(不支持中文)
- 或者在`my.ini`中配置默认编码`character-set-server=utf8`

## ==2.6、修改表==

> **修改**

```sql
-- 修改表名 
-- ALTER TABLE 旧表名 RENAME AS 新表名
ALTER TABLE teacher RENAME as tercher1

-- 增加表的字段 
-- ALTER TABLE 表名 ADD 字段名 列属性
ALTER TABLE teacher1 ADD age INT(11)

-- 修改表的字段 (修改字段类型和约束！)
-- ALTER TABLE 表名 MODIFY 字段名 列属性[]
ALTER TABLE teacher1 MODIFY age VARCHAR(11)

-- 修改表的字段 (重命名)
-- ALTER TABLE 表名 CHANGE 字段旧名字 新名字 列属性[]
ALTER TABLE teacher1 CHANGE age age1 INT(10)

-- 删除表的字段
-- ALTER TABLE 表名 DROP 字段名
ALTER TABLE teacher1 DROP age1
```

> **删除**

```sql
-- DROP TABLE [IF EXISTS] 表名
DROP TABLE IF EXISTS teacher1;
```

==创建和删除操作加上判断，以免报错==

**注意点:**

- **`` 字段名，包裹**
- **注释 --  /**/**
- **sql关键字大小写不明感,建议写小写**
- **所有符号用有英文**

# 3、 MySQL数据管理

## 3.1、 外键（了解）

约束constraint

> 方式一、在创建表的时候，增加约束

```sql
-- 学生表的gradeid 字段 引用年级表的gradeid字段
-- 定义外键key
-- 给这个外键添加约束(执行引用)  references 引用

CREATE TABLE `grade`(
    `gradeid` INT(10) NOT NULL AUTO_INCREMENT COMMENT '年级',
    `gradename` VARCHAR(50) NOT NULL COMMENT '年级名称',
    PRIMARY KEY(`gradeid`)
    
)ENGINE=INNODB DEFAULT CHARSET=utf8

CREATE TABLE IF NOT EXISTS `student`(
   `id` INT(4) NOT NULL AUTO_INCREMENT COMMENT '学号',
   `name` VARCHAR(30) NOT NULL DEFAULT '匿名' COMMENT '姓名',
   `pwd` VARCHAR(20) NOT NULL DEFAULT '123456' COMMENT '密码',
   `sex` VARCHAR(2) NOT NULL DEFAULT '女' COMMENT '性别',
   `birthday` DATETIME NOT NULL COMMENT '出生日期',
   `gradeid` INT(10) NOT NULL COMMENT '学生的年级',
   `address` VARCHAR(100) DEFAULT NULL COMMENT '家庭住址',
   `email` VARCHAR(50) DEFAULT NULL COMMENT '邮箱',
   PRIMARY KEY (`id`), 			-- 主键
    
   KEY `FK_gradeid`(`gradeid`),
   CONSTRAINT `FK_gradeid` FOREIGN KEY (`gradeid`) REFERENCES `grade`(`gradeid`)

)ENGINE=INNODB DEFAULT CHARSET=utf8
```

**==删除有外键关系的表时候，必须要先删除引用别人的表(从表），再删除被引用的表(主表).==**

> 方式二	创建表后、添加外键约束

```sql
ALTER TABLE `表名` 
ADD CONSTRAINT `约束名` FOREIGN KEY(`作为外键的列`) REFERENCES `主表`(`主表的那个键`);

ALTER TABLE `studentw` 
ADD CONSTRAINT `FK_gradeid` FOREIGN KEY(`gradeid`) REFERENCES `grade`(`gradeid`);
```

以上的操作都是

## ==3.2 、DML语言==

数据库意义：数据存储，数据管理
DML 语言，数据操作语言，

- insert
- delete
- update

----


### 添加	INSERT 

**字段和值	一一对应**

**语法:**

```sql
insert into `表名`([`字段名1`,`字段2`,`字段3`]) values ('值1'，'值2','值3'，...)

-- 插入多个字段
INSERT INTO `student`(`name`,`pwd`,`sex`) VALUES('李四',123,'男'),('王五',123,'女');
```

**注意事项：**

1. **字段和字段之间使用英文逗号隔开`,`，**
2. **字段可以省略，但是后面的值要一一对应不能少**
3. **可以同时插入多条数据，VALUES后面的值，需要使用`,`隔开    values( ),( ),( ),....**

-----


### 删减	DELETE

**语法：**

```sql
 -- 删除表的数据
 DELETE FROM `表名` WHERE [条件];  -- DELETE不会影响自增
 
 -- TRUNCATE  清空表 完全清空一个数据库表，表的结构和索引约束不会变
 TRUNCATE `表名`					-- TRUNCATE会清零自增
```

**DELETE和TRUNCATE的区别**

- **都能删除数据，都不会影响表的结构**
- **TRUNCATE 重新设置自增列，计数器会归零，不会影响事务**

**DELETE删除的问题,重启数据库**

- **INNODB  自增列会从1 开始，（存在内存当中，断电即失）**
- **MYISAM  继续从上一个自增量开始（存在文件中的，不会丢失）**

-----

### 更改	UPDATE

**语法：**

```sql
UPDATE `表名` SET `colnum_name`=value[,`colnum_name`=value,...]  WHERE [条件];
-- 条件：`where`字句运算符`id`等于某个值，大于某个值，在某个区间内修改...
```

**注意：**

1. **colnum_name是数据库的列，``**
2. **条件是筛选的条件，如果没有指定，修改全部列**
3. **value 是一个具体的值或者变量`CURRENT_TIME`**
4. **多个设置的属性之间，使用英文逗号隔开**

|      操作符      |     含义     |           示例           | 结果  |
| :--------------: | :----------: | :----------------------: | :---: |
|        =         |     等于     |           5=6            | false |
|   <> 或者  !=    |    不等于    |           5<>6           | true  |
|        >         |     大于     |           2>3            | false |
|        <         |     小于     |           2<3            | true  |
|        >=        |   大于等于   |           4>=2           | true  |
|        <=        |   小于等于   |           2<=3           | true  |
| BETWEEN...AND... | 在某个范围内 |          [2,5]           |       |
|       AND        |      &&      | `id`='张三' and sex='男' |       |
|        OR        |     \|\|     | `id`='张三' or sex='男'  |       |

```sql
UPDATE `student` SET `name`='景涛' WHERE id =1-- 不指定条件会改动所有表！
UPDATE `student` SET `name`='景涛';
-- 修改多个属性,逗号隔开
UPDATE `student` SET `name`='景涛',`email`='1374412025@QQ.com' WHERE id =1;
UPDATE `student` SET `name`='景涛',`email`='1374412025@QQ.com' WHERE id =1 and sex = '女';
UPDATE `student` SET `name`='景涛', `birthday`= CURRENT_TIME WHERE id =1;
```



# ==4、 DQL查询数据==

## 4.1、DQL 

Data Query Language：数据库查询语言

- 数据库中最核心的语言，最重要的语句
- 使用频率最高的语句

>select语法


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181557278.png)

## 4.2查询 SELECT

```sql
-- 查询全部
SELECT * FROM `表名`
-- 查询指定字段
SELECT `StudentNo`,`StudentName` FROM student;
-- 别名打开，字段，表名都可以换   字段名 AS 别名
SELECT `id` AS 学号,`name` AS 姓名 FROM `student` as 学生;
-- 函数 CONCAT(a,b)		拼接
SELECT CONCAT('姓名:',Studentname) AS 新名字 FROM student; 

```

**去重 distinct:**

作用：去除select结果重复的数据

```sql
SELECT `StudentNo` FROM `result`;-- 发现重复	
SELECT DISTINCT `StudentNo` FROM `result`; -- 去重	
```

**数据库的列（表达式）:**

```sql
SELECT VERSION()--查看系统版本
SELECT 100*3-1 AS 计算结果 ---用来计算
SELECT @@auto_increment_increment;-- 查询自增的步长(变量)

-----全员成绩加十分
SELECT `StudentResult`+10 AS 加分后 FROM student
```

**数据库的表达式: 文本值 , 列 , null , 函数 , 计算表达式 , 系统变量 ...**

**`select 表达式 from 表`**

## 4.3、where条件语句

**逻辑运算符号:**(尽量用英文字母而不是符号)

|  运算符   |       语法       |  描述  |
| :-------: | :--------------: | :----: |
|  and  &&  | a and b    a &&b | 逻辑与 |
| or   \|\| | a or b    a\|\|b | 逻辑或 |
|  not  !   |  not a      ! a  | 逻辑非 |

```sql
SELECT studentNo , studentresult  FROM result 
WHERE studentresult >= 95 AND studentresult<=100;-- and
SELECT studentNo , studentresult  FROM result 
WHERE studentresult >= 95 && studentresult<=100;

SELECT studentNo , studentresult  FROM result 
WHERE studentresult <60 OR studentresult>90;-- or
SELECT studentNo , studentresult  FROM result 
WHERE studentresult <60 || studentresult>90;

SELECT studentNo , studentresult  FROM result 
WHERE NOT studentNo = 1000;					-- not
SELECT studentNo , studentresult  FROM result 
WHERE studentNo != 1000;						
```

**模糊查询:**

|      运算符      |        语法        |             描述             |
| :--------------: | :----------------: | :--------------------------: |
|     IS NULL      |     a is null      |     操作符为null.为true      |
|   IS NOT NULL    |   a is not null    |       不为null,为ture        |
| BETWEEN...AND... | a between b and c  |       a在bc之间,为ture       |
|     **LIKE**     |      a like b      |  SQL 匹配,如果a匹配b,为true  |
|      **IN**      | a in (a1,a2,a3...) | 如果a 在a1或者a2...中,为true |




```sql
-- null 
SELECT studentno, studentname FROM `student` 
WHERE address='' OR address IS NULL;


SELECT studentNo, studentresult  FROM result 
WHERE studentresult BETWEEN 95 AND 100; 

SELECT *FROM result 
WHERE subjectno BETWEEN 1 AND 3 AND studentno !=1000;-- 多条件判断

-- 最后一个字带龙，'_'代表一个字符,'%'代表0到任意字符
SELECT *FROM tykdk 
WHERE `name` LIKE ('%龙')
SELECT *FROM tykdk 
WHERE `name` LIKE ('刘_龙')
SELECT *FROM tykdk 
WHERE `name` LIKE ('%三%')

-- 分数 是 59 或者 58 的同学		in 的字段是具体的值
SELECT *FROM result 
WHERE `studentresult`IN('59','58');
```

## 4.4、联表查询

![联表](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558772.png)

|    操作    |                       描述                       |
| :--------: | :----------------------------------------------: |
| inner join |         表中若至少有一个字段匹配,就返回          |
| left join  | 从左表中返回所有值,即使右表中没有,没有就填充null |
| right join | 从右表中返回所有值,即使左表中没有,没有就填充null |

### 笛卡尔积

有两个**集合A**和B，笛卡尔积表示**A集合中的元素和B集合中的元素**任意相互关联产生的所有可能的结果。
假如**A中有m个元素，B中有n个元素**，**A、B笛卡尔积产生的结果有m*n个结果**，相当于循环遍历两个集合中的元素，任意组合。
拿A集合中的第1行，去匹配集合B中所有的行，然后再拿集合A中的第2行，去匹配集合B中所有的行，最后结果数量为**m*n**。

```sql
SELECT student.studentno AS ss,result.studentno AS rs,studentname,subjectno,studentresult 
FROM student 
cross JOIN result;
-- 结果4*15
```

### 内连接 

```sql
-- 内连接
-- 内连接相当于在笛卡尔积的基础上加上了连接的条件。
select 字段 from 表1 inner join 表2 on 连接条件;
或
select 字段 from 表1 join 表2 on 连接条件;
或
select 字段 from 表1, 表2 [where 关联条件]; -- 不能用 on  因为 on和join关联
-- 但这种通过逗号隐式指定的联表形式其优先级要低于直接通过关键字（INNER JOIN, CROSS JOIN, LEFT JOIN）指定的形式。所以 t1, t2 JOIN t3 会被解析成 (t1, (t2 JOIN t3)) 而不是 ((t1, t2) JOIN t3)

-- 组合条件
-- 方式1：on中使用了组合条件。
select 字段 from 表1 inner join 表2 on 连接条件 and 条件
-- 方式2：在连接的结果之后再进行过滤yon，相当于先获取连接的结果，然后使用where中的条件再对连接结果进行过滤。
select 字段 from 表1 inner join 表2 on 连接条件 where 关联条件
-- 方式3：直接在where后面进行过滤。
select 字段 from 表1,表2 where 关联条件 and 条件
```

```sql
SELECT s.studentno,studentname,subjectno,studentresult 
FROM student  s
INNER JOIN result  r
ON s.studentno = r.studentno ;
```

`ON` 指定的联表条件其语法同 `WHERE`，所有后者可接受的表达式都可用于 `ON`。两者看起来功能上雷同，
`ON` 一般用于指定联表条件，即表之间怎么被联合，而 `WHERE` 则用于过滤结果。

### 外连接—左/右连接

```sql
select 列 from 主表 left join 从表 on 连接条件;
select 列 from 从表 right join 主表 on 连接条件;
```

```sql
SELECT s.studentno,studentname,subjectno,studentresult 
FROM student  s
LEFT JOIN result  r
ON s.studentno = r.studentno ;

SELECT s.studentno,studentname,subjectno,studentresult 
FROM student  s
LEFT JOIN result  r
ON s.studentno = r.studentno 
where s.studentno is not null;
```

外连接查询结果为主表中所有记录。如果从表中有和它匹配的，则显示匹配的值，这部分相当于内连接查询出来的结果；如果**从表中没有和它匹配的，则显示null**。
**最终：外连接查询结果 = 内连接的结果 + 主表中有的而内连接结果中没有的记录。**

>自连接

自己的表和自己的表连接，核心：拆成两个一模一样的表


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558895.png)

父类


子类


查询父类对应的子类


```java
SELECT a.`categoryname` AS 'father',b.`categoryname`AS'son'
 FROM `test1`AS a,`test1`AS b
 WHERE a.`categoryid`=b.`pid`
```

## 4.5、分页和排序

>排序：

```sql
SELECT *FROM `student`
ORDER BY id DESC
----DESC降序，ASC排序----
```

>分页

```sql
SELECT  *FROM `tykdk`
 ORDER BY `id` DESC
 LIMIT 0,10
```

## 4.6、子查询

where(这个值是计算出来的)

本质：在where语句嵌套一个查询语句）

```sql
SELECT `id`,`name`,`pwd`
FROM `student`
WHERE id=(
SELECT `id` FROM `grade`
WHERE `pwd`='***'
)
```

## 4.7、分组和过滤

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-jMiW02m4-1621309051592)(C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200429180334341.png)]

## 4.8、select小节

# 5、


## 5.1、常用函数

```sql
--数学
SELECT ABS(-55)
SELECT CEILING(22.995)
SELECT FLOOR(9.8)
SELECT RAND ()
SELECT SIGN(99)

--字串

SELECT CHAR_LENGTH('沃日你麻痹')
SELECT CONCAT('c','n','m')
SELECT INSERT ('我是你爸爸',1,2,'操你妈的逼')
SELECT LOWER('DSDDSADASF')
SELECT UPPER('sadasdasd')
SELECT INSTR ('zengnanbin','n')
SELECT REPLACE('你是一个大傻逼','傻逼','杂种')



SELECT REPLACE(`name`,'刘','牛') FROM `student`
WHERE `name` LIKE ('刘%')

---时间
SELECT CURDATE()
SELECT NOW()
SELECT LOCALTIME()
SELECT SYSDATE()

SELECT YEAR(NOW())



SELECT USER()
SELECT VERSION()
```

## 5.2、聚合函数

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-QRShGLiE-1621309051595)(C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200429174708478.png)]

```sql
SELECT COUNT(`name`)FROM `tykdk`

SELECT SUM(`9`)AS '总和' FROM `tykdk`

SELECT AVG (`9`)AS '平均分'FROM `tykdk`

SELECT MAX(`9`)AS '最高分'FROM `tykdk`

SELECT MIN(`9`) AS '最低分'FROM `tykdk`
```

## 5.3、数据库级别的MD5加密

MD5不可逆，具体的MD5密码值是一样的

MD5破解网站的原理，背后有一个字典

```sql
UPDATE `testmd5` SET `pwd`='123456',`name`='张三' WHERE id=1

INSERT INTO `testmd5` (`pwd`,`name`) VALUES ('123457','李四'),('1234557','王五')

UPDATE `testmd5` SET `pwd`=MD5(pwd) WHERE id=1

INSERT INTO `testmd5`  VALUES ('4',MD5('123456'),'xm')
```


要么都成功，要么都失败

>事务原则：ACID原则 原子性，一致性，隔离性，持久性（脏读，欢幻）

参考博客：https://blog.csdn.net/dengjili/article/details/82468576

**原子性（Atomicity）**

要么都成功，要么都失败

**一致性（Consistency）**

事务前后数据要保持一致

**隔离性（Isolation）**

事务的隔离性是多个用户并发访问数据库时，数据库为每一个用户开启的事务，不能被其他事务的操作数据所干扰，多个并发事务之间要相互隔离。

**持久性（Durability）**

事务一旦提交就不可逆，被持久化到数据库中

隔离性问题：


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558024.png)

>执行事务

```sql
---mysql是默认开启事务自动提交的
SET autocmmit=0--关闭
SET autocommit=1--开启
---手动处理事务
SET autocommit =0--关闭自动提交
---事务开启
START TRANSACTION --标记一个事务的开始，从这个之后的sql都在一个事务内
INSERT XX

---提交：持久化（成功）
commit
--回滚--
ROLLBACK---回到之前的样子
--事务结束
SET autocommit=1---开启自动提交

--了解
SAVEPOINT 保存点名---设置一个事务保存点
ROLLBACK TO SAVEPOINT 保存点名--回滚到保存点
RELEASE SAVEPOINT 保存点名---撤销保存点
```

```sql
SET autocommit =0;--关闭自动提交
START TRANSACTION --开始事务
UPDATE account1 SET money=money-2000 WHERE `id` = 1
UPDATE account1 SET money=money+2000 WHERE `id` = 2
COMMIT;--成功
ROLLBACK;--回滚
SET autocommit=1;--开启自动提交
```

# 7、

## 7.1、索引的分类

>在一个表中主键索引只可以有一个，唯一索引可以有多个

-  主键索引(PRIMARY KEY) 唯一标识，主键不可重复，只可有个  
-  唯一索引(UNIQUE KEY) 避免重复的列出现，可以重复，多个列都可以标识唯一索引  
-  常规索引(FullText) 默认的，可以用index，key关键字设置  
-  全文索引 在特定的数据库引擎才有，mylsam 快速定位数据 --增加一个全文索引
   ALTER TABLE school.student ADD FULLTEXT INDEX `studentName` (`studentName`)
   ----EXPLAIN 分析sql的执行情况

EXPLAIN SELECT *FROM student ---非全文索引

EXPLAIN SELLCT * FROM student WHERE MATCH(studentName)AGAINST('刘') 

## 7.2、测试索引

```sql
---插入一千万条数据
DELIMITER $$
CREATE FUNCTION mock_data000()
RETURNS INT
BEGIN
   DECLARE num INT DEFAULT 10000000;
   DECLARE i INT DEFAULT 0;
   WHILE i<num DO
     INSERT INTO `app_user` (`name`,`phone`,`pwd`,`age`) VALUES 
(CONCAT('用户',i),FLOOR(CONCAT('18',RAND()*(999999999-100000000)+100000000)),UUID(),FLOOR(RAND()*100));
      SET i=i+1;
   END WHILE;
   RETURN i;
END;



EXPLAIN SELECT * FROM `app_user` WHERE `name`='用户854569'

----插入索引
CREATE INDEX id_app_user_name ON `app_user`(`name`)
```

加入索引前


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558108.png)

加入索引后


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558894.png)

## 7.3、索引原则

- 索引不是越多越好 
- 不要对经常变的数据加索引 
- 小数据的表不要加 
- 一般加在常用在查询的字段上面

>索引的数据结构

Hash 类型的索引

Btree：InnoDB 的默认数据结构

参考资料：https://blog.csdn.net/zq602316498/article/details/39323803

# 8、


## 8.1、用户管理

>SQLyog可视化管理

用户表：mysql.user

```sql
---创建用户
CREATE USER kuangshen IDENTIFIED BY '123456'
---修改密码（当前账户）
SET PASSWORD =PASSWORD('123456')
---修改密码（指定账户）
SET PASSWORD FOR kuangsheng =PASSWORD('123456')

---用户授权
GRANT ALL PRIVLEGES PN*.* TO kuangshen

--查看权限
SHOW GRANTS FOE kuangshen

--撤销权限
REOMVE ALL PRIVILEGES OM*.* FROM kuangshen
```

## 8.2、数据库备份

为什么要备份

- 保证数据不丢失 
- 数据转移

MySQL数据库备份的方式

- 直接拷贝物理文件 
- sqlyog可视化工具 
- 命令行导出 mysqldump 命令行使用

```sql
-- musqldummp -h表名 -u用户名 -p密码 数据库 数据库表1 数据库表2.... >导入位置
-- 导出
mysqldump -hlocalhost -uroot -pehero000921 daka tykdk >D:a.sql
 
-- 导入
-- 登录的情况下，切换到指定的数据库

-- 导入，登录的情况下
source D:/文件.sql

-- 没有登录的情况

mysql -u用户 -p密码  数据库名字<备份文件
```

备份数据库防止数据丢失

把数据库给朋友，sql文件给比人即可！

# 9、


## 9.1、为什么要设计

当数据库比较复杂的时候就要设计

**糟糕的数据库设计：**

- 数据冗长，浪费空间 
- 数据库插入和删除都会麻烦，异常 
- 程序性能差

**良好的数据库设计**

- 节省空间 
- 保证完整性 
- 方便开发

**软件开发中，关于数据库的设计**

- 分析需求 
- 概要设计

**设计数据库的步骤**

-  收集信息，分析需求 用户表（用户登录注销，用户的个人信息，写博客，创建分类） 分类表（文章分类，谁创建的） 文章表（文章的信息） 评论表 友情链接（信息） 自定义表（系统信息，某个关键字） 说说表（发表心情。。。。id）  
-  标识实体（把需求落地到每个字段）  
-  标识实体之间的关系 user ->blog user->category 关注：user->user 友链：links 评论：user->user-blog 

## 9.2、规范数据库设计

**为什么要有范式**

-  信息重复  
-  更新异常  
-  插入异常 无法正常显示信息  
-  删除异常 丢失有效的信息 

>三大范式

**第一范式**

原子性：保证每一列不可再分

**第二范范式**

前提：满足第一范式的前提下，每张表只表示一个信息

**第三范式**

前提：满足第一第二范式


确保数据表的每一列数据都和主键直接相关，而不能见解相关 ![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558125.png)

# 10、

## 10.1、数据库驱动

驱动：声卡，显卡，数据库

## 10.2、JDBC


![img](https://raw.githubusercontent.com/1374412025/images/main/imgs202303181558674.png)

## 10.3、第一个JDBC程序

>创建测试数据库

1、创建一个普通项目

```sql
CREATE DATABASE `jdbcstudy`

CREATE TABLE  users
(
`id` INT (4) PRIMARY KEY,
`name` VARCHAR(40),
`password` VARCHAR(40),
`birthday` DATE
);

INSERT INTO `users` (`id`,`name`,`password`,`birthday`) 
VALUES ('1','张三','123456','1999-02-02'),('2','李四','1234556','1999-08-02'),('3','王五','1288556','1998-02-15')
,('4','赵六','752156','1999-12-12')
```

2.导入数据库驱动

```java
package JDBC01;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
public class test01 {
   	
   public static void main(String[] args) throws ClassNotFoundException, SQLException {
   
		//1.加载驱动
		Class.forName("com.mysql.jdbc.Driver");//固定
		//2.连接用户信息和url
		String url="jdbc:mysql://localhost:3306/jdbcstudy?useUnicode=true&characterEncoding=utf8&useSSL=true";
		String username ="root";
		String password="ehero000921";
		//3.连接成功，数据库对象 Connection
		Connection connection=DriverManager.getConnection(url, username, password);
		//4.执行sql对象
		Statement statement  =connection.createStatement();
		//5.执行sql的对象去执行sql
		String sql="select * from users";
		ResultSet rs=statement.executeQuery(sql);
		while (rs.next())
		{
   
			System.out.print("id="+rs.getObject("id")+" ");
			System.out.print("name="+rs.getObject("name")+" ");
			System.out.print("password="+rs.getObject("password")+" ");
			System.out.println("birthday="+rs.getObject("birthday"));
		}
		//6.释放连接
		rs.close();
		statement.close();
		connection.close();
	}
}
```

步骤总结：

1.加载驱动

2.连接数据库DriverManager

3.获取执行sql的对象Statement

4.获的返回的结果集

5.释放连接

>DriverManager

```sql
Class.forName("com.mysql.jdbc.Driver");
//固定写法
```

>URL

```sq
String  url ="jdbc:mysql://localhost:3306/jdbcstudy?useUnicode=true&characterEncoding=utf8&useSSL=true"
    //mysql默认3306
    //协议://主机地址:端口号/数据库名？参数1&参数2&参数3
```

>Statement 执行SQL的对象 PrepareStatement 执行的SQL的对象

```java
String sql="sekect * from users";
statement.executeQuery();//查询
statement.execute();//执行任何SQL
statement.executeUpdate();//更新，插入，删除
```

>ResultSet 查询的结果集：封装了所有的查询结果

获取定的数据类型

```java
resultset.getint();
resultset.getobject();
resultset.getDate();
...
    

//指针
resultset.beforFirst();//移动到第一个
resultset.afterLast();//移动到自动一个
resultset.absolute(row)//移动到指定类
```

## 10.4、statement对象

>配置类

```java
driver=com.mysql.jdbc.Driver
url=jdbc:mysql://localhost:3306/jdbcstudy?useUnicode=true&characterEncoding=utf8&useSSL=true
username=root
password=ehero000921
##最好写在src目录文件下，注意看写在什么地方
```

>工具类

```java
package JDBC01;
import java.io.IOException;
import java.io.InputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

public class jdbcutils {
   

	private static String driver=null;
	private static String url=null;
	private static String username=null;
	private static String password=null;
	static{
   
		try{
   
//			InputStream in=jdbcutils.class.getClassLoader().getResourceAsStream("db.properties");
			InputStream in=jdbcutils.class.getClassLoader().getResourceAsStream("JDBC01/db.properties");//这样就好了 
			Properties properties=new Properties();
			properties.load(in);
			driver =properties.getProperty("driver");
			url =properties.getProperty("url");
			username =properties.getProperty("username");
			password =properties.getProperty("password");
			Class.forName(driver);
			//驱动只加载一次
		
			
		}catch(IOException e){
   
			e.printStackTrace();
		}catch (ClassNotFoundException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
	//获取连接
	public static Connection getConnection() throws SQLException
	{
   
		return DriverManager.getConnection(url,username,password);
	}
	
	//释放连接资源
	
	public static void release(Connection conn,Statement st, ResultSet rs) throws SQLException
	{
   
		if(rs!=null)
		{
   
			rs.close();
		}
		if(st!=null)
		{
   
			st.close();
		}
		if(conn!=null)
		{
   
			conn.close();
		}
		
	}
	
}
```

>代码：

```java
package JDBC01;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class testinsert {
   

	public static void main(String[] args) throws Exception {
   
		Connection conn =null;
		Statement st=null;
		ResultSet rs=null;
		
		try {
   
			conn= jdbcutils.getConnection();
			st=conn.createStatement();
			String sql="INSERT INTO `users`  (`id`,`name`,`password`,`birthday`)"
					+ " VALUES ('9','大傻逼2','55201314','2000-12-11') ";
			int i=st.executeUpdate(sql);
			if(i>0)
			{
   
				System.out.println("插入成功!");
			}
		} catch (SQLException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}finally {
   
			jdbcutils.release(conn, st, rs);
		}
	}
}
//只需要改sql
```

>sql注入问题

sql存在漏洞，会导致被拼接

```java
package JDBC01;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class sql {
   

	public static void main(String[] args) {
   
		sql.login(" 'or '1=1", "'or '1=1");
	}
	public static void login(String username,String password)
	{
   
		Connection conn=null;
		Statement sta=null;
		ResultSet re=null;
		try {
   
			conn= jdbcutils.getConnection();
			sta=conn.createStatement();
			String sql="SELECT * FROM `users`  WHERE `name`='"+username+"' AND `password`='"+password+"'";
		    re=sta.executeQuery(sql);
		    while(re.next())
		    {
   
		    	System.out.print(re.getString("name")+"  ");
		    	System.out.println(re.getString("password"));
		    }
		} catch (SQLException e) {
   
			
			e.printStackTrace();
		}
	}
}
```

## 10.5、PreparedStatement

>增加

```java
package JDBC01;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.util.Date;

import com.mysql.fabric.xmlrpc.base.Data;

public class test02 {
   

	public static void main(String[] args) {
   
		
		Connection con=null;
		PreparedStatement pst=null;
		try {
   
			con=jdbcutils.getConnection();
			String sql ="insert into users(id,name,password,birthday) values(?,?,?,?)";
			pst=con.prepareStatement(sql);
			pst.setInt(1, 7);
			pst.setString(2, "蠢货");
			pst.setString(3, "5201314888");
			pst.setDate(4, new java.sql.Date(new Date().getTime()) );
			int i=pst.executeUpdate();
			if(i==1)
				System.out.println("插进去了");
		} catch (SQLException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}finally {
   
			if(pst!=null)
				try {
   
					pst.close();
				} catch (SQLException e) {
   
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			if(con!=null)
				try {
   
					con.close();
				} catch (SQLException e) {
   
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
		}
	}
	
}
```

>删除

```java
package JDBC01;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class test03 {
   

	public static void main(String[] args) {
   
		Connection con=null;
		PreparedStatement pst=null;
		try {
   
			con=jdbcutils.getConnection();
			String sql="delete from users where id=? ";
			pst=con.prepareStatement(sql);
			pst.setInt(1, 7);
			int i=pst.executeUpdate();
			if(i==1)
				System.out.println("删了");
		} catch (SQLException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}
```

>改变

```java
package JDBC01;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class test04 {
   

	public static void main(String[] args) {
   
		Connection con=null;
		PreparedStatement pst=null;
		try {
   
			con=jdbcutils.getConnection();
			String sql="update users set `name`='杂种' where `id`=?";
			
			pst=con.prepareStatement(sql);
			pst.setInt(1, 5);
			int i=pst.executeUpdate();
			if(i==1)
				System.out.println("成功");
		} catch (SQLException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}
```

>删除

```java
package JDBC01;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.Date;

import com.mysql.fabric.xmlrpc.base.Data;

public class test05 {
   

	public static void main(String[] args) {
   
		Connection con=null;
		PreparedStatement pst=null;
		ResultSet rs=null;
		try {
   
			con=jdbcutils.getConnection();
			String sql="select * from `users` where id=?";
			pst=con.prepareStatement(sql);
			pst.setInt(1, 2);
			rs=pst.executeQuery();
			while(rs.next())
			{
   
				System.out.println(rs.getInt("id"));
				System.out.println(rs.getString("name"));
				System.out.println(rs.getString("password"));
				System.out.println(rs.getString("birthday"));
//				System.out.println(rs.getDate(new java.sql.Date(new Date().getTime())));
			}
		} catch (SQLException e) {
   
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}
```

## 10.6、使用IDEA连接数据库

## 10.7、数据库连接池

数据库连接----执行完毕—释放

连接十分浪费资源

**池化技术：准备一些预先的资源，过来就是连接准备好的**

----开门----业务员：等待–服务—

常用连接数：10

最小连接数：10

最小连接数：100 业务最高承载上限

等待超时：100ms

编写连接池，实现一个接口 DateSource

>开源数据源实现

DBCP

C3P0

Druid：阿里巴巴

使用这些数据库连接池后在项目就不需要写项目连接池了

>DBCP

