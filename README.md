# docker basic for PHP,MySQL

## install & start

```
$ git clone git@github.com:techbeansjp/docker-php.git
$ cd docker-php
$ docker-compose build
$ docker-compose up -d
```

## confirm browsing

```
http://localhost:8080/phpinfo.php
```

You will confirm `phpinfo()` in your browser.

## access in docker-container

```
$ docker-compose exec app /bin/bash
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
