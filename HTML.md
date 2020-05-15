### :speak_no_evil: インライン要素とブロック要素<br>
#### 中央よせするには？
  ・インライン要素　→　【text-align: center;】<br>
  ・ブロック要素　　→　【marginプロパティ】<br><br>
![無題](https://user-images.githubusercontent.com/59868344/82009779-315d6600-96ab-11ea-9f6e-d1affdae6ab5.png)
### :speak_no_evil: クラスとID<br>
#### 詳細度の順
  タグ　→span<br>
  class →.<br>
  ID    →♯<br> 
### :speak_no_evil: 一発入力<br>
 ```
 #container>.cls*3
 ```
``` 
<div id="container">
            <div class="cls"></div>
            <div class="cls"></div>
            <div class="cls"></div>
 </div>
 ```
<br><br>
 ```
 #container>.cls-$*3
 ```
``` 
 <div id="container">
                <div class="cls-1"></div>
                <div class="cls-2"></div>
                <div class="cls-3"></div>
  </div>
 ```
