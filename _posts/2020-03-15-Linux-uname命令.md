---
layout:     post   				    # 使用的布局（不需要改）
title:     Linux-uname命令			    # 标题 
subtitle:                 #副标题
date:       2020-03-15			# 时间
author:     Btbsja					# 作者
header-img: img/bg-2020-03-09.jpg 	    #这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签

    - Linux
---

# Linux uname命令

## 语法

```
uname [-amnrsv][--help][--version]
```

## 参数

- -a或--all 　显示全部的信息
- -m或--machine 　显示电脑类型
- -n或-nodename 　显示在网络上的主机名称
- -r或--release 　显示操作系统的发行编号
- -s或--sysname 　显示操作系统名称
- -v 　显示操作系统的版本
- --help 　显示帮助
- --version 　显示版本信息

## 附录

- who 可以查询当前登录在系统上的登录用户的信息
- who am i 等同于 who -m，只打印执行该命令的登录用户的信息
- whoami 可以查询当前有效用户的名字