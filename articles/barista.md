barista
======

概要
------
rails, sinatraで CoffeeScript を使うためのプラグインです。

(補足) rails 3.1からは、baristaを使わなくても CoffeeScriptを導入できるようになってます

rails3へのインストール
-----

Gemfileに記入
    gem 'barista'
    gem 'json' # ruby 1.8.7以下の場合必要
    gem 'therubyracer' # therubyracerは一例。https://github.com/sstephenson/execjs ここにあるいずれかのJavaScriptコンパイル用のライブラリを指定する

インストールコマンド
    $ bundle install
    $ rails g barista:install # 設定ファイル config/initializers/barista_config.rb が生成される



動作
-----
app/coffeescripts 以下に .coffee 拡張子のファイルを置くと、.jsファイルが
アクセスされたタイミングで、自動で .js ファイルをコンパイルします。

例) ブラウザから、/javascripts/some.js にアクセスされた時、
app/coffeescripts/some.coffee -> public/javascripts/some.js
にコンパイルする

サンプル
-----
app/coffeescripts/hello.coffee
    alert 'Hello, Coffee'


確認
-----
    $  curl http://localhost:3001/javascripts/hello.js                                                                                                               [~]
    /* DO NOT MODIFY. This file was compiled Sun, 07 Aug 2011 16:48:20 GMT from
     * /home/kameda/work/rails_tool_test/barista_test/app/coffeescripts/hello.coffee
     */
    
    (function() {
      alert('Hello, Coffee');
    }).call(this);


サイト
-----
[github Sutto / barista](https://github.com/Sutto/barista)


更新日
-----
2011/08/08 01:49:32
