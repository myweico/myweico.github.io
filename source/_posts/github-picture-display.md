---
title: 解决 github 图片显示不了的问题
date: 2020-02-21 06:16:03
tags: 
- github
categories:
- 技巧
---
{% img  /images/github-pic-display.png 600 '"title text" "alt text"' %}

有时候发现，国内的 github 的图片显示不了，这就让人很苦恼。

其实是存放图片的`avatars0.githubusercontent.com`等相关网址被墙了原因。

只需要修改 host 文件的相关内容即可以让 github 正常显示图片。

<!-- more --->
## host 文件位置
- Mac OS: `/etc/hosts`
- Windows: `C:\system32\drivers\etc\hosts`

## host 文件添加内容
寻找到 host 文件，在里面添加以下内容
```
# github start
192.30.253.112    github.com
192.30.253.119    gist.github.com
199.232.28.133    assets-cdn.github.com
199.232.28.133    raw.githubusercontent.com
199.232.28.133    gist.githubusercontent.com
199.232.28.133    cloud.githubusercontent.com
199.232.28.133    camo.githubusercontent.com
199.232.28.133    avatars0.githubusercontent.com
199.232.28.133    avatars1.githubusercontent.com
199.232.28.133    avatars2.githubusercontent.com
199.232.28.133    avatars3.githubusercontent.com
199.232.28.133    avatars4.githubusercontent.com
199.232.28.133    avatars5.githubusercontent.com
199.232.28.133    avatars6.githubusercontent.com
199.232.28.133    avatars7.githubusercontent.com
199.232.28.133    avatars8.githubusercontent.com
# github end
```
然后尝试刷新浏览器，便可以看到 github 可以正常显示图片了

{% img https://blog-1257268092.cos.ap-guangzhou.myqcloud.com/notes/20200221070415.png 600 '"title text" "alt text"' %}

若不行，再尝试刷新 DNS 缓存。