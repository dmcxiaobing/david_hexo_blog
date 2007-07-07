---
title: 【Docker】docker常用命令总结大全
categories: "Java后端" #分类
tags:   #标签
	- Docker
---

##### docker命令的具体使用参数帮助
```shell
docker 命令 --help
```
##### 查看当前正在运行的容器
```shell
 docker ps
```
##### 查看所有容器的状态。最近运行过的所有容器
```shell
docker ps -a
```
##### 启动/停止某个容器
```shell
 docker start/stop id/name
```
##### 进入某个容器(使用exit退出后容器也跟着停止运行)
```shell
 docker attach id
```
##### 启动一个伪终端以交互式的方式进入某个容器
 ```shell
docker  exec -it   9af8c6c13cb4（容器ID）   /bin/bash
```
##### 查看本地镜像
```shell
 docker images
```
##### 删除某个容器
```shell
 docker rm id/name
```
##### 删除某个镜像
###### 有时候删除会失败，比如：有一个容器正在使用该镜像文件。这时可以加参数-f 强制删除
```shell
docker rmi id/name
```
##### 复制ubuntu容器并且重命名为test且运行，然后以伪终端交互式方式进入容器，运行bash
```shell
docker run --name test -ti ubuntu /bin/bash
```
##### Docker容器中使用vi编辑器

```
apt-get update
apt-get install vi

这个命令的作用是：同步 /etc/apt/sources.list 和 /etc/apt/sources.list.d 中列出的源的索引，这样才能获取到最新的软件包。安装V编辑器。
```


