
---
title: 【Gradle】Windows安装并配置gradle
categories: "Gradle" #分类
tags:   #标签
	- Gradle
---

##### 1.下载最新的Gradle压缩包：
`Gradle官网:https://gradle.org`

当前最新版本下载地址:`https://gradle.org/releases/`,下载binary-only即可
##### 2.解压下载的压缩包到指定位置,比如:
`D:\Gradle\gradle-4.3.1`
##### 3.配置环境变量：
`右键计算机->属性->高级系统设置->环境变量,在系统变量区域，点击新建，输入变量名为：GRADLE_HOME，变量值为：D:\DavidSoft\Gradle\gradle-4.3.1（根据实际情况）。找到Path，在原始内容基础上加入%GRADLE_HOME%\bin;，必须以分号结束`
##### 4.测试配置是否成功
`打开一个新的cmd命令窗口或者powershell或者其他命令行工具（比如cmder），输入命令gradle -v，如果出现类似下面的消息,则说明配置成功`