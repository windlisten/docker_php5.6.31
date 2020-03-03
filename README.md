# docker_php5.6.31

- 本项目包含构建 php5.6.31 镜像的源文文件； 
- docker image 地址：[wenzhi/php5.6.31](https://cloud.docker.com/repository/registry-1.docker.io/wenzhi/php5.6.31)

## 拓展
[PHP Modules]     
amqp
apc
apcu
bcmath
calendar
Core
ctype
curl
date
dom
ereg
filter
ftp
gd
gettext
hash
iconv
imagick
json
libxml
mbstring
mcrypt
mhash
mongo
mysqli
mysqlnd
openssl
pcntl
pcre
PDO
pdo_mysql
pdo_sqlite
Phar
posix
rdkafka
redis
Reflection
session
shmop
SimpleXML
soap
sockets
SPL
sqlite3
standard
swoole
sysvmsg
sysvsem
sysvshm
tokenizer
xhprof
xml
xmlreader
xmlrpc
xmlwriter
Zend OPcache
zip
zlib
zookeeper

[Zend Modules]     
Zend OPcache

## 使用方式
### php-fpm :  
nginx conf :    
```
    location ~ \.php$ {
        fastcgi_pass     0.0.0.0:9009;
        fastcgi_param   SCRIPT_FILENAME /var/www_data$fastcgi_script_name;
        include         fastcgi_params;
        try_files $uri =404;
    }
```  
docker run -p9009:9000 -v /your-php-file-path:/var/www_data -d wenzhi/php5.6.31
### php-cli :
alias docker_php="docker run -it --rm -v /usr/src:/usr/src -v /home/xxx:/home/xxxx -w $PWD wenzhi/php5.6.31 php"
docker_php test.php
