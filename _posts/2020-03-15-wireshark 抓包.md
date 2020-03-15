---
layout:     post   				    # 使用的布局（不需要改）
title:     wireshark教程			    # 标题 
subtitle:                 #副标题
date:       2020-03-15			# 时间
author:     Btbsja					# 作者
header-img: img/bg-2020-03-09.jpg 	    #这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签

    - 工具
---

# wireshark教程

wireshark 是非常流行的网络封包分析软件，功能十分强大。可以截取各种网络封包，显示网络封包的详细信息。使用 wireshark 的人必须了解网络协议，否则就看不懂 wireshark 了。

为了安全考虑，wireshark 只能查看封包，而不能修改封包的内容，或者发送封包。wireshark 能获取 HTTP，也能获取 HTTPS，但是不能解密 HTTPS，所以 wireshark 看不懂 HTTPS 中的内容，总结，如果是处理 HTTP,HTTPS 还是用 Fiddler, 其他协议比如 TCP,UDP 就用 wireshark.

wireshark 开始抓包
--------------

![](https://img-blog.csdn.net/20171208162350490?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

wireshark 是捕获机器上的某一块网卡的网络包，当你的机器上有多块网卡的时候，你需要选择一个网卡。  
点击 Caputre->Interfaces.. 出现下面对话框，选择正确的网卡。然后点击”Start” 按钮, 开始抓包  
![](https://img-blog.csdn.net/20171208162606037?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### Wireshark 窗口介绍

![](https://img-blog.csdn.net/20171208163430300?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

WireShark 主要分为这几个界面  
1. Display Filter(显示过滤器)， 用于过滤  
2. Packet List Pane(封包列表)， 显示捕获到的封包， 有源地址和目标地址，端口号。 颜色不同，代表  
3. Packet Details Pane(封包详细信息), 显示封包中的字段  
4. Dissector Pane(16 进制数据)  
5. Miscellanous(地址栏，杂项)

### Wireshark 显示过滤

![](https://img-blog.csdn.net/20171208163750867?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

使用过滤是非常重要的， 初学者使用 wireshark 时，将会得到大量的冗余信息，在几千甚至几万条记录中，以至于很难找到自己需要的部分。搞得晕头转向。  
过滤器会帮助我们在大量的数据中迅速找到我们需要的信息。  
过滤器有两种，  
一种是显示过滤器，就是主界面上那个，用来在捕获的记录中找到所需要的记录  
一种是捕获过滤器，用来过滤捕获的封包，以免捕获太多的记录。 在 Capture -> Capture Filters 中设置

### 保存过滤

在 Filter 栏上，填好 Filter 的表达式后，点击 Save 按钮， 取个名字。比如”Filter hls”,  

![](https://img-blog.csdn.net/20171208164629274?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)


Filter 栏上就多了个”Filter hls” 的按钮。  
![](https://img-blog.csdn.net/20171208164716529?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

过滤表达式的规则
--------

表达式规则  
1. 协议过滤  
比如 TCP，只显示 TCP 协议。  
2. IP 过滤  
比如 ip.src ==192.168.1.102 显示源地址为 192.168.1.102，  
ip.dst==192.168.1.102, 目标地址为 192.168.1.102  
3. 端口过滤  
tcp.port ==80, 端口为 80 的  
tcp.srcport == 80, 只显示 TCP 协议的愿端口为 80 的。  
4. Http 模式过滤  
http.request.method==”GET”, 只显示 HTTP GET 方法的。  
5. 逻辑运算符为 AND/ OR

封包列表 (Packet List Pane)
-----------------------

封包列表的面板中显示，编号，时间戳，源地址，目标地址，协议，长度，以及封包信息。 你可以看到不同的协议用了不同的颜色显示。  
你也可以修改这些显示颜色的规则， View ->Coloring Rules.  
![](https://img-blog.csdn.net/20171208165046952?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

封包详细信息 (Packet Details Pane)
----------------------------

这个面板是我们最重要的，用来查看协议中的每一个字段。  
各行信息分别为  
Frame: 物理层的数据帧概况  
Ethernet II: 数据链路层以太网帧头部信息  
Internet Protocol Version 4: 互联网层 IP 包头部信息  
Transmission Control Protocol: 传输层 T 的数据段头部信息，此处是 TCP  
Hypertext Transfer Protocol: 应用层的信息，此处是 HTTP 协议  
![](https://img-blog.csdn.net/20171208165400201?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

wireshark 与对应的 OSI 七层模型
-----------------------

![](https://img-blog.csdn.net/20171208165634035?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

TCP 包的具体内容
----------

从下图可以看到 wireshark 捕获到的 TCP 包中的每个字段。  
![](https://img-blog.csdn.net/20171208165702355?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

实例分析 TCP 三次握手过程
---------------

看到这， 基本上对 wireshak 有了初步了解， 现在我们看一个 TCP 三次握手的实例  
三次握手过程为  
![](https://img-blog.csdn.net/20171208165740999?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

在 wireshark 中输入 http 过滤， 然后选中 GET /zijian.hls.video.qq.com 的那条记录，右键然后点击”Follow TCP Stream”,  
这样做的目的是为了得到与浏览器打开网站相关的数据包，将得到如下图  
![](https://img-blog.csdn.net/20171208172103278?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

图中可以看到 wireshark 截获到了三次握手的三个数据包。第四个包才是 HTTP 的， 这说明 HTTP 的确是使用 TCP 建立连接的。

### 第一次握手数据包

客户端发送一个 TCP，标志位为 SYN，序列号为 0， 代表客户端请求建立连接。 如下图  
![](https://img-blog.csdn.net/20171208172851923?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 第二次握手的数据包

服务器发回确认包, 标志位为 SYN,ACK. 将确认序号 (Acknowledgement Number) 设置为客户的 I S N 加 1 以. 即 0+1=1, 如下图  
![](https://img-blog.csdn.net/20171208172934945?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 第三次握手的数据包

客户端再次发送确认包把服务器发来 ACK 的序号字段 + 1, 放在确定字段中发送给对方. 并且在数据段放写 ISN 的 + 1, SYN 标志位为 1,ACK 标志位为 1. 如下图:  
![](https://img-blog.csdn.net/20171208173006339?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY2g4NTMxOTk3Njk=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

就这样通过了 TCP 三次握手，建立了连接