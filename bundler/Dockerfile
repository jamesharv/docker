FROM ubuntu:14.04


RUN apt-get update -y && \
    apt-get install -y wget git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev && \
    wget -c http://ftp.ruby-lang.org/pub/ruby/2.2/ruby-2.2.2.tar.gz && \
    tar -xzf ruby-2.2.2.tar.gz && \
    cd ruby-2.2.2 && \
    ./configure && \
    make && \
    make install && \
    export PATH="/usr/local/ruby/bin:$PATH" && \
    echo "gem: --no-ri --no-rdoc" > ~/.gemrc && \
    gem update --system && \
    gem install bundler

ADD entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENV PATH /usr/local/ruby/bin:$PATH

ENTRYPOINT ["/entrypoint.sh"]
