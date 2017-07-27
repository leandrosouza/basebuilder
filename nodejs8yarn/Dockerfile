from   ubuntu:14.04
run     locale-gen en_US.UTF-8
env     LANG en_US.UTF-8
env     LANGUAGE en_US:en
env     LC_ALL en_US.UTF-8
run    apt-get update
run    DEBIAN_FRONTEND=noninteractive apt-get install wget curl apt-transport-https -y --force-yes
run    wget http://github.com/zanaca/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run    mkdir /var/lib/tsuru
run    tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run    cp /var/lib/tsuru/nodejs/deploy /var/lib/tsuru
run    cp /var/lib/tsuru/base/start /var/lib/tsuru
run    apt-get install nodejs npm -y --force-yes
run    /var/lib/tsuru/base/install
run    npm install -g gulp bower node-gyp yarn n
run    n 8.1.3
run    ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime