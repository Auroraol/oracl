# Oracle在线网站

SQL Fiddle: http://sqlfiddle.com/

![图6.png](oracl.assets/1613999346_266118.png)

![tu1.png](oracl.assets/1613999613_743789.png)

点击Browser查看是否建表成功

<img src="oracl.assets/8c7bb95ee3264a04896f8c3668193692.png" alt="在这里插入图片描述" style="zoom: 50%;" />

如果不想每次都自己手敲建表语句，可以使用页面头标签的Text to DDL：

<img src="oracl.assets/image-20231030201704402.png" style="zoom: 50%;" />



**注意：左边是初始化表跟数据，即每次执行右边的sql的时候，数据都会是从一开始初始化的状态开始跑sql的**

实例

```mysql
CREATE TABLE `Scores` (
  `Id` int(2) NOT NULL AUTO_INCREMENT,
  `Score` double(5,2) NOT NULL,
  PRIMARY KEY (`Id`)
) ENGINE=InnoDB;
INSERT INTO `Scores` (`Id`, `Score`) VALUES
(1, 3.50),
(2, 3.65),
(3, 4.00),
(4, 3.85),
(5, 4.00),
(6, 3.65);
```

```
select * from Scores;
```

![image-20231030202614083](oracl.assets/image-20231030202614083.png)

# 安装Oracle19c

https://www.oracle.com/database/technologies/oracle-database-software-downloads.html

<img src="oracl.assets/1567668194696-0fb940c8-9211-401c-a436-732cc1298142.png" alt="img" style="zoom: 50%;" />

需要登录Oracle的账号。

## 解压压缩包

![img](oracl.assets/1567668203270-309ca42f-131d-4734-9ab6-336bb2d17115.png)

## 双击安装程序



![img](oracl.assets/1567668209885-cae2984c-8803-459f-82fd-2492f8b58f52.png)

## 创建数据库实例

![img](oracl.assets/1567668241164-b68fe434-df2f-4c88-b6d1-d370bd943df6.png)

## 选择类型

- 桌面类
- 服务类

当前笔记本，选择桌面类即可。

![img](oracl.assets/1567668246973-56ba38b8-7851-41ea-9aa0-9f7cb7fbcc6c.png)

## 选择账户

选择windows内置账户

![img](oracl.assets/1567668256732-01beabdf-dcb1-4b6a-98c8-3ba7034e617b.png)

确认



![img](oracl.assets/1567668272297-5141ad62-4512-4641-a205-71d645526c3c.png)

## oracle目录选择

![img](oracl.assets/1567668278848-bc37d65e-bfa0-45d6-90ae-62602bd804bb.png)

【密码问题】

输入orcl之后点击两次下一步。

![img](oracl.assets/1567668287620-25c0b570-0618-49f4-8fd7-f7a30f4c1dcf.png)

## 安装

![img](oracl.assets/1567668295243-4d23ec91-a3af-4cda-8fc1-7b4f6d78fde6.png)

![img](oracl.assets/1567668302334-fbf57058-c092-43f2-a3f8-56014228a0b9.png)

## 验证

打开sqlplus



![img](oracl.assets/1567668310901-acde5421-74d9-4a2f-98ec-077dd9742109.png)

输入命令

```plain
sys as sysdba
```

键入密码

```plain
orcl
```

看到下面的画面，代表成功。

![img](oracl.assets/1567668323400-091e87e6-1591-4fcf-b73a-11b47f46e8c4.png)

## 容器数据库配置

关闭oracle所有的服务。

进入服务

```plain
win + r
```

```plain
services.msc
```

![img](oracl.assets/1567668339561-587d3e75-4c58-465f-99d5-38d9b4e338eb.png)

```sql
E:\oracle19c\network\admin
```

追加内容如下：

```plain
orclpdb =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = localhost)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = orclpdb)
    )
  )
```

最后把oracle服务全部重启。

## 容器数据库开启

![img](oracl.assets/1567668383903-9196b4f3-d554-457b-8221-a0345cbf6813.png)



![img](oracl.assets/1567668383892-7e12cf8f-0f16-4201-8607-71997bce4392.png)



![img](oracl.assets/1567668383905-dcd3f1a9-3b7a-4e91-9fc4-8679dc4f7253.png)![img](oracl.assets/1567668383938-6b250543-d4ba-4e30-bc8f-62adc40c6a41.png)







# 安装oracle11g

 WINDOWS安装Oracle

　　1. 解压缩文件，将两个压缩包一起选择， 鼠标右击 -> 解压文件 如图

![img](oracl.assets/1618743235491-76407957-c53a-430b-a1ee-993882dfe9ae.jpeg)

