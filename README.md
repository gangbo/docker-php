# docker-compose
## php开发环境快速搭建
## 环境说明
由于pecl安装时网络问题，所以把常用的几个扩展下载到了本地`docker-compose/pecl`
- php7.4
- swoole 4.6.7 
- redis

## 启动nginx,php-fpm(php7.4)
``
docker-compose -f docker-compose74fpm.yaml up -d
``
## 启动nginx,php-fpm(php8)
```docker-compose -f docker-compose8fpm.yaml up -d```

## 启动swoole(php8-cli,swoole)
```docker-compose -f docker-compose8cli-swoole.yaml up -d```

php8-cli启动后会执行`tail -f /dev/null`,这个命令在entrypoint.sh里，你可以替换成
swoole服务```php swoole_server.php```,在开发的时候也可以手动启动swoole服务
```
docker-compose -f docker-compose8cli-swoole.yaml exec app bash
php blog/swoole_server.php

```

##访问
``http://localhost:8099``

##快速启动
如果你一直是在php7.4版本做开发的话，可以把`docker-compose74fpm.yaml`改成`docker-compose.yaml`,
这样启动的时候可以直接`docker-compose up -d`
