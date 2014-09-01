## Redis Dockerfile 60% smaller image on debian:wheezy

This repository contains **Dockerfile** of [Redis](http://redis.io/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/dockerfile/redis/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).

The original master is based of Debian ubuntu:14.04: 473MB.
This image is based on debian wheezy: 185MB.
```
$ docker images
REPOSITORY                        TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
hmalphettes/redis                 latest              1adb1e2723d3        27 seconds ago      185.7 MB
dockerfile/redis                  latest              755cafb337f4        20 hours ago        473 MB
```


### Base Docker Image

* [google/debian:wheezy](https://github.com/GoogleCloudPlatform/debian-docker)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/dockerfile/redis/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull dockerfile/redis`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/redis" github.com/dockerfile/redis`)


### Usage

#### Run `redis-server`

    docker run -d --name redis -p 6379:6379 dockerfile/redis

#### Run `redis-server` with persistent data directory. (creates `dump.rdb`)

    docker run -d -p 6379:6379 -v <data-dir>:/data --name redis dockerfile/redis

#### Run `redis-server` with persistent data directory and password.

    docker run -d -p 6379:6379 -v <data-dir>:/data --name redis dockerfile/redis redis-server /etc/redis/redis.conf --requirepass <password>

#### Run `redis-cli`

    docker run -it --rm --link redis:redis dockerfile/redis bash -c 'redis-cli -h redis'
