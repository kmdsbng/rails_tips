# -*- encoding: utf-8 -*-
fabrication
======

概要
------
one of fixture replacement.

インストール
-----

Gemfileに以下の行を追加

    gem 'fabrication'


test, rspec実行前に、以下のファイルを自動で読み込みます。

    spec/fabricators/**/*fabricator.rb
    test/fabricators/**/*fabricator.rb

例
-----

Basic

    Fabricator(:person)

既存のFabricatorを継承

    Fabricator(:adult, :from => :person)

ブロック付き

    Fabricator(:person) do
      name 'Greg Graffin'
      profession 'Professor/Musician'
    end


呼び出し側

    Fabricate(:person, :first_name => "Corbin", :last_name => "Dallas")

動作
----

belongs_to関連にオブジェクトを定義しても、DBには関連先のオブジェクトのidは
保存されてません。そういうテストには使えないみたいです。

サイト
-----
[github paulelliott / fabrication](https://github.com/paulelliott/fabrication)



更新日
-----
2011/08/21 22:14:52
