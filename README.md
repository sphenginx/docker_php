# docker_php
ubuntu config php with docker, the dockefile from https://hub.docker.com/r/inblank/php5.6-apache/dockerfile

# 0、install docker
> by yourself

# 1、docker build image

```
docker build -t php56-latest -f php56-latest.docker .
```

# 2、docker run with build image

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