[![img](oracl.assets/1618743235957-f681dd14-4c9f-4d57-a490-376eb947bfd6.jpeg)

　　2.两者解压到相同的路径中，如图：

![img](oracl.assets/1618743236463-72ef790c-d560-45dd-abdf-2190b1e0b957.jpeg)



　　3. 到相应的解压路径上面，找到可执行安装文件【 setup.exe 】双击安装。如图：

![img](oracl.assets/1618743236955-462e1267-5821-4718-8759-b7ffdeda42ba.jpeg)



 

　　4. 安装第一步：配置安全更新，这步可将自己的电子邮件地址填写进去(也可以不填写，只是收到一些没什么用的邮件而已)。取消下面的“我希望通过My Oracle Support接受安全更新(W)”。 如图：

![img](oracl.assets/1618743237488-9394e8f0-5f98-4a28-9468-0653f46dceb7.jpeg)

　　5. 安全选项，直接选择默认创建和配置一个数据库(安装完数据库管理软件后，系统会自动创建一个数据库实例)。 如图：

![img](oracl.assets/1618743237924-1262cc74-4450-41a0-8d23-9b4eee62bd7c.jpeg)

　　6. 系统类，直接选择默认的桌面类就可以了。(若安装到的电脑是，个人笔记本或个人使用的电脑使用此选项) 如图：

![img](oracl.assets/1618743238459-e0265e78-bc78-41f0-93cc-2088db98c773.jpeg)

　　7. 典型安装。 重要步骤。建议只需要将Oracle基目录更新下，目录路径不要含有中文或其它的特殊字符。全局数据库名可以默认，且口令密码，必须要牢记。密码输入时，有提示警告，不符合Oracel建议时不用管。 (因Oracel建议的密码规则比较麻烦， 必须是大写字母加小写字母加数字，而且必须是8位以上。麻烦，可以输入平常自己习惯的短小密码即可) 如图：

![img](oracl.assets/1618743239001-9c6a839e-1211-405b-b0f6-4508aaf7c535.jpeg)

　　8. 若输入的口令短小简单，安装时会提示如下。直接确认Y继续安装就是了。如图：

![img](oracl.assets/1618743239532-8a2d2c44-9c32-4469-98d8-627ad138744f.jpeg)

　　9. 先决条件检查。 安装程序会检查软硬件系统是否满足，安装此Oracle版本的最低要求。 直接下一步就OK 了。如图：

![img](oracl.assets/1618743240004-868bce20-437b-40e6-b323-503e51e0427f.jpeg)

　　10. 概要 安装前的一些相关选择配置信息。 可以保存成文件 或 不保存文件直接点完成即可。如图：

![img](oracl.assets/1618743240501-04c49143-4c23-4195-8a9c-de95be125dbe.jpeg)

　　11. 安装产品 自动进行，不用管。如图：

![img](oracl.assets/1618743241043-aa1f6509-5867-4bfe-a535-cc822a95a86f.jpeg)

　　12. 数据库管理软件文件及dbms文件安装完后，会自动创建安装一个实例数据库默认前面的orcl名称的数据库。如图：

![img](oracl.assets/1618743241573-18fb23e6-5589-460c-9563-cee3884a3fe8.jpeg)

　　13. 实例数据库创建完成了，系统 默认是把所有账户都锁定不可用了(除sys和system账户可用外)，建议点右边的口令管理，将常用的scott账户解锁并输入密码。 如图：

![img](oracl.assets/1618743242062-154dfa1f-7b38-48ab-8a08-96861d4a768a.jpeg)

　　14. 解锁scott账户， 去掉前面的绿色小勾，输入密码。同样可以输入平常用的短小的密码，不必非得按oracle建议的8位以上大小写加数字，麻烦。如图：

![img](oracl.assets/1618743242341-aa7cc6e2-34ab-405f-aae5-1c7f564f1253.jpeg)

　　15. 同样，密码不符合规则会提示。不用管它，继续Y即可。如图：

![img](oracl.assets/1618743242675-e3f11030-6512-4d96-9481-819e0d94fcbc.jpeg)

　　16. 安装成功，完成即可。如图：

![img](oracl.assets/1618743243055-b1a063d1-26e5-47e8-97e2-1456088365d9.jpeg)

# 一、引言

安装可参考：[Windows10环境下载安装Oracle19c教程](https://blog.csdn.net/qq_29864051/article/details/131261905?spm=1001.2014.3001.5501)

## 1.1 Oracle的体系结构

在Oracle数据库中，存在以下层次关系：实例（Instance） > 用户（User） > 表空间（Tablespace） > 表（Table）

1. 实例（Instance）：
   实例是Oracle数据库运行时的一个独立环境。它包括了数据库`内存结构和后台进程`，负责管理数据库的访问和操作。一个物理服务器上可以`同时运行多个`Oracle实例，每个实例都有自己的系统资源和配置。
2. 用户（User）：
   用户是数据库中的逻辑概念，用于`识别和控制对数据库的访问和操作`。每个用户都有自己的用户名和密码，并且被授予特定的权限和角色。用户可以创建表、视图、索引等数据库对象，并可以执行各种SQL操作。
3. 表空间（Tablespace）：
   表空间是`逻辑存储单元`，用于组织和管理数据库中的表、索引和其他对象。一`个数据库可以包含多个表空间，每个表空间由一个或多个数据文件组成`，这些文件存储了实际的数据和索引。
4. 表（Table）：
   表是数据库中的`基本存储结构`，用于存储数据。表由一个或多个列组成，每列定义了特定的数据类型。表包含行（记录），每行代表一个数据实体。用户可以在自己的模式中创建表，并使用SQL语句对表进行插入、更新、删除和查询操作。

<img src="oracl.assets/image-20231101221101818.png" alt="image-20231101221101818" style="zoom:67%;" />

# 二、Oracle数据库的用户

oracle安装成功后，会默认生成三个用户

+ 超级管理员：      sys  权限最高 它的角色 dba 密码 change_on_install

+ 系统管理员：      system 权限也很高他的角色是dbaoper 密码 manager

+ 普通用户：          scott   密码tiger或者123,  没有操作用户的权限【创建修改删除】

sys有 create databse 的权限 ，而system没有.其它相似在日常对oracle管理过程中，使用system就够了

# 三、 sqlplus常用命令

## 3.1 登录相关

**1、进入sqlplus模式**

```cmd
C:\Users\wd-pc>sqlplus /nolog
SQL>
```

**2、以OS身份连接** 

登录本机的数据库  

```cmd
C:\Users\wd-pc>sqlplus / as sysdba  
或 
SQL>connect / as sysdba
```

**3、以普通用户登录**

```cmd
C:\Users\wd-pc>sqlplus scott/123 
或
SQL>connect scott/123      普通用户登录默认数据库   
SQL>conn scott/tiger       普通用户登录默认数据库   
或
SQL>connect scott/123@servername    普通用户登录指定的servername数据库     
```

scott:是Oracle提供的示例用户，有一些数据表(emp雇员表,dept部门表,salgrade薪水等级表,bonus奖金表)

用之前给scott用户解锁，可以先连接conn sys/密码 as sysdba

```sql
alter user scott account unlock; ——解锁
conn scott/tiger ——即可登录
```

**4、以超级管理员登录**

```sql
管理员输入指令：conn sys/密码 @orcl as sysdba 
操作员输入指令：conn sys/密码 @orcl as sysoper
```

@orcl表示连接标识符(服务器名，如果没有该标识符，SQL Plus会连接到默认数据库)(OracleOradb12gHome1TNSListener要启动)

```cmd
C:\Users\wd-pc>sqlplus sys/change_on_install as sysdba　
或
SQL>connect sys/change_on_install as sysdba
```

**5、以系统管理员登录**

```sql
conn system/密码
```

```cmd
SQL>connect system/manager as sysdba
```

**6、切换用户**

```cmd
SQL>conn hr/123456 
注：conn同connect
```

 **7、退出**

```cmd
SQL>exit
```

例子

```cmd
C:\Users\Administrator>sqlplus /nolog
SQL*Plus: Release 11.2.0.1.0 Production on 星期三 11月 1 0
Copyright (c) 1982, 2010, Oracle.  All rights reserved.
SQL> conn system/manager as sysdba     //以system用户登陆
已连接。
SQL> conn scott/123  //以scott用户登录
ERROR:
ORA-28002: the password will expire within 7 days
已连接。
SQL> conn sys/change_on_install as sysdba //以sys用户登陆,必须要加上as sysdba
已连接。
SQL> show user
USER 为 "SYS"
SQL>
```

例子

<img src="oracl.assets/image-20231030232756813.png" alt="image-20231030232756813" style="zoom:67%;" />

例子

<img src="oracl.assets/image-20231030232916427.png" alt="image-20231030232916427" style="zoom:67%;" />

解锁用户：       alter user scott account unlock;   

锁定用户：       alter user scott account lock;     

注意：只有管理员才有权限解锁和锁定用户！！！  

显示当前登录用户：    show user; 

DBA：数据库管理员  DB：database 数据库  DBMS：数据库管理系统

删除用户:drop user lxixi cascade;  cascade 级联删除    授权：创建的用户任何权限【我们需要对用户授权】       角色： connect resource dba       grant connect,resource,dba to lxixi    撤销权限：      revoke connect,resourc,dba from lxixi;

##  3.2 连接命令

**1.conn[ect]**

说明:：conn 用户名/密码@网络服务名[as sysdba/sysoper]当用特权用户身份连接时，必须带上as sysdba或是as sysoper

远程连接：sqlplus usr/pwd@//host:port/sid 如：conn sys/admin@127.0.0.1:1521/orcl as sysdba;

**2.disc[onnect]**

说明: 该命令用来断开与当前数据库的连接

**3.psssw[ord]**

说明: 该命令用于修改用户的密码，如果要想修改其它用户的密码，需要用sys/system登录。4.show user

说明: 显示当前用户名

**5.exit**

说明: 该命令会断开与数据库的连接，同时会退出sql*plus 

## 3.3 文件操作命令

**1.start和@**

说明: 运行sql脚本

案例: sql>@ d:\a.sql或是sql>start d:\a.sql

**2.edit**

说明: 该命令可以编辑指定的sql脚本

案例: sql>edit d:\a.sql,这样会把d:\a.sql这个文件打开

**3.spool**

说明: 该命令可以将sql*plus屏幕上的内容输出到指定文件中去。

案例: sql>spool d:\b.sql 并输入 sql>spool off 

##  3.4 交互式命令

**1.&**

说明：可以替代变量，而该变量在执行时，需要用户输入。

select * from emp where job='&job'；

**2.edit**

说明：该命令可以编辑指定的sql脚本

案例：SQL>edit d:\a.sql

**3.spool**

说明：该命令可以将sql*plus屏幕上的内容输出到指定文件中去。

spool d:\b.sql 并输入 spool off

## 3.5 显示和设置环境变量

概述：可以用来控制输出的各种格式，set show如果希望永久的保存相关的设置，可以去修改glogin.sql脚本

**1.linesize**

说明：设置显示行的宽度，默认是80个字符

```oracle
show linesize 
set linesize 90
```

**2.pagesize**

说明：设置每页显示的行数目，默认是14

```oracle
set pagesize 20
```

**3. time on**

```oracle
SQL> set time on
08:30:13 SQL>
```

#  四、oracle用户管理

**权限角色**

1、connect角色：

>  授予最终用户的典型权限，最基本的权利，能够连接到oracle数据库，并对其他用户的表有访问权限，做select、update、insert等操作

2、 resource角色：

> 是授予开发人员的，可以在自己的表空间创建表、序列

 3、dba角色：

> 是授予系统管理员的，拥有该角色的用户就能成为系统管理员了，它拥有所有的系统权限

## 4.1 创建用户及授权

概述：在oracle中要创建一个新的用户使用create user语句，<font color=red>一般是具有dba(数据库管理员)的权限才能进进行。</font>

create user 用户名 identified by 密码; (oracle有个毛病，密码必须以字母开头，如果以字母开头，它不会创建用户)

```sql
create user 用户名 identified by 密码;		# 创建用户
grant 权限 on 表空间.表名 to 用户名;			# 赋权限给用户
```

例子：

```sql
SQL> create user newuser identified by 123;			# 创建用户
User created.
SQL> grant connect,resource,dba to newuser;	        # 赋权限
Grant succeeded.
```

## 4.2 用户修改密码

概述：

+ 如果给自己修改密码可以直接使用

+ 如果给别人修改密码则需要具有dba的权限，或是拥有alter user的系统权限

```sql
SQL> password 用户名      #修改自己的密码
SQL> alter user 用户名 identified by 新密码  #修改别人的密码
```

## 4.3 删除用户

概述：<font color=red>一般以dba的身份去删除某个用户，如果用其它用户去删除用户则需要具有drop user的权限。</font>

在删除用户时，如果要删除的用户，已经创建了表，那么就需要在删除的时候带一个参数cascade; 

```sql
drop user 用户名 [cascade]
```

## 4.4 对权限的维护

\* 希望xiaoming用户可以去查询scott的emp表/还希望xiaoming可以把这个权限继续给别人。

**如果是对象权限**

```sql
grant select on emp to xiaoming with grant option
```

我的操作过程：

```sql
SQL> conn scott/tiger;
已连接。
SQL> grant select on scott.emp to xiaoming with grant option;
授权成功。
SQL> conn system/p;
已连接。
SQL> create user xiaohong identified by m123;
用户已创建。
SQL> grant connect to xiaohong;
授权成功。 
SQL> conn xiaoming/m12;
已连接。
SQL> grant select on scott.emp to xiaohong;
授权成功。 
```

**如果是系统权限**

system给xiaoming权限时：

```sql
 grant connect to xiaoming with admin option
```

**撤销权限**

问题：如果scott把xiaoming对emp表的查询权限回收，那么xiaohong会怎样？

答案：被回收。

下面是我的操作过程：

```sql
SQL> conn scott/tiger;
已连接。
SQL> revoke select on emp from xiaoming;
撤销成功。 
SQL> conn xiaohong/m123;
已连接。
SQL> select * from scott.emp;
SQL> ORA-00942: 表或视图不存在
```

## 4.5 用户管理的案例

概述：创建的新用户是没有任何权限的，甚至连登陆的数据库的权限都没有，需要为其指定相应的权限。给一个用户赋权限使用命令grant，回收权限使用命令revoke。

警告: 您不再连接到 ORACLE。

```sql
SQL> show user; 
USER 为 "" 
SQL> conn system/p;
已连接。 
SQL> grant connect to xiaoming;
授权成功。 
SQL> conn xiaoming/m12;
已连接。 
SQL>
```

注意：grant connect to xiaoming;

例子

\* 希望xiaoming用户可以去查询scott的emp表

```sql
 grant select on emp to xiaoming 
```

\* 希望xiaoming用户可以去修改scott的emp表

```sql
 grant update on emp to xiaoming
```

\* 希望xiaoming用户可以去修改/删除，查询，添加scott的emp表

```sql
 grant all on emp to xiaoming
```

\* scott希望收回xiaoming对emp表的查询权限

```sql
revoke select on emp from xiaoming 
```

## 4.6 使用profile管理用户口令

概述：profile是口令限制，资源限制的命令集合，当建立数据库的，oracle会自动建立名称为default的profile。当建立用户没有指定profile选项，那么oracle就会将default分配给用户。 

### 4.6.1 账户锁定

概述：指定该账户(用户)登陆时最多可以输入密码的次数，也可以指定用户锁定的时间(天)一般用dba的身份去执行该命令。

**profile方式锁定:**

例子:  指定scott这个用户最多只能尝试3次登陆，锁定时间为2天，让我们看看怎么实现。创建profile文件

```sql
SQL> create profile lock_account limit failed_login_attempts 3 password_lock_time 2; 
SQL> alter user scott profile lock_account; 
```

**普通方式锁定:**

```sql
alter user 用户名 account lock;
```

### 4.6.2 给用户解锁

```sql
alter user 用户名 account unlock;
```

例子:

```sql
SQL> alter user tea account unlock; 
```

### 4.6.3 终止口令

为了让用户定期修改密码可以使用终止口令的指令来完成，同样这个命令也需要dba的身份来操作。

例子：

给前面创建的用户tea创建一个profile文件，要求该用户每隔10天要修改自己的登陆密码，宽限期为2天。看看怎么做。

```sql
SQL> create profile myprofile limit password_life_time 10 password_grace_time 2; 
SQL> alter user tea profile myprofile;
```

### 4.6.4 口令历史

概述：如果希望用户在修改密码时，不能使用以前使用过的密码，可使用口令历史，这样oracle就会将口令修改的信息存放到数据字典中，这样当用户修改密码时，oracle就会对新旧密码进行比较，当发现新旧密码一样时，就提示用户重新输入密码。

例子：

password_reuse_time //指定口令可重用时间即10天后就可以重用

```sql
-- 1）建立profile
SQL>create profile password_history limit password_life_time 10 password_grace_time 2 password_reuse_time 10 
-- 2）分配给某个用户 
SQL> alter user tea profile password_history;
```

### 4.6.5 删除profile

概述：当不需要某个profile文件时，可以删除该文件。

```sql
SQL> drop profile password_history [casade]
```

注意：文件删除后，用这个文件去约束的那些用户通通也都被释放了。加了casade，就会把级联的相关东西也给删除掉

## 4.7 其他

```sql
# 查看当前用户
show user;
# 查看当前用户表空间的表
select table_name from user_tables;
# 修改用户密码
alter user 用户名 identified by 密码;
# 创建表空间
create tablespace 空间名 datafile '存放文件路径' size 空间大小;
# 设置当前用户默认使用的表空间
alter database default tablespace 表空间;
# 修改表空间的名字
alter tablespace 旧名 rename to 新名;
# 删除表空间
drop tablespace 表空间名 including contents and datafiles;
```

# 五、数据库oracle与mysql区别:crossed_swords:

## 5.1 数据类型

### 5.1.1 Number类型

+ MySQL中是没有Number类型的，但有int、decimal 、tinyint、smallint、mediumint、bigint等类型

+ Oracle中

  + Number(5,1) 对应MySQL中的decimal(5,1)
  + Number(5) 对应int(5), mysql8.0直接用int
  + 没有int、decimal 、tinyint、smallint、mediumint、bigint等类型

###  5.1.2 Varchar2(n)类型

+ MySQL中用varchar(n)替代Oracle Varchar2(n)类型
+ Oracle中
  + 有CHAR、NCHAR、VARCHAR2和NVARCHAR2类型

###  5.1.3 Date 类型

+ MySQL 中的日期时间类型有Date、Time、Datetime等类型
  + MySQL中Date类型仅表示日期(年-月-日)
  + Time类型仅表示时间（时:分:秒)
  + Datetime类型表示日期时间(年-月-日 时:分:秒)
  
+ Oracle中的Date类型和MySQL中的Datetime类型一致, 

  + ORACLE中默认的日期格式`DD-MON--YY`如 '09-6月-99'表示1999年6月9号

  + 改日期的默认格式

    ```sql
    alter session set nls-date-format ='yyyy-mm-dd';
    insert into student values('A002','MIKE','男'，'1905-05-06'，10)；  #ok
    ```

+ 例子

  ```sql
  -- 日期类型
  08:46:08 SQL> insert into st values('信息', '1999-12-02');
  insert into st values('信息', '1999-12-02')
                                *
  第 1 行出现错误:
  ORA-01861: 文字与格式字符串不匹配
  
  
  08:47:20 SQL> insert into st values('信息', '1999-12月-02');
  insert into st values('信息', '1999-12月-02')
                                *
  第 1 行出现错误:
  ORA-01861: 文字与格式字符串不匹配
  08:47:31 SQL> insert into st values('信息', '09-12月-1999');  #ok
  ```

## 5.2 创建表空间/数据库

### 5.2.1  Oracle创建表空间(数据库)

**创建表空间**

```sql
create tablespace 表空间名称 logging datafile '路径\名称.dbf' size 2000m autoextend on next 500m maxsize 30720m extent management local;
```

示例： 

```sql
create tablespace NWZC logging datafile 'D:\javautils\oracle1\oradata\ORCL\zuigaofa.dbf' size 2000m autoextend on next 500m maxsize 30720m extent management local;
```

![img](oracl.assets/6c1650acb3094c24a83ab6447b218157.png)

**创建用户**

```sql
create user 用户名 identified by 密码 default tablespace 表空间名;
```

切换到指定用户，修改用户默认表空间：

```sql
alter database default tablespace 表空间;
```

示例： 

```sql
alter database  default tablespace NWZC;
```

![image-20231103203348575](oracl.assets/image-20231103203348575.png)

**授权** 

```sql
grant exp_full_database to 用户名 ;
grant imp_full_database to 用户名 ;
grant resource to 用户名 ;
grant connect to 用户名 ;
grant dba to 用户名 ;
```

示例：

```sql
grant exp_full_database to NWZC;
grant imp_full_database to NWZC;
grant resource to NWZC;
grant connect to NWZC;
grant dba to NWZC;
```

<img src="oracl.assets/65691c818e304135abce41a2e2f49683.png" alt="img" style="zoom: 80%;" />

### 5.2.2 MySQL创建数据库

```sql
-- 查询数据库
SHOW DATABASES;
-- 创建数据库
CREATE DATABASE 数据库名称;
-- 创建数据库(判断，如果不存在则创建)
CREATE DATABASE IF NOT EXISTS 数据库名称;
 
-- 查看当前使用的数据库
SELECT DATABASE();
-- 使用数据库
USE 数据库名称;
```

## 5.3 删除表空间/数据库

### 5.3.1  Oracle删除表空

1、删除无任何数据对象的表空间：

```sql
drop tablespace xxx
```

2、删除有任何数据对象的表空间

```sql
drop tablespace xxx including contents and datafiles;
```

### 5.3.2 MySQL删除数据库

```sql
-- 删除数据库
DROP DATABASE 数据库名称;
-- 删除数据库(判断，如果存在则删除)
DROP DATABASE IF EXISTS 数据库名称;
```



## 5.4 创建临时表

### 5.4.1 Oracle创建临时表

Oracle临时表默认所有会话内可见，一旦创建就会存在，直到显式删除。可以设置临时表仅在当前会话内或事务内可见。

```sql
CREATE GLOBAL TEMPORARY TABLE temp_table (
    id NUMBER,
    name VARCHAR2(50)
) ON COMMIT DELETE ROWS;
```

ON COMMIT DELETE ROWS指定了当事务提交时，临时表中的所有行都会被删除。这保证了当会话结束时，所有临时数据都会被清除。 

**设置临时表消失的时机：**

- ON COMMIT DELETE ROWS ：数据行只有在当前事务中可见，也是默认值,事务提交后数据行将消失
- ON COMMIT PRESERVE ROWS ：数据行仅在当前会话中可见

**临时表中数据的增删改查，跟普通表一致：**

```sql
Insert into tmp_gttable (id,name) values(1,'test');
Update tmp_gttable set name = 'test_update' where id = 1；
Delete from tmp_gttable where id = 1;
```

### 5.4.2 MySQL创建临时

MySQL临时表只在当前会话可见，一旦会话关闭，临时表会自动删除。

```sql
CREATE TEMPORARY TABLE 表名 (字段列表);
```

示例如下：

```sql
CREATE TEMPORARY TABLE tmp_table (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    PRIMARY KEY (id)
) ENGINE=InnoDB;
```

临时表创建成功后，可以使用SELECT、INSERT、UPDATE、DELETE等语句对其进行操作，与普通表的语法相同。

## 5.5 insert语法

### 5.5.1 Oracle创建表和插入记录

```sql
# 在Oracle中批量添加时
insert all
into student (id,name,sex) values ('01','小明','男')
into student (id,name,sex)values ('02'，'小红','女')

# 在Oracle中批量添加时, 可以同时对多个表进行批量添加
insert all
into student (id,name,sex) values ('01','小明','男')
into student (id,name,sex) values ('02'，'小红','女')
into teacher (id,name,sex) values ('01'，'王老师','女')
into teacher (id,name,sex) values ('02'，'李老师','女')
```

### 5.5.2 MySQL创建表和插入记录

```sql
# 在MySQL中批量添加时
insert into student (id,name,sex)
values  
(01,'小明','男'),
(02,'小明','男'),
(03,'小明','男');
```

MySQL插入日期使用now() 或 sysdate()，可以插入多条，使用逗号隔开
删表数据：Oracle可以省略from：delete from t_student; (删除所有数据)

**外键约束：**Oracle是constraints, MySQL是constraint

级联操作：

- Oracle：on delete set null 或者on delete cascade
- MySQL: on delete set null on update CASCADE

## 5.6 分页

+ MySQL通过limit来获取前n条记录

+ Oracle可通过rownum获取前n条记录
+ 在Oracle中rownum作为where条件的一部分，而MySQL中limit不是where条件的一部分。   

### 5.6.1 Oracle：rownum

```sql
-- oracle
-- rownum语法如下：
SELECT * FROM XJ_STUDENT WHERE ROWNUM = 1; -- 查询第一条数据
SELECT * FROM XJ_STUDENT WHERE ROWNUM <= 10; -- 获取前10条数据
-- 但rownum不支持查询后几条或第n(n>1)条数据，例如以下sql是不支持的
SELECT * FROM XJ_STUDENT WHERE ROWNUM > 2;  #报错
SELECT * FROM XJ_STUDENT WHERE ROWNUM = 3;  #报错
```

### 5.6.2 MySQL：limit

```sql
-- mysql
-- limit 语法如下：
select * from test2 order by sid desc limit 0,5;
SELECT * from fw_department limit 3; -- 查询前3条数据
SELECT * from fw_department limit 2, 4; -- 从第2(序号从0开始)条开始，查4条记录
```

## 5.7 函数

**1. length(str)函数**

+ MySQL 中对应的函数为char_length(str)
+ Oracle中的length(str)是获取字符串长度的函数

**2. sys_guid()函数**

+ MySQL中通过UUID()生成随机序列 
+ Oracle中通过sys_guid()函数是生成随机序列

**3. 时间格式化函数**

+ 将时间转换为字符串型时间
  + MySQL中date_format(NOW(),'%Y-%m-%d')  
  + 对应Oracle中的to_char(sysdate, 'YYYY-MM-DD')

+ 将字符串型时间转换为时间类型
  + MySQL 中str_to_date('2019-01-01','%Y-%m-%d') 
  + 对应Oracle中的 to_date('2019-01-01', 'YYYY-MM-DD')

+ MySQL 中包括时分秒的函数转换：DATE_FORMAT(NOW(),'%Y-%m-%d %H:%i:%s')，str_to_date('2019-01-01','%Y-%m-%d %H:%i:%s')

**4. 条件函数（nvl()、nvl2()、decode()）**

+ nvl(tab.columnName, 0)：如果tab.columnName值为空，则返回值取0，否则取tab.columnName；对应的MySQL函数为：ifnull(tab.columnName, 0)

+ nvl2(expr1,expr2,expr3)：如果expr1不为null，则返回expr2，否则返回expr3；对应的MySQL函数为：if(expr1,expr2,expr3)。

+ DECODE(value, val1, val2, val3)：如果value等于val1，则返回val2，否则返回val3；MySQL可用IF函数表示：if(value=val1, val2, val3)；

+ DECODE(value, if1, val1, if2,val2,...,ifn, valn, val)：如果value等于if1，则返回val1，如果value等于if2，则返回value2...如果value等于ifn，则返回valn，否则返回val；MySQL对于这种判断可以通过case when then else end;l来判断，即：case when value=if1 then val1 when value=if2 then val2,,,when value=ifn then valn else val end;

**5. trunc()函数**

+ TRUNC(12.123)：返回整数(12)；MySQL对应的函数：truncate(12.123, 0)；

+ TRUNC(12.123, 2)：返回值保留2为小数(12.12)；MySQL对应的函数：truncate(12.123, 2)；

+ TRUNC(SYSDATE)：返回值为(2019-07-26 00:00:00)；MySQL对应的为cast(now() as datetime)：返回值为(2019-07-26 14:11:38)；

+ MySQL的cast函数语法为：CAST(xxx AS 类型) （可用类型为：二进制,同带binary前缀的效果:BINARY；字符型,可带参数:CHAR()；日期:DATE；时间:TIME；日期时间型: DATETIME；浮点数: DECIMAL；整数:SIGNED；无符号整数:UNSIGNED）

**6. to_char() to_number()**

+ to_char(123)：将数字123转换为字符串123；MySQL对应的函数为CAST(123 AS CHAR(3))；

+ to_number('123')：将字符串数字123转换为数字类型；MySQL对应的函数为cast('123' as SIGNED)；

**7. sysdate 当前时间**

+  sysdate：返回当前日期+时间
+  MySQL对应的函数为 now()

## 5.8 其他

**1. 引号**

+ MySQL可识别双引号和单引号
+ Oracle只能识别单引号

**2. 字符串连接符 ||** 

+ Oracle 可用'||'来连接字符串
+ MySQL不支持'||'连接，MySQL可通过concat()函数链接字符串。

```sql
--Oracle的
a.studentname||'【'||a.studentno||'】'
--相当于 MySQL的 
concat(a.studentname, '【', a.studentno, '】')
```

**3. ROWNUM**

+ MySQL通过limit来获取前n条记录

+ Oracle可通过rownum获取前n条记录
+ 在Oracle中rownum作为where条件的一部分，而MySQL中limit不是where条件的一部分。   

```sql
-- oracle
-- rownum语法如下：
SELECT * FROM XJ_STUDENT WHERE ROWNUM = 1; -- 查询第一条数据
SELECT * FROM XJ_STUDENT WHERE ROWNUM <= 10; -- 获取前10条数据
-- 但rownum不支持查询后几条或第n(n>1)条数据，例如以下sql是不支持的
SELECT * FROM XJ_STUDENT WHERE ROWNUM > 2;  #报错
SELECT * FROM XJ_STUDENT WHERE ROWNUM = 3;  #报错

-- mysql
-- limit 语法如下：
SELECT * from fw_department limit 3; -- 查询前3条数据
SELECT * from fw_department limit 2, 4; -- 从第2(序号从0开始)条开始，查4条记录
```

**4. 空数据排序(nulls first 和nulls last)**

```sql
-- null值排在最前
SELECT * FROM FW_DEPARTMENT A ORDER BY A.REMARK DESC NULLS FIRST
-- null值排在最后
SELECT * FROM FW_DEPARTMENT A ORDER BY A.REMARK DESC NULLS LAST
 
-- MySQL 可通过IF和ISNULL函数达到相同的效果
-- null值排在最后
select * from FW_DEPARTMENT A order by IF(ISNULL(A.REMARK),1,0),A.REMARK desc
-- null值排在最前
select * from FW_DEPARTMENT A order by IF(ISNULL(A.REMARK),0,1),A.REMARK desc
```

**5. 表(左/右)关联(+)**

+ MySQL只能使用left join 和 right join

+ Oracle左连接,右连接可以使用(+)来实现

```sql
-- Oracle 左关联
select * from taba, tabb where taba.id = tabb.id(+);
-- Oracle 右关联
select * from taba, tabb where taba.id(+) = tabb.id;

-- MySQL 左关联
select * from taba left join tabb on taba.id=tabb.id;
-- MySQL 右关联
select * from taba right join tabb on taba.id=tabb.id;
```

**6. 删除语法**

MySQL的删除语法没有Oracle那么随意，例如下面的sql在Oracle中可以执行，但在MySQL中就不可以。注意: mysql8.0后可以

```sql
-- Oracle 可执行，但MySQL中不能执行
DELETE FROM FW_DEPARTMENT A WHERE A.DEPID = '111';
DELETE FW_DEPARTMENT WHERE DEPID = '111';

-- MySQL中删除语句格式如下：
DELETE FROM FW_DEPARTMENT WHERE DEPID = '111';
```

**7. 递归查询(start with connect by prior)**

MySQL不支持(start with connect by prior)的这种递归查询，但可以通过自定义函数来实现。

```sql
-- Oracle 递归查询 查询部门ID为‘1111’的所有子部门（包含自身）
SELECT *
FROM FW_DEPARTMENT
START WITH DEPID='1111'
CONNECT BY PRIOR DEPID = PARENTDEPID;
-- Oracle 递归查询 查询部门ID为‘1111’的所有父部门（包含自身）
SELECT *
FROM FW_DEPARTMENT
START WITH DEPID='1111'
CONNECT BY PRIOR PARENTDEPID = DEPID;

-- MySQL 先创建fun_getDepIDList函数，用于查询部门ID字符串
CREATE FUNCTION fun_getDepIDList(rootId VARCHAR(32))
RETURNS VARCHAR(6000)
BEGIN 
	DECLARE pTemp VARCHAR(6000);
	DECLARE cTemp VARCHAR(6000);
	SET pTemp='$';
	SET cTemp=rootId;
	WHILE cTemp is not null DO
		set pTemp=CONCAT(pTemp,',',cTemp);
		SELECT GROUP_CONCAT(depid) INTO cTemp from fw_department
		WHERE FIND_IN_SET(PARENTDEPID,cTemp)>0;
	END WHILE;
	RETURN pTemp;
END;

-- 查询部门ID为‘1111’的所有子部门（包含自己）
select * from fw_department
where FIND_IN_SET(DEPID, fun_getDepIDList('1111'));

-- 查询部门ID为‘1111’的所有父部门(包含自己)
select * from fw_department
where FIND_IN_SET('1111', fun_getDepIDList(DEPID));
```

**8. merge into**

MySQL不支持（merge into），但提供的replace into 和on duplicate key update可实现相似的功能。

```sql
-- Oracle merge into (有则修改，无则新增)
MERGE INTO TMPDEPTAB A
USING (SELECT '1111' DEPID, '哈哈' DEPNAME FROM DUAL) B
ON (A.DEPID = B.DEPID)
WHEN MATCHED THEN 
	UPDATE SET A.DEPNAME = B.DEPNAME
WHEN NOT MATCHED THEN 
	INSERT(DEPID, DEPNAME) VALUES(B.DEPID, B.DEPNAME);

-- MySQL replace into (特点：1、先删后增； 2、插入/更新的表必须有主键或唯一索引；
-- 3、未修改/新增的数据项，如果必填，则必须有默认值)
-- 1、由于是先删后增，所以需要满足以下2个条件之一：
--      1.要么必填项有默认值； 
--      2.要么插入/更新时为没有默认值的必填项赋值， 否则新增时会报错。
-- 2、表中需要有主键或唯一索引，否则下面语句如果执行多次，表中会出现重复数据。
replace into fw_department(DEPID,PARENTDEPID,DEPNO,DEPNAME) 
values('1111111', '1234','123', '哈哈');

-- MySQL on duplicate key update (特点：1、插入/更新的表必须有主键或唯一索引；
-- 2、未修改/新增的数据项，如果必填，则必须有默认值)
insert into fw_department(depid,parentdepid,depno,depname)
select '1111111' depid, '123' parentdepid, 'e12' depno, '哈哈哈哈' depname
from fw_department
on duplicate key 
update parentdepid = values(parentdepid),
	depno=values(depno),
	depname=values(depname);
```

## 十、 oracle表的管理(杂)

[Oracle的DCL、DDL、DML语言学习使用](https://blog.csdn.net/qq_29864051/article/details/131294279?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~OPENSEARCH~Rate-1-131294279-blog-50623974.235^v38^pc_relevant_sort_base1&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~OPENSEARCH~Rate-1-131294279-blog-50623974.235^v38^pc_relevant_sort_base1&utm_relevant_index=2)

数据类型，表创建删除，数据 CRUD操作

· 5.oracle数据库的创建
期望目标 

· 1.掌握oracle表的管理（创建/维护）

· 2.掌握对oracle表的各种查询技巧 

· 3.学会创建新的oracle数据库 

oracle的表的管理

表名和列的命名规则

· 必须以字母开头

· 长度不能超过30个字符

· 不能使用oracle的保留字

· 只能使用如下字符 A-Z，a-z，0-9，$,#等

oracle支持的数据类型

n 字 符类 

char  定长 最大2000个字符。

例子：char(10) ‘小韩’前四个字符放‘小韩’，后添6个空格补全 如‘小韩   ’ varchar2(20) 变长 最大4000个字符。

例子：varchar2（10） ‘小韩’ oracle分配四个字符。这样可以节省空间。

clob(character large object) 字符型大对象 最大4G

char 查询的速度极快浪费空间，查询比较多的数据用。

varchar 节省空间 

n 数字型

number范围 -10的38次方 到 10的38次方

可以表示整数，也可以表示小数 

number(5,2)

表示一位小数有5位有效数，2位小数

范围：-999.99到999.99

number(5)

表示一个5位整数

范围99999到-99999 

n 日期类型 

date 包含年月日和时分秒  oracle默认格式 1-1月-1999 

timestamp 这是oracle9i对date数据类型的扩展。可以精确到毫秒。

n 图片 

blob 二进制数据 可以存放图片/声音 4G  一般来讲，在真实项目中是不会把图片和声音真的往数据库里存放，一般存放图片、视频的路径，如果安全需要比较高的话，则放入数据库。怎样创建表 

n 建表 

--学生表 

create table student (  ---表名

​     xh    number(4),  --学号

​     xm  varchar2(20),  --姓名

​     sex   char(2),   --性别

​     birthday date,     --出生日期

​     sal   number(7,2)  --奖学金

); 

--班级表 

CREATE TABLE class(

classId NUMBER(2),

cName VARCHAR2(40)

);

修改表

n 添加一个字段

SQL>ALTER TABLE student add (classId NUMBER(2)); 
n 修改一个字段的长度

SQL>ALTER TABLE student MODIFY (xm VARCHAR2(30));

 n 修改字段的类型/或是名字（不能有数据） 不建议做

SQL>ALTER TABLE student modify (xm CHAR(30)); 

n 删除一个字段 不建议做(删了之后，顺序就变了。加就没问题，应为是加在后面) 

SQL>ALTER TABLE student DROP COLUMN sal; 

n 修改表的名字  很少有这种需求

SQL>RENAME student TO stu; 

n 删除表 

SQL>DROP TABLE student;

添加数据 

n 所有字段都插入数据

INSERT INTO student VALUES ('A001', '张三', '男', '01-5月-05', 10); 

oracle中默认的日期格式‘dd-mon-yy’ dd日子（天） mon 月份 yy 2位的年 ‘09-6月-99’ 1999年6月9日

修改日期的默认格式（临时修改，数据库重启后仍为默认；如要修改需要修改注册表）

ALTER SESSION SET NLS_DATE_FORMAT ='yyyy-mm-dd';

修改后，可以用我们熟悉的格式添加日期类型：

 INSERT INTO student VALUES ('A002', 'MIKE', '男', '1905-05-06', 10); 

n 插入部分字段

INSERT INTO student(xh, xm, sex) VALUES ('A003', 'JOHN', '女');

 n 插入空值

INSERT INTO student(xh, xm, sex, birthday) VALUES ('A004', 'MARTIN', '男', null);

问题来了，如果你要查询student表里birthday为null的记录，怎么写sql呢？

错误写法：select * from student where birthday = null;

正确写法：select * from student where birthday is null;

如果要查询birthday不为null,则应该这样写：

 select * from student where birthday is not null;

修改数据

n 修改一个字段

UPDATE student SET sex = '女' WHERE xh = 'A001'; 

n 修改多个字段

UPDATE student SET sex = '男', birthday = '1984-04-01' WHERE xh = 'A001';

修改含有null值的数据

不要用 = null 而是用 is null；

 SELECT * FROM student WHERE birthday IS null;

n 删除数据

DELETE FROM student;

删除所有记录，表结构还在，写日志，可以恢复的，速度慢。

Delete 的数据可以恢复。

savepoint a; --创建保存点

DELETE FROM student; 

rollback to a; --恢复到保存点

一个有经验的DBA，在确保完成无误的情况下要定期创建还原点。

DROP TABLE student; --删除表的结构和数据；

 delete from student WHERE xh = 'A001'; --删除一条记录；

 truncate TABLE student; --删除表中的所有记录，表结构还在，不写日志，无法找回删除的记录，速度快。

### oracle表查询(1)

n 介绍

在我们讲解的过程中我们利用scott用户存在的几张表（emp，dept）为大家演示如何使用select语句，select语句在软件编程中 非常有用，希望大家好好的掌握。

emp 雇员表 

clerk 普员工

salesman 销售

manager 经理

analyst 分析师

president 总裁

mgr 上级的编号

hiredate 入职时间

sal 月工资

comm 奖金

deptno 部门
dept部门表

deptno 部门编号

accounting 财务部

research 研发部

operations 业务部

loc 部门所在地点

salgrade  工资级别

grade  级别

losal  最低工资

hisal  最高工资

简单的查询语句

n 查看表结构

DESC emp;

 n 查询所有列

SELECT * FROM dept;

切忌动不动就用select *

SET TIMING ON; 打开显示操作时间的开关，在下面显示查询时间。

CREATE TABLE users(userId VARCHAR2(10), uName VARCHAR2 (20), uPassw VARCHAR2(30)); 

INSERT INTO users VALUES('a0001', '啊啊啊啊', 'aaaaaaaaaaaaaaaaaaaaaaa');

 --从自己复制，加大数据量 大概几万行就可以了 可以用来测试sql语句执行效率

INSERT INTO users (userId,UNAME,UPASSW) SELECT * FROM users; 

SELECT COUNT (*) FROM users;统计行数

n 查询指定列

SELECT ename, sal, job, deptno FROM emp; 

n 如何取消重复行DISTINCT

SELECT DISTINCT deptno, job FROM emp;

?查询SMITH所在部门，工作，薪水

SELECT deptno,job,sal FROM emp WHERE ename = 'SMITH';

注意：oracle对内容的大小写是区分的，所以ename='SMITH'和ename='smith'是不同的

n 使用算术表达式 nvl null

问题：如何显示每个雇员的年工资？

SELECT sal*13+nvl(comm, 0)*13 "年薪" , ename, comm FROM emp;

 n 使用列的别名

SELECT ename "姓名", sal*12 AS "年收入" FROM emp;

 n 如何处理null值

使用nvl函数来处理

n 如何连接字符串（||）

SELECT ename || ' is a ' || job FROM emp; 

n 使用where子句

问题：如何显示工资高于3000的 员工？

 SELECT * FROM emp WHERE sal > 3000;

问题：如何查找1982.1.1后入职的员工？

 SELECT ename,hiredate FROM emp WHERE hiredate >'1-1月-1982';

问题：如何显示工资在2000到3000的员工？

 SELECT ename,sal FROM emp WHERE sal >=2000 AND sal <= 3000;

n 如何使用like操作符 

%：表示0到多个字符 _：表示任意单个字符

问题：如何显示首字符为S的员工姓名和工资？

SELECT ename,sal FROM emp WHERE ename like 'S%';

如何显示第三个字符为大写O的所有员工的姓名和工资？

SELECT ename,sal FROM emp WHERE ename like '__O%'; 

n 在where条件中使用in

问题：如何显示empno为7844, 7839,123,456 的雇员情况？

SELECT * FROM emp WHERE empno in (7844, 7839,123,456); 

n 使用is null的操作符

问题：如何显示没有上级的雇员的情况？

错误写法：select * from emp where mgr = '';

正确写法：SELECT * FROM emp WHERE mgr is null; 

###  oracle表查询(2)

n 使用逻辑操作符号

问题：查询工资高于500或者是岗位为MANAGER的雇员，同时还要满足他们的姓名首字母为大写的J？

 SELECT * FROM emp WHERE (sal >500 or job = 'MANAGER') and ename LIKE 'J%'; 

n 使用order by 字句  默认asc

问题：如何按照工资的从低到高的顺序显示雇员的信息？

 SELECT * FROM emp ORDER by sal;

问题：按照部门号升序而雇员的工资降序排列

SELECT * FROM emp ORDER by deptno, sal DESC; 

n 使用列的别名排序

问题：按年薪排序

select ename, (sal+nvl(comm,0))*12 "年薪" from emp order by "年薪" asc;

别名需要使用“”号圈中,英文不需要“”号

n 分页查询

等学了子查询再说吧。。。。。。。。

Clear 清屏命令

oracle表复杂查询

n 说明

在实际应用中经常需要执行复杂的数据统计，经常需要显示多张表的数据，现在我们给大家介绍较为复杂的select语句

n数据分组 ——max，min， avg， sum， count

问题：如何显示所有员工中最高工资和最低工资？

SELECT MAX(sal),min(sal) FROM emp e; 

最高工资那个人是谁？

错误写法：select ename, sal from emp where sal=max(sal);

正确写法：select ename, sal from emp where sal=(select max(sal) from emp);

注意：select ename, max(sal) from emp;这语句执行的时候会报错，说ORA-00937：非单组分组函数。因为max是分组函数，而ename不是分组函数.......

但是select min(sal), max(sal) from emp;这句是可以执行的。因为min和max都是分组函数，就是说：如果列里面有一个分组函数，其它的都必须是分组函数，否则就出错。这是语法规定的

问题：如何显示所有员工的平均工资和工资总和？

问题：如何计算总共有多少员工问题：如何

扩展要求：

查询最高工资员工的名字，工作岗位

SELECT ename, job, sal FROM emp e where sal = (SELECT MAX(sal) FROM emp);

显示工资高于平均工资的员工信息

SELECT * FROM emp e where sal > (SELECT AVG(sal) FROM emp); 

n group by 和 having子句

group by用于对查询的结果分组统计，

having子句用于限制分组显示结果。

问题：如何显示每个部门的平均工资和最高工资？

SELECT AVG(sal), MAX(sal), deptno FROM emp GROUP by deptno;

（注意：这里暗藏了一点，如果你要分组查询的话，分组的字段deptno一定要出现在查询的列表里面，否则会报错。因为分组的字段都不出现的话， 就没办法分组了）

问题：显示每个部门的每种岗位的平均工资和最低工资？ 

SELECT min(sal), AVG(sal), deptno, job FROM emp GROUP by deptno, job;

问题：显示平均工资低于2000的部门号和它的平均工资？

SELECT AVG(sal), MAX(sal), deptno FROM emp GROUP by deptno having AVG(sal) < 2000; 

n 对数据分组的总结

1 分组函数只能出现在选择列表、having、order by子句中(不能出现在where中) 

2 如果在select语句中同时包含有group by, having, order by 那么它们的顺序是group by, having, order by 

3 在选择列中如果有列、表达式和分组函数，那么这些列和表达式必须有一个出现在group by 子句中，否则就会出错。

如SELECT deptno, AVG(sal), MAX(sal) FROM emp GROUP by deptno HAVING AVG(sal) < 2000;

这里deptno就一定要出现在group by 中

多表查询

n 说明

多表查询是指基于两个和两个以上的表或是视图的查询。在实际应用中，查询单个表可能不能满足你的需求，（如显示sales部门位置和其员工的姓 名），这种情况下需要使用到（dept表和emp表）

问题：显示雇员名，雇员工资及所在部门的名字【笛卡尔集】？

规定：多表查询的条件是 至少不能少于 表的个数-1 才能排除笛卡尔集

（如果有N张表联合查询，必须得有N-1个条件，才能避免笛卡尔集合）

SELECT e.ename, e.sal, d.dname FROM emp e, dept d WHERE e.deptno = d.deptno;

问题：显示部门号为10的部门名、员工名和工资？

 SELECT d.dname, e.ename, e.sal FROM emp e, dept d WHERE e.deptno = d.deptno and e.deptno = 10;

问题：显示各个员工的姓名，工资及工资的级别？

先看salgrade的表结构和记录

SQL>select * from salgrade;

GRADE     LOSAL     HISAL 

-------------  -------------  ------------

 1       700       200 
    2       1201     1400 
    3       1401     2000 
    4       2001     3000 
    5       3001     9999 
SELECT e. ename, e.sal, s.grade FROM emp e, salgrade s WHERE e.sal BETWEEN s.losal AND s.hisal;

扩展要求：

问题：显示雇员名，雇员工资及所在部门的名字，并按部门排序？

 SELECT e.ename, e.sal, d.dname FROM emp e, dept d WHERE e.deptno = d.deptno ORDER by e.deptno;

（注意：如果用group by，一定要把e.deptno放到查询列里面）

n 自连接

自连接是指在同一张表的连接查询

问题：显示某个员工的上级领导的姓名？

比如显示员工‘FORD’的上级

SELECT worker.ename, boss.ename FROM emp worker,emp boss WHERE worker.mgr = boss.empno AND worker.ename = 'FORD';

子查询 

n 什么是子查询

子查询是指嵌入在其他sql语句中的select语句，也叫嵌套查询。

n 单行子查询

单行子查询是指只返回一行数据的子查询语句

请思考：显示与SMITH同部门的所有员工？

思路：

1 查询出SMITH的部门号

select deptno from emp WHERE ename = 'SMITH'; 

2 显示

SELECT * FROM emp WHERE deptno = (select deptno from emp WHERE ename = 'SMITH');

数据库在执行sql 是从左到右扫描的， 如果有括号的话，括号里面的先被优先执行。

n 多行子查询

多行子查询指返回多行数据的子查询

请思考：如何查询和部门10的工作相同的雇员的名字、岗位、工资、部门号

SELECT DISTINCT job FROM emp WHERE deptno = 10; 

SELECT * FROM emp WHERE job IN (SELECT DISTINCT job FROM emp WHERE deptno = 10);

（注意：不能用job=..，因为等号=是一对一的）

n 在多行子查询中使用all操作符

问题：如何显示工资比部门30的所有员工的工资高的员工的姓名、工资和部门号？

 SELECT ename, sal, deptno FROM emp WHERE sal > all (SELECT sal FROM emp WHERE deptno = 30);

扩展要求：

大家想想还有没有别的查询方法。

SELECT ename, sal, deptno FROM emp WHERE sal > (SELECT MAX(sal) FROM emp WHERE deptno = 30);

执行效率上， 函数高得多 

n 在多行子查询中使用any操作符

问题：如何显示工资比部门30的任意一个员工的工资高的员工姓名、工资和部门号？

 SELECT ename, sal, deptno FROM emp WHERE sal > ANY (SELECT sal FROM emp WHERE deptno = 30);

扩展要求：

大家想想还有没有别的查询方法。

SELECT ename, sal, deptno FROM emp WHERE sal > (SELECT min(sal) FROM emp WHERE deptno = 30); 

n 多列子查询

单行子查询是指子查询只返回单列、单行数据，多行子查询是指返回单列多行数据，都是针对单列而言的，而多列子查询是指查询返回多个列数据的子查询 语句。

请思考如何查询与SMITH的部门和岗位完全相同的所有雇员。

SELECT deptno, job FROM emp WHERE ename = 'SMITH'; 

SELECT * FROM emp WHERE (deptno, job) = (SELECT deptno, job FROM emp WHERE ename = 'SMITH'); 

n 在from子句中使用子查询

请思考：如何显示高于自己部门平均工资的员工的信息

思路：

\1. 查出各个部门的平均工资和部门号

SELECT deptno, AVG(sal) mysal FROM emp GROUP by deptno; 

\2. 把上面的查询结果看做是一张子表

SELECT e.ename, e.deptno, e.sal, ds.mysal FROM emp e, (SELECT deptno, AVG(sal) mysal FROM emp GROUP by deptno) ds WHERE e.deptno = ds.deptno AND e.sal > ds.mysal;

如何衡量一个程序员的水平？

网络处理能力， 数据库， 程序代码的优化程序的效率要很高

小总结：

在这里需要说明的当在from子句中使用子查询时，该子查询会被作为一个视图来对待，因此叫做内嵌视图，当在from子句中使用子查询时，必须给 子查询指定别名。

注意：别名不能用as，如：SELECT e.ename, e.deptno, e.sal, ds.mysal FROM emp e, (SELECT deptno, AVG(sal) mysal FROM emp GROUP by deptno) as ds WHERE e.deptno = ds.deptno AND e.sal > ds.mysal;

在ds前不能加as，否则会报错 （给表取别名的时候，不能加as；但是给列取别名，是可以加as的）

n 分页查询

按雇员的id号升序取出

oracle的分页一共有三种方式

1.根据rowid来分

 select * from t_xiaoxi where rowid in (select rid from (select rownum rn, rid from(select rowid rid, cid from t_xiaoxi order by cid desc) where rownum<10000) where rn>9980) order by cid desc;

执行时间0.03秒

2.按分析函数来分

select * from (select t.*, row_number() over(order by cid desc) rk from t_xiaoxi t) where rk<10000 and rk>9980;

执行时间1.01秒 

3.按rownum来分

 select * from (select t.*,rownum rn from(select * from t_xiaoxi order by cid desc)t where rownum<10000) where rn>9980;

执行时间0.1秒

其中t_xiaoxi为表名称，cid为表的关键字段，取按cid降序排序后的第9981-9999条记录，t_xiaoxi表有70000多条 记录。

个人感觉1的效率最好，3次之，2最差。

//测试通过的分页查询okokok 

select * from (select a1.*, rownum rn from(select ename,job from emp) a1 where rownum<=10)where rn>=5;

下面最主要介绍第三种：按rownum来分

\1. rownum 分页

SELECT * FROM emp; 

\2. 显示rownum[oracle分配的] 

SELECT e.*, ROWNUM rn FROM (SELECT * FROM emp) e;

rn相当于Oracle分配的行的ID号

3.挑选出6—10条记录

先查出1-10条记录

SELECT e.*, ROWNUM rn FROM (SELECT * FROM emp) e WHERE ROWNUM <= 10;

如果后面加上rownum>=6是不行的，

 \4. 然后查出6-10条记录 

SELECT * FROM (SELECT e.*, ROWNUM rn FROM (SELECT * FROM emp) e WHERE ROWNUM <= 10) WHERE rn >= 6; 

\5. 几个查询变化 

a. 指定查询列，只需要修改最里层的子查询

只查询雇员的编号和工资

SELECT * FROM (SELECT e.*, ROWNUM rn FROM (SELECT ename, sal FROM emp) e WHERE ROWNUM <= 10) WHERE rn >= 6; 

b. 排序查询，只需要修改最里层的子查询

工资排序后查询6-10条数据

SELECT * FROM (SELECT e.*, ROWNUM rn FROM (SELECT ename, sal FROM emp ORDER by sal) e WHERE ROWNUM <= 10) WHERE rn >= 6; 

n 用查询结果创建新表

这个命令是一种快捷的建表方式

CREATE TABLE mytable (id, name, sal, job, deptno) as SELECT empno, ename, sal, job, deptno FROM emp;

创建好之后，desc mytable；和select * from mytable;看看结果如何？

n 合并查询

有时在实际应用中，为了合并多个select语句的结果，可以使用集合操作符号union，union all，intersect，minus

多用于数据量比较大的数据局库，运行速度快。

1). Union

该操作符用于取得两个结果集的并集。当使用该操作符时，会自动去掉结果集中重复行。

SELECT ename, sal, job FROM emp WHERE sal >2500 

UNION

SELECT ename, sal, job FROM emp WHERE job = 'MANAGER';

 2).union all

