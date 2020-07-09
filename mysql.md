# DAY 01

## 1.快捷键

```
Alt＋Tab：切换当前的窗口

Windows＋D：显示/隐藏界面

Windows＋E：打开此电脑/资源管理器

Windows＋R：打开运行窗口   cmd：命令行/mspaint：画图/calc: 计算器/


```



## 2.



## 3.软件生命周期（软件开发流程）

#### 1）软件定义期

（1）可行性研究阶段- - 《可行性研究报告》

​			技术、人力、设备、时间、资金、回报率、政策、风俗

（2）需求分析阶段- - 《软件需求说明书》

​			功能性需求分析和非功能性需求分析

​			非功能性需求是保证功能性需求正常使用的前提

#### 2）软件开发期

（3）概要设计阶段- - 架构师

​	子系统、模块、各自功能、数据库设计

（4）详细设计阶段- - 模块负责人

​	页面、主题内容、属性

（5）编码实现阶段

​	UI设计- - 产品的效果图

​	前端    - - 将效果图转为html.css.js文件

​	后端    - - 为前端提供数据

（6）测试阶段 - - 软件测试工程师

​	软件测试

#### 3）软件维护期

（7）部署阶段 - - 运维工程师

​	部署到服务器

（8）维护阶段

​	软件维护



## 4.学子商城功能性需求分析

前台：www.codeboy.com:9999

后台：www.codeboy.com:9999/admin/login.html

后台子系统：

​					商品模块（列表、搜素、添加、修改、删除）

​					用户模块（列表、搜素、删除、修改）

​					订单模块（列表、修改、删除）

前台子系统：

​					商品模块（首页、列表、详情）

​					用户模块（注册、登录、修改、个人中心、收藏）

​					购物车模块（添加、修改、删除、结算）

移动端子系统：

​					商品模块（首页、详情、列表）

​					用户模块（注册、登录、修改、个人中心、收藏）

​					购物车模块（添加、修改、删除、结算）



## 5.服务器

硬件：服务器就是一台计算机

软件：可以提供各种服务，例如：web服务器、数据库服务器等

访问服务器：

​	找服务器：域名/IP地址

​	服务器对应的服务：端口				

​	使用该服务所用的协议：https://www.codeboy.com:9999

​											   https://101.86.128.94:9999

​												协议      域名/IP地址      端口

## 6.访问FTP服务器

提供文件下载的服务

下载地址：https://code.tarena.com.cn

用户名：tarenacode

密码 ：code_2013



# DAY02

## 1.项目中的数据存储方式

特定文件/内存/第三方服务



## 2.什么是数据库

按照特定的形式组织存储的数据，目的为了操作数据- - 增删查改

### （1）数据库的发展历史

网状数据库- - 层次型数据库 - - 关系型数据库 - - 非关系型数据库

### （2）关系型数据库逻辑结构

| Server         -Database        -Table          -Row          -Column |
| ------------------------------------------------------------ |
| 服务器            数据库               数据表          行                  列 |



## 3.Mysql

```
Oracle：Mysql

Martin：Mariadb
```



| xampp：服务器套装，包含多款服务器端软件  |
| ---------------------------------------- |
| https://www.apachefriends.org/index.html |

### （1）mysql部署

服务器端：存储、维护数据- - 例如：银行数据库服务器

```
C:/xampp/mysql/bin/mysqld.exe
```

确保端口3306不被占用

客户端：负责链接服务器，对数据进行操作- - 主要是增删查改 - - 例如： ATM机

```
C:/xampp/mysql/bin/mysql.exe
```



### （2）使用客户端链接服务器

代码：

mysql.exe -h(127.0.0.1) -P3306 -uroot -p

| localhost/127.0.0.1为自己电脑 h：host主机（域名/IP地址） |
| -------------------------------------------------------- |
| p：port端口        u：user 用户名     root：管理员用户   |
| 简写形式：mysql -uroot                                   |



## 4.mysql常用命令

| quit;	退出服务器链接                        |
| ---------------------------------------------- |
| show databases；	显示所有的数据库           |
| use 数据库名称；	进入指定的数据库           |
| show tables；	显示当前数据库下的所有表      |
| desc 表名称；     查看表头，描述表中都有哪些列 |



