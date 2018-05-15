FROM ruby:2.2.2

RUN apt-get update && apt-get install build-essential libmysqlclient-dev mysql-client sudo openssl libssl-dev -y
RUN	wget http://github.com/leandrosouza/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
RUN	mkdir /var/lib/tsuru
RUN	tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
RUN	cp /var/lib/tsuru/ruby-base/deploy /var/lib/tsuru
RUN	cp /var/lib/tsuru/base/start /var/lib/tsuru
RUN	/var/lib/tsuru/base/install