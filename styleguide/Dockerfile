# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru static image
# to run it:
# 1 - tsuru-admin platform-add static -d https://raw.github.com/tsuru/basebuilder/master/static/Dockerfile

from	ubuntu:14.04
run     locale-gen en_US.UTF-8
env     LANG en_US.UTF-8
env     LANGUAGE en_US:en
env     LC_ALL en_US.UTF-8
run     apt-get update
run     apt-get install wget curl apt-transport-https -y --force-yes
run     wget http://github.com/leandrosouza/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run     mkdir /var/lib/tsuru
run     tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run     cp /var/lib/tsuru/static/deploy /var/lib/tsuru
run     cp /var/lib/tsuru/base/start /var/lib/tsuru
run    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
run     apt-get update
run     apt-get install nodejs ruby-full -y --force-yes
run    npm install -g gulp bower node-gyp grunt-cli
<<<<<<< HEAD
run	   gem install bundle
run     /var/lib/tsuru/static/install
=======
run    ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
run    chown -R ubuntu:ubuntu /home/ubuntu/.npm/
>>>>>>> d2e88b76904e663a828946c135f221ae175a706a