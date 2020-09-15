# docker_php
ubuntu config php with docker, the dockefile from https://hub.docker.com/r/inblank/php5.6-apache/dockerfile

## includes:
- apache 2.4.5 (with rewrite、ssl module)
- php 5.6.40

## include php extentions:

- gd
- imap
- memcached
- memcache
- redis
- mongo
- mongodb
- amqp
- ssh2
- rar
- dbase
- exif
- opcache
- pdo_mysql
- mysql
- mysqli
- soap
- pcntl
- sockets
- tidy
- zip

# follow:

## 0、install docker
> by yourself

## 1、docker build image

```
docker build -t php56-latest -f php56-latest.docker .
```

## 2、docker run with build image

```
docker run -d  \
--name php56  \
-p 80:80 \
-v /media/develop/A_workspace:/var/www \
-v /media/develop/docker/apache/apache2.conf:/etc/apache2/apache2.conf \
-v /media/develop/docker/apache/vhosts.conf:/etc/apache2/sites-enabled/000-default.conf \
-v /media/develop/docker/apache_logs:/var/log/apache2 \
php56-latest

```