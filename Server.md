### 初期設定時<br>
#### :globe_with_meridians:SSL設定・httpとhttpsの違い<br>
 セキュリティーレベルの違い。検索エンジンの評価も上がる。```基本はhttps```
 <br>
 ドメイン取得後WPの設定も必ず変更する。
 ```
 1.サーバーで設定。(ドメイン・SSL設定)※時間がかかる場合あり
 2.WPサイト:globe_with_meridians:で設定。
    ・設定→一般→WPアドレスとサイトアドレスの2か所を変更(httpsに)
 3.サーバで設定。.htaccess設定を変更<br>
    .htaccessファイルの一番上に以下のコードを貼り付け
    
    <IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTPS} off
    RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R,L]
    </IfModule>
  ```
#### :globe_with_meridians:パーマリンク設定<br>
パーマリンク →URLの部分<br>
題名がなることが多いが日本語は対応してないので文字化けになる。→タイトルを英語翻訳にして打ち換えが理想<br><br>
　設定方法<br>
  1.ダッシュボード→設定→パーマリンク設定<br>
```
 基本） パーマリンの設定をカスタム構造にする。
 /%year%/%monthnum%/%day%/%post_name%/
 
 これだとnameが文字ばけするので、idに変更が無難
 
 /%year%/%monthnum%/%day%/%post_id%/
 
 #### ※固定ページには通用しない 固定ページを作成した場合は、パーマリンクを作成して設定。
 ```
