# demo_mina

创建rails项目
rails new demo_mina

创建git仓库
echo "# demo_mina" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:MichaelRoshen/demo_mina.git
git push -u origin master

mina init
生成deploy.rb

mina setup
生成mina目录

--current
--last_version
--releases
--scm
--shared
--tmp

mac : enable ssh

Go to System Preferences -> Sharing, enable Remote Login.

本机免密码登录
cd ~
ssh-keygen -t rsa
cat id_rsa.pub >> authorized_keys
ssh username@localhost


set :domain, 'localhost'
set :repository, 'git@github.com:MichaelRoshen/demo_mina.git'
set :term_mode, :system
set :user, 'michael'    # Username in the server to SSH to.
set :port, '22'     # SSH port number.
set :deploy_to, '/deploy_path'

# Installing gem dependencies using Bundler
# command not found: bundle

task :environment do
  ＋invoke :'rvm:use[ruby-2.2.0@default]'
end


cp config/database.yml config/secrets.yml $deploy_to/shared/config

mina deploy


-----> Using RVM environment 'ruby-2.2.0@default'
Using /Users/michael/.rvm/gems/ruby-2.2.0
-----> Creating a temporary build path
-----> Fetching new git commits
-----> Using git branch 'master'
Cloning into '.'...
done.
-----> Using this git commit

michael (75a17a7):
> first commit

-----> Symlinking shared paths
-----> Installing gem dependencies using Bundler
/Users/michael/.rvm/gems/ruby-2.2.0@global/gems/bundler-1.9.9/bin/bundle
Using rake 11.2.2
Using i18n 0.7.0
Using json 1.8.3
Using minitest 5.9.0
Using thread_safe 0.3.5
Using tzinfo 1.2.2
Using activesupport 4.2.5
Using builder 3.2.2
Using erubis 2.7.0
Using mini_portile2 2.1.0
Using pkg-config 1.1.7
Using nokogiri 1.6.8
Using rails-deprecated_sanitizer 1.0.3
Using rails-dom-testing 1.0.7
Using loofah 2.0.3
Using rails-html-sanitizer 1.0.3
Using actionview 4.2.5
Using rack 1.6.4
Using rack-test 0.6.3
Using actionpack 4.2.5
Using globalid 0.3.6
Using activejob 4.2.5
Using mime-types-data 3.2016.0521
Using mime-types 3.1
Using mail 2.6.4
Using actionmailer 4.2.5
Using activemodel 4.2.5
Using arel 6.0.3
Using activerecord 4.2.5
Using coffee-script-source 1.10.0
Using execjs 2.7.0
Using coffee-script 2.4.1
Using thor 0.19.1
Using railties 4.2.5
Using coffee-rails 4.1.1
Using concurrent-ruby 1.0.2
Using multi_json 1.12.1
Using jbuilder 2.5.0
Using jquery-rails 4.1.1
Using open4 1.3.4
Using mina 0.3.8
Using bundler 1.9.9
Using sprockets 3.6.0
Using sprockets-rails 3.0.4
Using rails 4.2.5
Using rdoc 4.2.2
Using sass 3.4.22
Using tilt 2.0.5
Using sass-rails 5.0.4
Using sdoc 0.4.1
Using sqlite3 1.3.11
Using turbolinks 2.5.3
Using uglifier 3.0.0
Bundle complete! 13 Gemfile dependencies, 53 gems now installed.
Gems in the groups development and test were not installed.
Bundled gems are installed into ./vendor/bundle.
-----> DB migrations unchanged; skipping DB migration
-----> Skipping asset precompilation
-----> Cleaning up old releases (keeping 5)
-----> Deploy finished
-----> Building
-----> Moving build to releases/2
-----> Build finished
-----> Launching
-----> Updating the current symlink
-----> Launching
-----> Done. Deployed v2
Connection to localhost closed.
       Elapsed time: 11.09 seconds

