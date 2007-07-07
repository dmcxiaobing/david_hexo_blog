---
title: 【MyBatis】Mybatis中大于、等于、小于等于在xml中的写法
categories: "MyBatis" #分类
date: 2015-08-08 11:11:11
tags:   #MyBatis
	- MyBatis
---

##### 由于MyBatis的sql写在XML里面，有些sql的语法符号和xml里面的冲突，比如：大于号 > 和小于号 < 在xml是标签的闭合符号，这样就产生了冲突。下面官方给出了解决方法。

 

##### 方法（1）：使用原生的写法。


```
符号：     <        <=      >        >=        &           '             "  
替换符号   &lt;    &lt;=   &gt;    &gt;=     &amp;       &apos;        &quot;
```

  
##### 例如：sql如下：  

```
where update_time &gt;= #{startDate} and update_time &lt;= #{endDate}  
gt --> greater than （大于 ）
lt --> less than（小于）
```


 

##### 方法（2）：使用xml语法写法。


```
大于等于 <![CDATA[ >= ]]>  
小于等于 <![CDATA[ <= ]]>
```

  
##### 例如：sql如下：  

```
update_time <![CDATA[ >= ]]> #{startDate} and update_time <![CDATA[ <= ]]> #{endDate}
```
 