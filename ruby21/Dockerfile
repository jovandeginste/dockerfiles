FROM ubuntu
MAINTAINER Jo Vandeginste "jo.vandeginste@gmail.com"

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv C3173AA6 \
 && echo "deb http://ppa.launchpad.net/brightbox/ruby-ng/ubuntu trusty main" >> /etc/apt/sources.list \
 && apt-key adv --keyserver keyserver.ubuntu.com --recv C300EE8C \
 && echo "deb http://ppa.launchpad.net/nginx/stable/ubuntu trusty main" >> /etc/apt/sources.list
RUN apt-get update \
 && apt-get -y install ruby2.1-dev git-core curl build-essential libmysqlclient-dev \
 && update-locale LANG=C.UTF-8 LC_MESSAGES=POSIX \
 && rm -rf /var/lib/apt/lists/* # 20140918
RUN gem install --no-document bundler 
