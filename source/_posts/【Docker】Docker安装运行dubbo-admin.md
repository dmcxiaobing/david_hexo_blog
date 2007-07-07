---
title: 【Docker】Docker安装运行dubbo-admin
categories: "Java后端" #分类
tags:   #标签
	- Docker
---
###### 运行dubbo-admin服务, 此服务需要单独启动一个zookeeper容器
###### dubbo-admin将监听所有注册到zookeeper的服务, dubbo-admin默认端口8080


##### 1 运行一个zookeeper服务。

```
docker pull qq986945193/david_zookeeper3.4.13:v1.0

docker run --privileged=true -d --name zookeeper --publish 2181:2181  -d qq986945193/david_zookeeper3.4.13:v1.0

docker logs -f 54f6b80ffa64ea604aa691adbd5b6c296b087a3f97bc6355a629f841bbf77c20
```


##### 2 拉取镜像，运行dubbo-admin服务。

```
docker run --name dubbo-admin -p 8888:8080 --link zookeeper -d qq986945193/david_dubbo_admin
```


##### 3 直接访问，用户名密码：root   root

```
http://localhost:8888
```
