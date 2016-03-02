This are the sources for chaosnetz.org

# About

It uses pelican as static site generator and compass for compiling sass, therefore it requires a python and a ruby environment. 

As the compiled css is part of the theme inside this repository you can skip the ruby and bundler part if you don't change anything template related and just want to use pelican to generate content.

# install
for working with content install
* python
* virtualenv

for working on css also install
* ruby
* bundler

# init environment

    git submodule init
    git submodule update

## python
    virtualenv -p python2 .
    . bin/activate
    pip install -r requirements.text

## ruby environment
maybe skip this (see above)
    bundle install

# building
## full development environment
    . bin/activate #if not already in virtualenv
    bundler exec foreman start
this has to happen inside the virtualenv environment so foreman is able to run pelican. pelican will serve files under localhost:8000, will watch files for changes and autorefreshes the browser if they do

## just pelican
    . bin/activate #if not already in virtualenv
    make html #build html
    make serve PORT=8000 #serve output directory via http://localhost:8000

## live
via script, automation server, ...
    compass compile
    bin/pelican content -o output -s pelicanconf.py
these commands will run only once and will build the whole page into the output folder. entering the virtualenv is not required

# etcetera

ocra font from:
https://github.com/opensourcedesign/
