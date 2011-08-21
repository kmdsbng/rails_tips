# -*- encoding: utf-8 -*-
recaptcha
======

概要
------
reCAPTCHAという captcha を表示するAPIを利用するためのヘルパメソッドを追加します。
reCAPTCHAは有料のサービスです。

[reCAPTCHA](http://www.google.com/recaptcha)

インストール
-----

Gemfileに以下の行を追加

    gem "recaptcha", :require => "recaptcha/rails"

使用例
-----

view

    respond_to do |format|
      if verify_recaptcha(:model => @post, :message => "Oh! It's error with reCAPTCHA!") && @post.save
        # ...
      else
        # ...
      end
    end


サイト
-----
[github ambethia / recaptcha](https://github.com/ambethia/recaptcha)



更新日
-----
2011/08/21 22:56:05