该操作符与union相似，但是它不会取消重复行，而且不会排序。

SELECT ename, sal, job FROM emp WHERE sal >2500

UNION ALL

SELECT ename, sal, job FROM emp WHERE job = 'MANAGER';

该操作符用于取得两个结果集的并集。当使用该操作符时，会自动去掉结果集中重复行。

3). Intersect

使用该操作符用于取得两个结果集的交集。

SELECT ename, sal, job FROM emp WHERE sal >2500

INTERSECT

SELECT ename, sal, job FROM emp WHERE job = 'MANAGER';

 4). Minus

使用改操作符用于取得两个结果集的差集，他只会显示存在第一个集合中，而不存在第二个集合中的数据。

SELECT ename, sal, job FROM emp WHERE sal >2500

MINUS

SELECT ename, sal, job FROM emp WHERE job = 'MANAGER';

（MINUS就是减法的意思）

创建数据库有两种方法：

1). 通过oracle提供的向导工具。

database Configuration Assistant 【数据库配置助手】

2).我们可以用手工步骤直接创建。 

# 六、java操作oracle

TODO

# 七、事物

##  7.1 Oracle：**完全支持事务**，默认不自动提交

oracle默认不自动提交，需要用户手动提交，提交可以通过以下几个命令实现：

- **BEGIN：**事务块开始的标志。事务块里的SQL语句要么全部执行成功，要么全部失败回滚。
- COMMIT：提交事务。执行成功时，事务将被提交，并且对数据库的修改是可见的。
- ROLLBACK：ROLLBACK用于取消尚未提交的事务，并将数据库恢复到事务开始之前的状态。当ROLLBACK语句执行成功时，事务中的所有修改都将被撤销。
- SAVEPOINT：SAVEPOINT用于在事务中创建一个保存点，以便在事务执行过程中可以回滚到该保存点。它可以在事务中设置一个中间点，以便在需要时回滚到该点。
- SET TRANSACTION：SET TRANSACTION用于设置事务的属性。通过该命令，可以设置事务的隔离级别、读写权限等属性。

