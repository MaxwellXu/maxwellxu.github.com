---
layout: post
title: "使用google问题"
date: 2014-06-12 01:50:00
keywords: google搜索用不了,google 403
categories: Other
---

早上用google搜索出错，出现*403 forbidden*错误，一时很茫然，以为是自己设置了什么，后来在微博能搜到这个错误，很多人都遇到这样的问题，就是说*google*又被墙了。

要能够在国内使用正常使用*google*，我自己的经验来看，只有3种方法：

+   修改*hosts*文件
+   使用*ipv6*
+   使用*vpn*

## 记录

### 2013-06-13
今天又用不了*google*，ip:*218.189.25.180*，ping不通。重新换了ip也无法使用搜索功能，将域名指向*218.189.25.132*提示*SSL Error*，不使用https可搜索。

## 修改*hosts*文件

由*月光博客*发的一条[微博][1]可以找到[google全球ip][2]，找一个可用去替换掉下面的*ip*即可

{% highlight TeX %}
#218.189.25.180 encrypted.google.com
#218.189.25.180 encrypted-tbn0.google.com
#218.189.25.180 encrypted-tbn1.google.com
#218.189.25.180 encrypted-tbn2.google.com
#218.189.25.180 encrypted-tbn3.google.com
#218.189.25.180 encrypted-tbn4.google.com
#218.189.25.180 encrypted-tbn5.google.com
#218.189.25.180 encrypted-tbn6.google.com
#218.189.25.180 encrypted-tbn7.google.com
#218.189.25.180 encrypted-tbn8.google.com
#218.189.25.180 encrypted-tbn9.google.com
#218.189.25.180 encrypted.google.com.hk
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

## 使用*ipv6*

### 通过*isatap*隧道

#### win7配置如下

+	1、确保本地连接`ipv6`协议勾选中
+	2、确保`IP Helper`服务是自动启动并运行中
+	3、确保是宽带拨号，如果是通过路由连接并使用nat，那么是不能正常连接`isatap`服务器
+	4、管理员打开命令行窗口，输入`netsh`，输入`int`，输入`ipv6`，输入`set route isatap.sjtu.edu.cn`，输入`set state enabled`，此时设置完毕，退出输入`exit`

以上4点做到，应该是能成功，能成功标识是访问一下测试网站

+	1、[google-ipv6][21] 能打开是说明成功的
+	2、[kame][22] 点击*watch dancing kame*，乌龟会动说明是成功的

详细图文请参考[ipv6高速访问国外网站][20]

##另外1种方法，待整理再更新

[1]:http://weibo.com/1494759712/B8vu5EkGv?type=repost "月光博客-google-ip"
[2]:http://www.kookle.co.nr/ "google-all-ip"

[20]:http://logicmd.net/2010/04/high-speed-visiting-abroad-websites-using-ipv6/ "ipv6-tutorial-1"
[21]:http://ipv6.google.com "ivp6-test－connection-1"
[22]:http://www.kame.net "ivp6-test-connection-2"

