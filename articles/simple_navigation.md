# -*- encoding: utf-8 -*-
simple-navigation
======

概要
------

階層メニューを描画するヘルパを導入する、railsプラグインです。

インストール
-----

    gem "simple-navigation"

設定
-----


メニュー定義を config/navigation.rb に書く。

    SimpleNavigation::Configuration.run do |navigation|  
      navigation.items do |primary|
        primary.item :books, 'Books', books_path
        primary.item :music, 'Music', musics_path
        primary.item :dvds, 'Dvds', dvds_path
      end
    end

使用例
-----

ヘルパメソッド

    render_navigation 


サイト
-----
[github andi / simple-navigation](https://github.com/andi/simple-navigation)
[デモ](http://simple-navigation-demo.andischacke.com/dvds/comedy)



更新日
-----
2011/08/21 23:36:21
