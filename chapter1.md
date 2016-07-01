# nginx 安装

>ningx version: 1.8.0



##1.基础环境：


```
[root@java01 ~]# cat /etc/redhat-release 
CentOS release 6.7 (Final)
[root@java01 ~]# uname -r
2.6.32-573.el6.x86_64
```

## 2.yum安装nginx依赖包

- pcre：重写rewrite
- zlib：gzip压缩

```
yum install gcc gcc-c++ autoconf -y
yum install openssl openssl-devel -y 
yum install pcre pcre-devel -y
yum install zlib zlib-devel -y
yum install openssl openssl-devel -y
```
## 3.pagespeed安装：

- ngx_pagespeed插件：前端网页访问提速优化插件 

``` 
# pwd
/home/yongzhen/tools
wget https://github.com/pagespeed/ngx_pagespeed/archive/v1.8.31.4-beta.tar.gz 
wget https://dl.google.com/dl/page-speed/psol/1.8.31.4.tar.gz 
tar -zxvf v1.8.31.4-beta.tar.gz 
cp 1.8.31.4.tar.gz ./ngx_pagespeed-1.8.31.4-beta 
cd ngx_pagespeed-1.8.31.4-beta 
tar -xzvf 1.8.31.4.tar.gz
```

##4.nginx 安装

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