# 编译安装nginx

```
useradd www -u 666 -M -s /sbin/nologin
wget http://nginx.org/download/nginx-1.8.0.tar.gz 
tar -zxvf nginx-1.8.0.tar.gz 
cd nginx-1.8.0 
./configure --user=www \
--prefix=/usr/local/nginx-1.8.0 \
--with-http_ssl_module \
--with-http_stub_status_module \
--with-http_realip_module \
--add-module=/home/yongzhen/tools/ngx_pagespeed-1.8.31.4-beta
make && make install
cd ..
ln -s /usr/local/nginx-1.8.0/ /usr/local/nginx
```