# VSCODE

![logo](https://assets.gitlab-static.net/uploads/-/system/project/avatar/13865455/1200px-Visual_Studio_Code_1.35_icon.svg.png)

## INDEX

- [VSCODE](#vscode)
  - [INDEX](#index)
  - [BADGES](#badges)
  - [INTRODUCTION](#introduction)
  - [PREREQUISITES](#prerequisites)
  - [INSTALL](#install)
    - [DOCKER RUN](#docker-run)
    - [DOCKER COMPOSE](#docker-compose)
  - [LICENSE](#license)

## BADGES

[![pipeline status](https://gitlab.com/oda-alexandre/vscode/badges/master/pipeline.svg)](https://gitlab.com/oda-alexandre/vscode/commits/master)

## INTRODUCTION

Docker image of :

- [vscode](https://code.visualstudio.com/)

Continuous integration on :

- [gitlab pipelines](https://gitlab.com/oda-alexandre/vscode/pipelines)

Automatically updated on :

- [docker hub public](https://hub.docker.com/r/alexandreoda/vscode/).

## PREREQUISITES

Use [docker](https://www.docker.com)

## INSTALL

### DOCKER RUN

```\
docker run -d --name vscode -v /tmp/.X11-unix/:/tmp/.X11-unix/ -v ${HOME}:/home/vscode -e DISPLAY --cap-add=SYS_ADMIN --network host alexandreoda/vscode
```

### DOCKER COMPOSE

```yml
version: "3.7"

services:
  vscode:
    container_name: vscode
    image: alexandreoda/vscode
    restart: "no"
    network_mode: host
    privileged: false
    cap_add:
      - SYS_ADMIN
    environment:
      - DISPLAY
    volumes:
      - "${HOME}:/home/vscode"
      - "/tmp/.X11-unix:/tmp/.X11-unix"
```

## LICENSE

[![GPLv3+](http://gplv3.fsf.org/gplv3-127x51.png)](https://gitlab.com/oda-alexandre/vscode/blob/master/LICENSE)
