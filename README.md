# 演算子

| 演算子 | 説明                                         |
| ------ | -------------------------------------------- |
| +      | 足し算                                       |
| -      | 引き算                                       |
| \*     | 掛け算                                       |
| /      | 割り算                                       |
| %      | 割り算の余り                                 |
| ()     | ()内の計算を優先して計算<br/> 例：2 \* (2+3) |
| ++     | 1 を加算                                     |
| --     | 1 を減算                                     |

# 変数の種類

## let

<br/>
一度値を代入した後、再度別の値を代入することができます<br/>
年齢のように値が変化する数字を扱う場合などは let で変数宣言する

```JavaScript
<script>
    let age = 20;
    document.write("山田さんの年齢は" + age + "歳です");  //「20歳」と表示

    age = 20 + 10;
    document.write("10年後の年齢は" + age + "歳です");  //「30歳」と表示
</script>
```

## const

<br/>

変数にあとから別の値を代入してもエラーとなります<br/>
値をあとから代入できないようにするには const で変数宣言する

```JavaScript
<script>
    const tax = 1.1;　// 消費税
    let sweets = 500 * tax; // おやつ
    let book = 1000 * tax; // 本
    document.write(sweets + book); //おやつと本の税込み価格
</script>
```

## var

<br/>
再代入が可能な変数宣言で、ES6よりも前のバージョンのJavaScriptでは変数宣言にvarが使われていました

<br/>

# 変数のスコープ

関数の中で宣言した変数はその関数の中でしか利用することができません。<br/>
このことを変数のスコープと言います。変数を宣言した場所によって変数を呼び出せる範囲が変わります。

```JavaScript
let tax = 1.1;
  function recept_2() {
    let egg = 300 * tax;
    let rice = 1000 * tax;
    let soysauce = 200 * tax;
    let total = egg + rice + soysauce;
  }
document.write(total);　//エラーとなる
```

- 関数の外で宣言した変数 tax は関数に外でも呼び出せる
- 関数の中で宣言した変数 total は関数の外では呼び出せない

<br/>

# 変数と関数の命名ルール

変数名は好きな名前を付けられますが以下のようなルールがあります。

- 変数名に使ってもよい記号は\_(アンダーバー)$(ドル）のみ
- 変数名の１文字目に数字は使えない
- 大文字と小文字は区別され、let ABC と let abc は別の変数となる
- 変数名に予約語は使えない

# 予約語

予約語とは、変数名や関数名に使うことができない文字列のことです。<br/>
これらの文字は JavaScript の命令などですでに使われているため、自分で変数名や関数名として宣言しようとするとエラーとなります。

|          |           |            |           |              |
| -------- | --------- | ---------- | --------- | ------------ |
| abstract | arguments | boolean    | break     | byte         |
| case     | catch     | char       | class     | const        |
| continue | debugger  | default    | delete    | do           |
| double   | else      | enum       | eval      | export       |
| extends  | false     | final      | finally   | float        |
| for      | function  | goto       | if        | implements   |
| import   | in        | instanceof | int       | interface    |
| let      | long      | native     | new       | null         |
| package  | private   | protected  | public    | return       |
| short    | static    | super      | switch    | synchronized |
| this     | throw     | throws     | transient | true         |
| try      | typeof    | var        | void      | volatile     |
| while    | with      | yield      |           |              |

# 比較演算子

| 演算子 | 条件文  | 意味                                      |
| ------ | ------- | ----------------------------------------- |
| <      | x < y   | x は y より小さい                         |
| <=     | x <= y  | x は y 以下                               |
| >      | x > y   | x は y より大きい                         |
| >=     | x >= y  | x は y 以上                               |
| ==     | x == y  | x と y は等しい（値の比較）               |
| !=     | x !=y   | x と y は等しくない（値の比較）           |
| ===    | x === y | x と y は等しい（オブジェクトの比較）     |
| !==    | x !== y | x と y は等しくない（オブジェクトの比較） |

# 論理演算子

条件が複数ある場合に使う

| 演算子 | 条件文             | 意味                                                                    |
| ------ | ------------------ | ----------------------------------------------------------------------- |
| &&     | x == y && a == b   | x と y は等しい、かつ a と b も等しい(両方の条件に当てはまる場合)       |
| ｜｜   | x == y ｜｜ a == b | x は y は等しい、または a と b が等しい(どちらかの条件に当てはまる場合) |

# 繰り返し

```JavaScript
<script>
    for (let i = 0; i < 10; i++) {
        document.write("繰り返しの" + i + "回目です");
        document.write("<br />");
    }
</script>
```

()の中に書いてあるのが何回繰り返すかの条件が書いてあります。

直訳するとこのようになります。

- let i=0;の部分は変数 i を 0 から数え始める
- i < 10;の部分は i が 10 より小さければ繰り返し処理を続ける
- i++の部分は i に１を加算する

# foreach

```JavaScript
  let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
  array.forEach(function (element) {
      document.write("配列の" + element + "番目を表示");
      document.write("<br />");
  });
```

配列 array の最初の要素から最後の要素まで順に取り出して値を表示しています。<br/>
forEach は配列の機能のひとつで配列名.forEach(....)のように利用します。<br/>
element の部分に配列の値が１個ずつ格納されています。element の部分は function の引数で、<br/>
この引数の名前は element 以外の自分で分かりやすい名前をつけることもできます。<br/>
{}中に繰り返して実行したい処理を記述します。

# イベント

| イベント    | 発生タイミング                                     |
| ----------- | -------------------------------------------------- |
| onchange    | チェックボックスなどのフォームの状態が変わった時   |
| onclick     | クリックしたとき                                   |
| oninput     | テキストボックスなどのフォームに入力したとき       |
| onload      | HTML の読み込みが完了したとき、HTML を表示する直前 |
| onmouseover | マウスカーソルが要素の上にあるとき                 |
| onmouseout  | マウスカーソルが要素から離れた時                   |
| onmousedown | マウスのボタンを押し込んだ時                       |
| onresize    | 画面のサイズが変わった時                           |
| onscroll    | 画面をスクロールした時                             |
| onsubmit    | フォームを送信した時                               |
