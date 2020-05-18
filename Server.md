### 初期設定時<br>
#### :globe_with_meridians:SSL設定・httpとhttpsの違い<br>
 セキュリティーレベルの違い。検索エンジンの評価も上がる。```基本はhttps```
 <br>
 ドメイン取得後WPの設定も必ず変更する。
 ```
 1.サーバーで設定。(ドメイン・SSL設定)※時間がかかる場合あり
 2.WPサイトで設定。
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

#### :globe_with_meridians:プラグイン設定<br>

| プラグイン名 | 機能 |
----|---- 
| All In One SEO Pack | 検索エンジン最適化 |
| Black Studio TinyMCE Widget | ウィジェットが便利に使用できる |
| Invisible reCaptcha for WordPress | スパム対策 |
| Ninja Forms | お問い合わせフォーム作成 |
| PS Auto Sitemap | サイトマップ作成 |
| TinyMCE Advanced | 記事を書く画面が使いやすい |
| WebSub/PubSubHubbub | 記事の更新情報が世界に届きやすい |
| WP User Avatar | プロフィール写真が設定できる |
|WP Multibyte Patch | マルチバイト文字の不具合修正 |


```
All In One SEO Pack
Black Studio TinyMCE Widget
Invisible reCaptcha for WordPress
Ninja Forms
PS Auto Sitemap
TinyMCE Advanced
WebSub/PubSubHubbub
WP User Avatar
WP Multibyte Patch
```
#### :globe_with_meridians:プラグインの詳細設定
##### All In One SEO Pack<br>
①ダッシュボード→All In One SEO Pack→機能管理<br>
 ・XMLサイトマップ<br>
 ・ソーシャルメディア<br>
有効化する。<br>
##### Invisible reCaptcha for WordPress<br>
①ダッシュボード→設定→Invisible reCaptcha<br>
②```https://www.google.com/recaptcha/intro/v3.html```アクセス<br>
③右上の管理コンソールをクリック<br>
④各項目を記入。<br>
 ・ラベル→（ドメイン）<br>
 ・reCAPTCHA タイプ→reCAPTCHA v3<br>
 ・ドメイン<br>
⑤送信後のサイトキーとシークレットキーをWPのサイトに張り付け<br>
⑥言語を日本語設定を選び保存<br>
⑦Invisible reCaptchaの設定の１つしたのWordPressを選択→すべての項目にチェック<br><br>

#### Ninja Forms<br>
お問い合わせフォームの作成<br>

#### PS Auto Sitemap
<br>
①固定ページ→新規追加をクリック→タイトルをサイトマップに<br>
②文章→パーマリンク→URLスラッグを『site』に変更→下書きに保存<br>
③ブラウザのURL欄から、post○○の部分の数字だけをコピーする<br>
④設定→「PS Auto Sitemap」をクリック→サイトマップを表示する記事という入力欄にコピーした数字を記入する<br>
⑤その後「変更を保存」をクリック。
⑥固定ページ→下書きしたサイトマップ→文章→『カスタムHTML』を選択
⑦```<!-- SITEMAP CONTENT REPLACE POINT -->```をはりつける<br>
⑧公開する<br>

#### TinyMCE Advanced<br>
①設定→TinyMCE Advanced→すべてのアイコンを使用する側にいどうさせる<br>

#### :globe_with_meridians:外観<br>
#### プラグインの詳細設定
カスタムエディターが自由自在で便利<br>
#### メニューの詳細設定<br>
カスタムリンク→他のサイトへのリンク
#### プロフィールの詳細設定<br>
アイコンはアバターから設定する<br>
