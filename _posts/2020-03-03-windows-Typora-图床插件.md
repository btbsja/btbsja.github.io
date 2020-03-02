---

layout:   post          # 使用的布局（不需要改）

title:   windows-Typora-图床插件          # 标题 

subtitle:         #副标题

date:    2020-03-03       # 时间

author:   Btbsja         # 作者

header-img: img/bg-2020-03-03.jpg          #这篇文章标题背景图片

catalog: true            # 是否归档

tags:                #标签

  - Blog

---
# windows-Typora-图床插件

[插件下载](https://download.csdn.net/download/Btbsja/12206646)

## 功能
用 Typora 写 md 文件时自动上传 图片至网络图床
## 安装步骤
1. 将下载的 plugins 文件夹粘贴至安装目录

```
例如：C:\Program Files\Typora\resources\app
```

2. 修改 app 文件夹内 window.html 文件

CTRL+F 搜索

```
<script src="./app/window/frame.js" defer="defer"></script>
```

在其后增加一行

```
<script src="./plugins/image/upload.js" defer="defer"></script>
```

3. 重启Typora

4. 上传至 Github 设置

打开 plugins/image/upload.js 文件
最下面将最后一行的 $.image.init()
修改

```
$.image.init({
    target:'github',
    github:{
        Token : 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx', 
        CommitterName : 'nickname',                 // github的昵称
        CommitterEmail : 'email@mail.com',          // github的邮箱
        Repository : 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',      // github项目名
        Filepath : '/img',                              // 图片保存目录
        jsDelivrCND : false,       // 是否开启GitHub图片走镜像,如要打开设置为：true
    }
});
```

具体关于 Token 的申请可以参考[另一篇文章](https://btbsja.ml/2020/02/04/Github+jsDelivr+PicGo%E6%90%AD%E5%BB%BA%E5%AE%8C%E7%BE%8E%E5%8D%9A%E5%AE%A2%E5%9B%BE%E5%BA%8A/)



本教程参考于 [Github](https://github.com/Thobian/typora-plugins-win-img)

其他图床的教程请参考作者仓库