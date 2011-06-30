will_paginate
======

概要
------
Railsアプリケーションで、簡単にページング機能を実現する
プラグインです。


例
-----
コントローラ
    @posts = Post.paginate :page => params[:page], :per_page => 50
    

ビュー
    <ol>
      <% for post in @posts -%>
        <li>Render `post` in some nice way.</li>
      <% end -%>
    </ol>

    <p>Now let's render us some pagination!</p>
    <%= will_paginate @posts %>


サイト
-----
[The Ruby Toolbox: Rails Pagination](http://www.ruby-toolbox.com/categories/rails_pagination.html#mislav_will_paginate)
[github mislav / will_paginate](https://github.com/mislav/will_paginate)



更新日
-----
2011/06/02 12:43:01
