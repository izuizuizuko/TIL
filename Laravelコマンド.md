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
#### 本番環境では表示させないようにする
```
php artisan config:clear
php artisan cache:clear
```
.env<br>
```DEBUGBAR_ENABLED=false  # 必ず無効```
<br>

## :point_up:MVC<br>
### コントローラ作成<br>
```
例）entryの場合
php artisan make:controller EntriesController   
```
※　コントローラ名は複数形！<br>
コントローラーに必ず記載<br>
```use Illuminate\Support\Facades\View;```（ビューの表示）<br>
```use App\モデル名;```（モデルの使用）<br>

### モデルの作成<br>
```
例）entryの場合
php artisan make:Model Entry
```

### ビューのテンプレート化<br>
①共通部分のファイルを作成(viewにlayoutsフォルダーを作成しその中にappファイルを作成）<br>
各所で読み込みたい場所に【@yield】を記入。
```
例
            <!DOCTYPE html>
            <html lang="ja">
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <title>@yield("title")</title>
            </head>
            <body>
                @yield("content")
            </body>
            </html>
```
<br>

②それぞれのビューで共通テンプレートを読み込む<br>
```
例）index.bldae.phpの場合<br>

@extends("layouts.app")

@section("title", "blog")
@section("content", "hello")
```
<br>
<br>
・@extendsで共通ファイルの読み込み
<br>
<br>・@sextionで@yieldの部分の置き換え<br>

```
例）view.bldae.php(詳細画面）の場合<br>


@extends("layouts.app")

@section("title", $entry->title)
@section("content")
<p>{{ $entry->title }}</p>
<article>
{[ $entry->content }}
</article>
@endsection
```
<br>
@sectionにそのレイアウトのHTMLを記載する場合（例：リストとか）は、@endsectionをつけること。
 <br>
<br>

## :point_up:DB関係<br>
### マイグレーションファイル作成<br>
```php artisan make:migration create_(テーブル名)_table```
<br>
### migrationの実行<br>
```php artisan migrate```<br>
### ロールバックの実行<br>
```php artisan migrate:rollback```<br>
### seedデータの登録<br>
```php artisan make:seeder <テーブル名>TableSeeder```<br>
テーブル作成後seederに記載<br>
```
（例）entryテーブルの場合
DB::table("entries")->insert([
            "title"=>"entry1",
            "content"=>"hello",
            "created_at"=>date("Y-m-d H:i:s"),
            "update_at"=>date("Y-m-d H:i:s")
        ]);
 ```
 ### seedデータの読み込み<br>
 ・seeds=>Databaseseedr.phpに記載<br>
 
 ```
  public function run()
    {
        // $this->call(UserSeeder::class);
        $this->call(EntriesTableSeeder::class);
    }
 ```
 <br>
 
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
