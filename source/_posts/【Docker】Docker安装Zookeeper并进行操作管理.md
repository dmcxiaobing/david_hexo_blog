---
title: 【Docker】Docker安装Zookeeper并进行操作管理
categories: "Java后端" #分类
tags:   #标签
	- Docker
---

##### 下载Zookeeper镜像
```shell
docker pull zookeeper
```

##### 启动容器并添加映射
```shell
docker run --privileged=true -d --name zookeeper --publish 2181:2181  -d zookeeper:latest
```

##### 查看容器是否启动
```shell
docker ps
```



