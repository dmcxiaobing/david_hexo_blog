---
title: 【JDK】Windows安装jdk配置环境变量详解教程。
categories: "Java后端" #分类
tags:   #标签
	- JDK
---
1、配置环境变量，右击【我的电脑】---【属性】-----【高级】---【环境变量】，

选择【新建系统变量】--弹出“新建系统变量”对话框，在“变量名”文本框输入

```
JAVA_HOME
```

在“变量值”文本框输入JDK的安装路径

```
D:\KaiFaGongJu\Java\jdk1.8.0
```

2、在“系统变量”选项区域中查看PATH变量，如果不存在，则新建变量 

```
PATH
```
否则选中该变量，单击“编辑”按钮，在“变量值”文本框的起始位置添加


```
%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;
```

或者是直接

```
%JAVA_HOME%\bin;
```

3、在“系统变量”选项区域中查看变量

```
CLASSPATH
```
如果不存在，则新建变量

```
CLASSPATH
```
否则选中该变量，单击“编辑”按钮，在“变量值”文本框的起始位置添加

```
.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
```

4、在DOS窗口，输入javac命令，能够正常输出java信息即可。
