FROM ubuntu:14.04
RUN sudo apt-get -y update && \
  # PHP FPM itself.
  sudo apt-get -y install php5-fpm && \
  # PHP CLI.
  sudo apt-get -y install php5-cli && \
  # PHP extensions.
  sudo apt-get -y install php5-curl && \
  sudo apt-get -y install php5-gd && \
  sudo apt-get -y install php5-imagick && \
  sudo apt-get -y install php5-memcached && \
  sudo apt-get -y install php5-mcrypt && \
  sudo apt-get -y install php5-mongo && \
  sudo apt-get -y install php5-mysql && \
  sudo apt-get -y install php5-oauth && \
  sudo apt-get -y install php5-readline && \
  sudo apt-get -y install php5-redis && \
  sudo apt-get -y install php5-xdebug && \
  sudo apt-get -y install php5-xhprof && \
  # MySQL client.
  sudo apt-get install -y mysql-client && \
  # Composer.
  sudo apt-get -y install curl && \
  sudo apt-get -y install git && \
  curl -sS https://getcomposer.org/installer | php5 && \
  mv composer.phar /usr/local/bin/composer && \
  composer global require drush/drush:dev-master && \
  ln -s $HOME/.composer/vendor/drush/drush/drush /usr/local/bin/drush

ADD php.ini /etc/php5/fpm/php.ini
ADD www.conf /etc/php5/fpm/pool.d/www.conf
CMD /usr/sbin/php5-fpm --nodaemonize
EXPOSE 9000
