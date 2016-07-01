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

