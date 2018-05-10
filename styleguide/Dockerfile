# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru python3 image
# to run it:
# 1 - tsuru-admin platform-add python3 -d https://raw.github.com/tsuru/basebuilder/master/python3/Dockerfile

from	ubuntu:14.04
run		locale-gen en_US.UTF-8
env		LANG en_US.UTF-8
env		LANGUAGE en_US:en
env		LC_ALL en_US.UTF-8
run		apt-get update
run		apt-get install software-properties-common curl wget -y
run		wget http://github.com/leandrosouza/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run		mkdir /var/lib/tsuru
run		tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run		cp /var/lib/tsuru/styleguide/deploy /var/lib/tsuru
run		cp /var/lib/tsuru/base/start /var/lib/tsuru
run		/var/lib/tsuru/base/install
run 	apt-get install -y make git
run     curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
run     apt-get update
run     apt-get install nodejs ruby-full -y --force-yes
run		npm install -g grunt-cli
run		gem install bundle
run		ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
