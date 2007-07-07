---
title: 【Hexo】Hexo搭建静态博客教程
categories: "Nodejs" #分类
tags:   #标签
	- Hexo
---
##### 首先安装好git和nodejs
##### 安装hexo

```
npm install -g hexo
npm install -g hexo-cli
```
##### 新建一个blog的目录，然后在该目录依次执行以下命令

```
hexo init
npm install
```
##### 执行完成后，输入以下命令，然后通过访问:http://localhost:4000，来访问，一个本地博客就可以看到了，值得注意的是，默认主题是landscape，如需要变主题，得自己手动修改。

```
hexo g
hexo s
```
##### 修改主题，比如已经下载过yilia.只需修改_config.yml中theme:为

```
theme: yilia
```

##### hexo命令解析

```
hexo g #完整命令为hexo generate,生成静态文件 
hexo s #完整命令为hexo server,启动服务器,本地可以测试 
hexo d #完整命令为hexo deploy,将本地编译好的静态文件发布到github上 
hexo n #完整命令为hexo new,新建一篇文章 
hexo clean #清除当前项目的静态文件
hexo clean && hexo g && hexo s #命令一起执行
```
