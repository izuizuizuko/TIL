WP初期設定
AWS→Lightsail→
SSHログイン→ターミナルにて【cat bitnami_application_password 】でパスワード。ユーザ名は【user】

WPにログイン後すること
1.すべてをアップロード
2.日本語設定。その他設定（時刻、カレンダー、UTF+9)
3.ディスカッションでコメントの設定（基本は表示させない。上３つのチェックを外す。→下は修正せずにOK）
4.userの設定変更。
　1新たにユーザーを作成する（必ず管理者設定を選ぶ）
  2一旦ログアウトし、作成したUSERでログイン。
  3SSHの時のUSERを削除
  
  Snow Monkey を設定。
  ZIPファイルを設定→有効化
  プラグイン設定→【Snow Monkey Blocks】を入れる
  
  投稿の初期設定
  ……のところ→オプション→公開前チェックをはずす

パーマリンク
URLの部分なる（題名がなることが多いが日本語は対応してないので文字化けになる。→タイトルを英語翻訳にして打ち換えが理想）
基本）
パーマリンの設定をカスタム構造にする。
/%year%/%monthnum%/%day%/%post_name%/
これだとnameが文字ばけするので、idに変更が無難
/%year%/%monthnum%/%day%/%post_id%/
固定ページには通用しない
固定ページを作成した場合は、パーマリンクを作成して設定。

カテゴリーとタグ
カテゴリー→おおきな分類
タグ→小さい分類

厳密な違いはない。
カテゴリーは選択必須。

抜粋は選択しないと本文の最初が出る（途中できれるので、設定してあげると◎）

<br><br>

![image](https://user-images.githubusercontent.com/59868344/81904829-c9514600-95fe-11ea-8854-d624f87c98ad.png)