
---
title: 【SQL】MySQL创建用户并授权某个数据库权限
categories: "SQL" #分类
tags:   #标签
	- SQL
---

##### 1.创建用户：
`CREATE USER 'david'@'%' IDENTIFIED BY 'david';`
##### 2.修改密码：
`update mysql.user set password=password('qq986945193') where user='david';`
##### 3.授权数据库权限给用户：
`grant all privileges on 数据库名.* to 'david'@'%';`
all 可以替换为 select,delete,update,create,drop
##### 4.刷新权限
在操作 mysql 库做用户的增删修改的时候，操作完毕的时候最好使用 `flush privilege` 命令刷新一下权限。
`flush privileges;`