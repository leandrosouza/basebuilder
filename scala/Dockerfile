# Copyright 2015 basebuilder authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

# this file describes how to build tsuru java image
# to run it:
# 1- run: $ tsuru-admin platform-add java -d https://raw.github.com/tsuru/basebuilder/master/java/Dockerfile

from	ubuntu:14.04
env     locale-gen en_US.UTF-8
env     LANG en_US.UTF-8
env     LANGUAGE en_US:en
env     LC_ALL en_US.UTF-8
run	apt-get update
run	apt-get install wget software-properties-common -y --force-yes
run	wget http://github.com/leandrosouza/basebuilder/tarball/master -O basebuilder.tar.gz --no-check-certificate
run	mkdir /var/lib/tsuru
run	tar -xvf basebuilder.tar.gz -C /var/lib/tsuru --strip 1
run	cp /var/lib/tsuru/scala/deploy /var/lib/tsuru
run	cp /var/lib/tsuru/base/start /var/lib/tsuru
run	/var/lib/tsuru/scala/install
run      ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime