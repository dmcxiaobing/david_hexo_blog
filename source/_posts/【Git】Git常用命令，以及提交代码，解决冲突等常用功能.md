---
title: 【Git】Git常用命令，以及提交代码，解决冲突等常用功能
categories: "Java后端" #分类
date: 2015-08-08 11:11:11
tags:   #标签
	- Git
---

##### 1 首先下载Git，下载地址：[https://git-scm.com](https://git-scm.com)    
##### 2 安装好之后，可以使用git命令，在终端中查看是否成功

```
[david@DavidMacbookPro ~]# git
usage: git [--version] [--help] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

最常用的 git 命令有：
   add        添加文件内容至索引
   bisect     通过二分查找定位引入 bug 的变更
   branch     列出、创建或删除分支
   checkout   检出一个分支或路径到工作区
   clone      克隆一个版本库到一个新目录
   commit     记录变更到版本库
   diff       显示提交之间、提交和工作区之间等的差异
   fetch      从另外一个版本库下载对象和引用
   grep       输出和模式匹配的行
   init       创建一个空的 Git 版本库或重新初始化一个已存在的版本库
   log        显示提交日志
   merge      合并两个或更多开发历史
   mv         移动或重命名一个文件、目录或符号链接
   pull       获取并合并另外的版本库或一个本地分支
   push       更新远程引用和相关的对象
   rebase     本地提交转移至更新后的上游分支中
   reset      重置当前HEAD到指定状态
   rm         从工作区和索引中删除文件
   show       显示各种类型的对象
   status     显示工作区状态
   tag        创建、列出、删除或校验一个GPG签名的 tag 对象

命令 'git help -a' 和 'git help -g' 显示可用的子命令和一些指南。参见
'git help <命令>' 或 'git help <指南>' 来查看给定的子命令帮助或指南。
```
##### 3 配置和GitHub、gitee等平台的公钥和私钥。

```
## 1 检查一下用户名和邮箱是否配置（github支持我们用用户名或邮箱登录）：
git config --global  --list 

bogon:david david$ git config --global  --list 
user.name=david
user.email=986945193@qq.com
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
core.autocrlf=input
credential.helper=store

```

```
## 2 配置我们的用户名和密码
git config --global  user.name "这里换上你的用户名"
git config --global  user.email "这里换上你的邮箱" 

```

```

## 3 生成秘钥，此时，我们可以一直点回车，主要是为了提示生成文件位置，以及配置密码：
ssh-keygen -t rsa -C "这里换上你的邮箱"
```

```
## 4 可以看到在自己用户目录下，生成了私钥和公钥。此时，可以将公钥内容，复制到GitHub等系统后台。
bogon:david david$ ls ~/.ssh/
git config --global  user.name "david"
id_rsa
id_rsa.pub
known_hosts
```

```
## 5 id_rsa.pub公钥内容类似如下

ssh-rsa DDDDDDDDC1yc2EAAAADAQABAAABAQDHlYIVVrGI/xjKEjUnKVlW2JMO4kvJjpQJhKnVoM60+XapMC8gORUvvgaQqi5DMZOOf0qglrDYjwhkztFkZsSJIeBIeNIZFfSaI3Z9UKxl7PxA9JrzOBUgLMsFx4ITOdQMC/DDDDD4Qdz5AGI+DbjOGD3p8pciwTr9oyZ9Atli33y6TURg0Xc1YTve9h97ibc3jOHMfo+Zw0MwxFhr50FOUg5u5hjDM0X4/G8sbBB4Uujn4FKY6Qss+seAl2/mhol6qj0mQ9R+I0z3V1Lf2E4aoTBDtaDRNgSuGsW7pHlMFur/ra/BIIyhqJcSjxCrLdmBpZvOo/6s0nYjdWrDDDDD 986945193@qq.com
```
##### 4 此时就可以使用ssh下载我们的项目了，也就是有两种方式下载项目如下：

```

git clone git@192.168.1.188:david/david_github_demo.git

git clone http://192.168.1.105:8888/david/david.git

```

##### 常用命令介绍
###### 当配置完成ssh之后，监测是否成功命令：

```
 ssh -T git@192.168.1.188
```
###### git clone下载代码，指定分支。默认是从master分支下载

```
## 其中dev_0.0.1 代表分支名称
git clone -b dev_0.0.1 git@192.168.1.188:david/david_demo.git
```
###### 查看所有的远程库。关联此项目的

```
git remote -v 
```
### 团队发中，前提fork了一份代码之后，后续提交，合并，解决冲突
###### 1 拉取自己用户目录的项目到本地

```
 git clone '本用户目录下的项目地址'
```
###### 2 在本地项目加入主库的地址

```
 git remote add main '主库地址'
```

###### 3 拉取主库的最新代码。更新主库代码到本地。  master 代表：分支名称。

```
 git pull main master
```
###### 4 提交代码。

```
## 添加当前目录下文件
 git add .
## 提交到本地仓库
 git commit -m ''
## 推送到远端仓库 
 git push
```
###### 5 从自己项目库下载项目后，更新主库项目到本地仓库。然后将主库项目更新的文件，提交到自己项目库下，然后再开发，最后提交自己文件到自己库下，最后合并到主库中。如果使用开发工具，可以直接commit and push....
###### 6 如果从主库更新下来，有冲突，则可以解决冲突后，commit push，并合并到主库项目中。解决冲突可使用开发工具或者记事本等工具。




