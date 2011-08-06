httparty
======

概要
------
http clientユーティリティです


例
-----
サンプル
    dir = File.expand_path(File.join(File.dirname(__FILE__), '..', 'lib'))
    require File.join(dir, 'httparty')
    require 'pp'

    class Rubyurl
      include HTTParty
      base_uri 'rubyurl.com'

      def self.shorten( website_url )
        post( '/api/links.json', :query => { :link => { :website_url => website_url } } )
      end
    end

    pp Rubyurl.shorten( 'http://istwitterdown.com/')


コマンドラインインタフェイス
    httparty "http://twitter.com/statuses/public_timeline.json"


サイト
-----
[github jnunemaker / httparty](https://github.com/jnunemaker/httparty)



更新日
-----
2011/08/07 02:15:12
