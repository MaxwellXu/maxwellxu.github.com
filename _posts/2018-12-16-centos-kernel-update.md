---
layout: post
title: "centos6/7内核升级"
date: 2018-12-16 15:30:00
keywords: centos6,centos7,内核升级
categories: linux,centos,kernel
---

Linux内核按升级方式分为2种，即大版本升级或者小版本升级..


## * 大版本升级

待补充....

## * 小版本升级
### centos7

test
+  1、升级前必须要做几个检查
+ /boot剩余空间，默认为100Mb，仅仅可能容纳2-3个内核版本，分区的时候还是要留多点空间

test


1. test 
 2. 当前内核版本`uname -r`
  3. 系统所有内核版本`awk -F\' '$1=="menuentry " {print i++ " : " $2}' /etc/grub2.cfg`
   4. 网络是否可用`ping www.baidu.com`


### 升级内核
 查看是否有新版内核`yum info kernel`
- 通过yum升级`yum update kernel`

###卸载旧内核
- 通过yum卸载
 1. 查看已安装的内核`rpm -qa |grep kernel`
 ```
kernel-3.10.0-514.el7.x86_64
kernel-ml-4.18.7-1.el7.elrepo.x86_64
kernel-tools-libs-3.10.0-862.11.6.el7.x86_64
kernel-tools-3.10.0-862.11.6.el7.x86_64
kernel-3.10.0-862.11.6.el7.x86_64
 ```
 
 2. 通过yum卸载老版内核`yum remove kernel-3.10.0-514.el7.x86_64`
- 手动清除残余


### 重新生成grub 配置文件

1. 命令`grub2-mkconfig -o /boot/grub2/grub.cfg`


# 参考文章

1. _[Centos7 升级内核版本](https://www.cnblogs.com/xzkzzz/p/9627658.html)_

