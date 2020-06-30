### Vue.jsの基本<br>
①　<id>タグで囲む<br>
```
  <div id="app">
    {{ message }}
  </div>
 ```
 ② <body>の最後に追加。<br>
  ```<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>```
 ③定型文を記載<br>
  ```
  <script>
    var app = new Vue({
    el: "#app",
    data: {
      message: "タイトル"
    }
    });
  </script>
  ```
<br>

### if文<br>
①属性を追加する<br>
```
<p v-if="error">エラー</p>
```
 <br>

### 属性の書き換え<br> 
```
<p v-bind:class="error_class">エラー</p>
```
 <br>
