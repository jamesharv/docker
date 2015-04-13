FROM ubuntu:14.04
RUN sudo apt-get -y update && \
 sudo apt-get -y install mysql-server libapache2-mod-auth-mysql php5-mysql
CMD mysqld_safe
EXPOSE 3306
