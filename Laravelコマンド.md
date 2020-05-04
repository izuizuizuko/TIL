## 作成時<br>
### コマンド接続<br>
```php artisan serve```
<br>
### Laravelアプリ作成<br>
```composer create-project --prefer-dist laravel/laravel タイトル```
<br>
### デバック表示<br>
Debugbarをインストール<br>
```composer require barryvdh/laravel-debugbar```
<br><br>
.env<br>
```
DEBUGBAR_ENABLED=null  # デフォルト。APP_DEBUGに応じて決まる
DEBUGBAR_ENABLED=true  # 必ず有効
DEBUGBAR_ENABLED=false # 必ず無効
```
<br>

#### 本番環境では表示させないようにする
```
php artisan config:clear
php artisan cache:clear
```
<br><br>
.env<br>
```DEBUGBAR_ENABLED=false  # 必ず無効```
<br>
## DB関係<br>

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
