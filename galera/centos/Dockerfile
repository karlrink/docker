
FROM centos:7
ENV container docker
MAINTAINER Karl Rink <karl@usaepay.com>

RUN groupadd -r mysql -g 3306 && useradd -r -g mysql -d /var/lib/mysql -s /sbin/nologin -c "MySQL Server" -u 3306 mysql
COPY etc/yum.repos.d/MariaDB.repo /etc/yum.repos.d/MariaDB.repo
RUN yum install -y mariadb-server mariadb-client

COPY etc/my.cnf /etc/my.cnf

RUN yum install -y net-tools

EXPOSE 3306 4444 4567 4567/udp 4568

ENTRYPOINT ["mysqld"]

