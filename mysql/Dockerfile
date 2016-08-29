FROM ubuntu:14.04
MAINTAINER Pantheon Systems

RUN apt-get -y update
RUN apt-get -y install vim curl wget mysql-server

RUN sed -i 's/127.0.0.1/0.0.0.0/g' /etc/mysql/my.cnf

ADD scripts /scripts
RUN chmod 755 /scripts/*

VOLUME ["/var/lib/mysql", "/var/log/mysql"]
EXPOSE 3306

CMD ["/bin/bash", "/scripts/start.sh"]
