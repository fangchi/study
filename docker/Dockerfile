# This is a comment
FROM fangchi:v1
ENV TERM linux
MAINTAINER fangchi  <fangchi1986@aliyun.com>
# open port 80
EXPOSE 80
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
