---
title: ソルブ表示用ボックスの作成
permalink: /FMC/test-solvebox.html
---

## ソルブ表示ボックスを作成する
### １．手順をテキストとして与える
テスト用のソルブ表示ボックスを表示します。まずはボックスを表示するために、表示されるテキストを準備します。このテキストはliquidで処理され、`<pre>`タグで囲まれて表示されます。{% raw %}`{% capture %}`{% endraw %}を用いてテキストをliquidに与えます。
{% raw %}
```
{% capture display_text %}
B' F D2 //Pseudo 2x2x1 (3/3)
L' B * R2 //Pseudo 3x2x2 (3/6)
F2 D F' D2 F //Found using NISS (5/11)
R' D' R D2 F U2 //Found using NISS (6/17)
* = B2 L B L' B D2 F' R F D2 //2c2e insertion (9/26)
{% endcapture %}
```
{% endraw %}

### ２．ボックス作成用のhtmlファイルをインクルードする
liquidのinclude構文を利用して、下記のように呼び出します。  
引数として、上記のtextに加えて`title`、`scramble`、`solution`、`img_src`を与えます。画像ファイルはalg.cubing.netにスクランブルを入力して生成したものをローカルにダウンロードして利用します。
{% raw %}
```
{% include solvebox.html
title = "2C2E Insertion - Example"
scramble = "B' L' D2 R U F' U' L U2 D R2 U2 F B R2 B U2 B L2 B2 U2"
text = display_text
solution = "B' F D2 L' R2 B R B' R2 F R' B R F' R2 F2 D F' D2 F R' D' R D2 F U2 (26)"
img_src="../assets/img/2C2E_alg.png"%}
```
{% endraw %}

### ３．インクルード先を作成する
最後に、インクルード先のhtml側でボックスを作成します。
```html
{% raw %}<div class="solvebox clearfix shadow-sm">
    {% if include.title %}<h2>{{ include.title }}</h2>{% endif %}
    {% if include.scramble %}<div class="solvetext scramble">スクランブル: {{ include.scramble }}</div>{% endif %}
    <img class='float-md-right img-responsive shadow-none' style='width:150px;height:auto;padding:0;margin:15px 0 0 15px;' src='{{ include.img_src }}'>
    <div class="solvetext clearfix shadow-none"><pre class="shadow-none">{{ include.text }}</pre></div>
    {% if include.solution %}<div class="solvetext solution">ソリューション: {{ include.solution }}</div>{% endif %}
</div>{% endraw %}
```
### ４．cssを定義する
同時にcssも定義しておきます。
```css
.solvebox{
    border: solid 1px rgb(65, 65, 65);
    background-color: white;
    padding-left: 5px;
    padding-right: 5px;
}

.solvebox .scramble{
    border-bottom: solid 1px rgb(65, 65, 65);
}

.solvebox .solution{
    border-top: solid 1px rgb(65, 65, 65);
}
```


## 表示結果
このコードを処理させると、次のようなボックスが表示されます。
{% capture display_text %}
B' F D2 //Pseudo 2x2x1 (3/3)
L' B * R2 //Pseudo 3x2x2 (3/6)
F2 D F' D2 F //Found using NISS (5/11)
R' D' R D2 F U2 //Found using NISS (6/17)
* = B2 L B L' B D2 F' R F D2 //2c2e insertion (9/26)
{% endcapture %}
{% include solvebox.html
title = "2C2E Insertion - Example"
scramble = "B' L' D2 R U F' U' L U2 D R2 U2 F B R2 B U2 B L2 B2 U2"
text = display_text
solution = "B' F D2 L' R2 B R B' R2 F R' B R F' R2 F2 D F' D2 F R' D' R D2 F U2 (26)"
img_src="../assets/img/2C2E_alg.png"%}

FMC Tutorialの翻訳中に出てくるボックスはこの形で表示できるようにします。これで少し楽になるかな？