# docker-compose
## php开发环境快速搭建
## 环境说明
由于pecl安装是网络问题，所以把常用的几个扩展下载到了本地`docker-compose/pecl`
- php7.4
- swoole 4.6.7 
- redis

## 启动(默认php7.4)
``
docker-compose up -d
``
## php8
```docker-compose -f docker-compose8.yaml up -d```
