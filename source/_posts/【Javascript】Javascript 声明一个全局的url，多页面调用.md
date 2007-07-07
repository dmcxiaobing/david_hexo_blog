---
title: 【Javascript】Javascript 声明一个全局的url，多页面调用
categories: "Javascript" #分类
tags:   #标签
	- Javascript
---
##### 新建一个js文件  publicDavid.js
`var baseUrl = "http://weibo.com/mcxiaobing";`

`function getBaseUrl() {
    return baseUrl;
}`
##### 页面引用：
`<script src="./publicDavid.js"></script>`

##### 使用全局配置url

```
var baseUrl = getBaseUrl();
```
