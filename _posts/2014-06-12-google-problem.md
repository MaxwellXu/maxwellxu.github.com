---
layout: post
title: "使用google问题"
date: 2014-06-12 01:50:00
keywords: google用不了,google 403
categories: Other
---

早上用google搜索出错，出现*403 forbidden*错误，一时很茫然，以为是自己设置了什么，后来在微博能搜到这个错误，很多人都遇到这样的问题，就是说*google*又被墙了。

要能够在国内使用正常使用*google*，我自己的经验来看，只有3种方法：

+   修改*hosts*文件
+   使用*ipv6*
+   使用*vpn*


## 修改*hosts*文件

由*月光博客*发的一条[微博][1]可以找到[google全球ip][2]，找一个可用去替换掉下面的*ip*即可

{% highlight TeX %}
218.189.25.180 encrypted.google.com
218.189.25.180 encrypted-tbn0.google.com
218.189.25.180 encrypted-tbn1.google.com
218.189.25.180 encrypted-tbn2.google.com
218.189.25.180 encrypted-tbn3.google.com
218.189.25.180 encrypted-tbn4.google.com
218.189.25.180 encrypted-tbn5.google.com
218.189.25.180 encrypted-tbn6.google.com
218.189.25.180 encrypted-tbn7.google.com
218.189.25.180 encrypted-tbn8.google.com
218.189.25.180 encrypted-tbn9.google.com
218.189.25.180 encrypted.google.com.hk
218.189.25.180 www.google.com.hk
218.189.25.180 www.google.com
218.189.25.180 www.google.hk
218.189.25.180 themes.googleusercontent.com
218.189.25.180 fonts.googleapis.com
218.189.25.180 lh4.googleusercontent.com
218.189.25.180 account.google.com
218.189.25.180 ssl.gstatic.com
{% endhighlight %}

### windows的hosts路径
修改可能需要权限，`C:\Windows\System32\drivers\etc\hosts`

### mac的hosts路径
修改需要权限，`/etc/hosts`

##另外2种方法，待整理再更新

[1]:http://weibo.com/1494759712/B8vu5EkGv?type=repost "月光博客-google-ip"
[2]:http://www.kookle.co.nr/ "google-all-ip"