## 5.SQL命令

结构化查询语言，用来操作关系型数据库，主要是对数据的增删查改。

### （1）交互模式

在客户端输入一行，回车，服务端执行一行；适用于临时性的操作数据。

### （2）脚本模式

客户端把要执行的SQL命令写在一个脚本文件中，然后一次性的提交给服务器执行；适用于批量的操作数据。

​	前提：不能连接，要在连接前

​	mysql -uroot<拖拽脚本 回车

练习：编写脚本文件02.sql，打开脚本，显示所有的数据库，进入到数据库phpmyadmin中，显示当前数据库中所有的表，描述表pma__recent中都有哪些列。

```
#desc pma__recent (#为单行注释)
/* xxxx
	xxxx
	xxx
	xxx*/(/* xxx */为多行注释)
```

**提醒：SQL命令的语法规范**

（1）一个命令可以跨越多行，以英文的分号结尾；

（2）命令不区分大小写，习惯上关键字大写，非关键字小写；

（3）假设某一行命令出现错误，则此行代码以及后面所有代码都不执行；

（4）分为单行注释（#）和多行注释（/* */)

## 6.常用的SQL命令

### （1）丢弃数据库，如果存在

​	drop database if exists jd;

### （2）创建一个新的数据库

​	create database jd;

### （3)   进入数据库

​	use jd;

### （4） 闯进保存数据的表

​	create table student(

​				id int,

​				name varchar(8),

​				sex varchar(1)

​				score int

);

### （5）插入数据

insert into stuent values（'1','ran','b','59');

### （6）查询数据

select * from student；

# DAY 03

## 1.常用SQL命令	

### （1）修改数据

```
update user set upwd='88888',isOnline='n',where uid='2';
```

###   （2）删除数据

```
delete from user where uid = '3';
```

## 2.计算机如何存储字符

### （1）如何存储英文字符

ASCII:对128个英文字母及其符号进行了编码

Latin-1：对欧洲字符进行了编码，总共有256个，兼容ASCII

### （2）如何存储中文字符

GB2312：对常用的6000多汉字进行了编码，兼容ASCII

GBK:对2万多汉字进行的编码，兼容GB2312

Unicode：对世界上主流国家的常用语言进行了编码，兼容ASCII，不兼容GB2312，GBK等，具体使用分为utf-8，utf-16，utf-32

### （3）解决Mysql中文乱码

脚本文件另存为的编码为utf-8

客户端链接服务器端的编码为utf-8

```
	set names utf8;
```

服务器端创建数据库使用的编码为utf-8

```
	create database xz charset= utf8;
```

练习：编写脚本文件01_sina.sql,先丢弃再创建数据库sina，设置编码为utf-8，进入数据库，创建保存新闻数据的表news，包括有编号nid，标题title，发布时间ctime，详情detail，来源origin；插入若干条数据，修改1条，删除1条。     在交互模式下查询数据

## 3.列类型

创建表的时候，指定的列存储的数据类型

```
create table t1( id 列类型	);	
```

### （1） 数值型--引号可加可不加

tinyint 	微整型，占1个字节，范围-128~127

smallint 	小整型，占2个字节，范围 -32768~32767

int	整型，占4个字节，范围-2147483648~2147483647

bigint 	大整型，占8字节，范围很大                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        

```
TB 	GB 	MB 	KB 	BYTE(字节) 	Bit（位）

1BYTE=8Bit
```

位：计算机最底层的单位，只能存储1或者0

### （2）浮点型

float	单精度浮点型，占4个字节

double(M,D)	双精度浮点型，占8个字节

decimal(M,D)	定点小数，小数点不会发生变化,M代表总的有效位数，D代表小数点后的有效位数。

boolean/bool	布尔型，只有两个值，分别是true和false；真正存储的时候会转为tinyint，也可以存数字。Mysql没有真正的布尔型。常用于存储只有两个值得数据，例如：性别，是否在线，是否登录...

| 如果插入的值是true，自动转为1，false转为0，true和false是关键字，使用的时候不能加引号。 |
| ------------------------------------------------------------ |
| 如果插入的值是true，自动转为1，false转为0，true和false是关键字，使用的时候不能加引号。 |



### （3）日期时间型--必须加引号

