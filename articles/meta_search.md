meta_search
======

概要
------
クエリパラメータから、DBへの検索条件を作成してくれるRailsプラグインです。


例
-----
* コントローラ

     def index
       @search = Article.search(params[:search])
       @articles = @search.all   # load all matching records
       # @articles = @search.relation # Retrieve the relation, to lazy-load in view
       # @articles = @search.paginate(:page => params[:page]) # Who doesn't love will_paginate?
     end


* ビュー

     <%= form_for @search, :url => articles_path, :html => {:method => :get} do |f| %>
       <%= f.label :title_contains %>
       <%= f.text_field :title_contains %><br />
       <%= f.label :comments_created_at_greater_than, 'With comments after' %>
       <%= f.datetime_select :comments_created_at_greater_than, :include_blank => true %><br />
       <!-- etc... -->
       <%= f.submit %>
     <% end %>


meta_searchにより、モデルにはあらかじめsearchメソッドが定義されます。
searchメソッドがクエリパラメータを解釈し、scopeを作ります。


* サポートしている検索条件
  * All data types
    * equals (alias: eq) - Just as it sounds.
    * does_not_equal (aliases: ne, noteq) - The opposite of equals, oddly enough.
    * in - Takes an array, matches on equality with any of the items in the array.
    * not_in (aliases: ni, notin) - Like above, but negated.
    * is_null - The column has an SQL NULL value.
    * is_not_null - The column contains anything but NULL.

  * Strings
    * contains (aliases: like, matches) - Substring match.
    * does_not_contain (aliases: nlike, nmatches) - Negative substring match.
    * starts_with (alias: sw) - Match strings beginning with the entered term.
    * does_not_start_with (alias: dnsw) - The opposite of above.
    * ends_with (alias: ew) - Match strings ending with the entered term.
    * does_not_end_with (alias: dnew) - Negative of above.

  * Numbers, dates, and times
    * greater_than (alias: gt) - Greater than.
    * greater_than_or_equal_to (aliases: gte, gteq) - Greater than or equal to.
    * less_than (alias: lt) - Less than.
    * less_than_or_equal_to (aliases: lte, lteq) - Less than or equal to.

  * Booleans
    * is_true - Is true. Useful for a checkbox like "only show admin users".
    * is_false - The complement of is_true.

  * Non-boolean data types
    * is_present - As with is_true, useful with a checkbox. Not NULL or the empty string.
    * is_blank - Returns records with a value of NULL or the empty string in the column.


* 他のscopeと組み合わせられる

     @search = current_user.projects.search(params[:search])

* any, all 検索が可能
    <%= f.multiparameter_field :title_contains_any,
          *5.times.inject([]) {|a, b| a << {:field_type => :text_field}} +
          [:size => 10] %>


* アソシエーションをたどって検索できる

  * モデル

    class Company < ActiveRecord::Base
      has_many :developers
    end
    
    class Developer < ActiveRecord::Base
      belongs_to :company
      has_many :notes
    end


  * ビュー

    <%= f.text_field :developers_notes_developer_company_name_contains %>


* ソート順の指定

  * ビュー

    <%= f.sort_link :title %>


サイト
-----
[github ernie / meta_search](https://github.com/ernie/meta_search)



更新日
-----
2011/06/30 20:12:04
