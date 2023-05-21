# Supported tags and respective `Dockerfile` links

* `7.0-fpm` [(7.0/fpm/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.0/fpm/Dockerfile)
* `7.0-cli` [(7.0/cli/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.0/cli/Dockerfile)
* `7.1-fpm` [(7.1/fpm/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.1/fpm/Dockerfile)
* `7.1-cli` [(7.1/cli/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.1/cli/Dockerfile)
* `7.2-fpm` [(7.1/fpm/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.2/fpm/Dockerfile)
* `7.2-cli` [(7.1/cli/Dockerfile)](https://github.com/diglin/docker/blob/master/php/7.2/cli/Dockerfile)
* `8.2-cli` [(7.1/cli/Dockerfile)](https://github.com/diglin/docker/blob/master/php/8.2/cli/Dockerfile) - No blackfire and Xdebug. Used for our internal deployment tool

# Reference

Please refer to [the official library on docker hub](https://hub.docker.com/_/php/).

# What is the difference ?

- Please see the original maintainer of the image that we use [Monsieur Biz](https://github.com/monsieurbiz)
- Additionally we added XDEBUG version depending on the PHP supported version

# Usage

```
version: "3"

services:
  php-fpm:
    images: diglin/php:7.0-fpm
    build:
      args:
        - XDEBUG_ENABLED=1
    volumes:
      - ./src:/var/www:cached
      - ./src/.composer:/var/www/.composer:cached
      - ./docker/php/php-fpm.conf:/usr/local/etc/php-fpm.conf
    links: 
      - mariadb # if relevant

``` 


# Maintainer

The whole team of [diglin](https://github.com/diglin) maintains these images.

# Big thanks

To the [Monsieur Biz](https://github.com/monsieurbiz) Team for sharing their docker repo.
