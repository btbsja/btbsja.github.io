---

layout:   post          # 使用的布局（不需要改）

title:   Github+jsDelivr+PicGo搭建完美博客图床          # 标题 

subtitle:  Blog          #副标题

date:    2020-02-04       # 时间

author:   Btbsja         # 作者

header-img: img/bg-2020-02-04.jpg          #这篇文章标题背景图片

catalog: true            # 是否归档

tags:                #标签

  - Blog

---

# Github+jsDelivr+PicGo搭建完美博客图床

![图片来源于网络 侵删](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200223131843.jpg)

【图片来源于网络 侵删】

## 前言

由于最近刚刚搭建了个人博客，急需一个个人图床，经过对七牛云、又拍云、SM.MS等等得对比发现并不稳定并且存在流量和空间得限制，最后确定出 Github + jsDelivr + picGo 的完美解决方案。

* Github——数据仓库

* jsDelivr——CDN加速

* PicGo——图床上传工具

  

## 一、 Github 仓库

1.  新建一个仓库。

2.  在个人设置里找到 Developer settings![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200223120957.png)
   
3.  点击 Personal access tokens![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200223121109.png)

4.  Generate new token

5.  勾选 repo

6.  完成

7.  记下 token ，他只显示一次。

## 二、 PicGo

1.  下载 [PicGo](https://github.com/Molunerfinn/picgo/releases)

2.  安装后打开 GitHub 图床设置![](https://cdn.jsdelivr.net/gh/btbsja/btbsjaimg/img/20200223121821.png)


3.  把第一步得到的数据填入其中

4.  自定义域名：由于使用 jsDelivr 加速访问，所以将自定义域名设置为”https://cdn.jsdelivr.net/gh/用户名/图床仓库名 “。

5.  请您愉快的使用图床，或移步安装插件，或进行相应的重命名设置。