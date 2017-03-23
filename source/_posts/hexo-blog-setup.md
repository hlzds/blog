---
title: 用Hexo搭建网站
date: 2016-05-15 4:30:06
categories: 
- 开源
tags: [hexo,blog,tool]

---

## 开始
- 网上资料无穷尽，但还是推荐[官方文档](https://hexo.io/zh-cn/)


## 无数的坑
- .yml文件，凡是冒号后面一定要跟空格，不然会出现各种奇怪死法
- 如果node_modules里面的工具重复装，就会出现错误，这是需要删掉之后，重新`npm install`，如`npm install hexo-deployer-git --save`
- hexo的结构我都快背下来了：_config.yml是主要配置文件，`/source/_posts`里面放的是.md文章，public放的是生成的网页，theme里面放的是主题（废话），node_modules里面放的是npm的工具，两个.json文件是数据库连接文件

<!-- more -->

- _config.yml配置GitHub和Coding双线路岂止是有点坑···要在source目录下touch一个空白标志文件，要用`git -T git@coding.net`还有`git remote -u origin master`连接，复习了一遍git的高级用法···
- 图标和LOGO分别放在主目录下的source目录和主题目录下的source/image目录（把里面能读的英文文档都读一遍，也就知道了）
- 部署博客到线上：`hexo d -g`。但是我发现有个文件夹名字无论如何都是大写的，即使我在本地小写，但是使用这个命令push上去之后还是大写！后来查`npm_modules/hexo-deploy-git/`目录里的.md文档，发现了reset的方法：删掉一个隐藏的`.deploy`目录，然后重新生成就可以了

- 把主题的_config.yml里面的谷歌字体🈲了之后，加载速度**飞快**（3秒），之前将近10秒简直感人
- 本地调试`hexo s`访问localhost：4000.但是开VPN就进不了
- **······还有无数的坑，可能会从以下的链接得到解答，也可能不会**==但是hexo真的很好玩啊==
- categories这选项点开一直不能用？先分别看看根目录和主题目录里面的_config.yml文件里面的category_dir路径打开了没（就是#去掉了没），然后`hexo new page categories`,进入source/categories,编辑.md文件，类似这样：
 
```
title: categories
date: 2015-10-20 06:49:50
type: "categories"
comments: false
```

## 链接
[小土刀的博客-静态博客 Github 并存指南](http://wdxtub.com/2016/01/05/hexo-github-site/)

[Hexo系列教程: (四)将独立域名与GitHub Pages的空间绑定](http://iread.io/2015/09/hexo-guide-4/)

[利用Hexo玩转Coding pages](http://httpbin.com.cn/%E5%88%A9%E7%94%A8hexo%E7%8E%A9%E8%BD%ACcoding-pages/)

[leo的博客](http://note.leodev.me/)速度好慢啊

[各种好玩的工具](http://theme-next.iissnan.com/third-party-services.html)

[hero同时部署到coding(gitcafe)和github](http://shomy.top/2016/03/03/hexo-in-coding-github/)

[Hexo 一键群发_Hexo Batch Deploy](http://daxiawj.github.io/2014/05-14-Hexo-%E4%B8%80%E9%94%AE%E7%BE%A4%E5%8F%91-Hexo-Batch-Deploy.html)

[git优先账户](https://github.com/hexojs/hexo/issues/1927)到底先用哪个git账户？可以在.ssh/config里配置

[hexo分类和标签设置](https://segmentfault.com/q/1010000002561642)

## 其他
- 绑定独立域名
- 使用swifty搜索栏、访问统计、图床等工具
- CDN优化速度
- 精准定位


