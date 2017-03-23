# docker
## What is this?
This is the docker environment for PHP developers
- php
- nginx
- mysql
- redis
- composer

![basic](https://raw.githubusercontent.com/yesterday679/docker/master/images/compose.png)

![composer](https://raw.githubusercontent.com/yesterday679/docker/master/images/composer.png)

![phpstrom](https://raw.githubusercontent.com/yesterday679/docker/master/images/phpstrom.png)

> from [laradocker](https://github.com/laradock/laradock)

## CONFIG
- need modify file `docker-compose.yml` at line **25**
~~~
  22 drivers:
  23   image: tianon/true
  24   volumes:
  25     - YOUR-LOCAL-DIRECTORY:/var/www/html
~~~
- param **YOUR-LOCAL-DIRECTORY**  eg`c:\www`


## USE
- Download `docker` or `docker for windows`
- `Shared Drivers`
- Config `Daemon` `Registry mirrors`  *eg:daocloud*
- Enter this directory
- #####Please enjoy it

## SKILL ON WINDOWS
- quickly enter some container `DockerExec php-fpm`
~~~
Function DockerExec($name){
    docker exec -it  $(docker ps | grep $name| awk '{print $1}')  /bin/bash
}
~~~
- use php composer
~~~
Function composer {
    docker run --rm --interactive --tty  --volume ${PWD}:/app composer-china  composer $args
}
~~~
- git bash inside phpstorm terminal
    > File -> Settings -> Tools -> Terminal
    
    Put the following line in the Shell Path field (adjust as necessary for your platform):
    > "C:\Program Files (x86)\Git\bin\sh.exe" -login -i
    
    If you are using the 64-bit version of Git, the path is different:
    > "C:\Program Files\Git\bin\sh.exe" -login -i



