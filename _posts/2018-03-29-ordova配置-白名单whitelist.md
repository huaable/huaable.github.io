---
layout: post
title: cordova配置-白名单whitelist
date: 2018-11-04
categories: app开发
tags: cordova app开发
---
1.安装插件

```
 cordova plugin add cordova-plugin-whitelist
```
2.修改文件
```
config.xml
```

[白名单插件的使用方法 →](https://github.com/apache/cordova-plugin-whitelist)

3.修改文件

```
www/index.html
```
添加允许CSP meta 标签

```
<meta http-equiv="Content-Security-Policy" content="default-src *; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline' 'unsafe-eval'">

```
