
---
title: 【SQL】如何通过sql语句查看数据库的占用大小
categories: "SQL" #分类
tags:   #标签
	- SQL
---


##### 1、进入information_schema 数据库（存放了其他的数据库的信息）

```
use information_schema;
```


##### 2、查询所有数据的大小：

```
SELECT
	concat( round( sum( data_length / 1024 / 1024 ), 2 ), 'MB' ) AS DATA 
FROM
	TABLES;
```


##### 3、查看指定数据库的大小：
比如查看数据库david_db的大小

```
SELECT
	concat( round( sum( data_length / 1024 / 1024 ), 2 ), 'MB' ) AS DATA 
FROM
TABLES 
WHERE
	table_schema = 'david_db';
```


##### 4、查看指定数据库的某个表的大小
比如查看数据库david_db中 t_user 表的大小

```
SELECT
	concat( round( sum( data_length / 1024 / 1024 ), 2 ), 'MB' ) AS DATA 
FROM
TABLES 
WHERE
	table_schema = 'david_db' 
	AND table_name = 't_user';
```
