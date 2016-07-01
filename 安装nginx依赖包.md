# 安装nginx依赖包


- pcre：重写rewrite
- zlib：gzip压缩

```
yum install gcc gcc-c++ autoconf -y
yum install openssl openssl-devel -y 
yum install pcre pcre-devel -y
yum install zlib zlib-devel -y
yum install openssl openssl-devel -y
```

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