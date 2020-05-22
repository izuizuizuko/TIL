#### :full_moon_with_face:ホバー<br>
```.クラス名:hober```
別に作成し、ここに変更を記載する。

#### :full_moon_with_face:色の変化（トランジション）<br>
ベースをなるCSSに<br>
```transition: all ◎S；```
  <br>
  希望の変更箇所を第1引数に入力 <br>
  希望の秒数を第2引数に入力<br>
  第3.4引数に追加もできる（何秒後に○○する等）<br>
  
#### :full_moon_with_face:文字の間隔をあける<br>
```letter-spacing:  px;```<br>
```line-height:```
<br>行間を指定＝枠の中の文字の中央揃えをするときに使用(親の要素の高さにそろえる）<br>


#### :full_moon_with_face:Transform<br>
##### 複数を使う時は半角スペース<br>
##### アニメーションを使用したいときに使用
  ・XY軸を基準にtransform→translate(px);<br>
  ・→回転→rotate(deg);<br>
  ・回転軸を決定→transform-origin→場所;<br>
  ・ひし形（斜め→transform→skew(px);<br>
  ・3D表示→transform-style: preserve-3d;(子要素に対して3Dを実行できる）
    ・奥行(遠近感）→perspective(親要素につける）
  
#### :full_moon_with_face:sticky<br>
親要素に追随する<br>

#### :full_moon_with_face:疑似要素<br>
動きをつけるときに、<span>を利用したイメージで前後のコードを書くとき空のspanタグを記述すのではなく『::before』又は『::after』で記述する。<br>
その際必ず```content```を記述すること。<br>
  ``` 
  &::before {
     content: '';
  ```
  <br>
  
  #### :full_moon_with_face:flexとposition<br>
  flexを使用すると重なりあいはできない。<br>
  ```flex-direction: column```縦方向の均等<br>
  ```flex-grow:;```grow=親要素を満たすまで均等に表示（動的に横幅をきめれる）<br>
  
  #### :full_moon_with_face:レスポンシブ対応<br>
  ①モバイルとデスクトップの２つのcssを作成する。<br>
  ②htmlには```style.css```を読み込む<br>
   ```<link rel="stylesheet" href="style.css">```
   <br>
   ③style.cssに以下を書き込んで読み込む<br> 
 ```
  @import "mobile.scss";

  @media screen and (min-width: 601px) {
    @import 'desktop.scss';
  }
```
<br>
デスクトップの方が複雑なので、簡単なモバイルをベースにデスクトップの部分だけ追記する形をとる<br>

 #### :full_moon_with_face:googleフォント使用時の注意<br>
 cssに記載する際の順は、```ローマ字フォント→日本語フォント→保険のフォント```<br>
 <br>フォントは毎回設定するよりある程度揃えた方がサイトに統一感がでる<br>
 ```
          モバイル　　PC
 font-sm　14px     16px
 font-md　17px     19px
 font-lr  17px     23px
 font-lg  25px     36px
 ```
 <br><br>
 #### :full_moon_with_face:リセットCSSとノーマライズCSS<br>
 ・リセットCSS→すべてを打ち消す。<br>
 ```https://meyerweb.com/eric/tools/css/reset/```<br>
 ・ノーマライズCSS→ブラウザ毎に違う部分を統一する<br>
 ```https://necolas.github.io/normalize.css/8.0.1/normalize.css```<br>
 ・BootStrapのrebootCSS<br>
 ```https://github.com/twbs/bootstrap/blob/v4.3.1/dist/css/bootstrap-reboot.css```<br>
 #### ※すべて一番先頭で読み取る必要がある。
 
