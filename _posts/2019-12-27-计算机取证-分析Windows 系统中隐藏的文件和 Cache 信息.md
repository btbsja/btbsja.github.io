---
layout:     post   				    # 使用的布局（不需要改）
title:      计算机取证-分析Windows 系统中隐藏的文件和 Cache 信息			 # 标题 
subtitle:            #副标题
date:       2019-12-27          # 时间
author:     Btbsja				# 作者
header-img: img/bg-2019-12-23.jpg 	#这篇文章标题背景图片
catalog: true 					# 是否归档
tags:							#标签
    - 计算机取证
---
# 分析Windows 系统中隐藏的文件和 Cache 信息

5.1 实验目的

**1. 学会使用取证分析工具查看Windows操作系统下的一些特殊文件，找出深深隐藏的证据；**

**2. 学会使用网络监控工具监视 Internet 缓存，进行取证分析。**

5.2 实验环境和设备

**1. Windows Xp 或 Windows 2000 Professional操作系统。**

**2. Windows File Analyzer 和 CacheMonitor 安装软件。**

**3. 一张可用的软盘（或U盘）。**

5.3 实验内容和步骤

**1. 用 Windows File Analyzer 分析 Windows 系统下隐藏的文件。Windows File Analyzer 软件不需要安装，点击图标可直接进入应用程序窗口，分析 Windows 操作系统中一些特定的文件，以报告的形式打印出来。**

**（1）用 Thumbnail Datebase Analyzer读出 Thumbs.db 文件。打开 Windows File Analyzer 应用窗口，选择" File" -\>" Analyze**

**Thumbnail"下拉式菜单，查看 Thumbs.db 的内容，通过 Thumbs.db 得到此文件夹中所有的文件内容，导出其中的缩略图，包括那些有不健康内容的图片。**

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102312.png){width="3.5305555555555554in" height="2.707638888888889in"}

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102313.png){width="4.122916666666667in" height="2.2305555555555556in"}

**（2）用 Index.dat Analyzer 分析 Index.dat文件。**

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102314.png){width="5.377083333333333in" height="4.038194444444445in"}

（3）用Prefetch Analyzer 挖出Prefetch文件夹存储信息。

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102315.png){width="6.292361111111111in" height="4.384722222222222in"}

（4）用Recycle Bin Analyzer打开隐藏的回收站，显示回收站中Info2 文件信息。

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102316.png){width="6.299305555555556in" height="4.4840277777777775in"}

（5）用Shortcut Analyzer找出特定文件夹中的快捷方式,并显示存储在它们里面的数据。

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102317.png){width="6.299305555555556in" height="4.753472222222222in"}

3.  **用 CacheMonitor 监控 Internet 缓存。**

![](https://gitee.com/btbsja/BlogImg/raw/master/blog/2020/03/20200309102318.png){width="5.438194444444444in" height="2.3229166666666665in"}


