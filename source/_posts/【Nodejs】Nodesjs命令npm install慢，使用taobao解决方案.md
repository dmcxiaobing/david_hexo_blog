---
title: 【Nodejs】Nodesjs命令npm install慢，使用taobao解决方案
categories: "Nodejs" #分类
tags:   #标签
	- Nodejs
---
##### 可用 get命令查看registry
    
    npm congfig get registry原版结果为
    
    http://registry.npmjs.org

##### 原版结果为

    http://registry.npmjs.org

##### 用set命令换成阿里的镜像就可以了

```
npm config set registry http://registry.npm.taobao.org
```