date	日期型	‘2020-10-10’

time	时间型	‘15:30:20’

datetime	日期时间型	‘2020-10-10 15:30:20'

| 注意：                                    |
| ----------------------------------------- |
| 如果是汉字年月日，则date不行，用varchar。 |



### （4）字符串型--必须加引号

varchar（M）	变长字符串，几乎不会产生空间浪费，操作速度相对慢，M的最大值是65535，常用于存储变化长度的数据，例如：用户名、密码、文章内容等

char(M)	定长字符串，可能会产生空间浪费，操作速度相对快，M的最大值是255，常用于存储固定长度的数据，例如：身份证、电话号码等等

text（M）	大型变长字符串，M的最大值是2G

|        | varchar（5） | char（5）    |
| ------ | ------------ | ------------ |
| a      | a\0          | a\0\0\0\0    |
| ab     | ab\0         | ab\0\0\0     |
| 一二三 | 一二三\0     | 一二三\0\0\0 |

```sql
例子：
create table t1(
	id int,
	age tinyint,
	Salary decimal(8,2),   #9999.99
	Ctime date,
	Phone char(11)
	Detail varchar(5000)
)
```

练习：使用合理的列类型，编写脚本文件02_xuezi.sql,先丢弃再创建数据库xuezi，设置编码utf-8，进入数据库，创建保存笔记本数据的表laptop，包含有编号lid，标题title，价格prince，库存量stockCount，上架时间shelfTime，是否为首页推荐isIndex，插入若干条数据。

```sql
#设置客户端链接服务器端代码
set names utf8;
#先丢弃数据库
drop database if exists xuezi;
#设置编码
create database xuezi charset= utf8;
#进入数据库
use xuezi;
#创建表laptop 
create table laptop(
	lid int primary key,
	title varchar(20) not null,
	price decimal(8,2),
	stockCount smallint,
	shelfTime date,
	isIndex bool);#也可以直接使用tinyint。

insert into laptop values('01','时间刺客','19999.99','240000','2010-10-1',true);
insert into laptop values('02','节奏大师'，'2990.99','130000','2013-1-1',false);
select * frm laptop;
```

### （5）列约束

对要插入的数据进行特定的验证，只有符合要求才允许插入，例如插入性别只能是男或女，例如一个人的成绩范围0~100

```
create table t1( lid int 列约束 );
```

#### （1）主键约束--primary key

声明了主键约束的列上不允许插入重复的值,一个表中只能有一个主键约束，通常加在编号列，会加快数据的查找速度。

NULL空，代表一个无法确定的值，例如无法确定一个员工的生日，电话等，无法确定一个商品的价格。

注意：主键列上不能插入NULL。

#### （2）非空约束--NOT NULL

声明了非空约束的列上不允许插入NULL

| 任务：                                                       |
| ------------------------------------------------------------ |
| 编写脚本文件xz.sql,先丢弃再创建数据库xz，设置编码utf8，进入数据库，创建保存笔记本分类的表family，保护fid，fname分类名称，插入以下数据: |
| 10  联想  20  戴尔 30 小米  创建保存笔记本数据表laptop，保护lid，标题title，价格price，规格spec，详情detail，上架时间shelfTime，是否在售isOnsale，所属分类编号familyId；插入若干条数据。 |

|      |
| ---- |
|      |

```sql
#设置客户端链接服务器端的编码
set names utf8;
#丢弃数据库，如果存在 
drop database if exists xz;
#进入数据库
use xz；
#创建保存分类的表
create table family(
	fid int primary key,
	fname varchar(10) unique
	);
#插入数据
insert into family values('10','联想'),('20','戴尔'),('30','小米');
#创建保存笔记本的数据表
create table laptop;
	lid int primary key,
	title varchar(20),
	prince decimal(7,2),
	spec varchar(20),
	detail varchar(5000),
	shelTime date,
	isOnsale tinyint default 0,
	familyId int,
	#把familyId这列作为外键，这一列的取值到family表中的fid中
	foreign key(familyId) references family(fid)
	);
insert into laptop values('01','液晶显示器','4999','27寸','60hz刷新频率','2010-10-10',1,30);
insert into laptop values('02','曲面液晶显示器','2666.66','27寸','144hz刷新频率','2010-10-10',default,20);
select * from laptop;	
```

