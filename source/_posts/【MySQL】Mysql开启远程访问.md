
---
title: 【SQL】【MySQL】Mysql开启远程访问
categories: "SQL" #分类
tags:   #标签
	- SQL
---
###### 使用MySQL：

```
mysql> use mysql;
Database changed

```
###### 查看用户只有localhost
```
mysql>  select user,host from user;
+-----------+-----------+
| user      | host      |
+-----------+-----------+
| mysql.sys | localhost |
| root      | localhost |
+-----------+-----------+
2 rows in set (0.02 sec)
```
###### 设置远程访问

```
mysql> update user set host='%' where user='root';
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0
```

###### 刷新即可
```
mysql> flush privileges;
Query OK, 0 rows affected (0.01 sec)
```
