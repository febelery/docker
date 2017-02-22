# docker
## What is this?
This is the docker environment for PHP developers
- php
- nginx
- mysql
- redis
- composer

> from laradocker

## CONFIG
- need modify file `docker-compose.yml` at line **25**
~~~
  22 drivers:
  23   image: tianon/true
  24   volumes:
  25     - YOUR-LOCAL-DIRECTORY:/var/www/html
~~~
- param **YOUR-LOCAL-DIRECTORY**  eg`c:\www`



## SKILL ON WINDWOS
~~~
Function DockerExec($name){
    docker exec -it  $(docker ps | grep $name| awk '{print $1}')  /bin/bash
}
~~~
~~~
Function composer {
    docker run --rm --interactive --tty  --volume ${PWD}:/app composer-china  composer $args
}
~~~


