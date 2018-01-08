---
layout: post
title:  "Install Ruby on Ubuntu"
date:   2018-01-08 16:00:27 +0100
categories: ubuntu
---
Default install of Ruby on Ubuntu is not good.
1. Remove actual installation
`sudo apt-get remove ruby`
`sudo apt autoremove`

2. Update & install necessary packages
`sudo apt-get update`
`sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev`

3. Download Ruby environnement: rbenv
`git clone https://github.com/rbenv/rbenv.git ~/.rbenv`
`echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc`
`echo 'eval "$(rbenv init -)"' >> ~/.bashrc`
`exec $SHELL`

4. Download Ruby
`git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build`
`echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc`
`exec $SHELL`

5. Install Ruby
`rbenv install 2.3.1`
`rbenv global 2.3.1`
`ruby -v`