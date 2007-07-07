---
title: 【Hibernate】在Hibernate框架中配置显示sql语句
categories: "Java后端" #分类
tags:   #标签
	- Hibernate
---
###### 使用Hibernate的框架开发时，可在Hibernate.cfg.xml中加上


    <property name="hibernate.show_sql">true</property><!-- 配置显示sql语句 -->
    <property name="format_sql">true</property><!-- 让输出的sql语句格式化 -->


就可以在控制台显示对应的sql语句了，对于开发很有帮助。
在项目部署时最好将其删掉，因为会消耗一定的资源。