**⑴事务用于确保数据的一致性，由一组相关的DML语句组成，要么全部不执行，要么全部撤销。**

**⑵当执行事务操作时，Oracle会自动在作用的表上加锁，以防止其他用户锁定该表，同时也在行上加行级锁，以防止其它事务在相应行上执行DML操作。**

**⑶当执行事务提交或者回滚时，Oracle会确认事务变化或回滚事务、结束事务、删除保存点，释放锁。**

**⑷事务期间应避免与使用者交互。**

**⑸尽可能让事务持续时间越短越好。**

**⑹在事务中尽可能存取最少的数据量。**

**事务控制语句：**

　　1、COMMIT:提交事务，对数据库的修改进行保存。

　　2、ROLLBACK:回滚事务，取消对数据库所做的修改。

　　3、SAVEPOINT:在事务中创建存储点。

　　4、ROLLBACK TO <SAVEPOINT>:将事务回滚到存储点。

　　5、SET TRANSACTION:设置事务的属性。

**SET TRANSACTION：**可以用来设置事务的属性，但是必须放在事务的第一条。可以设置3个属性。

　　1、设置事务的隔离级别。

　　1）SET TRANSACTION READ ONLY

　　2）SET TRANSACTION ISOLATION LEVEL READ COMMITTED

　　3）SET TRANSACTION ISOLATION LEVEL SERIALIZABLE

