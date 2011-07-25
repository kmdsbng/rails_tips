rails3_acts_as_paranoid
======

概要
------
論理削除を実現するRails3用プラグインです。


例
-----
モデル

    class Paranoiac < ActiveRecord::Base
      acts_as_paranoid
    end


抽出条件

    Paranoiac.only_deleted # retrieves the deleted records
    Paranoiac.with_deleted # retrieves all records, deleted or not


復活
    Paranoiac.only_deleted.where("name = ?", "not dead yet").first.recover




サイト
-----
[github goncalossilva / rails3_acts_as_paranoid](https://github.com/goncalossilva/rails3_acts_as_paranoid)



更新日
-----
2011/07/25 13:59:10
