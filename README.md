# RedmineOnWindow
레드마인 수동 설치 시 명령어
---


환경:
ruby 2.3 x64
mysql 8.0


-----------ruby만 깔려있을 때 해야 함. jruby 깔려있으면 안됨----------

```console
gem install bundler -v 1.8
bundle install --without development test postgresql sqlite rmagick
bundle exec rake generate_secret_token
gem install mysql2 -- '--with-mysql-lib = "C:\Program Files\MySQL\MySQL Server 8.0\lib"--with-mysql-include ="C:\Program Files\MySQL\MySQL Server 8.0\include"'
//gem install mysql2 -- '--with-mysql-dir="C:\Program Files\MySQL\MySQL Connector C 6.1"
// bundle show mysql2 없을때
// bundle install --without development test postgresql sqlite rmagick
// bundle update
gem install activerecord-mysql2-adapter
set RAILS_ENV=production
bundle exec rake db:migrate
set RAILS_ENV=production_setup
set REDMINE_LANG=ko
bundle exec rake redmine:load_default_data
bundle exec ruby bin/rails server webrick -e production

```
