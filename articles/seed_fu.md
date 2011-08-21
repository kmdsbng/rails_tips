# -*- encoding: utf-8 -*-
seed-fu
======

概要
------
マスタデータ管理するための rails プラグインです。

インストール
-----

Gemfileに以下の行を追加

    gem 'seed-fu'

使用例
-----

db/fixtures/xxx.rb にマスタデータの内容を定義します。



    # db/fixtures/user.rb
    User.seed do |s|
      s.id    = 1
      s.login = "jon"
      s.email = "jon@example.com"
      s.name  = "Jon"
    end

    User.seed do |s|
      s.id    = 2
      s.login = "emily"
      s.email = "emily@example.com"
      s.name  = "Emily"
    end


以下のコマンドでマスタデータをDBに保存します


    $ rake db:seed_fu


サイト
-----
[github mbleigh / seed-fu](https://github.com/mbleigh/seed-fu)



更新日
-----
2011/08/21 22:37:38
