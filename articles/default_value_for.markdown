default_value_for
======

概要
------
モデルのデフォルト値を定義できるようにするプラグインです。  
値を直接渡す方法と、ブロックで渡す方法があります。


例
-----
    class User < ActiveRecord::Base
      default_value_for :name, "(no name)"
      default_value_for :last_seen do
        Time.now
      end
    end
    
    u = User.new
    u.name       # => "(no name)"
    u.last_seen  # => Mon Sep 22 17:28:38 +0200 2008


[The Ruby Toolbox: ActiveRecord Default Values](http://ruby-toolbox.com/categories/activerecord_default_values.html)



更新日
-----
2011/05/13 20:28:58
