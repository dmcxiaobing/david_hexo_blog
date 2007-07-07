---
title: 【Docker】docker搭建本地gitlab，使用Git服务托管代码
categories: "Java后端" #分类
tags:   #标签
        - Docker
---

##### 1 首先下载gitlab的镜像 
```
docker pull gitlab/gitlab-ce:latest
```
##### 2 在服务器上创建目录，存放gitlab数据

```
mkdir -p /home/work/ins/conf
mkdir -p /home/work/ins/logs
mkdir -p home/work/ins/data/gitlab

```
#####  3 创建容器启动脚本。如果有以前执行过的，则停止并删除容器。


```
sudo docker stop gitlab && sudo docker rm gitlab

```

##### 4 启动，并设置端口号

```
sudo docker run  -d \
                 -p 2222:22 \
                 -p 8888:80 \
                 -p 8443:443 \
         -v /etc/localtime:/etc/localtime:ro \
                 -v  /home/work/ins/conf/gitlab:/etc/gitlab \
                 -v /home/work/ins/logs/gitlab:/var/log/gitlab \
                 -v /home/work/ins/data/gitlab/data:/var/opt/gitlab \
                 -h gitlab \
                 --name gitlab \
                 --privileged=true \
                 gitlab/gitlab-ce:latest
```

##### 5 登录验证。ip地址加端口号访问即可。


```
192.168.1.111:8888
```


