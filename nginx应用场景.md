# nginx的应用场景
-    提供静态服务（图片、视频服务、html、js、css、.flv，jpg，gif等），类似ighttpd，支持几万并发
-    提供动态服务，nginx+fastcgi的方式运行php、jsp，动态并发：500-1500
-    提供反向代理（proxy）服务，或者称为负载均衡，日PV2000w以下，并发1万以下，都可以直接用nginx做反向代理。相当于haproxy、F5、A10
-    提供缓存服务。类似squid，varnish，ats

