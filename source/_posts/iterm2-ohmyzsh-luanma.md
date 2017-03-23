---
title: iterm2+ohmyzsh-乱码
date: 2016-05-18 02:35:32
tags: [iterm2,乱码,ohmyzsh]
categories: [工具,配置]
---

## 起因
**自从装上了iTerm2和ohmyzsh，一打开终端就会出现`口~口`，查阅多方得知，这只是个符号，不算是乱码，可以在`~/.zshrc`里面配置，但是我还是看着不爽🙊**

## 解决办法
参考了[V2EX的一篇文章](https://www.v2ex.com/t/184928)，通过评论区的另一个链接，`git clone`了powerline字体并安装，然后在如下：
<!--more-->
```

Menu Bar ▸ iTerm ▸ Preference ▸ Profiles
 ▸ (Your Profile) ▸ Text ▸ Regular Font 
是否选择了 Powerline 字体。
```
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="http://music.163.com/outchain/player?type=2&id=149306&auto=1&height=66"></iframe>