#### （3）唯一约束--unique

声明了唯一约束的列上不允许出现重复的值，允许插入NULL，甚至多个NULL；一个表中允许出现多个唯一约束

练习：在laptop表中，给title列添加唯一约束，并禁止插入NULL，并插入数据测试。

```sql
 title varchar unique not null;
```

#### （4）默认值约束--default

mysql可以使用default关键字设置默认值，具体应用方式有两种。

```sql
insert into laptop values('01','液晶显示器'，default...);
insert into laptop(lid,title) values('02','曲面液晶显示器');
```

```sql
eg：prince decimal(7,2) default 10000,
....................................
insert into laptop values('01','液晶显示器','default','27寸','60hz刷新频率','2010-10-10',1,30)
```

#### （5）检查约束

也称为自定义约束

```sql
create table student(
	score tinyint check(score>=0 AND score<=100)
);
mysql不支持检查约束，mysql认为会影响数据的插入。对服务器造成较大的压力，最终是由JS完成的。
```

#### （6）外键约束 

外键列上的取值范围需要在另一个表的主键列出现过，外键和对应的主键列类型要保持一致，允许为NULL。

```
foreign key(列) references family(主键列)
foreign key(famlilyId) references family(family)
把familyId这列作为外键，这一列的取值到family表中的fid列去取
```

#### （7）自增列

auto_increment：自动增长，在插入编号的时候无需手动赋值，只需要插入为NULL就会获取当前的最大值，然后加1插入。

注意：（1）必须添加在主键列上

​			（2）允许手动赋值

## 5.简单查询

```sql
#设置客户端连接服务器端编码
SET NAMES UTF8;
#丢弃数据库，如果存在
DROP DATABASE IF EXISTS tedu;
#创建数据库，设置编码
CREATE DATABASE tedu CHARSET=UTF8;
#进入数据库
USE tedu;
#创建保存部门数据的表
CREATE TABLE dept(
  did INT PRIMARY KEY AUTO_INCREMENT,
  dname VARCHAR(8) UNIQUE
);
#插入数据
INSERT INTO dept VALUES(10,'研发部');
INSERT INTO dept VALUES(20,'市场部');
INSERT INTO dept VALUES(30,'运营部');
INSERT INTO dept VALUES(40,'测试部');
#创建保存员工数据的表
CREATE TABLE emp(
  eid INT PRIMARY KEY AUTO_INCREMENT,
  ename VARCHAR(8),
  sex BOOL DEFAULT 1,
  birthday DATE,
  salary DECIMAL(7,2),  #99999.99
  deptId INT,
  FOREIGN KEY(deptId) REFERENCES dept(did)
);
#插入数据
INSERT INTO emp VALUES(NULL,'然哥',1,'1977-5-30',50000,10);
INSERT INTO emp VALUES(NULL,'刘大会',1,'1994-8-30',12000,20);
INSERT INTO emp VALUES(NULL,'李洋',0,'1996-7-3',8000,30);
INSERT INTO emp VALUES(NULL,'孙绪东',1,'1993-10-2',6000,10);
INSERT INTO emp VALUES(NULL,'郝瑞',1,'1991-10-2',7500,20);
INSERT INTO emp VALUES(NULL,'张玥',0,'1996-8-1',4500,30);
INSERT INTO emp VALUES(NULL,'杨瑞',0,'2000-1-1',4000,20);
INSERT INTO emp VALUES(NULL,'姜成林',1,'1990-4-20',15000,30);
INSERT INTO emp VALUES(NULL,'叶煦安',0,'1998-6-1',4700,10);
INSERT INTO emp VALUES(NULL,'代鹏峰',1,'1995-3-1',8700,20);
INSERT INTO emp VALUES(NULL,'杜悦鑫',0,'1996-3-1',9700,30);
INSERT INTO emp VALUES(NULL,'张瑞',1,'1997-3-1',10700,10);
INSERT INTO emp VALUES(NULL,'王宗浩',0,'1998-3-1',11700,30);
INSERT INTO emp VALUES(NULL,'张天翔',1,'1999-3-1',12700,NULL);
INSERT INTO emp VALUES(NULL,'王伟茜',0,'1997-3-1',13700,30);

```



