---
title: 【Hexo】利用node、hexo实现博客后台运行。
categories: "Nodejs" #分类
tags:   #标签
	- Hexo
---
##### 用pm2 来接管hexo的进程

###### 开始操作.安装pm2


```
$ npm  install -g pm2
```

###### 写一个执行脚本.在博客根目录下面创建一个hexo_run.js


```
//run
const { exec } = require('child_process')
exec('hexo server',(error, stdout, stderr) => {
        if(error){
                console.log('exec error: ${error}')
                return
        }
        console.log('stdout: ${stdout}');
        console.log('stderr: ${stderr}');
})
```

###### 运行脚本.在根目录下执行。


```
# pm2 start hexo_run.js
```

如果关闭，可以使用关闭命令。
```
pm2 stop hexo_run
```