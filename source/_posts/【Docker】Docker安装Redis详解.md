---
title: 【Docker】Docker安装Redis详解
categories: "Java后端" #分类
tags:   #标签
	- Docker
---
##### 1 拉取Redis镜像
```
sudo docker pull redis:3.2
```
##### 2 直接启动Redis

```
sudo docker run -p16379:6379 -d docker.io/redis:3.2 
```

```
-p 6379:6379 : 将容器的6379端口映射到主机的16379端口
-d 后台运行
```
##### 3 其他可选参数

```
-v $PWD/data:/data  -d redis:3.2 redis-server --appendonly yes
-v $PWD/data:/data : 将主机中当前目录下的data挂载到容器的/data
redis-server –appendonly yes : 在容器执行redis-server启动命令，并打开redis持久化配置
最后添加--requirepass "mypassword" 设置密码。
```
##### 4  连接、查看容器..    使用redis镜像执行redis-cli命令连接到刚启动的容器

```
docker exec -it 43f7a65ec7f8（容器Id） redis-cli
```



