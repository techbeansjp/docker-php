# docker basic for PHP,MySQL

## clone

```
$ git clone git@github.com:techbeansjp/docker-php.git
$ cd docker-php
```

## select web server 

check docker-compose.yml

choise apache or nginx: 

```
  httpd:
    build:
      context: ./docker/httpd
    ports:
      - ${HTTPD_PORT}:80
    privileged: true
    links:
      - php
    volumes:
      - "./src/:/var/www/html"
      - "./docker/httpd/apache.conf:/etc/httpd/conf/httpd.conf"
```

```
  nginx:
    build:
      context: ./docker/nginx
    ports:
      - ${HTTPD_PORT}:80
    privileged: true
    links:
      - php
    volumes:
      - "./src:/var/www/html"
      - "./docker/nginx/default.conf:/etc/nginx/nginx.conf"
```

Please comment-out if you do not use it.

## select port

if you want to change port, check `.env` file.
(HTTPD_PORT, MYSQL_PORT)

## install

```
$ docker-compose build
```

## start

```
$ docker-compose up -d
```

## confirm browsing

```
http://localhost:8080/phpinfo.php
```

You will confirm `phpinfo()` in your browser.
(if you changed port that setting your port.)

## access in docker-container

```
$ docker-compose exec php /bin/bash
```

## mysql

Information for connect to mysql 

```
host: 127.0.0.1
username: mysqluser
password: password
database: dev_php
port: 3307
```

## and...

please delete `.git` and `.gitignore` .
