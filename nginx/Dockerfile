FROM ubuntu:14.04
RUN echo "deb http://ppa.launchpad.net/nginx/stable/ubuntu $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/nginx-stable.list && \
 sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C300EE8C && \
 sudo apt-get -y update && \
 sudo apt-get -y install nginx
ADD nginx.conf /etc/nginx/nginx.conf
ADD default /etc/nginx/sites-available/default
CMD sudo service nginx start
EXPOSE 80
