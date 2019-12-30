---
title: ソルブ表示用ボックスの作成
---

## ソルブ表示ボックスを作成する
テスト用のソルブ表示ボックスを表示します。まずはボックスを表示するために、表示されるテキストを準備します。このテキストはliquidで処理され、`<pre>`タグで囲まれて表示されます。
{% raw  %}
```
{% capture display_text %}
B' F D2 //Pseudo 2x2x1 (3/3)
L' B * R2 //Pseudo 3x2x2 (3/6)
F2 D F' D2 F //Found using NISS (5/11)
R' D' R D2 F U2 //Found using NISS (6/17)
* = B2 L B L' B D2 F' R F D2 //2c2e insertion (9/26)
{% endcapture %}
```
{% endraw  %}

liquidのinclude構文を利用して、下記のように呼び出します。  
引数として、上記のtextに加えて`title`、`scramble`、`solution`、`img_src`を与えます。画像ファイルはalg.cubing.netにスクランブルを入力して生成したものをローカルにダウンロードして利用します。
{% raw  %}
```
{% include solvebox.html
title = "2C2E Insertion - Example"
scramble = "B' L' D2 R U F' U' L U2 D R2 U2 F B R2 B U2 B L2 B2 U2"
text = display_text
solution = "B' F D2 L' R2 B R B' R2 F R' B R F' R2 F2 D F' D2 F R' D' R D2 F U2 (26)"
img_src="../assets/img/2C2E_alg.png"%}
```
{% endraw  %}

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

FMC Tutorialの翻訳中に出てくるボックスはこの形で表示できるでしょう。