delorean
======

概要
------
Time.nowが返す値を変更します。現在時刻を利用する処理のテストに重宝します。

インストール
-----

    $ gem install delorean


使い方
----

    require 'delorean'
    
    # Date.today => Wed Feb 24
    Delorean.time_travel_to "1 month ago" # Date.today => Sun Jan 24
    Delorean.back_to_the_present          # Date.today => Wed Feb 24

引数にはDate、DateTime、Timeも指定できる。ブロックを引数に取ると、ブロックの中だけ
適用することができる。

    Delorean.time_travel_to(Date.today.beginning_of_month) {
      ...
    }


Testing
----

RSpecに導入するには、 spec_helper.rb に以下の設定を追加する

Spec::Runner.configure do |config|
  config.include Delorean
  ...


サイト
-----
[github bebanjo / delorean](https://github.com/bebanjo/delorean)


更新日
-----
2011/08/18 19:20:03
