# Nginx介绍

 
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