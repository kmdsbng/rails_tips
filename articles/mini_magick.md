# -*- encoding: utf-8 -*-
mini_magick
======

概要
------

メモリ使用量を抑えた、ImageMagickライブラリです。


使用例
-----

    image = MiniMagick::Image.open("input.jpg")
    image.resize "100x100"
    image.write  "output.jpg"


サイト
-----
[github probablycorey / mini_magick](https://github.com/probablycorey/mini_magick)



更新日
-----
2011/08/25 23:35:29
