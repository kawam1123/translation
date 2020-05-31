---
title: 第3章 高度なツール - 最少手数競技入門 by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 17:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/chapter3
layout: single
classes: wide
toc: false
tocright: true
toc_icon: "cog"
toc_sticky: true

author_profile: false
sidebar:
  nav: "fmc-v3"
footnote_script: true
---
[戻る：第2章](chapter2){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第4章](chapter4){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->

## 高度なツール (Advanced Tools)
ここまでの章では、よい解答を見つけるために必要な基本的なテクニックを見てきました。この章ではもっと高度なツールを紹介します。必須ではありませんが、探索に行き詰まったときの助けになります。
<!--
Chapter 3
Advanced Tools
In the previous chapter we have looked at the basic techniques, needed to find a good solution.
In this one more advanced tool will be provided. They are not necessary, but they help getting
unstuck and give you more possibilities to explore.
-->
### 3.1 逆スクランブル(Inverse Scramble)

**いいスタートが見つからない時は、逆スクランブル(Inverse scramble、インバーススクランブル)を試してみましょう。**逆スクランブルで解答を見つけたら、それを逆手順にすることで通常のスクランブルに対する解答になります。複雑そうに見えますが、実はとてもシンプルです。

Tim Reynoldsの北アメリカ記録から例を挙げましょう。

{% capture display_text %}
逆スクランブルで
R' U F' L2 //2x2x2 (4/4)
F2 D' B' * D2 B //2x2x3 (5/9)
R2 F R2 F' R2 //F2L-1 (5/14)
F D' F' D //3コーナー以外完成 (4/18)
* = B' U2 B D B' U2 B D' //最後3コーナー (6/24)
{% endcapture %}
{% include solvebox.html
title = "逆スクランブル - Example"
scramble = "D2 L2 B R2 U2 F' L2 U2 B2 L2 F' D L2 B U L' U2 L' F' R'"
text = display_text
solution = "D' F D F' R2 F R2 F' R2 B' D' B' U2 B D' B' U2 B2 D F2 L2 F U' R (24)"
img_src="../../../assets/img/alg-310.png"
algcubing = "https://alg.cubing.net/?setup=R_F_L_U2_L_U-_B-_L2_D-_F_L2_B2_U2_L2_F_U2_R2_B-_L2_D2&alg=R-_U_F-_L2_%2F%2F2x2x2%0AF2_D-_B-_(B-_U2_B_D_B-_U2_B_D-)_D2_B_%2F%2F2x2x3%0AR2_F_R2_F-_R2_%2F%2FF2L%26%2345%3B1%0AF_D-_F-_D_%2F%2FAll_but_3_corners"
%}

<!--
3.1 Inverse Scramble
If you can’t find any good start, you can try with inverse scramble: if you find a solution for the
inverse sequence1
, you just need to invert it to get a solution for the normal scramble. It looks
complicated but it is actually very simple.
As an example, here is the former North American record by Tim Reynolds.
Inverse Scramble - Example
Scramble: D2 L2 B R2 U2 F' L2 U2 B2 L2 F' D L2 B U L' U2 L' F' R'
Inverse Scramble: R F L U2 L U' B' L2 D' F L2 B2 U2 L2 F U2 R2 B' L2 D2
On Inverse Scramble:
R' U F' L2 //2x2x2 (4/4)
F2 D' B' * D2 B //2x2x3 (5/9)
R2 F R2 F' R2 //F2L-1 (5/14)
F D' F' D //All but 3 corners (4/18)
* = B' U2 B D B' U2 B D' //Last 3 corners (6/24)
Solution: D' F D F' R2 F R2 F' R2 B' D' B' U2 B D' B' U2 B2 D F2 L2 F U' R (24)
See on alg.cubing.net
-->

この解答を追いかけるには、まず逆スクランブルを回してから、解答のステップに入りましょう。画像は「ノーマルスクランブル」のものです。逆スクランブルのものではないので、逆スクランブルしても一致しません。最後に、逆スクランブルに対する`R' U F' L2 F2 D' B2 U2 B D B' U2 B D B R2 F R2 F' R2 F D' F' D`という解答が見つかりました。これを逆手順にしたものが上記の最終解答です。

|ノーマルスクランブル|逆スクランブル|
|:-------------------|:--------------|
|![](../../../assets/img/alg-310n.png){:width="250px" height="auto" class="img-responsive align-center"}|![](../../../assets/img/alg-310.png){:width="250px" height="auto" class="img-responsive align-center"}|
|D2 L2 B R2 U2 F' L2 U2 B2 L2 F' D L2 B U L' U2 L' F' R'|R F L U2 L U' B' L2 D' F L2 B2 U2 L2 F U2 R2 B' L2 D2|

よくある間違いとして、通常のスクランブルと逆スクランブルはまったく関係がないという考えがありますが、実はこの二つはよく似ています。たとえば、ZZを使うなら、二つのスクランブルを見て同じ数の悪いエッジ(bad edge)があるけれど違う場所にあることがわかるでしょう。また、どちらか一方で見つけたブロックはもう一方にもあって、色の組み合わせや場所が違っていることもわかるでしょう。

<!--
To follow the solution, apply the inverse scramble first, and then the solution steps. The
picture represents the “normal” scramble, not the inverse one, so your scrambled cube shouldn’t
match it. In the end you find the solution
R' U F' L2 F2 D' B2 U2 B D B' U2 B D B R2 F R2 F' R2 F D' F' D
for the inverse scramble, that inverted gives the actual solution written above.
It is a common mistake to think that normal and inverse scramble are complete unrelated.
They are actually very similar: for example, if you use ZZ, you will notice that, for any orientation, the two scrambles have the same number of “bad” edges, but in different positions. You
will also notice that any block found in one of the two is also in the other one, but sometimes
it is somewhere else and made of pieces of different colors.

-->
一般則は次の通りです。

**通常のスクランブルでピース「X」がピース「Y」の場所にあるならば、逆スクランブルではピース「Y」はピース「X」の場所にある**
{: .notice}

すなわち、**揃ったピースと、場所はあっているがねじれているピースは、逆スクランブルにおいてもそれぞれ同じようになっています。ねじれたコーナーは逆方向にねじれます。**「固定された」ブロックは同様に残りますが「移動する」ブロックは違うピースに入れ替わり別の場所に行きます。


<!--
 The general rule is this:
1
I prefer repeating myself: the inverse sequence of, for example, F R U' is U R' F', not F' R' U or U' R F!
35
36 CHAPTER 3. ADVANCED TOOLS
If in the normal scramble piece X is in the place of piece Y, in the inverse
scramble piece Y is in the place of piece X.
Therefore, solved and flipped-in-place pieces will be respectively solved and flipped-in-place
in the inverse scramble, with twisted corners twisted the other way round. “Fixed”2 blocks will
stay the same, while “moving” blocks will be made of different pieces and placed somewhere else.
-->

公式／非公式の試技で、始まったときにまず逆スクランブルを書いておく人もいますし、NISSなどを使うときに初めて書く人もいます。こうしておくと、特に努力することなく、使いたいときいつでも逆スクランブルを使えるようになります。ただし、試技を始める一番最初に、紙に逆スクランブルを書いてから、間違いがないかを確認しなければなりません。私はこうする代わりに、**通常のスクランブルを右から左に読みながら、頭の中でそれぞれの記号を逆にして逆スクランブルを使います。** 最初は難しいでしょうけれど、最終的には普通のスクランブルと同じくらい速く回せるようになりますし、ほとんど苦労しないでしょう。このやり方をするかどうかはあなたの好み次第です。 

逆スクランブルはそのままでも役立つテクニックですが、次の節で話す内容の基礎になります。つまり、ソルブの最初で詰まったときや単にもっと多くの可能性を探索したいときに役立ちます。


<!--
During an official or unofficial attempt, some people write down the inverse scramble in full
before starting the attempt, or when they decide to use it (or to use NISS). This way it’s easier
to apply the inverse scramble any time you want without additional effort, but it takes to write
it down at first (and to check for mistakes!). Instead, to apply the inverse scramble I simply
invert each move in my head while reading the normal scramble from right to left. This may
seem difficult at first, but in the end it becomes about as fast as aplying a regular scramble and
almost without additional effort. It’s up to you to decide which method you prefer.
Besides being a technique useful as it is, in case you get stuck right at the beginning of a
solve or simply to get more possibilities to explore, the ideas explained here are fundamental to
the techniques introduced in the next paragraph.
-->
### 3.2 疑似ブロック、プリムーブ、NISS (Pseudo Blocks, Premoves and NISS)
3.2節はまとめて一気に読むといいでしょう。ここで説明する3つのテクニックは密接な関連があります。
<!--
3.2 Pseudo Blocks, Premoves and NISS
This whole Section 3.2 is better read all at the same time, since the three techniques explained
are deeply related.
-->
#### 3.2.1 疑似ブロック (Pseudo Blocks)
**疑似ブロック**を使った例はこれまでにもいくつか見てきました。この概念をもっとわかりやすくするために、次のスクランブルを詳しく見てみましょう

スクランブル: `F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'`

![](../../../assets/img/alg-321a.png){:width="300px" height="auto" class="img-responsive align-center"}

`R2 F`すれば2x2x1ブロックができます。2、3手で2x2x2ブロックに拡張できればいいですが、`L' U B' D`とさらに4手かかるのはちょっと多すぎます。ところが、`L2 D'`とやってみましょう。つまり、合わせて`R2 F L2 D'`と回すと次のようになります。

<!-- 訳者TODO 画像入れる -->

![](../../../assets/img/alg-321b.png){:width="300px" height="auto" class="img-responsive align-center"}
`R2 F L2 D'`と回した後にDFLコーナー側から見たキューブ
{: .text-center}

ここでできているのは**本物の2x2x2ブロックではなく疑似2x2x2ブロックです。**このときのD面を一時的に`D2`だけズレた状態であると考えて、すべてが完成したあとで`D2`するものだと考えてみることができます。たとえば、このまま（非効率的ですが）CFOPでソルブを進めてみましょう。

<!--
3.2.1 Pseudo Blocks
We have already met some examples of pseudo blocks. To make the concept more clear, lets
look in detail at the following scramble.
Scramble: F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'
The moves R2 F make a 2x2x1 block. It would be nice to expand it to a 2x2x2 in 2 or 3
moves, but the 4 moves required (L' U B' D) are maybe too many. But try with L2 D':
View at the DFL corner of the cube after moves R2 F L2 D’
2
“Fixed” blocks are those than can’t more around centers, such as a 2x2x2 or a 2x2x3. “Moving” blocks are,
for example, 3x2x1s, 2x2x1s and corner/edge pairs.
3.2. PSEUDO BLOCKS, PREMOVES AND NISS 37
What you get is not an actual 2x2x2 block, but a pseudo 2x2x2 block. We can think of the
D layer as it was temporarily off by a D2 move, that we can do at the end to solve everything
back. For example, we can continue with a (inefficient) CFOP solve:
-->
`R2 F L2 D'` //疑似2x2x2  
`B' U2 R' U2 R2 U R` //クロス、2つ目のペア  
`U2 F' U F U' F' U' F` //3つ目のペア  
`L U2 L'` //4つ目のペア  
`B L' B' U' B U L U' B'` //OLL  
`F2 D' L2 D F2 R2 D B2 D' R2` //PLL  
`D2` //プリムーブをもとに戻す  

このケースであれば、`D2`はOLLの前やOLLとPLLの間にやってしまっても構いませんが、F2Lのステップが終わっていないなら最後にやらなければなりません。


<!--
R2 F L2 D' //Pseudo 2x2x2
B' U2 R' U2 R2 U R //Cross and second pair
U2 F' U F U' F' U' F //Third pair
L U2 L' //Fourth pair
B L' B' U' B U L U' B' //OLL
F2 D' L2 D F2 R2 D B2 D' R2 //PLL
D2 //Undo premove
In this case the D2 move could have been done before the OLL, or between OLL and PLL,
but if you don’t finish the F2L as an intermediate step you have to do it at the end.
-->
#### 3.2.2 プリムーブ (Premoves) {#premove}
前の節で示した状況はそこまで難しいものではありませんが、「疑似性 (pseudoness)」を考え
たまま、ソルブを進めるのは難しいでしょう。**F2Lのペアの認識はすぐにはできませんし、F2Lがズレた状態でのOLLやPLLを認識することを考えると、通常はとんでもないことになります。**たとえば、`R`だけズレたものを考えてみましょう！

疑似ブロックを作ったまま進めるとよいと言う人もいるでしょうが、全てを簡単にしてしまうワザがあります。**全て揃った最後にやるべきムーブ（ここでは`D2`）をスクランブルの前にやるだけでよいのです。**（なので、この手法は**「プリムーブ」**と呼ばれます）さあ、やってみましょう！

{% capture display_text %}
R2 F L2 D' //2x2x2
B' U2 R' U2 R2 U R //クロス、2つ目のペア
U2 F' U F U' F' U' F //3つ目のペア
L U2 L' //4つ目のペア
B L' B' U' B U L U' B' //OLL
F2 D' L2 D F2 R2 D B2 D' R2 //PLL
{% endcapture %}
{% include solvebox.html
title = "プリムーブで修正したスクランブル Example"
scramble = "D2 F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'"
text = display_text
solution = ""
img_src="../../../assets/img/alg-322.png"
algcubing = ""
%}

<!--
3.2.2 Premoves
The situation of the previous example is not particularly difficult, but the “pseudoness” makes
it harder to go on with the solve: the recognition of F2L pairs is not immediate. Usually it’s
even worse: imagine recognizing OLL and PLL when the F2L is off by, for example, R!
Someone advises to try and solve with pseudo blocks, but there is a trick that makes everything easier: you just need to perform the move that should be done at the end (in this case,
D2) before the scramble (and that’s why they are called “pre-moves”). Try it out!
Premoves - Modified Scramble Example
Scramble: D2 F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'
R2 F L2 D' //2x2x2
B' U2 R' U2 R2 U R //Cross and second pair
U2 F' U F U' F' U' F //Third pair
L U2 L' //Fourth pair
B L' B' U' B U L U' B' //OLL
F2 D' L2 D F2 R2 D B2 D' R2 //PLL
See on alg.cubing.net
-->

このような解答を見つけたときには、**プリムーブを解答の最後に付け加えることで元のスクランブルに対する解答になると覚えておきましょう。**一つ前の節で見たものはこうして得られたものです。複数手のプリムーブをやることもできます。例として次のソルブを見てみましょう。これは私の最初の公式ソルブで、元イタリア記録のものです。スクランブルする前にプリムーブを入れるのを忘れないようにしてください。

{% capture display_text %}
Premoves: D2 B2
R2 B' R2 B //2x2x2, B2というプリムーブをここで見つけた
D L2 F D F2 //2x2x3
L' D F' D2 F D' //F2L-1, D2というプリムーブをここで見つけた
L' D * L' F L' F' D' L' //3コーナー以外完成
* = B L' F L B' L' F' L //3コーナー
{% endcapture %}
{% include solvebox.html
title = "プリムーブで修正したスクランブル Example"
scramble = "U L' F' L2 F' D2 F'B' U' R2 U L' F2 U' F2 L2 U2 F2 L2 U2"
text = display_text
solution = "R2 B' R2 B D L2 F D F2 L' D F' D2 F D' L' D B L' F L B' L2 F' D'
L' D2 B2 (28)"
img_src="../../../assets/img/alg-3222.png"
algcubing = ""
%}

<!--
Once you have found such a solution, remember that the premove (or premoves, if there is
more than one) has to be added at the end of the solution, to solve the original scramble. In
this way we get back the final solution of the previous sub-section.
You can use more than one premove: take for example this solve, which is my first official
solve as well as former Italian National Record. Remember to permorm the premoves before
starting scrambling.
Multiple Premoves - Example
Scramble: U L' F' L2 F' D2 F'B' U' R2 U L' F2 U' F2 L2 U2 F2 L2 U2
Premoves: D2 B2
R2 B' R2 B //2x2x2, found premove B2 here
D L2 F D F2 //2x2x3
L' D F' D2 F D' //F2L-1, found premove D2 here
L' D * L' F L' F' D' L' //All but 3 corners
* = B L' F L B' L' F' L //Last 3 corners
Solution: R2 B' R2 B D L2 F D F2 L' D F' D2 F D' L' D B L' F L B' L2 F' D'
L' D2 B2 (28)
See on alg.cubing.net
-->
#### 3.2.3 NISS
前の節の最後の例では、2つのプリムーブを、2つの違う時点で見つけました。2つ以上のプリムーブが必要な疑似ブロックを見つけるのは少し難しいです。たとえば次のスクランブルを見てみましょう。

`F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'`
{: .text-center}

![](../../../assets/img/alg-323-1.png){:width="300px" height="auto" class="img-responsive align-center"}

同じように2x2x1ブロックから始めてみましょう(`R2 F'`)。ここに`D F'`というプリムーブを加えることで2x2x2ブロックができることに気づくのは、たとえ熟練者でも難しいでしょう。加えると次のようになります。

スクランブル：`D F' F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'`  
ここに`R2 F'`をして2x2x2ができる
{: .text-center}

![](../../../assets/img/alg-323-2.png){:width="300px" height="auto" class="img-responsive align-center"}
`D F'`というプリムーブを加えてから、`R2 F`をした状態(DFRコーナーから見たもの)
{: .text-center}

**しかし、NISS (Normal-Inverse Scramble Switch)を知っていれば、こういったプリムーブを見つけることはそう難しくありません。** このテクニックは2009年にRazoux Schultzによって最初に考案されました。

ここ説明する概要は、Tomoaki Okayamaによる素晴らしい投稿によるものです[^3-2-3-1]。最も重要なのことは次のようにまとめられます。

**スクランブルと解答は、単一のムーブのループ配列として考えることができ、これはキューブの状態にまったく影響しない。**
{: .notice}

<!--/
3.2.3 NISS
In the last example, I have found the two premoves in two different moments. It is a little harder
to recognize pseudo blocks that require more than one premove: with our scramble
F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'
start with the same 2x2x1 (R2 F'). Even an expert will find it difficult to see that by adding
D F' as premoves you get a 2x2x2:
Scramble: D F' F' L2 F2 U2 R2 B R2 F' R2 D2 U2 L' U' B' U R U L2 F2 L'
2x2x1: R2 F
2×2×2 in DFR after R2 F, with premoves D F'.
But such premoves are not har to find, if you know NISS (Normal-Inverse Scramble Switch).
This technique was first introduced by Guus Razoux Schultz in 2009 and we explanation we
outline here is taken form this excellent post3 by Tomoaki Okayama. The most important fact
is the following:
The scramble and the solution can be thought of as a single move sequence
loop, that doesn’t affect the cube in any way.
-->

これだけではわかりにくいので解説しましょう。たとえば、抽象化して、`A B C D`をスクランブル、`p q r s`をそれに対する解答と考えてみましょう。`A B C D p q r s `という配列で、キューブは完成状態に戻ります。

ここで、同じように、次のような「ズラした」配列をいくつか考えてみると、どれもキューブの状態に影響しないことがわかります。（崩れません）

`s (A B C D p q r s) s'` = `s A B C D p q r`  
`r s (A B C D p q r s) s' r'` = `r s A B C D`  
`q r s (A B C D p q r s) s' r' q'` = `q r s A B C D`  
`p q r s (A B C D p q r s) s' r' q' p'` = `p q r s A B C D`  
`D p q r s (A B C D p q r s) s' r' q' p' D'` = `D p q r s A B C`  
. . .
{: .text-center}

もちろん、逆手順にしてもキューブの状態に影響しません。

<!--
For example, let abstractly A B C D be a scramble and p q r s a solution for it. The
sequence A B C D p q r s brings the cube back to it solved state. In the same way, every
“shifted” version of this sequence:
s (A B C D p q r s) s' = s A B C D p q r
r s (A B C D p q r s) s' r' = r s A B C D
q r s (A B C D p q r s) s' r' q' = q r s A B C D
p q r s (A B C D p q r s) s' r' q' p' = p q r s A B C D
D p q r s (A B C D p q r s) s' r' q' p' D' = D p q r s A B C
. . .
doesn’t affect the cube. Inverse sequences don’t affect the cube either, obviously.
-->

さて、`D2`を使う最初のプリムーブの例では、このループは次のようになっていました。

(スクランブル) `R2 F L2 D'` (他のムーブ) `D2`
{: .text-center}

言い換えれば、ここでの**「`R2 F L2 D'` (他のムーブ) `D2`」をスクランブルに対する解答と見なすことができるわけです。**つまり、「`R2 F L2 D'` (他のムーブ)」を「`D2` (スクランブル)」に対する解答と見なすこともできます[^3-2-3-2]。

プリムーブの仕組みを理解するにはこれで十分だと思います。このことを知っていれば、**通常のスクランブルに対する部分解答と逆スクランブルに対する部分解答を見つけることができるのです。** つまり、どういうことでしょうか？　同じスクランブルで同じように`R2 F`から考えてみましょう。この時点で、(W)を何らかの手順と考えると、解答は`R2 F (W)`となることがわかります。ここでのループ配列は次のようになります。
<!--
In our first example with premove D2, the loop would have been:
(Scramble) R2 F L2 D' (Other moves) D2
And preforming D2 at the beginning only means taking one of the shifted variations:
D2 (Scramble) R2 F L2 D' (Other moves)
In other words, we can consider “R2 F L2 D' (Other moves) D2” as a solution for “(Scramble)” or “R2 F L2 D' (Other moves)” as a solution for “D2 (Scramble)”4
.
This should be enough to understand how premoves work. Knowing this, we can also find a
solution partly on the normal scramble scramble and partly on the inverse one. How? Consider
the same scramble and the same start R2 F. We know that, starting from here, our solution will
look like R2 F (W), where (W) stays for some sequence of moves. Our loop sequence is:
3
https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-52#post-667292
4You can also see the scramble as a solution to the solution!
3.2. PSEUDO BLOCKS, PREMOVES AND NISS 39
-->

`(スクランブル) R2 F (W)`
{: .text-center}

前にも言ったように、これの逆手順は「同一」のループです。（逆スクランブルを使って解答を探すのと同じです）

`(W)' F' R2 (逆スクランブル)`
{: .text-center}

なので、`(W)' F' R2`を`(逆スクランブル)`に対するに解答、またたとえば`(W)'`を`F' R2 (逆スクランブル)`に対する解答と考えることができます。このように、次の一般則を導くことができます。

**通常スクランブルで見つけた手順の逆手順を、逆スクランブルに対するプリムーブとして使うことができる**
{: .notice}

<!--
(Scramble) R2 F (W)
As we said before, the inverse of this is also an “identity” loop (It is equivalent to finding a
solution using the inverse scramble):
(W)' F' R2 (Inverse Scramble)
We can therefore consider “(W)' F' R2” as a solution for “(Inverse Scramble)” but also, for
example, (W)' as a solutin for “F' R2 (Inverse Scramble)”. In this way we have come to the
general rule
You can use the inverse of the moves found on normal scramble as premoves
for the inverse scramble.
-->

仮に、逆スクランブルに対して`F' R2`というプリムーブを加えてから**`(K)`**という解答を見つけたとしましょう。すると、 **`(K)`**は上に示した`(W)'`と同じような効果になるでしょう。これで終わりです！最終解答は **`R2 F (K)'`**という形になるでしょう。


このプロセスは繰り返すことができます。逆スクランブルに対して上のプリムーブを加えてから`F D'`をすると、2x2x2ブロックができたがあまりうまく続かなかったとしましょう。**この時点で(さらに)ノーマルスクランブルに戻ることができます。**　今度は`D F'`をプリムーブとして考えます。まとめると、ループした配列は次のようになります。

`F' R2 (逆スクランブル) F D' (まだ見つかっていないムーブ)`
{: .text-center}

これを逆にすることで別のループを作ることができます。

`(まだ見つかっていないムーブの逆) D F' (スクランブル) R2 F`
{: .text-center}

つまり、ここでは `D F'` を本来のスクランブルに対するプリムーブ、 `R2 F'`はスクランブルのあとのムーブとしてみなすことができます。[実例](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-10#post-258791)を見るともっとはっきりとわかるでしょう。[^3-2-3-3]

|ノーマルスクランブル|逆スクランブル|
|:-------------------|:--------------|
|![](../../../assets/img/alg-323-b-1n.png){:width="250px" height="auto" class="img-responsive align-center"}|![](../../../assets/img/alg-323-b-1i.png){:width="250px" height="auto" class="img-responsive align-center"}|
|R B U L' U' B U2 D2 F D R L D B2 L2 D' F2 D2 L2 D|D' L2 D2 F2 D L2 B2 D' L' R' D' F' D2 U2 B' U L U' B' R'|

<!--
Suppose now you have found a solution, call it (K), to the inverse scramble with premoves
F' R2. Then (K) must have the same effect as (W)', so you are done: your final solution would
be R2 F (K)'.
You can repeat this process: suppose you have found the moves F D' on inverse scramble
with premoves (which make a 2x2x2 block), but no good continuation. At this point we can go
back to normal scramble, using D F' as premoves. In fact, the loop sequence is:
F' R2 (Inverse Scramble) F D' (Moves yet to be found)
Inverting it gives another identity loop:
(Inverse of moves yet to be found) D F' (Scramble) R2 F
So we can consider D F' as premoves for the original scramble and start with R2 F.
An example5 will make everything clearer.
Scramble: R B U L' U' B U2 D2 F D R L D B2 L2 D' F2 D2 L2 D
Inverse Scramble: D' L2 D2 F2 D L2 B2 D' L' R' D' F' D2 U2 B' U L U' B' R'
Normal Scramble Inverse Scramble
-->
まずは逆スクランブルで `B L' U F2` といういいスタートがあります。

![](../../../assets/img/alg-323-b2.png){:width="300px" height="auto" class="img-responsive align-center"}
(逆スクランブル) B L' U F2
{: .text-center}

これをノーマルスクランブルに適用します。(`F2 U' L B'`をプリムーブにして）`D' B' U B2 R2`とするとつながりがよいです。

![](../../../assets/img/alg-323-b3.png){:width="300px" height="auto" class="img-responsive align-center"}
F2 U' L B' (スクランブル) D' B' U B2 R2
{: .text-center}

さらに逆スクランブルに適用します。(`R2 B2 U' B D`をプリムーブにして) `B L' U F2`と回します。

![](../../../assets/img/alg-323-b4.png){:width="300px" height="auto" class="img-responsive align-center"}
R2 B2 U' B D (逆スクランブル) B L' U F2
{: .text-center}

このまま逆スクランブルで続けてもよい手順があります。`R B R' U R' U2 R B`でF2Lを完成させましょう。

![](../../../assets/img/alg-323-b5.png){:width="300px" height="auto" class="img-responsive align-center"}
F2 U' L B' (逆スクランブル) D' B' U B2 R2 R B R' U R' U2 R B
{: .text-center}

最後にLLを揃えます。

LL: `U2 R' U2 R' D' L F2 L' D R2`
{: .text-center}

そしてプリムーブをキャンセルする補正をしましょう。

`R2 B2 U' B D`
{: .text-center}

最終解答： D' B' U B2 D' L F2 L' D R U2 R U2 B' R' U2 R U' R B' R' F2 U' L B'


**訳注：**  
ノーマルスクランブルとインバーススクランブルを行ったり来たりするNISSの手法はプリムーブを自然に拡張した手法ですが、理解するまでがなかなか大変なものだと思います。NISSについての日本語レファレンスとしては、やはり[WRCCの解説記事](http://wrcc.main.jp/commentary_fmc/fmc/6)を読んでおくと間違いないでしょう。また、NISSを使ったソルブ例を詳しく解説したものとしては、まっしゅ氏による[FMCアドベントカレンダーの記事](http://cubingmushroom.blog.fc2.com/blog-entry-46.html)が読みやすいと思います。翻訳者はこれを読んでNISSの流れがようやく理解できました。  
[6. NISS - WRCC FMC入門](http://wrcc.main.jp/commentary_fmc/fmc/6)  
[FMC Advent Calendar 2019 3日目 - きゅーびんぐまっしゅるーむ](http://cubingmushroom.blog.fc2.com/blog-entry-46.html)
{: .notice--info}
<!--
Explanation:
Nice start on inverse scramble: B L' U F2
(Inverse Scramble) B L' U F2
Apply on normal scramble: [pre-moves F2 U' L B'] nice continuation: D' B' U B2 R2
F2 U' L B' (Scramble) D' B' U B2 R2
Apply on inverse scramble: [pre-moves R2 B2 U' B D]: B L' U F2
R2 B2 U' B D (Inverse Scramble) B L' U F2
Easy continuation on inverse scramble:
F2L: R B R' U R' U2 R B
R2 B2 U' B D (Inverse Scramble) B L' U F2 R B R' U R' U2 R B
LL: U2 R' U2 R' D' L F2 L' D R2
Premoves correction: R2 B2 U' B D
Solution: D' B' U B2 D' L F2 L' D R U2 R U2 B' R' U2 R U' R B' R' F2 U' L B'
-->
このような(NISSを繰り返す)解答を短く簡単に書くには、**逆スクランブルでのムーブをカッコで囲むという表記を使うとよいでしょう。**今ではこのような表記は広くFMC競技者に受け入れられていますが、NISSを知らない初心者が説明なしで見ると混乱するかもしれません。

たとえば、Guusのソルブであれば次のようになります。

{% capture display_text %}
(B L' U F2) //逆スクランブルでのよいスタート
D' B' U B2 R2 //つながりもよい
(R B R' U R' U2 R B) //F2L
(U2 R' U2 R' D' L F2 L' D R2) //LL
{% endcapture %}
{% include solvebox.html
title = "NISS Example"
scramble = "R B U L' U' B U2 D2 F D R L D B2 L2 D' F2 D2 L2 D"
inversescramble = "D' L2 D2 F2 D L2 B2 D' L' R' D' F' D2 U2 B' U L U' B' R'"
text = display_text
solution = "D' B' U B2 D' L F2 L' D R U2 R U2 B' R' U2 R U' R B' R' F2 U' L B' (25)"
img_src="../../../assets/img/alg-323-4.png"
algcubing = ""
%}

<!--
To make writing such solutions shorter and easier, I have proposed the following notation:
put moves that are done on inverse scramble are written inside round brackets. This notation
is now widely accepted and used among FMC solvers, but can still confuse beginners who don’t
know NISS if you use it without explaining it.
For example, Guus’ solve becomes:
3.3. REVERSE NISS 41
NISS - Example
Scramble: R B U L' U' B U2 D2 F D R L D B2 L2 D' F2 D2 L2 D
Inverse Scramble: D' L2 D2 F2 D L2 B2 D' L' R' D' F' D2 U2 B' U L U' B' R'
(B L' U F2) //Nice start on inverse scramble
D' B' U B2 R2 //Nice continuation
(R B R' U R' U2 R B) //F2L
(U2 R' U2 R' D' L F2 L' D R2) //LL
Solution: D' B' U B2 D' L F2 L' D R U2 R U2 B' R' U2 R U' R B' R' F2 U' L B' (25)
-->

最終解答にまとめるときには、**ノーマルスクランブルに対するムーブを上から順に進んで行き、そして逆スクランブルに対するムーブを逆向きに書いていきましょう。**たとえば、カッコ付きの記法で次のような解答ができたとしましょう。

`A B`  
(`C`)  
`D`  
(`E F`)  
(`G`)
{: .text-center}

すると、**最終解答は次のように書きます。**

`A B D G' F' E' C'`
{: .text-center}

<!--
When you have to write down the final solution, just go though all the moves done on the
normal scramble and then backwards through the moves on inverse scramble, inverting each of
them. For example, if you have written down the solution with the brackets notation
A B
(C)
D
(E F)
(G)
the final solution is
A B D G' F' E' C'
-->
### 3.3 Reverse NISS {#ch3-3}
これは広く知られたテクニックではありませんが、役に立つ場合もあります。「[2.4.9節 Conjugateをして揃える(Conjugate and Solve)](chapter2#ch2-4-9)」や「[2.6.1節 戻ってやり直そう (Go Back and Change your Solve)](chapter2#ch2-6-1)」の両方を改善したものと考えてもいいでしょう。

少しだけ(4～8個)ピースを無視すればよいスケルトンになる手順を見つけたとしましょう。ここでインサートして揃えるのが普通ですが、このピースのステッカーの色に一つも共通のものがない（つまり全て違う層にある）ときは、インサートするアルゴリズムを見つけるのが非常に大変でしょう。

ここでの仕掛けはこうです：**（スケルトンを作る途中の）ソルブの中で全ての未処理ピースが単一の層で共役(conjugate)になる点を見つけて、このソルブを「分割」してしまうのです。分割した前半のムーブは全てプリムーブとして考えます。**これがReverse NISSと呼ばれる所以です。さて、このとき「Last Layer」だけが残った状態になります。必要なら何手かのセットアップをはさんでもいいでしょう。

では実例を見てみましょう！ [^3-3]

{% capture display_text %}
プリムーブ: R2
F2 U R' U' F D2 * F' U2 //2x2x3
R D R' D2 B2 //F2L (5ピース以外全部)
R2 //プリムーブを戻す
* = (F R) F D F2 R F R2 D R D2 (R' F') //5ピース
{% endcapture %}
{% include solvebox.html
title = "Reverse NISS Example"
scramble = "L2 D2 F2 U' L2 D L2 D2 B2 U' F' U' R' D B2 L D B' F' R'"
text = display_text
solution = "F2 U R' U' F D2 F R F D F2 R F R2 D R D2 R' F2 U2 R D R' D2 B2 R2 (26)"
img_src="../../../assets/img/alg-330.png"
algcubing = "https://alg.cubing.net/?setup=R2_L2_D2_F2_U-_L2_D_L2_D2_B2_U-_F-_U-_R-_D_B2_L_D_B-_F-_R-&alg=%2F%2FPremove_added_to_the_scramble%0AF2_U_R-_U-_F_D2_((F_R)_F_D_F2_R_F_R2_D_R_D2_(R-_F-))_F-_U2_%2F%2F2x2x3%0AR_D_R-_D2_B2_%2F%2FF2L_(All_but_5_pieces)"
%}

インサーションの中にある`F R`というムーブで全ての未処理のピースを単一の層で共役可能にしています。これを加えると、スケルトンは

`F2 U R' U' F D2` `F R`{: .codestrong} `*` `R' F'`{: .codestrong} `F' U2 R D R' D2 B2 R2`
{: .text-center}

となります。ここで`*`のポイントでソルブを「分割」してみましょう。

すると、**`R' F' F' U2 R D R' D2 B2 R2`がノーマルスクランブルに対するプリムーブとなります。**まとめると次のようになります。

プリムーブ：`R' F2 U2 R D R' D2 B2 R2`  
F2L: `F2 U R' U' F D2 F R`  
LL: `F D F2 R F R2 D R D2`

<!--
3.3 Reverse NISS
It is not a widely used technique, but it can occasionally be useful: it can be considered an
improvement over both “Conjugate and Solve” and “Go Back and Change your Solve”.
Suppose you have found a good skeleton solving everything but a few pieces (from 4 to 8).
You would like to insert an algorithm to solve them, but if these pieces don’t have at least
one color in common (they don’t belong to the same layer) it can be hard to recognize which
algorithm to use. The trick is this: if you find a spot in the solve where all your unsolved pieces
are conjugated to one layer, you can “split” the solve there, using all the following moves as
premoves (that is why I called it “Reverse NISS”); at this point, you have only a “Last Layer”
left to solve. If needed, you can use some setup moves.
Let’s take this solve as an example6
.
Reverse NISS - Example
Scramble: L2 D2 F2 U' L2 D L2 D2 B2 U' F' U' R' D B2 L D B' F' R'
Premove: R2
F2 U R' U' F D2 * F' U2 //2x2x3
R D R' D2 B2 //F2L (All but 5 pieces)
R2 //Undo premove
* = (F R) F D F2 R F R2 D R D2 (R' F') //5 pieces
Solution: F2 U R' U' F D2 F R F D F2 R F R2 D R D2 R' F2 U2 R D R' D2 B2 R2 (26)
See on alg.cubing.net
6Actually, in this solve, the algorithm was easy to recognize simply by marking the pieces with arrows and Xs,
so I didn’t use this technique, but this solution is a good example anyway.
42 CHAPTER 3. ADVANCED TOOLS
The moves F R in the insertion conjugate all the unsolved pieces to the same layer. If you
add them the skeleton becomes
F2 U R' U' F D2 F R * R' F' F' U2 R D R' D2 B2 R2
and we can “split” it at *: use R' F' F' U2 R D R' D2 B2 R2 as premoves for the normal
scramble and you have:
Premoves: R' F' F' U2 R D R' D2 B2 R2
F2L: F2 U R' U' F D2 F R
LL: F D F2 R F R2 D R D2
-->
### 3.4 EO中のNISS利用 (Using NISS during EO)
よいEOが見つけられないとき、NISSが役立つときがあります。ノーマルスクランブルで1手か2手だけ動かすことで、悪いエッジ (Bad edge)の個数を減らすことができることがあるでしょう。残った悪いエッジがノーマルスクランブルで悪い位置にあったとして、逆スクランブルにスイッチしてもっといい位置に移動しないか試してみることができます。もちろん、逆スクランブルからスタートして、途中でノーマルスクランブルにスイッチしてからEOを終わらせる順番でもよいです。

次のスクランブルを見てみましょう。

スクランブル：R' U' F L F L B2 L2 U2 B2 L B2 R B2 L2 U F' D U' F2 R' B R' U' F
{: .text-center}
![](../../../assets/img/alg-340n.png){:width="300px" height="auto" class="img-responsive align-center"}

たとえば、F/B軸でのよいEOを探しているとしましょう。しかし、6手かかるムーブ(たとえば`F B L' U D' F`)より良いものが見つけられません。逆スクランブルでもそれほど状況は変わらず、6手かかります。(たとえば`F B L' U D' F`)

しかし、ここでノーマルスクランブルに戻って、EO手順の最初の2手(`F B`のこと)をやったところで立ち止まってみましょう。この時点でF/B軸に対する悪いエッジは4つ(UR, RF, DL, DR)しかありません。しかし、最良の場所ではありません。ここでEOを逆スクランブルにスイッチすることで簡単になるでしょうか？やってみましょう！

プリムーブ：`F' B'`  
逆スクランブル：F' U R B' R F2 U D' F U' L2 B2 R' B2 L' B2 U2 L2 B2 L' F' L' F' U R  
{: .text-center}
![](../../../assets/img/alg-340i.png){:width="300px" height="auto" class="img-responsive align-center"}

すると、たった3手のムーブ(`U' L F`)でEOを解消できます。すなわち、5手のEO処理が見つかったということです。上述した表記を使えば、 `F B (U' L F)`と書くことができます。

数手ごとに簡単なEOがないかをチェックするためにスクランブルをスイッチするのは時間がかかります。しかし、練習すれば何度もやらなくてもよくなります。上のスクランブルに戻って、`F B`のムーブをしたときに何が起きているかをよく見てみましょう。ここで探しているのは、スイッチした後に4つの悪いエッジがよい場所に移動しているという状況です。しかし、3.1節で説明したように、**逆スクランブルを使ったときにエッジがノーマルスクランブルのどこに移動するかを知る手段があります。**どのエッジの向きが揃っていないかを確認することができます。

たとえば、上記のケースでの(逆スクランブルでの)悪いエッジはDF, UL, UB, RF[^3-4-1]にあります。つまり、スイッチしたあとでは、悪いエッジはそれぞれDF, UL, UB, RFに配置されます。ノーマルスクランブルで続けた場合のものよりも簡単なEOになるかどうかを判断することは、最初は難しく感じるでしょう。しかし、練習を積むことで**3手でEOを揃える「パターン」がわかってきます。**

このテクニックを練習したいなら、F/B軸に対する5手EO手順が他にないか探してみましょう。この例では逆スクランブルから始めて、数手回してから、ノーマルスクランブルに戻ってきています。[^3-4-2]

### 3.5 役立つアルゴリズム (Useful Algorithms)
気付いたかもしれませんが、一つ前のソルブ例ではあまり知られていないであろうOLL手順(`R U R2 F R F2 U F (U2)`)を使いました。これは特に役立つアルゴリズムで、ピースの位置を変えずに向きだけを変えることができます。

一般的にLast Layerの最短アルゴリズム**(9～10手以下まで)**を覚えておくと役に立ちます。全手順のリスト（回転、左右対称、逆手順は法とする）を作りましたので、[こちら](https://github.com/sebastianotronto/fmctutorial/blob/master/misc/LL_algs_6-10.txt)を参照してください。

「決してLast Layerに影響を与えずにF2Lを完成させてはならない」ルール（役立ちます！）を破ろうとするなら、Last Layerを短い簡単なアルゴリズムで揃えられると嬉しいでしょう。こういうケースではたくさん知っているほど嬉しいことがあります！

ちょっとしたコツも共有しましょう。**Last Layerのアルゴリズムを使うときには、AUF (U面合わせ、Adjust Upper Face)をその前後で試してみましょう。前後でキャンセルするかもしれません。**

少なくとも6手～9手までのアルゴリズムを知っておくといい理由はこれだけではありません。さらに2つあります。1つ目は、Last Layerの正確なアルゴリズムを知らない場合やF2Lがまだ終わっていない場合であっても、**アルゴリズムを使うことでよいスケルトン(3コーナーなど)になることがあるからです。**数手キャンセルがあるかもしれません。

2つ目は、アルゴリズムを学ぶことで、ブロックの作り方、F2Lの揃え方、スケルトンの作り方など、違うやり方を知ることができるからです。たとえば、T permの最適手順を見てみましょう。

`R2 Uw R2 Uw' R2 y L2 Uw' L2 Uw L2 (U')`
{: .text-center}

これはF2Lアルゴリズム(`R2 Uw R2 Uw' R2`)を2回繰り返しているだけです。

**単にアルゴリズムを学ぶだけでなく、アルゴリズムから学ぶこともできるのです。**

<!--
3.5 Useful Algorithms
As you can see, in the last example solve I have used an OLL that is maybe not well known: R
U R2 F R F2 U F (U2) (modulo rotations). This one in particular is very useful, because it is
the shortest algorithm that affects the orientation but not the permutation of pieces.
It is in general useful to know some of the shortest last layer algorithms, up to 9 or 10
moves. You can find a complete list (modulo rotations, symmetries and inverses) here: https:
//github.com/sebastianotronto/fmctutorial/blob/master/misc/LL_algs_6-10.txt.
If you decide to break the “never build an F2L without influencing the last layer” rule
(sometimes it is worth trying!) you can hope the last layer can be solved with a single short
algorithm: in this case, the more you know, the better!
A little tip: when using a last layer algorithm, remember that you can try performing the
AUF (“Adjust Upper Face”) both before and after it, hoping to cancel some moves with the
ones before it of with premoves.
There are two other reasons why it is worth learning some algorithms, at least the ones from
6 to 9 moves. The first one is that even if you don’t know the exact algorithm for the last layer,
or if you haven’t completed the F2L, one of these algorithms may leave you with a good skeleton
(for example, a corner 3-cycle), hopefully cancelling some moves.
The second reason is that by studying algorithms you can learn different ways to match
blocks, complete the F2L or ake a skeleton. Let’s take a look at the optimal T perm:
R2 Uw R2 Uw' R2 y L2 Uw' L2 Uw L2 (U')
It is just a useful F2L algorithm repeated twice.
Besides just learning algorithms, you can also learn from the algorithms.
-->
### 3.6 ペア分析 (Pair Analysis)
これはとても曖昧なテクニックであり、直感に基づいています。これを使うことで、ソルブが有利に進むかどうかは実証されていません。では、ペア分析とはどんなものでしょう？「ペアを分析する」というのは、スクランブルの中にあるいくつかの要素を考慮に入れるということです。たとえば

- **既にできているペアはあるか** : これは言うまでもありません。
- **1手で揃うペアはあるか** : これを見つけるには、前に書いたように、「総当たりテクニック」を使うこともできますし、一目見て判断できるように練習することもできます。さらに言えば、**疑似ペア(pseudo pair)の認識方法**を知っておくことも役に立つことがあるでしょう。ノーマルスクランブルや逆スクランブルでペアを作る手順が見つかれば、最初の1手として使うほか、その逆向きのスクランブルに対するプリムーブとしても使えます。
- **悪いペアはあるか** : コーナーとエッジのペアのどちらかがねじれていて、正しくマッチしていないものがあります。直感的ですが、こういったペアは悪いペアなので、できるだけ早く壊すのがいいでしょう。

このテクニックについてはドキュメントがたくさんあるわけではありません。特に「悪いペア」についてはまるでありません。Guus Razoux SchultzがTwente Open 2012の第一試技についてよい分析をしたものが[speedsolving.comに投稿されています。](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62##post-721942)[^3-6]

<!--
3.6 Pair Analysis
This is a really obscure technique, based on intuition, not proven to actually give you some
advantage during the solve. What is it about? “Analyzing pairs” means taking into account
some things about the scramble, which are:
• Ready made pairs. There isn’t much to say.
• Pairs that can be made with only one move. To find them you can use the “brute
force” technique described earlier or try to recognize them at first sight. Moreover, it can
be useful knowing how to recognize pseudo pairs, that is pairs that can be solved with
only one move on inverse scramble. Moves that make a pair, both on normal and on inverse
scramble, can be taken as first move, or as a premove for the inverse of the scramble you
are considering.
• Bad Pairs: those corner/edge pairs that are wrongly matched, because one of the pieces
is misoriented. Intuitively, such pairs are bad and you want to break most of them as soon
as you can.

There isn’t much documentation about this technique, especially for bad pairs. Guus Razoux Schultz did a good analysis for the first scramble of Twente Open 2012 in this post9 on
speedsolving.com.
-->
### 3.7 歪んだセンターで揃える (Solving with Skew Centers) {#ch3-7}
コーナーファーストという考え方を踏まえると、このテクニックを自然に理解しやすくなるでしょう。しかし、それ以外の手法でも使うことができるテクニックです。

コーナーとエッジをインサートするやり方はすでに見ましたが、ここではインサートすることでセンターを揃えるやり方を見てみましょう。**ソルブ中にセンターを無視して揃わないままにしておき、偶数手のスライスムーブ[^3-7-1]で揃う状態にします。**すると、`M E M' E'`や`M E2 M' E2`などのアルゴリズムで揃えることができるようになります。[^3-7-2]

![](../../../assets/img/alg-370-1.png){:width="300px" height="auto" class="img-responsive align-center"}
歪んだセンター：`M E M' E'`で揃う状態
{: .text-center}

もちろんスライスムーブ（内層回転ムーブ）をしなければならないので、歪んだセンターを揃えるには8手必要になります。しかし、心配しないでください。この8手をキャンセルできるチャンスはとても沢山あります。**このインサートを使うと、平均で3～4手でセンターを揃えることができます。**

どうしてこんなことになるのでしょう？実は、この手順には複数の揃え方があるのです。

`M E M' E'` = `S M' S' M` = `E' S' E S`
{: .text-center}

`M E2 M' E2` = `M' E2 M E2` = `M S2 M' S2` = `M' S2 M S2`
{: .text-center}

さらに2つ目は、逆手順にしても同じように揃います！

1つ目のケースを見てみましょう。センターを正しい位置に動かすためのスライスムーブをするときに、少なくとも4手はキャンセルすることになります。しかしそれだけではなく、もっと多くキャンセルする場合もありますので後で書く例を見てみましょう。

この手法の弱点は**書き直すのに時間がかかる**ということです。センターを動かすとき、ほかのピースにも同様に影響するように修正して書く必要があります。結果として、慣れていないと非常に時間がかかります。

では、私が世界大会2017で最後にやったソルブを例として見てみます。NISSとコーナーインサートも使っています。ここでは**センターを無視すれば2x2x2ブロックがすでに出来ているという状態です！**

<!--
3.6 Solving with Skew Centers
This technique is understood more naturally in the context of corners first solving, but can be
used with any method.
We have seen insertion for corners and edges, but we can also solve centers using insertions:
if you ignore centers during the solve and leave them unsolved, as long as they are off by an
even number of slice moves9
, you can solve them with algorithms such as M E M' E' or M E2
M' E210
.
Of course, since the moves required are all slices (or “inner layer” moves), the number of
moves required to solve the skew centers is 8. But don’t worry: there are many, many chances
to cancel moves. I estimate that, with insertions, you only need 3 moves on average to solve
centers. How is this possible? Notice that there is more than one way to solve them:
M E M' E' = S M S' M' = E S' E' S
and
M E2 M' E2 = M' E2 M E2 = M S2 M' S2 = M' S2 M S2
and in this second case, all inverse sequences solve the same case!
Sticking to the first case, as soon as you have a slice move in your (partial) solution, you
know you can cancel at least 4 moves: each of te 6 slice moves appears at the beginning or at
the end of one of the algorithms above.
The downside of this method is that it takes a lot of rewriting: when you move centers
around, the moves you have written need to be changed to affect in the same way the other
pieces. As a result, it can be really time consuming if you aren’t confident with it.
As an example, take my last solve from World Championship 2017 (which features also NISS
and a corner insertion). Notice that, ignoring centers, a 2x2x2 block is already solved!
-->
{% capture display_text %}
(U2 L2 B2 U) //3ペア (4/4)
R2 D2 R2 //ブロック (3/7)
(L B') //2x2x3 + square (2/9)
(L2 U2 L' U2 L' U2 L) //3コーナー以外完成 (7/16)
逆スクランブルでのスケルトン: U2 L2 B2 U L + B' L2 * U2 L' U2 L' U2 L B2 L2 B2
* = F' D F U2 F' D' F U2 //3c (6/22)
+ = M' S' M S //センター (4/26)
{% endcapture %}
{% include solvebox.html
title = "Skew Centers - Example"
scramble = "R' U' F U R2 B2 D' L2 F2 D U' F2 R' B D' F' U' L R D F2 U F' R' U' F"
text = display_text
solution = "R2 D2 R2 D' B2 D B2 D L' F L B2 L' F' L D2 L B' F D U' R' U' B2 L2 U2 (26)"
img_src="../../../assets/img/alg-370-2.png"
%}

解答を作るにあたって、最初は`S' M S M'`などの等価な手順を使ってセンターを揃えていました。そしてノーマルスクランブルでの解答を考えるにあたって、コーナーインサートを含む手順に至ったのです。この時点から解答を完成させるまでは、キューブに触れる必要もありません。

上記のインサートを含む解答を見つけた後で、**センターファーストを使っていないかのように、すべてのムーブを書き直さなければなりません。**これは簡単な変換です。`R`は`U`に、`D`は`F`に、という風に変換していくだけです。

次に3つあるコミュテータのうちのどれかをインサートして、センターを揃えます。**センターピースは持ち替えやスライスムーブがなければ動くことはないので、センターを揃えるコミュテータはどの時点も使うことができます。**このことさえ知っていれば、実際にキューブを回してみる必要はありません。単に、3つのコミュテータの1つを選んで、最もキャンセルが起こる場所を探せばいいだけです。

最後に、スライスムーブをインサートしてセンターを揃えたら、二回目の（そして最後の）書き直しをします。インサートしたところより前のムーブは変わりませんが、後のムーブは一回目と同じように変換しなければなりません。部分的解答を書くのに慣れていれば、最初のバージョンから最後のムーブだけをコピーすればよいですが、ここでは私はそうせず、解答用紙にとても乱雑に書くのでした。

コツをもう一つだけ。時間がないなら、センターをインサートした後にキューブの持ち替え記号を書いてしまい、書き直しの時間を節約してもいいでしょう。しかし、キャンセルを見逃さないようにしてください。スライスムーブでのキャンセル探しは通常よりもやりにくいですよ！

<!--
Skew Centers - Example
Scramble: R' U' F U R2 B2 D' L2 F2 D U' F2 R' B D' F' U' L R D F2 U F' R' U' F
(U2 L2 B2 U) //3 pairs (4/4)
R2 D2 R2 //blocks (3/7)
(L B') //2x2x3 + square (2/9)
(L2 U2 L' U2 L' U2 L) //All but 3 corners (7/16)
Skeleton: U2 L2 B2 U L + B' L2 * U2 L' U2 L' U2 L B2 L2 B2
* = F' D F U2 F' D' F U2 //3c (6/22)
+ = M' E M E' //Centers (4/26)
Solution: R2 D2 R2 D' B2 D B2 D L' F L B2 L' F' L D2 L B' F D U' R' U' B2 L2 U2 (26)
To find this solution, at first I did S' M S M', or one of the equivalent sequences, at the
beginning of the solve. Then I went on with finding a solution as I would do in a normal solve.
From this point on the final solution can be derived without touching the cube anymore.
7
https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-61#post-721325
8
https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62#post-721942
9This condition is required to avoid parity.
10These are actually commutators: M E M' E' = [M, E] and M E2 M' E2 = [M, E2].
44 CHAPTER 3. ADVANCED TOOLS
After I found the solution (including the insertion), I had to rewrite all the moves as if I
had done them without solving the centers first. This is a simple translation: R became U, D
became F and so on.
Then I had to insert one of the three commutators to solve centers. Since centers don’t
move around in a sequence of moves without rotation or slices, the commutators that solved
centers remained the same at every point. Knowing this, performing the moves on the cube is
unnecessary: you just need to find a spot where one of the three commutators cancels the most.
Finally, after inserting the slice moves that solve centers, there is the second (and last)
rewriting: the moves before the insertion remain unchanged, but the moves after that have to
be canged with same method used the first time. If you are disciplined in writing down your
partial solutions, you can get the first version of your solution and copy the last moves, but this
is not my case, as I write stuff down on my sheets in a very chaotic way.
-->
#### 3.7.1 歪んだセンターとNISS (Skew centers and NISS)
一つ前のソルブ例ではNISSを使いましたが、逆スクランブルに対するスケルトンの最後の3手は`R2 D2 R2`ではなく、`B2 L2 B2`になっています。これはノーマルスクランブルで解いたときの最初の3手と同じです！

するとどんな問題が起こるでしょうか？　それは、後でやろうと思っていたインサートによってセンターが動いてしまい、その後に続くムーブがすべて変わってしまうということです！逆スクランブルに対するスケルトンの最初の13手(`U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L`)をやってみましょう。そして次に、M S' M' Sでセンターを揃え、U面が白、F面が緑の向きに持ち替えましょう。単に`R L' U D' B F' R L'`とやってもよいです。ここからは「正しい」プリムーブの`R2 D2 R2`を使って、3コーナーのスケルトンにすることができます。

この問題はどうやって解決しましょう？　このケースでは、ノーマルスクランブルではたった3手しか回していないため、適応すべき正しいムーブがどれなのかを簡単に知ることができます。しかし一般的にはやりにくいものです。やり方は大きく2つあります。
1つ目は、**ノーマルスクランブルでのムーブから逆スクランブルでのムーブを知るための「変換表」**を用意することです。このケースでは次のような表ができます。

|                   |   |   |   |   |   |   |
|-------------------|---|---|---|---|---|---|
|ノーマルスクランブル：|B|F|L|R|U|D|
|逆スクランブル：|U|D|F|B|R|L|

なので、ノーマルスクランブルでの`R2 D2 R2`は、逆スクランブルでは`B2 L2 B2`になります！この手法は4つのセンターだけが残されているときには特に役立ちます。そういうときに、この表を毎回書かかなくてもいいようにしっかり覚えておきましょう。

2つ目の方法は、**持ち替えを使い、センターを無視した状態で揃ったピースを本来の位置に戻すことです。**たとえば、（逆スクランブルでの）スケルトンは次のようになります。

逆スクランブルでやったムーブ: `U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L`
持ち替えして修正する: `x z'`
ノーマルスクランブルでやったムーブ: `R2 D2 R2`
逆スクランブルでのスケルトン: `U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L` `x z'` `R2 D2 R2`

**くれぐれも持ち替え記号には注意してください！** [^3-7-1-1]

<!--
3.7.1 Skew centers and NISS
In the previous example solve I used NISS. However, the last three moves of the skeleton on
inverse are B2 L2 B2 instead of R2 D2 R2, which are the first three moves done on normal!
What is happening here? The problem is that one of the insertions that have been left for
later moves the centers around, changing all subsequent moves! Apply the inverse scramble and
then the first 13 moves of the skeleton (U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L). Now solve
the centers with M S' M' S and rotate back to have white on top and green on front (or just
apply the moves R L' U D' B F' R L'). From here you can apply the “correct” premoves R2 D2
R2 to get the 3c skeleton.
How to solve this problem? In this case it can be easy to see what the correct moves to
apply are, since there are only 3 moves done on the normal scramble. But in general it may be
tricky. There are basically two ways.
The first one is to use a “translation table” that tells you which moves you have to apply
on inverse depending on which moves you have done on normal. In this case it will look like:
Normal: B F L R U D
Inverse: U D F B R L
So the R2 D2 R2 on normal become B2 L2 B2 on inverse! This method works better when there
are only 4 centers left to fix (like M E2 M' E2): in that situation, the table can easily be kept in
mind without writing it down.
Another way consists in using rotations to bring the solved pieces to their usual position,
disregarding centers. For example, our skeleton (on inverse) would be:
Moves done on inverse: U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L
Fix: x z'
Moves done on normal: R2 D2 R2
Complete skeleton (on inverse): U2 L2 B2 U L B' L2 U2 L' U2 L' U2 L x z' R2 D2 R2
But be careful with rotations!12
3
-->

### 3.8 高度なエッジインサーション：フリースライス (Advanced edge insertions: free slices) {#freeslice}
エッジだけが残ったスケルトンを揃えるには、通常エッジコミュテータをインサートするか、エッジのダブルスワップ(`M2 U2 M2 U2`など)をインサートするかです。エッジを揃えるにはさらに高度はテクニックがあり、`[M2, U R U']`などのエッジコミュテータを特殊ケースとして変換することができます。

考え方を説明しましょう。たとえば`M`というムーブを考えると、これはHTMでは2手になりますが、興味深い性質があります。センターを無視すれば、これはエッジの4点交換をしていることになります。(UF→FD→DB→BU→UF) 同じように、`M2` はエッジの2点交換を繰り返しています。(UF↔DB、UB↔DF)

**このように単純なスライスムーブ(`M`や`M2`)をインサートすることで、エッジ交換を非常に効率的に揃えることができます！**

必要に応じてセットアップしてもよいでしょう。たとえば `[R F: M2]` = `R F M2 F' R'`は`M2`のような2点交換の繰り返しになります。この手法を**フリースライス(Free Slices)**と呼びたいですが、**スライスインサーション(slice insertions)**や**slicey shenanigans**という呼び方が一般的です。

**訳注**  
**slicey shenanigans**は直訳すれば「いたずらスライス」とか「ごまかしスライス」などと訳すことができます。ここではそのまま使います。
{: .notice--info}

しかし、センターはどうするのでしょう？これは大きな問題ではありません。スライスインサーションを使って、センターが揃うようなキャンセルが起こるかどうか注意してみたり、最後まで残しておいてから`[M, E]`などの手順を追加でインサートしてセンターを揃えたりしてもいいでしょう。追加のインサートをする場合、気をつけなければならないのは**パリティが起こらないようにすること**です。スライスムーブを使ったインサートの数が偶数になるようにしましょう。(`M2`は2回とカウントします) 偶数でない場合、エッジは揃えられません。

ラッキーな実例を見てみましょう。

<!--
3.8 Advanced edge insertions: free slices
If you have a skeleton that only leaves some edges unsolved, the standard way to conclude with
insertions is to insert edge commutators or maybe double swaps of edges, like M2 U2 M2 U2.
There is also a more advanced technique to solve edges, of which some edge commutators
like [M2, U R U'] can be interpreted as a special case.

The main idea is the following: consider the move M. It counts only as 2 moves in HTM, but its
effect is interesting. Ignoring centers, it completes a 4-cycle of edges: UF→FD→DB→BU→UF.
Similarly, the move M2 is a double 2-cycle of edges: UF↔DB and UB↔DF. Thus by inserting
simple slice moves like M and M2 in the skeleton one can very efficiently solve any type of edgecycle(s)! In case it is necessary, one can use setup moves; for example [R F: M2] = R F M2 F' R' is a double 2-cycle, just like M2.
I like to call this method free slices, but it has other popular names like slice insertions or
slicey shenanigans.

But what about centers? They are not a big problem: one can either pay attention that
the slice insertions “cancel each other” so that centers end up solved as well, or forget about
them and solve them with an extra center insertion like [M,E] later. If you go for this second
approach, the only thing to care about is avoiding parity: make sure that the total number of
slice moves inserted is even (where M2 counts as 2). But if this is not the case then edges cannot
result solved.
Let’s start with a (lucky) example:
-->
{% capture display_text %}
(B D' R F) //EO + 3ペア (4/4)
D2 R U' //2スクエア (3/7)
(R2 B2 R) //3c7e (3/10)
スケルトン: D2 R U' R' B2 R2 [1] F' R' D B' [2]
[1] と [2] にM2をインサートして 3e3c の12手スケルトンを作る
新しいスケルトン: D2 R U' R' B2 L2 B' R' U F' * R2 L2
* = U + R U' R2 L2 D R' D' R2 L2 (6)
+ = U2 R' D' R U2 R' D R (6)
{% endcapture %}
{% include solvebox.html
title = "世界大会2019の第2試技"
scramble = "R' U' F U2 R2 D' F2 D' L2 U' F2 L F' D' R' U' R2 F L2 B F R2 B2 R' U' F"
text = display_text
solution = "D2 R U' R' B2 L2 B' R' U F' U' R' D' R U2 R' D R2 U' R2 L2 D R' D' (24)"
img_src="../../../assets/img/alg-380-1.png"
algcubing="https://alg.cubing.net/?setup=R-_U-_F_U2_R2_D-_F2_D-_L2_U-_F2_L_F-_D-_R-_U-_R2_F_L2_B_F_R2_B2_R-_U-_F&alg=D2_R_U-_R-_B2_L2_B-_R-_U_F-_U-_R-_D-_R_U2_R-_D_R2_U-_R2_L2_D_R-_D-"
%}
<!--
World Championship 2019 - Scramble 2
Scr: R' U' F U2 R2 D' F2 D' L2 U' F2 L F' D' R' U' R2 F L2 B F R2 B2 R' U' F
(B D' R F) //EO + 3 pairs (4/4)
D2 R U' //2 squares (3/7)
(R2 B2 R) //3c7e (3/10)
Skeleton: D2 R U' R' B2 R2 [1] F' R' D B' [2]
Insert M2 both at [1] and at [2] to leave 3e3c in 12
New skeleton: D2 R U' R' B2 L2 B' R' U F' * R2 L2
* = U + R U' R2 L2 D R' D' R2 L2 (6)
+ = U2 R' D' R U2 R' D R (6)
Sol: D2 R U' R' B2 L2 B' R' U F' U' R' D' R U2 R' D R2 U' R2 L2 D R' D' (24)
See on alg.cubing.net
-->

[1]と書いた1つ目のインサートでは、3エッジを揃えて2手キャンセルしています。これは非常にラッキーなケースです。[2]と書いた2つ目のインサートはもっと標準的なもので、エッジを追加で1つだけ揃えて、3点交換を残し、1つ目のインサートで動いたセンターをもとに戻しています。

最後の2つのインサートは通常のコミュテータです。しかし、注目すべきは、＊と書いたエッジコミュテータは`[U R U', M2]`であり、`M2`直前にインサートされ、最後のスライスムーブをキャンセルしています。[2]の箇所に`[U R U', M2]` = `U R U' M2 U R' U'` をインサートしてもまったく同じ回答になります。単にセットアップしてからスライスムーブをしているだけです。多くのエッジコミュテータは2つのスライスインサーションの組み合わせでできています。セットアップなしのシンプルなものと、セットアップのあるものです。

では、次の例を見てみましょう。

<!--
Here the first insertion (the one marked by [1]) solves 3 edges and cancels 2 moves. This is
a very lucky case. The second insertion (marked with [2]) is more standard: it solves only one
more edge, leaving a 3-cycle, and solves back the centers that were set off by the first insertion.
The last two insertions are standard commutators, but there is one thing certainly worth
noticing: the edge commutator (insertion marked with *) is [U R U', M2], and it is inserted
right before an M2 move, leading to a cancellation of the last slice move. In fact, one could have
found the same exact solution by inserting [U R U': M2] = U R U' M2 U R' U' at [2], which
is just a setup + slice! Many edge commutators can be seen a combination of 2 slice insertions
– one simple (without setup moves) and one with setup moves.
Let’s take another example:
-->
{% capture display_text %}
スケルトン: U' B' U B' * L2 B2 R2 + F2 R D' R L' F D2 (5e)
* = E'
+ = [R' B' D' B: E]
{% endcapture %}
{% include solvebox.html
title = "Another free slices example"
scramble = "R' U' F U R2 D R2 B2 D' B2 L' D2 L2 R D U L2 F' U2 B L' B R' U' F"
text = display_text
solution = "U' B' U B' D U' F2 L2 B L' D' L D' U B' D B R F2 R D' L' R F D2 (25)"
img_src="../../../assets/img/alg-380-2.png"
algcubing="https://alg.cubing.net/?alg=U-_B-_U_B-_E-_L2_B2_R2_%5BR-_B-_D-_B:_E%5D_F2_R_D-_R_L-_F_D2&setup=R-_U-_F_U_R2_D_R2_B2_D-_B2_L-_D2_L2_R_D_U_L2_F-_U2_B_L-_B_R-_U-_F"
%}
<!--
Another free slices example
Scramble: R' U' F U R2 D R2 B2 D' B2 L' D2 L2 R D U L2 F' U2 B L' B R' U' F
Skeleton: U' B' U B' * L2 B2 R2 + F2 R D' R L' F D2 (5e)
* = E'
+ = [R' B' D' B: E]
Sol: U' B' U B' D U' F2 L2 B L' D' L D' U B' D B R F2 R D' L' R F D2 (25)
See on alg.cubing.net
-->
ここでは、5つのエッジが残ったスケルトンのうち、1つ目のインサートで2つのエッジを揃えて1つのエッジを崩しました。要するに4点交換をして、4つのエッジが残るようになります。2つ目のインサートはセットアップしてから4点交換をしています。

スケルトンの中のどこにスライスムーブにインサートするとよいかを判断するのは、いつも簡単とは限りません。私の場合、多くは試行錯誤しながらやりますが、覚えておくべきコツもあります。
- **あまり大きな成果がないように見えるスライスムーブでも、多くの手数がかからないのであれば役立つことがあります。**たとえば、`R2 L`というムーブの前後に`M2`をインサートすることで、1手削減することができます。こういったスライスムーブでエッジが揃う（ラッキー！）こともあり得ますし、少なくとも揃っていないエッジの数が変わらないということもあります。  
多くの場合、私は最初にこういったアプローチを念頭に入れた上でスケルトンを作り始めて、非常に短い数手を使ってもっと単純化できないかを狙うようにしています。そうした上で、3点交換やダブルスワップなどが残ったときに長めのインサートをしてソルブを終わらせます。
- **スライスインサーションで何個のエッジが揃うのかを把握することは簡単です。**正しい場所に移動するものがいくつあるかを数えて、逆に崩れるエッジの数を数えればよいのです。こういったエッジの正確な交換タイプを推測することは可能ですが、パリティによって難しいものもあります。  
たとえば、上に示した1つ目のソルブを見てみましょう。合わせて7つの揃っていないエッジがあり、1つ目のインサート([1]の箇所にある`M2`)で3つのエッジを揃えています。既に揃ったエッジは崩れません。このインサートの後には4つのエッジが揃っていない状態になります。しかし、`M2`はセンターのパリティを生みませんから、ここから先の可能性は1つだけです。この残った4つのエッジは2点交換を2回繰り返す（ダブルスワップ）ことで揃えられます。
- **場所はあっているけれどねじれたエッジや、`UF→UR→FU`などの「ねじれた交換」を避けるようにしましょう。**もしスケルトンの中にあるなら、最初のスライスムーブで取り除けないか試してみましょう。
- **最初にEOを処理をしたスケルトン（あるいはDomino Reduction。付録D参照）では、よいエッジのインサートが見つかることが多いです。**これは普通のアルゴリズム（コミュテータ、ダブルスワップ）でも、フリースライスでも同じことです。

<!--
Here the first insertion solves 2 of the 5 edges and unsolves a solved one, leading to 4 edges
unsolved in a 4-cycle. The second insertion is a setup to a 4-cycle.

It is not always easy to understand what is a good place to insert a slice move in a skeleton.
I mostly go with trial-and-error, but there are some tricks to keep in mind:
• Sometimes it is useful to insert slice moves that don’t seem to accomplish much, but also
don’t add many moves, for example because there is no setup move, or there are even
cancellations. But there is even more: by inserting, for example, an M2 move next to a
squence like R2 L one can even save one move. It can then happen that such a slice move
solves some edges (what luck!) or at least doesn’t change the number of unsolved edges.
In general, I tend to first go through the skeleton with this approach in mind and hopefully
simplify the situation using very few moves. Then, when there is only a 3-cycle or a double
swap left, I tend to use longer insertions to finish up the solve.
• It easy to find out how many edges are going to be solved after a slice insertion by counting
how many more end up in the correct spot (and how many solved edges become unsolved,
if any). Then it often possible to deduce the exact type of cycle they form, excluding some
cases by parity reasons.
For example, consider the first solve above. There are 7 unsolved edges in total, and the
first insertion (the M2 labelled with [1]) solves exactly 3 of them. No solved edge is taken
out of place. It follows that after that insertion exactly 4 edges are left unsolved. But
then, since M2 does not create center-parity, there is only one possibility: those 4 edges
must form a 2-2 cycle (double swap).
• Avoid edges flipped in place and “twisted cycles” like UF→UR→FU. If your skeleton has
some, try to get rid of them with your first slices.
• Skeletons with EO – or even Domino Reduction, see Appendix D – solved at the beginning
tend to give much nicer edge insertions, both with standard algorithms (commutators,
double swaps) and with free slices!
-->

### 3.9 コーナーファースト (Corner First) {#corner-first}
**「コーナーファースト」は厳密に言えば解法ではなく、むしろ解法のクラスと言ったほうがいいものでしょう。**CFと略されることもあります。たとえば、RouxはCF解法と見なすことができます。

ルービックキューブの揃え方を自分自身で見つけた人たちの中では、コーナーファーストのアプローチを取った人が多数派でしょう[^3-9-0]。直感的にキューブを揃えるようとするなら、コーナーとエッジを別々に考えるのは実に理にかなっていて、簡単です。さらに、コーナーを先に揃えてしまえば、エッジをもっと自由に動かして揃えることができるようになります。つまり、内側の層はコーナーに影響することなく動かすことができるのです。

ところが、これはFMCにおいては不利にもなる性質です。内側の層を回転させると2手としてカウントされてしまいます！こういう状況であるにも関わらず、少なくとも2名のFMCエキスパートはコーナーファーストのテクニックを使っています。[Attila Horváth](https://www.worldcubeassociation.org/persons/2012HORV01)と[Javier Cabezuelo Sánchez](https://www.worldcubeassociation.org/persons/2007SANC01)(FMCのスペイン記録保持者)です。この2名が共通して同意するのは、コーナーファーストはFMC向きの素晴らしい解法であると同時に、1時間という制限時間がある状況にはあまり向いていない、ということです。実際、Javierの公式記録のほとんどはDNFです。

Attila Horváthは、ほとんどの場合Guimond(向きを最初に揃える)に近い解法でコーナーを揃えています。このステップではセンターは気にしません。時々プリムーブやNISSを使うこともあります。それから、自分自信の見つけた解答を少しずつ修正していき、内層のムーブをインサートして、少なくとも2-3個のエッジは揃えてしまいます。最後に残ったエッジを揃えますが、特に決まった順番はありません。Attilaは最後までセンターを揃えないままでいることもあり、[3.7節](#ch3-7)で見たようにインサートしてセンターを揃えます。彼の解法をもっと知るには、speedsolving.comのフォーラムで彼の投稿[^3-9-1]を読んで直接聞いてみるのがいいと思います。喜んでテクニックを教えてくれるでしょう。

Attliaのソルブにコメントを付けたものがあります。

{% capture display_text %}
まずは短い手順でコーナーを揃えます。スクランブルが難しそうなら、いつもはプリムーブなどを使います。
このケースでは、ノーマルスクランブルに対して D B というプリムーブを見つけました。

コーナーの解法はこうなります。
B2 D' B' D2 B (Guimondの1ステップ目：コーナーの向きを揃える)
B2 D' R2 F2 (全てのコーナーを揃える)

プリムーブなしのコーナー解法はこうです。
B2 D' B' D2 B' D' R2 F2 D B

逆スクランブルでのコーナー解法はこうです。(1つ前のものの逆手順)
B' D' F2 R2 D B D2 B D B2

このバリエーションとして、より多くのエッジを揃えてみます。
B2 M b d' M' F2 R2 d2 D' b d2 B (コーナーまで2手、5エッジ揃う)

ここでセンタームーブを除いて、このように書きます。
B2 L' R U R' D' U L2 D2 F2 B' R U2 R

2手目のMは最初の4エッジに影響しませんが、最後にラッキーを引くために入れています。

次のステップは明らかです。3つのエッジを揃えるだけです。
U D セットアップでL' F' U2 D2 B Rという3エッジのアルゴリズムを回して、Eスライスのスキップが置きます。あらかじめMをいれておいたおかげです。
{% endcapture %}
{% include solvebox.html
title = ""
scramble = "U L U' R' F' L' U D R L' B2 D B' D L2 D' R2 U F2 D"
text = display_text
solution = "B2 D R' B' D2 U2 F L D' U' R' U2 R' B F2 D2 L2 U' D R U' R' L B2 (24)"
img_src="../../../assets/img/alg-390.png"
algcubing=""
%}

このチュートリアルの初版から、Attliaは徐々に解法を変化させてきました。最初にコーナーの向きを揃えるのは変わりませんが、エッジに注意しながらコーナーを完全に揃えるのではなく、COファーストのドミノリダクションをやるようになっています。たとえば、[Speedsolving.comのこの投稿](https://www.speedsolving.com/forum/threads/the-3x3x3-example-solve-thread.14345/page-280#post-1234805)や AlexandrosとTommasoの書いたドミノリダクションのチュートリアルにある実例を見てみるといいでしょう。

Javierのコーナーの揃え方は少し違います。一段目のコーナーを先に揃えてから、残りの4つを揃えるというやり方です。そして、インサートをしてエッジを揃えようとします。彼は逆スクランブル、プリムーブ、NISSなどのテクニックは使いません。Attliaと異なるのは、コーナーを揃えている最中にもセンターに注目しているということです。[Speedsolving.comのこの投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-111#post-945295)も見るといいでしょう。

AttliaとJavierはCF解法しか使いません。「何の制限もするな」というFMCのセオリーには反していますが、実際素晴らしい記録を残しているのです。

<!--
3.9 Corners First
“Corners First” (sometimes shortened to CF) is not really a method, but more a class of methods.
With these methods, as the name says, one solves first the corners and then the edges. Roux
can be considered a CF method.
Among the ones who have figured out how to solve the cube on their own, many had a
corners first approach:13 Thinking separately about corners and edges makes it somehow easier
to solve the cube intuitively. Moreover, by solving corners first one can solve edges more freely:
inner layers can be moved without affecting corners.
But this is also a disadvantage in FMC: inner layer moves count as two moves! Despite
this, there at least two expert FMCers that use this technique: Attila Horv´ath and Javier
Cabezuelo S´anchez. Both agree that Corner First methods are excellent for FMC, but not
very suitable for the one hour time limit. In fact, many of Javier’s official results are DNF.
Attila Horv´ath mostly solves corners using a method similar to Guimond (orient first).
Centers are not cared about in this step. For this step he sometimes uses premoves or NISS.
After this, he goes through the solution he has found and modifies it slightly, inserting inner
layer moves, to get at least 2 or 3 edges solved. At the end he solves the edges left, in no specific
order. He sometimes doesn’t solve the centers until the end, and solves them with an insertion,
as discussed in Section 3.7. To learn more about his method, I suggest reading his posts or
asking him directly on the speedsolving.com forum14. He is usually very happy to teach others
about his techniques.
Here is a commented solve by Attila.
13For example, Valery Morozov, who has made a tutorial to learn his method, available here: https://www.
speedsolving.com/forum/threads/a-unique-phase-method-for-a-rubiks-cube.44264/.
14Here is his profile: https://www.speedsolving.com/forum/members/attila.10652/.
52 CHAPTER 3. ADVANCED TOOLS
Scramble: U L U' R' F' L' U D R L' B2 D B' D L2 D' R2 U F2 D
Solution: B2 D R' B' D2 U2 F L D' U' R' U2 R' B F2 D2 L2 U' D R U' R' L B2 (24)
Explanation:
First I need a short corners-solution, usually I try something with premoves, if the
scramble seems too hard. In this case I found this premoves for normal scramble: D B.
Corners solution:
B2 D' B' D2 B (Guimond first step: orient corners)
B2 D' R2 F2 (Solve all corners)
Corners solve, without premoves:
B2 D' B' D2 B' D' R2 F2 D B
Corners solve for inverse scramble: (inverse of previous solve)
B' D' F2 R2 D B D2 B D B2
A variation of the previous solve, to get more edges solved:
B2 M b d' M' F2 R2 d2 D' b d2 B corners -2 moves and 5 edges solve,
Then I write this, without centers move:
B2 L' R U R' D' U L2 D2 F2 B' R U2 R
The second move (M) does not change the first five edges position, but it must be inserted
to get the lucky ending.
The next step is obvious, solve more 3 edges: U D setup moves, L' F' U2 D2 B R 3 edges
algo, then a lucky E slice skip, due to the previous M move.
Since the first version of this tutorial, Attila has gradually changed his method. He still
orients corners first, but rather than solving them completely and then taking care of edges,
he performs a CO-first Domino Reduction. Se for example this post15, or the example solves
collected in Alexandros’ and Tommaso’s DR tutorial.
Javier solves corners in a different way: first layer corners first, then the other four. He then
tries to solve edges inserting moves (or algorithms) in the solution he has found. He doesn’t use
techniques such as inverse scramble, premoves or NISS. Differently from Attila, he cares about
centers while solving corners. See also this post16
.
Both Attila and Javier only use their CF method, which breaks the “never restrict yourself”
rule; but they still get excellent results.
15https://www.speedsolving.com/forum/threads/the-3x3x3-example-solve-thread.14345/page-280#
post-1234805
16https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-111#post-945295
-->

### 3.10 置換して短くする (Replace and shorten) {#replace-and-shorten}
よい解答を見つけて書いてみたところ、その中のどこか短い部分がかなり非効率的である場合もあるでしょう。ソルブを通常のステップで進めている間はなかなか気付きにくいものです。特にNISSやインサーションの組み合わせを使っていると、最終解答で隣り合っている回転記号は考える過程とはまったく別物になります。

このような非効率的な一部があるなら、等価でもっと短い配列に書き直すことができ、もっとよい解答ができます。ひとつのやり方は、解答をもう一度見直して非効率的な部分を探すことです。おそらく「F2L-1に至るステップ」や「ドミノを作るステップ」([2.5.2節](chapter2#2-5-2)や[付録D](appendix#appendix-d)を参照)に注目することでしょう。対象がドミノを作るステップでない限り、このテクニックは非常に練習がしづらいです。ドミノリダクションのステップなら、[付録D](appendix#appendix-d)の最後にある実例を見るといいでしょう。また、AlexとTommasoのドミノリダクションのチュートリアルを読むともっと詳しく書いてあります。

「怪しい」ところが見つかったら、その部分をスクランブルとして使うようにして、完成状態のキューブに対して適用してみましょう。そして、もっと短くならないかを検討します。もし短くできるなら、元々の配列を短いものに書き直すだけで、数手短くなります！元々の配列と同じ手数のものを見つけられたら、その前後のどこかでキャンセルしないかを試してみましょう。

F2L-1の部分で「置換して短くする」ことの実例を挙げます。

スクランブル: `R' U' F U2 L' D2 B2 L R F2 R2 D' R2 U' L' D' B2 D2 F' D2 R' U R' U' F`  
解答: `F R L U' B F2 D' F2 D F2 D2 F2 [D R' L D' R D L' D'] L' D L D L2 U`
{: .text-center}

カッコで囲まれた部分 `D R' L D' R D L' D'` をスクランブルのように使ってみましょう。すると、次のようになります。

![](../../../assets/img/alg-3-10-0.png){:width="300px" height="auto" class="img-responsive align-center"}

これを `B R' D R D' B'`と解くことができるので、回答は次のように短くなります！

新しい解答: `F R L U' B F2 D' F2 D F2 D2 F2 [B R' D R D' B'] L' D L D L2 U`
{: .text-center}

<!--
3.10 Replace and shorten
Sometimes it happens that you have a nice solution written down, but some short subsequence
of this solution is actually inefficient. This might be hard to notice during the normal steps of
the solve, especially when you have used a combination of NISS and insertions so that moves
that are next to each other in the final solution are actually far apart in your thought process.
These inefficient subsequences can be substituted with equivalent but shorter sequences,
giving a better solution. One way to do so is to go through your solve once more and look for
inefficient sequences. These may look like “F2L-1” solutions, “domino” steps (see Section 2.5.2
and Appendix D) or something else. This is not very easy in practice, unless the sequence you
are looking at is a domino step. For this case you can see an example at the end of Appendix
D (WR solve), or many more in the DR tutorial by Alex and Tommaso17
Once you have found a “suspicious” sequence, apply it18 to a solved cube as a scramble, and
try to find a shorter solution. If you do, you can replace the original sequence with the shorter
one, and save a few moves! If you find an alternative solution of the same length as the original
one, you can try and see if it cancels something with the moves around it.
Here is an example of “replace and shorten” applied to an F2L-1 sequence:
Scramble: R' U' F U2 L' D2 B2 L R F2 R2 D' R2 U' L' D' B2 D2 F' D2 R' U R' U' F
Solution: F R L U' B F2 D' F2 D F2 D2 F2 [D R' L D' R D L' D'] L' D L D L2 U
Now apply the bracketed sequence D R' L D' R D L' D' as a scramble:
And solve it with B R' D R D' B':
New solution: F R L U' B F2 D' F2 D F2 D2 F2 [B R' D R D' B'] L' D L D L2 U
17You can find a link link in Section 2.5.2, Appendix A or Appendix D.
18Or its inverse.
-->
<!-- 通常コンテンツここまで-->

[戻る：第2章](chapter2){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第4章](chapter4){: .btn .btn--inverse}

[^3-2-3-1]: [https://www.speedsolving.com/threads/the-fmc-thread.13599/page-52#post-667292](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-52#post-667292)
[^3-2-3-2]: 「スクランブル」を解答に対する解答としてみなすこともできます！
[^3-2-3-3]: Taken from here: [https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-10#post-258791](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-10#post-258791)
[^3-3]: じつはこのソルブでは、揃っていないピースに矢印やバツ印を書くことで簡単にアルゴリズムを認識できるようになるのです。なので、私はここではReverse NISSというテクニックを実際には使いませんでしたが、解答自体がよい実例になるので書きます。
[^3-4-1]: ノーマルスクランブルではそれぞれUR, RF, DL, DR にあたります。しかし、現時点では無視してよいです。
[^3-4-2]: 実はこのスクランブルは非常にレアな偶然が重なっています。F/B軸に対してノーマルスクランブルと逆スクランブルの両方で6手が最適手順であり、どちらから始めてNISSを使ったとしても5手が最適となっています。
[^3-6]: [https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62##post-721942](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62##post-721942)
[^3-7-1]: パリティを避けるためにこの条件が必要です。
[^3-7-2]: 実はコミュテータです。`M E M' E'` = `[M, E]`で、`M E2 M' E2` = `[M, E2]`
[^3-7-1-1]: 持ち替え記号なしの解答の書き方については、5.1節を参照。
[^3-9-0]: たとえば Valery Morozov という人物は自分の解法を解説するチュートリアルを作りました。詳しくは[https://www.
speedsolving.com/forum/threads/a-unique-phase-method-for-a-rubiks-cube.44264/](https://www.
speedsolving.com/forum/threads/a-unique-phase-method-for-a-rubiks-cube.44264/) を参照してください。
[^3-9-1]: 彼のプロフィールページです。[https://www.speedsolving.com/forum/members/attila.10652/](https://www.speedsolving.com/forum/members/attila.10652/)
