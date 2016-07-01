# nginx介绍

 
- nginx是一款www服务软件，俄罗斯人开发的开源并且性能很高，软件大小共780K左右
- nginx本身是一个静态（html、js、css、jpg等）的www软件，不能解析动态的PHP、JSP、DO、
淘宝更改的nginx，tengine
- nginx使用平台：Unix、linux、Windows
- nginx目前排名：第二位，并且上升趋势，全球约25%占比

查看header

```
[root@lnmp01 application]# curl -I www.bjstack.com
HTTP/1.1 200 OK
Server: nginx
Date: Fri, 01 Jul 2016 07:13:42 GMT
Content-Type: text/html
Content-Length: 194
Connection: keep-alive
WWW-Authenticate: Basic realm="nginx basic auth for www.bjstack.com"
```

##nginx主要功能
- www  web服务、邮件服务、邮件代理
- 负载均衡（反向代理proxy）
- web cache（web缓存），相当于squid

##nginx特点：
- 最大特点
-    静态小文件（1M以下），支持高并发，同时占用的资源很少。3w并发，十个进程，内存占用150M
-    配置简单、灵活、轻量
-    高并发（静态小文件），静态几万的并发
-    占用资源少
-    支持epoll模型，使得nginx可以支持高并发，apache使用select模型
-    nginx可以配合动态PHP服务（Fastcgi接口）
-    利用nginx可以对IP限速，可以限制连接数
-    它所具备的其他www服务特性如下：
-    支持基于名字、端口以及IP的多虚拟主机站点
-    支持rewrite模块，支持URI重写及正则表达式匹配
-    支持基于客户端IP地址和HTTP基本认证的访问控制
-    支持http响应速率限制
-    支持同一IP地址的并发连接或请求数限制

#####2.4 nginx的应用场合
-    提供静态服务（图片、视频服务、html、js、css、.flv，jpg，gif等），类似ighttpd，支持几万并发
-    提供动态服务，nginx+fastcgi的方式运行php、jsp，动态并发：500-1500
-    提供反向代理（proxy）服务，或者称为负载均衡，日PV2000w以下，并发1万以下，都可以直接用nginx做反向代理。相当于haproxy、F5、A10
-    提供缓存服务。类似squid，varnish，ats

#####2.5 nginx主要应用场景
-    web服务器（首选）
-    静态文件，nginx首选
-    动态文件，配合fastcgi支持php
-    反向代理（负载均衡），1000-2000W PV，并发6000
-    web缓存，相当于squid（CDN主要适用squid）

#####2.6 nginx支持虚拟主机
-    一个Server标签就是一个虚拟主机
-    基于域名的虚拟主机。通过域名来区分虚拟主机  ==>应用：外部网站  *****
-    基于端口的虚拟主机。通过端口来区分虚拟主机  ==>应用：公司内部网站，网站的后台，主要为了安全考虑  ***
-    基于IP的虚拟主机。几乎不用，不支持ifconfig别名，配置文件可以。 ~~了解

