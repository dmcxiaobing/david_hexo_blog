---
title: 【Docker】Docker配置阿里云等镜像加速方法，适用Centos和Ubuntu
categories: "Java后端" #分类
tags:   #标签
	- Docker
---

##### 1. 安装／升级Docker客户端
###### 推荐安装1.10.0以上版本的Docker客户端，参考文档 docker-ce

##### 2. 配置镜像加速器
###### 针对Docker客户端版本大于 1.10.0 的用户

##### 您可以通过修改daemon配置文件/etc/docker/daemon.json来使用加速器

```
sudo mkdir -p /etc/docker

sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://1o70e58r.mirror.aliyuncs.com"]
}
EOF

sudo systemctl daemon-reload

sudo systemctl restart docker

```
#####  备注：
```
https://1o70e58r.mirror.aliyuncs.com这个是配置自己的阿里云加速地址，也可以国内其他平台的docker加速。
```

