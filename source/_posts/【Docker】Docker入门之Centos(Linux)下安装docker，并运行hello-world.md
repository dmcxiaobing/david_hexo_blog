
---
title: 【Docker】Docker入门之Centos(Linux)下安装docker，并运行hello-world
categories: "Java后端" #分类
tags:   #标签
	- Docker
---

##### 首先安装docker所需要的依赖库


```
sudo yum install -y cmake
sudo yum install -y  make
sudo yum install -y gcc
sudo yum install -y gcc-c++
sudo yum install -y bison
sudo yum install -y ncurses
sudo yum install -y ncurses-devel

```
###### 首先使用Centos的yum命令，安装docker：
```shell
 yum install docker
```
###### 然后安装完成之后，可以使用docker或者docker version命令查看
```shell
docker或者docker version
```
###### 启动docker命令service docker start
```shell
service docker start
```
```shell
[root@localhost local]# service docker start
Redirecting to /bin/systemctl start docker.service
```
###### 然后可以拉取Hello-world镜像：
```shell
docker pull hello-world
```
```shell
[root@localhost local]# docker pull hello-world
Using default tag: latest
Trying to pull repository docker.io/library/hello-world ... 
latest: Pulling from docker.io/library/hello-world
9db2ca6ccae0: Pull complete 
Digest: sha256:569d44f69ebf4592ec3a63cbea6d9c7b6cccfd50890794fa169455179b399eb4
Status: Downloaded newer image for docker.io/hello-world:latest
```
###### 最后可以运行Hello-world镜像：
```shell
[root@localhost local]# docker run hello-world
```
```shell
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/

```