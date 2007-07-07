---
title: 【Linux】Linux报找不到bin、bash问题
categories: "Linux" #分类
tags:   #Linux
	- Linux
---
##### 写了一个shell脚本，然后放到linux下跑的时候，我用指令：

```
chmod +x david_build.sh

./david_build.sh
```

但是却没有任何反应。报错 

```
“david_build.sh  /bin/bash^M:   坏的解释器：没有那个文件或目录”。
```
##### 最后，怀疑是空格\r和\n引起的，就执行了替换命令：

```
sed -i 's/\r$//' david_build.sh
```

#####  会把 david_build.sh 中的\r 替换成空白！最后，问题解决，成功可以执行。

