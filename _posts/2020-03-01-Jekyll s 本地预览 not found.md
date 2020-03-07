---
layout:     post   				    # 使用的布局（不需要改）
title:      Jekyll s 本地预览 not found		    # 标题 
subtitle:                 #副标题
date:       2020-03-01			# 时间
author:     Btbsja					# 作者
header-img: img/bg-2020-02-24.jpg 	    #这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签

    - Blog

---
# Jekyll s 本地预览 not found

## 问题阐述

执行 Jekyll 本地预览命令

```
Jekyll s
```

浏览器输入

```
127.0.0.1：4000
```

首页正常，但是点击文章链接显示 404 no found

![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200302101736.png)

此时，控制台显示文章不存在

![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200302102203.png)

但实际上文件存在于 _site 文件夹中

## 解决方法

打开文件

```
C:\Ruby26-x64\lib\ruby\2.6.0\webrick\httpservlet\filehandler.rb
```

按下图更改两处

![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200302103306.png)

![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200302103430.png)

再次运行

```
Jekyll s
```

文章显示正常。