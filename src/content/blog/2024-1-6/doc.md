---
title: "MySQL数据库学习笔记 Chapter 1 ——SQL语句语法"
pubDate: "2024-01-06"
description: "基础篇1"
heroImage: "http://localhost:4321/@fs/D:/code/Hope-second-try/src/theme-simple/assets/media/11.jpg?origWidth=2176&origHeight=1224&origFormat=jpg" 
tags: ["数据库"]
---

## 目录
+ DDL —— 数据定义语言 definition 。用于定义数据库对象（数据库、表、字段）
+ DML —— 数据操作语言 manipulation 。用于对数据库中的数据进行增删改
+ DQL —— 数据查询语言 query 。用于查询数据库中表的记录
+ DCL —— 数据控制语言 control 。用于创造数据库的访问权限

***********************

##### 通用语法
+ 不区分大小写
+ 以逗号结尾
+ --后面接着的表示注释

### DDL
+ 数据库操作
![](https://imgcdn.hope-blog.top/2024-1-6/11.png)

+ 表操作
![](https://imgcdn.hope-blog.top/2024-1-6/22.png)
（attention：创建表时最后一个项目不需要添加逗号）

+ 表的相关操作
![](https://imgcdn.hope-blog.top/2024-1-6/33.png)
![](https://imgcdn.hope-blog.top/2024-1-6/44.png)
![](https://imgcdn.hope-blog.top/2024-1-6/55.png)

+ 图形化界面操作
使用 datagrip 完成安装和连接 mysql 数据库之后可以在应用中直接以图形化的操作完成上面的操作
![](https://imgcdn.hope-blog.top/2024-1-6/66.png)

### DML
+ 表内容的修改
关键字：updata 表名 set 字段名1=值1 ，字段名2=值2，[where 条件]；
不加条件表示对所有内容进行修改，需要做进一步确认。

![](https://imgcdn.hope-blog.top/2024-1-6/77.png)
![](https://imgcdn.hope-blog.top/2024-1-6/88.png)

+ 表内容的删除
delate语句不能删除某个字段的值，要删除某个字段的值可以使用上面的关键字update为NULL；
关键字：delate from 表名 [where 条件]

![](https://imgcdn.hope-blog.top/2024-1-6/99.png)


### DQL
Data Query Languge  数据查询语言，是数据库最常用的方式。

+ 表内容的查询
语法：select 字段名 from 表名；
![](https://imgcdn.hope-blog.top/2024-1-6/10.png)

+ 条件查询
语法：select 字段名 from 表名 where 条件；
![](https://imgcdn.hope-blog.top/2024-1-6/12.png)

+ 聚合函数
语法：select 聚合函数（要操作的字段名） from 表名；
![](https://imgcdn.hope-blog.top/2024-1-6/13.png)

+ 分组查询
语法：select 字段名 from 表名 group by 字段名；
![](https://imgcdn.hope-blog.top/2024-1-6/14.png)

+ 排序查询
语法：select 字段名 from 表名 order by 字段名 asc(顺序)/desc(逆序)；
![](https://imgcdn.hope-blog.top/2024-1-6/15.png)

+ 分页查询
语法：select 字段名 from 表名 limit 起始索引，查询记录数；
![](https://imgcdn.hope-blog.top/2024-1-6/16.png)

+ DQL练习
![](https://imgcdn.hope-blog.top/2024-1-6/17.png)


### DCL
控制每一个数据库有哪些用户可以访问，以及每个用户具有怎样的访问权限。

##### 管理用户权限
+ 用户的增加删除、修改密码。
![](https://imgcdn.hope-blog.top/2024-1-6/21.png)

+ 用户权限的修改
![](https://imgcdn.hope-blog.top/2024-1-6/23.png)


