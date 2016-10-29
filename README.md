# MariaDB Docker image running on Alpine Linux

[![Docker Layers](https://img.shields.io/badge/docker%20layers-4-blue.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Size](https://img.shields.io/badge/docker%20size-47.9%20MB-blue.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Stars](https://img.shields.io/docker/stars/yobasystems/alpine-mariadb.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Pulls](https://img.shields.io/docker/pulls/yobasystems/alpine-mariadb.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/)

[![Alpine Version](https://img.shields.io/badge/alpine%20version-v3.4-green.svg?maxAge=2592000?style=flat-square)](http://alpinelinux.org/) [![MariaDB Version](https://img.shields.io/badge/Mariadb%20version-v10.1.18r0-green.svg?maxAge=2592000?style=flat-square)](https://mariadb.org/)


This Docker image [(yobasystems/alpine-mariadb)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) is based on the minimal [Alpine Linux](http://alpinelinux.org/) with [Mariadb 10.1.18-r0](https://mariadb.org/) (MySQL Compatible) database server.


## Features

  * Minimal size only 47.9 MB and only 4 layers
  * Memory usage is minimal on a simple install.
  * Mariadb Version 10.1.18-r0



## Creating an instance


```bash
docker run -it --name mysql -p 3306:3306 -v /var/lib/mysql:/var/lib/mysql -e MYSQL_DATABASE=wordpressdb -e MYSQL_USER=wordpressuser -e MYSQL_PASSWORD=hguyFt6S95dgfR4ryb -e MYSQL_ROOT_PASSWORD=hguyFtgfR4r9R4r76 yobasystems/alpine-mariadb

```
It will create a new db, and set mysql root password (default is RaNd0MpA$$W0Rd generated by pwgen) unless the data already exists.


## Volume structure

* `/var/lib/mysql`: Database files
* `/var/lib/mysql/mysql-bin`: MariaDB logs


## Environment Variables:

### Main Mariadb parameters:
* `MYSQL_DATABASE`: specify the name of the database
* `MYSQL_USER`: specify the User for the database
* `MYSQL_PASSWORD`: specify the User password for the database
* `MYSQL_ROOT_PASSWORD`: specify the root password for Mariadb

> https://mariadb.org/

## Docker Compose example:
####(Please pass your own credentials or let them be generated automatically, don't use these ones for production!!)

```yalm
mysql:
  image: yobasystems/alpine-mariadb
  environment:
    MYSQL_ROOT_PASSWORD: hguyFtgfR4r9R4r76
    MYSQL_DATABASE: wordpressdb
    MYSQL_USER: wordpressuser
    MYSQL_PASSWORD: hguyFt6S95dgfR4ryb
  expose:
    - "3306"
  volumes:
    - /data/example/mysql:/var/lib/mysql
  restart: always
```

## Source Repository

* [Bitbucket - yobasystems/alpine-mariadb](https://bitbucket.org/yobasystems/alpine-mariadb/)

* [Github - yobasystems/alpine-mariadb](https://github.com/yobasystems/alpine-mariadb)

## Links

* [Yoba Systems](https://www.yobasystems.co.uk/)

* [Dockerhub - yobasystems](https://hub.docker.com/u/yobasystems/)
