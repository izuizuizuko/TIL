## :point_up:作成時<br>
### コマンド接続<br>
```php artisan serve```
<br>
### Laravelアプリ作成<br>
```composer create-project --prefer-dist laravel/laravel タイトル```
<br>
## :point_up:デバック表示<br>
Debugbarをインストール<br>
```composer require barryvdh/laravel-debugbar```
<br><br>
.env<br>
```
DEBUGBAR_ENABLED=null  # デフォルト。APP_DEBUGに応じて決まる
DEBUGBAR_ENABLED=true  # 必ず有効
DEBUGBAR_ENABLED=false # 必ず無効
```
<br><br>
#### 本番環境では表示させないようにする
<br><br>
```
php artisan config:clear
php artisan cache:clear
```
<br><br>
.env<br>
```DEBUGBAR_ENABLED=false  # 必ず無効```
<br>
## :point_up:DB関係<br>

### マイグレーションファイル作成<br>
```php artisan make:migration create_(テーブル名)_table```
<br>
### migrationの実行<br>
```php artisan migrate```<br>
### ロールバックの実行<br>
```php artisan migrate:rollback```<br>
## Tinker<br>
```php aritisan tinker```
<br>
## :point_up:エラー文の日本語化<br>
### 1. ```/resources/lang/```に```ja```を作成する<br>
### 2. ```/resources/lang/ja```に移動する。(ターミナル）<br>
### 3. 4つのファイルを実行する<br>
```
$ curl -OL https://raw.githubusercontent.com/rito-nishino/Laravel-Japanese-Language-fileset/master/auth.php
$ curl -OL https://raw.githubusercontent.com/rito-nishino/Laravel-Japanese-Language-fileset/master/pagination.php
$ curl -OL https://raw.githubusercontent.com/rito-nishino/Laravel-Japanese-Language-fileset/master/passwords.php
$ curl -OL https://raw.githubusercontent.com/rito-nishino/Laravel-Japanese-Language-fileset/master/validation.php
```

### 注)必ずconfig/app.phpを```locale' => 'ja```に変更する<br>
## :point_up:ルートの確認<br>
### ターミナルにて一覧
```php artisan route:list```
<br>
### テキストでエディタにて一覧
```php artisan route:list > route.txt```
<br>
