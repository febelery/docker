FROM mysql:5.7

MAINTAINER ross <ross@huaxi100.com>

ADD startup /etc/mysql/startup

ARG MYSQL_USER=ross
ARG MYSQL_PASSWORD=ross
ARG MYSQL_ROOT_PASSWORD=root

ENV MYSQL_DATABASE=$MYSQL_DATABASE
ENV MYSQL_USER=$MYSQL_USER
ENV MYSQL_PASSWORD=$MYSQL_PASSWORD
ENV MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD

RUN sed -i 's/MYSQL_USER/'$MYSQL_USER'/g' /etc/mysql/startup && \
    sed -i 's/MYSQL_PASSWORD/'$MYSQL_PASSWORD'/g' /etc/mysql/startup

ADD my.cnf /etc/mysql/conf.d/my.cnf

EXPOSE 3306

CMD ["mysqld", "--init-file=/etc/mysql/startup"]
