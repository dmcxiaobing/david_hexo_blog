---
title: 【Docker】Docker安装并运行RabbitMQ
categories: "Java后端" #分类
tags:   #标签
	- Docker
---
##### 1 搜索一下，查看有哪些ActiveMQ镜像

```
docker search activemq
```
##### 2 我们需要安装webcenter/activemq 这个镜像

```
docker pull docker.io/webcenter/activemq
```
##### 3 拉取到镜像之后，在不加tag的情况下默认使用latest。查看一下镜像

```
docker images

REPOSITORY                                    TAG                 IMAGE ID            CREATED             SIZE
docker.io/qq986945193/david_mysql_5.7         1.0.1               9fd8428e083c        5 days ago          457 MB
docker.io/gitlab/gitlab-ce                    latest              b0e83ed9366b        7 days ago          1.55 GB
docker.io/qq986945193/david_jenkins1127       latest              23bccbdc26cb        3 weeks ago         701 MB
docker.io/wurstmeister/kafka                  latest              9de73503addf        4 weeks ago         337 MB
docker.io/qq986945193/david_oracle_11g        latest              bcc66886f00f        4 weeks ago         3.45 GB
docker.io/qq986945193/david_redis_3.2         v1.0                3b1eb32704df        4 weeks ago         76 MB
docker.io/qq986945193/david_mysql_5.7         1.0.0               9451e09270f0        4 weeks ago         447 MB
docker.io/qq986945193/david_zookeeper3.4.13   v1.0                f336949ce7a1        8 weeks ago         148 MB
docker.io/rabbitmq                            3.7.7-management    2888deb59dfc        3 months ago        149 MB
docker.io/qq986945193/david_dubbo_admin       latest              db722badcfdc        16 months ago       141 MB
docker.io/webcenter/activemq                  latest              3af156432993        23 months ago       422 MB
docker.io/wurstmeister/zookeeper              latest              351aa00d2fe9        2 years ago         478 MB
```

##### 4 最后我们直接启动镜像，创建容器。

```
docker run -d --name myactivemq -p 61617:61616 -p 8162:8161 docker.io/webcenter/activemq:latest

备注：
61616是activemq的容器使用端口（映射为61617），8161是web页面管理端口（对外映射为8162）
```
##### 5 我们可以使用 ip:8162访问我们的web后台。默认账号密码都是admin
