---
title: 【Mac】Mac操作系统下MySQL密码忘记后重置密码的方法
categories: "Mac" #分类
date: 2015-08-08 11:11:11
tags:   #Mac
	- Mac
---
1.苹果->系统偏好设置->最下边点mysql 在弹出页面中 关闭mysql服务（点击stop mysql server）

2.进入目录

```
cd /usr/local/mysql/bin 
```
3.获取权限。此时需要mac系统的密码，就是所谓的获取超级管理员权限。
```
sudo su 
```
4.重启服务器

```
./mysqld_safe --skip-grant-tables & 
```
回车后mysql会自动重启（偏好设置中mysql的状态会变成running）

5.重开个终端，重启一下mysql服务，然后直接进入mysql

```
// 重启mysql
sudo /usr/local/mysql/support-files/mysql.server restart
// 进入mysql
./mysql
// 执行以下命令，刷新，然后设置新的密码。最后用户名为root，密码就是你自己设置的。
FLUSH PRIVILEGES; 
SET PASSWORD FOR 'root'@'localhost' = PASSWORD('你的新密码');
```