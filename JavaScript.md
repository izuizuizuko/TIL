### :earth_asia:変数<br>
const→上書×<br>
let  →上書き○ 
<br>
### :earth_asia:プロパティとメソッド<br>
・プロパティ<br>
変数の値を保持している。【．】でつながっている。
```
let hello = "hello world";
console.log("hello.length);
```
<br>
・メソッド<br>
特定の処理を実行する【.();】でつながっている。<br>

```
let hello = "hello world";
console.log("hello.toLocaleUpperCase());
```
<br><br>
### :earth_asia:配列の使い方<br>
・length →　文字数のカウント<br>
・push →　配列の末尾に追加される<br>
・unshift →　配列の先頭に追加される<br>
・pop →　末尾を削除<br>
・shift → 先頭を削除<br>

### :earth_asia:for文（繰り返し処理）<br>
```
const arry = [1,2,3,4,5,];

for(let i = 0; i < arry.length; i ++) {
console.log(i);arry.length;
}
出力結果　＝　0 1 2 3 4
```
<br>
出力結果　＝　0 1 2 3 4
①let i = 0　初期化<br>
②arry.length; = ループを継続する条件<br>
③i ++ ループの終わり<br>

#### for in　と　for of<br>
・for in　= 添字が出力<br>
```
const arry = [1,2,3,4,5,];

for(let i in arry) {
  console.log(i);
  }
出力結果　＝　0 1 2 3 4
```

・for of =　値自体が出力<br>
```
const arry = [1,2,3,4,5,];

for(let v of arry) {
  console.log(v);
  }
  出力結果　＝　1 2 3 4 5
```
出力結果　＝　1 2 3 4 5<br>
<br>

### アロー関数・コールバック関数・reduce

### :earth_asia:DOM<br>
・情報の取得<br>
<br>
  ```document.querySelector("ほしい情報の名称")```
  <br>
dd
