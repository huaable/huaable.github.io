---
layout: post
title: 修改$PATH环境变量
date: 2018-03-30
categories: web开发
tags: linux mac web开发
---

# 公共环境变量

编辑文件
```$xslt
$ sudo vi /etc/profile
```

编辑内容(示例)

```$xslt
if [ -x /usr/libexec/path_helper ]; then
        eval `/usr/libexec/path_helper -s`
fi

if [ "${BASH-no}" != "no" ]; then
        [ -r /etc/bashrc ] && . /etc/bashrc
fi

#赋值
PATH=$PATH:/usr/local/php/bin

export PATH
```

退出编辑

```$xslt
:wq!

```
使其立刻生效(否则重启电脑后生效)
```$xslt
$ source /etc/profile
```


# 用户部分环境变量

```$xslt
$ cd ~
$ vi .bash_profile
```


编辑内容(示例)
```$xslt
LICOLOR=1
LSCOLORS=gxfxcxdxbxegedabagacad
COLOR=1
LSCOLORS=gxfxcxdxbxegedabagacad
exportPS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;36m\]\w\[\033[00m\]\$ '
export PATH=/Applications/MAMP/bin/php/php5.4.42/bin:$PATH

export PATH=${PATH}:/usr/local/bin:~/.composer/vendor/bin:/usr/bin:/bin:/usr/sbin:/sbin
export PATH=${PATH}:/Development/android-sdk/platform-tools:/Development/android-sdk/tools

# Add environment variable COCOS_CONSOLE_ROOT for cocos2d-x
export COCOS_CONSOLE_ROOT=/Applications/Cocos/frameworks/cocos2d-x-3.9/tools/cocos2d-console/bin
export PATH=$COCOS_CONSOLE_ROOT:$PATH

# Add environment variable COCOS_FRAMEWORKS for cocos2d-x
export COCOS_FRAMEWORKS=/Applications/Cocos/frameworks
export PATH=$COCOS_FRAMEWORKS:$PATH

# Add environment variable ANT_ROOT for cocos2d-x
export ANT_ROOT=/Applications/Cocos/tools/ant/bin
export PATH=$ANT_ROOT:$PATH
```


退出编辑
```$xslt
$ :wq!
```

使其立刻生效(否则重启电脑后生效)
```$xslt
$ source .bash_profile
```