　　2、规定回滚事务时所使用的存储空间。

　　3、对事务命名。SET TRANSACTION NAME 'tname';

示例：操作dept表：

```sql
INSERT INTO dept VALUES(50,'a',NULL);      --插入两条记录
INSERT INTO dept VALUES(60,'b',NULL); 
SAVEPOINT a;                                --设置保存点
INSERT INTO dept VALUES(70,'c',NULL);      --插入新的数据
ROLLBACK TO SAVEPOINT a;                   --回到保存点a，则保存点后的SQL语句失效。
select * FROM dept;                         --插入c的值没有了。
ROLLBACK;                                   --回滚事务，插入的a和b的值也没有了。
SELECT * FROM dept;
```

示例：

```sql
BEGIN
    SAVEPOINT sp;
    
    -- 向学生表插入数据
    INSERT INTO student_table (student_name, student_age) VALUES ('John', 18);
    INSERT INTO student_table (student_name, student_age) VALUES ('Emma', 19);
    
    -- 向班级表插入数据
    INSERT INTO class_table (class_name, class_size) VALUES ('Class A', 30);
    INSERT INTO class_table (class_name, class_size) VALUES ('Class B', 28);
    
    COMMIT;
EXCEPTION
    WHEN OTHERS THEN
        ROLLBACK TO sp;
        RAISE;
END;
```

