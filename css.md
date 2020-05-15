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
