== README
TO DO

* 0：バージョン確認

choiwaru2012@ubuntu:~$ ruby --version
ruby 2.0.0p576 (2014-09-19 revision 47628) [i686-linux]
choiwaru2012@ubuntu:~$ rails --version
Rails 4.0.5

* 1：作成する
デフォルトであるtestsディレクトりを作成しない
(テストをしないからではなく、RSpecというテストフレームワークを使用するため）

choiwaru2012@ubuntu:~$ rails _4.0.5_ new sample_app_last2014 --skip-test-unit
      create  Gemfile
      create  app/assets/javascripts/application.js

         run  bundle install
Fetching gem metadata from https://rubygems.org/..........
Resolving dependencies...
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.

* * 1-1：Gemfileを修正
* * 1-2：bundle install

choiwaru2012@ubuntu:~/sample_app_last2014$ bundle install --without production
//5分くらい時間がかかる
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Using rake 10.4.2

Post-install message from rdoc:
Depending on your version of ruby, you may need to install ruby rdoc/ri data:

<= 1.8.6 : unsupported
 = 1.8.7 : gem install rdoc-data; rdoc-data --install
 = 1.9.1 : gem install rdoc-data; rdoc-data --install
>= 1.9.2 : nothing to do! Yay!

* 2：config/initializers/secret_token.rbを修正する。
（サービスにアクセスした時に、誰がアクセスしているのか等確認する時に必要）

* 3：rspecできるようにする。

rails geenrate rspec:install
・rspecが実行できるための環境
・spechelperというアプリケーションが自動的に生成された
・rspecの設定が記載されている「.rspec」??が生成された。

※JavaScriptランタイムがインストールされていないというエラーが表示される
choiwaru2012@ubuntu:~/sample_app_last2014$ rails generate rspec:install
/home/choiwaru2012/.rbenv/versions/2.0.0-p576/lib/ruby/gems/2.0.0/gems/execjs-2.2.2/lib/execjs/runtimes.rb:51:in `autodetect': Could not find a JavaScript runtime. See https://github.com/sstephenson/execjs for a list of available runtimes. (ExecJS::RuntimeUnavailable)

⇒下記の方法でnodejsをインストール

choiwaru2012@ubuntu:~/sample_app_last2014$ sudo apt-get install nodejs
