chef 学习
====================
执行构建chef-solo
#!/usr/bin/env bash

# Pre-requisites
`sudo apt-get -y update`
`sudo apt-get --no-install-recommends -y install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev libgdbm-dev ncurses-dev automake libtool bison subversion pkg-config libffi-dev vim`

# Download and compile Ruby 2.0.0-p0
`cd /tmp`
`wget ftp://ftp.ruby-lang.org/pub/ruby/2.0/ruby-2.0.0-p0.tar.gz`
`tar -xvzf ruby-2.0.0-p0.tar.gz`
`cd ruby-2.0.0-p0`
`./configure --prefix=/usr/local`
`make`
`make install`

# Download and build Chef compatible with Ruby 2.0
`cd /tmp`
`curl -o chef.tar.gz -L https://api.github.com/repos/opscode/chef/tarball/`
`tar -xvzf chef.tar.gz`
`cd opscode-chef-634ad58`
`sudo gem build chef.gemspec`
`sudo gem install chef --no-ri --no-rdoc` 

# The rest
`sudo gem install ruby-shadow --no-ri --no-rdoc`

# 运行结束后检查安装结果
`sudo chef-solo -v`


[参考地址](https://gist.github.com/gogojimmy/5523985/raw/b9d777bc380ee791c2f4534e9261b4b99289ed9f/bootstrap-chef-solo.sh)

[参考地址](http://gogojimmy.net/2013/06/01/Chef-Solo-Basic-with-Vagrant/)