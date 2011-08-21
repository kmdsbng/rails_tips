# -*- encoding: utf-8 -*-
rr
======

概要
------

モックオブジェクトを定義するためのライブラリです。

インストール
-----

Gemfileに以下の行を追加

    gem 'rr'

設定
-----

rspecを使用している場合、以下の記述をspec_helper.rbに追加。

    Spec::Runner.configure do |config|
      config.mock_with :rr
    end

使用例
-----

    # User.find('42') を呼び出すと、janeが返される。
    # 異なる引数が与えられたり呼び出されなければ、アサーション
    mock(User).find('42') {jane}


Double Injections

    # my_object.hello が呼ばれないとアサーション
    my_object = MyClass.new
    mock(my_object).hello


stub (単にある値を返すメソッドを定義。呼ばれなくてもアサーションは起こさない)

    # 引数によってアクションを変える
    jane = User.new
    bob = User.new
    stub(User).find('42') {jane}
    stub(User).find('99') {bob}
    stub(User).find do |id|
      raise "Unexpected id #{id.inspect} passed to me"
    end


dont_allow

    dont_allow(User).find('42')
    User.find('42') # raises a TimesCalledError


他にもたくさん機能があります。


サイト
-----
[github btakita / rr](https://github.com/btakita/rr)



更新日
-----
2011/08/21 23:25:14
