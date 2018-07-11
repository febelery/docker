# docker

## What is this?
This is the docker environment for PHP developers
- php
- nginx
- mysql
- redis
- composer
- openresty
- slate
- mongo


## HOW TO USE
- Download `docker` or `docker for windows`
- `Shared Drivers`
- Config `Daemon` `Registry mirrors`  *eg:daocloud*
- Enter this directory


## SKILL
- enter container `DockerExec php-fpm`
~~~
Function DockerExec($name){
    docker exec -it  $(docker ps | grep $name| awk '{print $1}')  /bin/bash
}
~~~
- composer
~~~bash
cd composer/ 
docker build -t composer-china .
~~~
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

## ALIAS
```bash
alias winpwd="pwd | sed 's/^\/d/D:/' | sed 's/^\/c/C:/'"
alias composer="docker run --rm --interactive --tty  --volume `winpwd`:/app composer-china composer --ignore-platform-reqs --no-scripts $args"
alias php_docker="docker exec -ti `docker ps | grep php-fpm | awk '{print $1}'` bash"
alias python="docker run -it --rm --volume $(winpwd):/usr/src/app $(docker images | grep docker_python | awk '{print $3}') ipython $args"
alias cnpm="npm --registry=https://registry.npm.taobao.org --cache=$HOME/.npm/.cache/cnpm --disturl=https://npm.taobao.org/dist --userconfig=$HOME/.cnpmrc"
alias wrk='docker run --rm williamyeh/wrk $args'
alias openresty="docker exec -ti `docker ps | grep openresty | awk '{print $1}'` openresty $args"
```

## WRK
- https://github.com/wg/wrk

- Installation
```
docker pull williamyeh/wrk
```

- Show usage
```docker
docker run --rm williamyeh/wrk
```

- Script example
```docker
docker run --rm  -v `pwd`:/data  \
      williamyeh/wrk  \
      -s script.lua  http://www.google.com/
```

## Slate

- download [github](https://github.com/lord/slate)
- copy directory {slate_github}/slate/source to ./slate/source
    - or set `SLATE_SOURCE_PATH`  in .env file
- check ./slate/source has index.html.md file and at least six directory
- run `docker-compose up -d slate`
- open http://localhost:4567 in brower
 
enjoy it

## Author
> Copy By [laradocker](https://github.com/laradock/laradock)
