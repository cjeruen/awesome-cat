
# Docker for Cat

## How to use

### 1. Manual

```

1. cofigure something about cat before run
    1.1. create database cat
    1.2. create cat tables (src/Cat.sql)
    1.3. change data/appdatas/datasources.xml
         -> jdbc:mysql://mysql_cat:3306/cat

2. build new images
$ docker build -t dianping/cat:v2.0.0 .

3. run container
$ docker run --name dianping-cat -d -p 22801:2280 -p 22811:2281 dianping/cat:v2.0.0

```

### 2. via docker-compose

- https://github.com/cjeruen/awesome-cat/tree/master/docker-cat-example