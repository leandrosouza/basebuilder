# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru play image
# to run it:
# 1 - tsuru-admin platform-add play -d https://raw.github.com/tsuru/basebuilder/master/busca/Dockerfile

from ubuntu:14.04
run locale-gen en_US.UTF-8
env LANG en_US.UTF-8
env LANGUAGE en_US:en
env LC_ALL en_US.UTF-8
run apt-get update
run apt-get install wget -y --force-yes
run wget http://github.com/leandrosouza/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run mkdir /var/lib/tsuru
run tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run cp /var/lib/tsuru/play/deploy /var/lib/tsuru
run cp /var/lib/tsuru/base/start /var/lib/tsuru
run chmod -R 777 /var/lib/tsuru 
run curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add -
run echo 'deb https://deb.nodesource.com/node_0.12 trusty main' > /etc/apt/sources.list.d/nodesource.list
run apt-get update
run apt-get install nodejs -y --force-yes
run /var/lib/tsuru/base/install
run npm install -g n
run n 4.2.1
run /var/lib/tsuru/busca/install
run ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime