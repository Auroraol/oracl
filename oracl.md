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



# 下载Oracle19c资料包

https://www.oracle.com/database/technologies/oracle-database-software-downloads.html

![img](oracl.assets/1567668194696-0fb940c8-9211-401c-a436-732cc1298142.png)

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



# Oracle数据库的一些常用命令

## 一、sqlplus常用命令

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
C:\Users\wd-pc>sqlplus scott/123456 
或
SQL>connect scott/123456   普通用户登录默认数据库   
SQL>conn scott/tiger       普通用户登录默认数据库   
或
SQL>connect scott/123456@servername    普通用户登录指定的servername数据库     
```

**4、以超级管理员登录**

```cmd
C:\Users\wd-pc>sqlplus sys/123456 as sysdba　
或
SQL>connect sys/123456 as sysdba
```

**5、以系统管理员登录**

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

<img src="oracl.assets/image-20231030232756813.png" alt="image-20231030232756813" style="zoom:67%;" />

例子

<img src="oracl.assets/image-20231030232916427.png" alt="image-20231030232916427" style="zoom:67%;" />

解锁用户：       alter user scott account unlock;   

锁定用户：       alter user scott account lock;     

注意：只有管理员才有权限解锁和锁定用户！！！  

显示当前登录用户：    show user; 

DBA：数据库管理员  DB：database 数据库  DBMS：数据库管理系统

## 二、Oracle数据库的用户

oracle安装成功后，会默认生成三个用户

+ 超级管理员：      sys  权限最高 它的角色 dba 密码 changeon_installsystem

+ 系统管理员：      system 权限也很高他的角色是dbaoper 密码 manager

+ 普通用户：          scott   密码tiger,  没有操作用户的权限【创建修改删除】

sys有 create databse 的权限 ，而system没有.其它相似在日常对oracle管理过程中，使用system就够了

删除用户:drop user lxixi cascade;  cascade 级联删除    授权：创建的用户任何权限【我们需要对用户授权】       角色： connect resource dba       grant connect,resource,dba to lxixi    撤销权限：      revoke connect,resourc,dba from lxixi;

##  三、oracle的登录方式

```cmd
sqlplus / as sysdba							# 以操作系统权限认证的oracle sys管理员登录
sqlplus /nolog								# 不暴露密码的登录方式
sqlplus scott/tiger							# 非管理员用户登录
sqlplus										# 不显露密码的登录方式
```

例子

```cmd
[oracle@localhost ~]$ sqlplus /nolog
SQL*Plus: Release 11.2.0.3.0 Production on Wed Dec 14 00:11:34 2022
Copyright (c) 1982, 2011, Oracle.  All rights reserved.
SQL> connect taibai@prod
Enter password: 
Connected.
SQL>
Enter user-name：sys
Enter password：password as sysdba 	# 以sys用户登陆的话 必须要加上 as sysdba 子句，其他用户直接输入密码即可
#### 内部切换用户
[oracle@localhost ~]$ sqlplus /nolog
SQL*Plus: Release 11.2.0.3.0 Production on Wed Dec 14 00:16:02 2022
Copyright (c) 1982, 2011, Oracle.  All rights reserved.
SQL> connect /as sysdba
Connected.
SQL> connect scott/tiger
Connected.
SQL> 
```

