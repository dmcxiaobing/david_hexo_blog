---
title: 【Mac】Mac操作系统关闭指定端口号
categories: "Mac" #分类
tags:   #Mac
	- Mac
---
##### 1 查看指定端口号运行的程序：


```
lsof -i:端口号
```

##### 2 会有类似下面的结果： 

```
COMMAND     PID       USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
WebProces 42624 davidzhang    5u  IPv4 0x907152bbf7b2a875      0t0  TCP localhost:64438->localhost:radan-http (ESTABLISHED)
WebProces 42624 davidzhang   10u  IPv4 0x907152bbf7b64a05      0t0  TCP localhost:64439->localhost:radan-http (ESTABLISHED)
```

##### 3 然后执行： 


```
kill -9 42624
```

结束进程就搞定了。