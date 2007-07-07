---
title: 【Maven】Maven中央仓库改为阿里云的仓库，增快下载速度
categories: "Maven" #分类
date: 2015-08-08 11:11:11
tags:   #Maven
	- Maven
---
配置方法1: 在我们的 $MAVEN_HOME/conf 下的 settings.xml 的<mirrors>标签中添加如下配置:
```
<mirror>  
  <id>alimaven</id>  
  <name>aliyun maven</name>  
  <url>http://maven.aliyun.com/nexus/content/groups/public/</url>  
  <mirrorOf>central</mirrorOf>          
</mirror>  
```

配置方法2: 直接在我们的maven项目中的 pom.xml 中直接添加

```
<repositories><!-- 代码库 -->  
    <repository>  
        <id>maven-ali</id>  
        <url>http://maven.aliyun.com/nexus/content/groups/public//</url>  
        <releases>  
            <enabled>true</enabled>  
        </releases>  
        <snapshots>  
            <enabled>true</enabled>  
            <updatePolicy>always</updatePolicy>  
            <checksumPolicy>fail</checksumPolicy>  
        </snapshots>  
    </repository>  
</repositories>  
```