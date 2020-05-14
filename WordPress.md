## :point_up:自作テーマ作成
<br>
MAMP→htdocs→WordPressフォルダー→wp-content→themes→フォルダー作成<br>
1.index.php<br>
2.style.css
<br><br>
bootstrapのテーマをダウンロード後、【index.html】を作成したフォルダーに入れる。（index.phpを削除。index.htmlをindex.phpに変更

## :point_up:タグ
<br>
<?php the_title( $before, $after, $echo ); ?>
<?php wp_head(); ?>
 <?php wp\footer(); ?>
  <?php the_time(); ?>'Y年n月j日'('Y-m-d')('Y/m/d')
   <?php the_content(); ?>
    <?php the_post(); ?>
     <?php the_author(); ?>
     <?php echo get_template_directory_uri(); ?>

     ![image](https://user-images.githubusercontent.com/59868344/81788740-f7bb1c80-953d-11ea-9a8f-fdea38577527.png)<br>
<meta name="description" content="">
  <meta name="author" content="">

  <title>Clean Blog - Start Bootstrap Theme</title>
削除

cssの変更
 <link href="<?php echo get_template_directory_uri(); ?>/vendor/bootstrap/css/bootstrap.min.css" rel="stylesheet">

<?php bloginfo("name"); ?>タイトル変更（ボディのタイトル）
 <a class="navbar-brand" href="<?php echo home_url();?>"><?php bloginfo("name"); ?></a>（そのまえのとこ。TOPぺーじのURL変更）
 ```
       <?php while (have_posts()): the_post(); ?>
          <div class="post-preview">
            <a href="post.html">
              <h2 class="post-title">
              <?php the_title(); ?>
              </h2>
              <h3 class="post-subtitle">
              <?php the_content(); ?>
              </h3>
            </a>
            <p class="post-meta">Posted by
              <?php the_author(); ?></a>
              on <?php the_time('Y-m-d'); ?></p>
          </div>
          <hr>
        <?php endwhile; ?>
        ```
        while文で表示エンドで閉じ
          <?php while (have_posts()): the_post(); ?>
          <?php the_excerpt(); ?>
          <?php the_content(); ?>
          
          
        <!-- Pager -->
        <div class="clearfix">
         <?php previous_posts_link(); ?>
          <?php next_posts_link(); ?>

          <?php next_posts_link(); ?>
           <?php previous_posts_link(); ?>
           <?php echo paginate_links(); ?>
           
           リンク先詳細
            <a href="<?php the_permalink(); ?>">
            
           
           タイトルをひょうじさせる。
           
           
           
init→初期化
            functions.php
           <?php
function init_func() {
  add_theme_support('title-tag');
 add_theme_support('post-thumbnails');
}
add_action('init', 'init_func');

サムネ　single。PHP
  <?php
  $id = get_post_thumbnail_id();
  $img = wp_get_attachment_image_src($id);
  ?>
  <header class="masthead" style="background-image: url('<?php echo $img[0]; ?>)">
  
  カスタムフィールド
  投稿→右上の…→一番下のオプション→カスタムフィールド
  
  single。PHP
  コンテントのところに記述
  <!-- Post Content -->
  <article>
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-10 mx-auto">
        <?php the_content(); ?>
          <dl>
            <dt>価格</dt>
            <?php
            $price = get_post_meta(get_the_ID(), "価格", true);
            ?>
            <dd><?php echo $price; ?>円</dd>
            <dt>発売日</dt>
            <?php 
            $published = get_post_meta(get_the_ID(), '発売日', true);
            ?>
            <dd><?php echo $published ?></dd>
          </dl>

        </div>
      </div>
    </div>
  </article>

プラグイン（かすたむフィールd）
ACFをいれる。
  <article>
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-10 mx-auto">
        <?php the_content(); ?>
          <dl>
            <dt>価格</dt>
            <dd><?php the_field("価格"); ?>円</dd>
            <dt>発売日</dt>
            <dd><?php the_field("発売日"); ?>円</dd>
          </dl>

        </div>
      </div>
    </div>
  </article>
  
  記事の分類
  カスタム投稿タイプ
  fufunction.php
  
  <?php
function init_func() {
  add_theme_support('title-tag');
  add_theme_support( 'post-thumbnails' );

  register_post_type("item", [
    "labels" => [
      "name" => "商品",
    ],
    "public" => true,
    "has_archive" => true,
    "hierarchial" => false,
    "menu_position" => 5,
    "menu_icon" => ""
  ]);
} 
add_action('init', 'init_func');


posttypeメイはURLの一部になるので注意。（もともと使われているposttypeはしようできない）
重要；記入後、設定→パーマリンク設定で保存ボタンを押す。（反映しないままになる」）
作成したカスタムフィールドを追加もできる
  "hierarchial" => false,投稿用
  trueにしたら親子関係になる。
     "menu_icon" => ""ダッシュアイコンで検索して選択可能。（管理画面の見栄え）
     
     
     function.php
     hierarchial→カテゴリーかタグか(true　or false)
     <?php
function init_func() {
  add_theme_support('title-tag');
  add_theme_support( 'post-thumbnails' );

  register_post_type("item", [
    "labels" => [
      "name" => "商品",
    ],
    "public" => true,
    "has_archive" => true,
    "hierarchial" => false,
    "menu_position" => 5,
    "menu_icon" => "dashicons-twitter"
  ]);
  register_taxonomy("item_category", "item", [
    'labels' => [
      "name" => "商品カテゴリー",
    ],
    "hierarchical" => false,
  ]);
} 
add_action('init', 'init_func');
