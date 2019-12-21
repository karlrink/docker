
# Galera Cluster Dockerfile
FROM ubuntu:14.04
MAINTAINER Karl Rink <karl@rink.us>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y  software-properties-common
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv BC19DDBA
RUN add-apt-repository 'deb http://releases.galeracluster.com/galera-3/ubuntu trusty main'
RUN add-apt-repository 'deb http://releases.galeracluster.com/mysql-wsrep-5.6/ubuntu trusty main'


RUN apt-get update
RUN apt-get install -y galera-3 galera-arbitrator-3 mysql-wsrep-5.6 rsync

COPY my.cnf /etc/mysql/my.cnf
ENTRYPOINT ["mysqld"]


