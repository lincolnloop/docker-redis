## Redis Dockerfile


This repository contains **Dockerfile** of [Redis](http://redis.io/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/dockerfile/redis/) published to the public [Docker Registry](https://index.docker.io/).


### Dependencies

* [dockerfile/ubuntu](https://github.com/dockerfile/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/dockerfile/redis/) from public [Docker Registry](https://index.docker.io/): `docker pull dockerfile/redis`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/redis" .`)


### Usage

    docker run -i -t dockerfile/redis bash

#### `redis-server`

    docker run -i -t dockerfile/redis redis-server

#### `redis-cli`

    docker run -i -t dockerfile/redis redis-cli
