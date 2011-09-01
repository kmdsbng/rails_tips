# -*- encoding: utf-8 -*-
text-table
======

概要
------

配列を整形して出力します。


使用例
-----

    require 'rubygems'
    require 'text-table'

    array = [
      ['Student', 'Mid-Terms', 'Finals'],
      ['Sam', 94, 93],
      ['Jane', 92, 99],
      ['Average', 93, 96]
    ]

    puts array.to_table

    #    +---------+-----------+--------+
    #    | Student | Mid-Terms | Finals |
    #    | Sam     | 94        | 93     |
    #    | Jane    | 92        | 99     |
    #    | Average | 93        | 96     |
    #    +---------+-----------+--------+

サイト
-----
[github aptinio / text-table](https://github.com/aptinio/text-table)



更新日
-----
2011/09/02 01:55:38
