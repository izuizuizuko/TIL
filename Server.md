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
