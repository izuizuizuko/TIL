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
