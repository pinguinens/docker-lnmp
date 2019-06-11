# Introduction

Deploy lnmp(Linux, Nginx, MySQL, PHP7) using docker.

I want to share my ideas and designs about Web-Deploying using Docker with you.

### Architecture

![architecture][1]

The whole app is divided into three Containers:

1. Nginx is running in `Nginx` Container, which handles requests and makes responses.
2. PHP or PHP-FPM is put in `PHP` Container, it retrieves php scripts from host, interprets, executes then responses to Nginx. If necessary, it will connect to `MySQL` as well.
3. MariaDB lies in `MariaDB` Container, 

Our app scripts are located on host, you can edit files directly without rebuilding/restarting whole images/containers.

### Contents

- nginx:1.17.0
- php:7.3.6
- mariadb:10.3.15
- Self-signed SSL Certificate

### PHP Extensions
- xdebug:2.7.2 (port 9009)
- GD Lib
- PDO MySQL driver
- MySQL Extension

### Build and Run

At first, you should have had [Docker](https://docs.docker.com) and [Docker Compose](https://docs.docker.com/compose) installed.

Without building images one by one, you can make use of `docker-compose` and simply issue:

    $ sudo docker-compose up

For more operations to containers, please refer to:

    $ sudo docker-compose --help

Check out your https://\<docker-host\> and have fun :beer:

### Contributors

Pinguinens <nikolay@tegra.media>

Micooz <micooz@hotmail.com>

sndnvaps <sndnvaps@gmail.com>

### License

MIT

  [1]: architecture.png