##  7.2 MySQL：仅innoDB支持事务，默认自动提交

查看事务提交状态

```sql
SHOW STATUS LIKE 'Innodb_trx_id'
```

关闭事务提交：

```sql
set AutoCommit = 0;
```

手动提交事务：

```sql
START TRANSACTION;        -- 开始事务
INSERT INTO student (name,age) VALUES ('Tom',18); -- 执行一些数据操作
INSERT INTO score (student_id,score) VALUES (1,90);
COMMIT;                -- 手动提交事务
```

# 八、数据备份恢复

## 8.1 oracle导入dmp文件

1.首先确保dmp版本和本地oracle版本一致

2.将需要导入的dmp文件放在oracle11g的安装目录里面的`./admin/orcl/dpdump`目录下面

![img](oracl.assets/4c2317300bff4e608c855a7b003b875d.png)

3.右键dmp用notepad++打开，在第二行找到版本号，改成自己的oracle版本，例如我的版本是19c：

![img](oracl.assets/ce47e64bc4c2494582c0ba646707d089.png)3.sqlplus：用system账号创建用户并授权

```sql
create user ZHANGSAN identified by 1234;
grant connect , dba to ZHANGSAN ;
grant resource to ZHANGSAN ;
grant imp_full_database to ZHANGSAN ;
grant exp_full_database to ZHANGSAN ;
```

4.cmd命令行：迁移

```sql
impdp ZHANGSAN/1234 dumpfile = XXX.dmp
```

<img src="oracl.assets/897f1199e9ed4dfaacf0584ddef21f59.png" alt="img" style="zoom: 80%;" />

## 8.2 MySQL备份迁移

直接用navicat转储和运行SQL文件即可：

![img](oracl.assets/635a4c23a11b4d0e98cfef266f2dc883.png)



# 九、数据库管理

# 十、 plsql编程



