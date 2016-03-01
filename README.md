This are the sources for chaosnetz.org

It uses pelican as static site generator and compass for compiling sass, therefore it requires a python and a ruby environment.

install:
* python
* virtualenv
* ruby
* bundler

init the python environment:
  virtualenv -p python2 .
  . bin/activate
  pip install -r requirements.text

init the ruby environment
  bundle install

in developmet environment run:
  bundler exec foreman start
this has to happen inside the virtualenv environment so foreman is able to run pelican. pelican will serve files under localhost:8000, will watch files for changes and autorefreshes the browser if they do


in live enviroment run
  compass compile
  bin/pelican content -o output -s pelicanconf.py
these commands will run only once and will build the whole page into the output folder. the virtualenv is not required

ocra font from:
https://github.com/opensourcedesign/
