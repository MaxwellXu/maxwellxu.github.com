---
layout: post
title: "使用Apache Ftpserver"
date: 2015-01-25 00:50:00
keywords: ftp服务器,apache ftpserver
categories: Other
---

简单搭建ftp服务器，以前一直用**serv-u**来做ftp服务器，但是这个软件要收费，懒得破解。于是想起**apache**可能有开源的ftp项目，度娘了一下还真有。

##看了下文档，开始部署

### win7 64位

+	1、下载[Apache ftpserver][1]，并解压
+	2、修改`res\conf\ftpd-typical.xml`，可参考`res\conf\ftpd-full.xml`
+	3、安装`bin\server install ftpd res\conf\tpd-typical.xml`，可参考[命令行安装][2]
+	4、启动`bin\ftpdw`

### 附简易的配置

{% highlight XML %}
<server xmlns="http://mina.apache.org/ftpserver/spring/v1"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="
   http://mina.apache.org/ftpserver/spring/v1 http://mina.apache.org/ftpserver/ftpserver-1.0.xsd	
   "
id="myServer" max-logins="10">
	<listeners>
		<nio-listener name="default" port="21">
		    <ssl>
                <keystore file="E:\\Develop\\apache-ftpserver-1.0.6\\res\\ftpserver.jks" password="password" />
            </ssl>
		</nio-listener>
	</listeners>
	<file-user-manager file="E:\\Develop\\apache-ftpserver-1.0.6\\res\\conf\\users.properties" encrypt-passwords="md5"/>
</server>
{% endhighlight %}

### ps:
+	1、安装**Apache ftpserver**前需先配置好**32位JDK**
+	2、**ftpdw.exe**在win7 64位下可能运行不了，需以**windows xp**兼容模式运行
+	3、其他部署问题看`res\log`中的日志

[1]:http://mina.apache.org/ftpserver-project/ "Apache ftpserver"
[2]:http://mina.apache.org/ftpserver-project/ftpserver_as_windows_service.html "install ftpd as a windows service"