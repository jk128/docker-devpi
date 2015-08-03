## Devpi Dockerfile

This repository contains **Dockerfile** of [Devpi](http://doc.devpi.net/) and is derived from `github.com/scrapinghub/docker-devpi`.

It contains Latest version of devpi-server (2.2.2), devpi-client (2.3.0), and additionally devpi-web (2.4.0)

### Dependencies

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download (https://index.docker.io/u/jk128/devpi/) from public [Docker Registry](https://index.docker.io/): `docker pull jk128/devpi`

   (alternatively, you can build an image from Dockerfile: `docker build -t="jk128/devpi" github.com/jk128/docker-devpi`)


### Usage

#### Run `devpi-server`

    docker run -d --name devpi -p 3141:3141 jk128/devpi

Devpi creates a user named `root` by default, its password can be set with
`DEVPI_PASSWORD` environment variable.

Alternatively you can mount your own folder holding index data (which is useful if you publish some libraries to private index)

    docker run -d --name devpi -p 3141:3141 --volume=<host_dir>:/mnt jk128/devpi