### （1）查询特定的列

示例：

```sql
select eid,ename from emp;
```

### （2）查询所有的列

```sql
select * from emp;
select eid,ename,sex,birthday,salary,deptId from emp;
```

### （3）给列起别名

示例：查询所有员工的编号和姓名，使用汉字别名

````sql
select eid as 编号，ename as 姓名 from emp；
````

```
AS关键字可以省略，只需要跟别名中间留个空格就行！
```

练习：查询出所有员工的姓名，性别，生日，使用汉字别名

```sql
select ename as 姓名,sex as 性别,birthday as 生日 from emp;
```

### （4）显示不同的记录

示例：查询出都有哪些性别的员工

```sql
select distinct sex from emp;
注意：一句代码只能查一项
```

### （5）查询时执行运算

``` sql
select 2+3+8*23.5-6*14;
练习：查询出所有员工的姓名和年薪
select ename,salary*12 from emp;
练习：假设每个员工的工资加2000，年终奖30000，查询出所有员工的姓名及其年薪，使用汉字别名
select ename 姓名,(salary+2000)*12+30000 as 年薪 from emp;
```

### （6）查询出所有的部门，结果集按照编号升序、降序排列

```sql
select * from dept order by did asc;#ascendant 升序的
select * from dept order by did desc;#descendant 降序的
练习：查询出所有的员工，果集按照工资的降序排列
select * from emp order by salary desc;
练习：查询出所有的员工，结果集按照年龄从大到小排列
select * from emp order by birthday asc;
练习：查询出所有的员工，结果集按照姓名的升序排列
select * from emp order by ename asc;
或者：去掉asc，默认是按照升序排列的。
```

```sql
拓展：如果想查询出员工的姓名，工资，并且工资的降序排列
 select ename,salary from emp order by salary desc;
```

```sql
练习：查询出所有的员工，结果集要求女员工在前，如果性别相同，按照工资的降序排列
select * from emp order by sex asc,salary desc;
```

### （7）条件查询 ---练习

示例：查询出编号为5的员工所有列

```sql
select * from emp where eid=5;
```

```sql
练习：查询出然哥的姓名，生日，工资
select ename,birthday,salary from emp where ename='然哥';
练习：查询出所有的男员工
select * from emp where sex='1';
练习：查询出30号部门下的员工有哪些
select * from emp where deptId='30';
练习：查询出工资在6000以上的员工有哪些
select * from emp where salary>6000;
练习：查询出不在30号部门下的员工有哪些
select * from emp where deptId！='30';
练习：查询出没有明确部门的员工有哪些
select * from emp where deptId is NULL;
练习：查询出有明确部门的员工有哪些
select * from emp where deptId is not NULL;
练习：查询出工资在10000以上的女员工有哪些
select * from emp where sex=0 and salary >10000；
练习：查询出工资在8000~12000之间的员工有哪些
select * from emp where salary>=8000 and salary<=12000;
或者 ：select *from emp where salary between 8000 and 12000；
练习：查询出工资在8000以下和12000以上的员工有哪些
select * from emp where salary=>12000 or salary<=8000;
或者select * from emp where salary not between 8000 and 12000;
练习：查询出1997年出生的员工有哪些
select * from emp where birthday>='1997-01-01' and birthday<'1998-01-01';
或者：select * from emp where birthday between '1997-01-01' and '1997-12-31';
练习：查询出10号和30号部门的员工有哪些
select * from emp where deptId ='10' or deptId='30';
或者：select * from emp where deptId in(10,30);
练习：查询出不在10号，也不在30号部门的员工有哪些
select * from emp where deptId not in(10,30);
```

### （8）模糊条件查询

示例：查询出姓名中含有 瑞 的员工有哪些

```sql
select * from emp where ename like '%瑞'；
```

```
练习：查询出姓王的员工有哪些
select * from emp where ename like '王%';
练习：查询出员工名字中第二个字为悦的员工有哪些
select * from emp where ename like '_悦%'；
```

| 注意：                                   |
| ---------------------------------------- |
| %   匹配任意个字符 >=0                   |
| _     匹配任意一个字符   =1              |
| 以上两个匹配符号必须结合着like关键字使用 |

