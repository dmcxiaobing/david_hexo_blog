---
title: 【Docker】Docker部署安装yapi框架
categories: "Java后端" #分类
tags:   #标签
  - Docker
---
###### 1、启动 MongoDB

```
docker run -d --name mongo-yapi mongo
```


###### 2、获取 Yapi 镜像，版本信息可在 阿里云镜像仓库 查看

```
docker pull registry.cn-hangzhou.aliyuncs.com/anoy/yapi
```


###### 3、初始化 Yapi 数据库索引及管理员账号

```
docker run -it --rm \
  --link mongo-yapi:mongo \
  --entrypoint npm \
  --workdir /api/vendors \
  registry.cn-hangzhou.aliyuncs.com/anoy/yapi \
  run install-server
```


###### 4、启动 Yapi 服务

```
docker run -d \
  --name yapi \
  --link mongo-yapi:mongo \
  --workdir /api/vendors \
  -p 3000:3000 \
  registry.cn-hangzhou.aliyuncs.com/anoy/yapi \
  server/app.js
```


###### 使用 Yapi

```
访问 http://localhost:3000   登录账号 admin@admin.com，密码 ymfe.org
```


