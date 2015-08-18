# This is a comment
FROM fangchi:v5
ENV TERM linux
MAINTAINER fangchi  <fangchi1986@aliyun.com>
# open port 80
# EXPOSE 22 80
# update source.list
ADD sources.list /etc/apt/sources.list
RUN apt-get update
RUN apt-get -qqy install apt-utils
RUN apt-get -qqy install dialog
RUN apt-get -y upgrade
RUN apt-get -qqy install ruby ruby-dev
# RUN apt-get -qqy install apt-utils
# RUN apt-get -qqy install dialog
RUN apt-get -qqy install rubygems
RUN apt-get -qqy install openssh-server 
RUN apt-get -qqy install apache2 
RUN apt-get -qqy install supervisor
# RUN apt-get -qqy install apt-utils
RUN apt-get -qqy install inetutils-ping

# RUN gem install json
# RUN gem install tree
# ADD fangchiApp /var/www


RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
