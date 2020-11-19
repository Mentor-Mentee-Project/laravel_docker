# laravel Docker

## Introduction
Build Laravel development environment using Nginx + PostgreSQL with docker-compose.
This repository is highly inspired by https://github.com/ucan-lab/docker-laravel. Many thanks to [Yuki Imamura](https://github.com/ucan-lab).
The setting and instruction are expecially modified for **Windows OS**.

## Usage

```bash
$ git clone git@github.com:Ryo-M-49/laravel_docker.git
$ cd laravel_docker

$ git clone [whatever repository you want to clone] ./backend # Clone the existing repository you are about to work on
$ make init
```
Then, start up Command Prompt as **Administrator** on WIndows and
```Command Prompt
$ cd [laravel_docker root]/backend/public
$ mklink /D storage "/work/backend/storage/app/public"
```

You are ready to go!

## Container structure

```bash
├── app
├── web
└── db
```

### app container

- Base image
  - [php](https://hub.docker.com/_/php):7.4-fpm-buster
  - [composer](https://hub.docker.com/_/composer):2.0

### web container

- Base image
  - [nginx](https://hub.docker.com/_/nginx):1.18-alpine
  - [node](https://hub.docker.com/_/node):14.2-alpine

### db container

- Base image
  - [alpine](https://hub.docker.com/_/postgres):8.0
