---
title: 【Linux】Centos7 关闭防火墙方法详解
categories: "Linux" #分类
tags:   #Linux
	- Linux
---
## Centos7 关闭防火墙

CentOS 7.0默认使用的是firewall作为防火墙，使用iptables必须重新设置一下

1、直接关闭防火墙

```shell
systemctl stop firewalld.service #停止firewall

systemctl disable firewalld.service #禁止firewall开机启动
```

2、设置 iptables service（后面是安装iptables，若本地没有可省略)

```shell
yum -y install iptables-services
```

如果要修改防火墙配置，如增加防火墙端口3306

```shell
vi /etc/sysconfig/iptables
```

增加规则

```shell
-A INPUT -m state --state NEW -m tcp -p tcp --dport 3306 -j ACCEPT
```

保存退出后

```shell
systemctl restart iptables.service #重启防火墙使配置生效

systemctl enable iptables.service #设置防火墙开机启动

```


最后重启系统使设置生效即可。

其他系统关闭防火墙即可。
```shell
service iptables stop
```