---
title: 第2章 ソルブの進め方 - 最少手数競技入門 by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 15:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/chapter2
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
[戻る：第1章](chapter1){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第3章](chapter3){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->
## ソルブの進め方

[Per Kristen Fredlund](https://www.worldcubeassociation.org/persons/2004FRED02)[^2-0]の言葉を引用すれば、一般的なソルブの進め方は次の通りです。
> もっと次のように考えるのです。キューブを二段階で解くのだ、と。
>
> 一段階目では、可能な限り多くのピースを、可能な限り効率的に解きましょう。（つまり、よいスケルトン[^2-0-1]を作りましょう）  
> 二段階目では、未完成のピースを正しく揃えましょう。多くの場合、スケルトンにインサートをするアルゴリズム[^2-0-2]を使います。[^2-0-3]
>

これは一般的なアプローチですが、常にこうする必要はありません。たとえば、F2LでブロックビルディングをしてLast Layerアルゴリズムをやるだけでスキップを引いて、とても短い解答が見つかることも時にはあるでしょう。これとは違うやり方もあり、そのうち二つは第四章で解説します。

この記述があまりにも一般的すぎるように見えても、これ以外に書きようがないのです。FMCで常によい記録を出せるような標準的な解法はありません。チャンスを逃さないためには、**いつでも可能な限り多くの戦略を試してみるしかありません。**

ここではFMCで用いられる基本的なテクニックをいくつか記載します。前の章で書かれた解法を練習しているなら、すでにいくつかは学んだことがあるでしょう。この章を読み進めていくと、他の解法も学ばなければならないかもしれません。詳細に解説していくものもあります、単にさらなる学習のためのチュートリアルへのリンクを書くだけに留めるものもあります。

<!--
Chapter 2
How to Proceed During a Solve
To quote Per Kristen Fredlund, the general way to proceed is the following:
“Think of it more like so: solve the cube in 2 stages where stage 1 solves as many pieces as
possible as efficiently as possible (i.e.: make a good skeleton1
). The second step is fixing the
unsolved pieces, typically by inserting algorithms into the skeleton2”.3
This is the general approach, but you don’t need to use it every time: sometimes you can
find a very short solution by, for example, solving the F2L with blockbuilding and then finishing
the last layer with an algorithm. There are also different ways to proceed, two of which will be
explained in Chapter 4.
If this description seems too generic, it is because it can’t be differently: there isn’t a
standard method that allows you to always get good results, you should always try as many
strategies as you can, so that you don’t miss any chance.
Here I will describe some basic techniques used in FMC solves. You have already learnt
some of them by practicing the methods described in the previous chapter, while you will need
to study some other. Some will be explained in detail, some other will be only mentioned and
other tutorials will be linked for a more complete study.
-->
### 2.1 ブロックビルディング (Blockbuilding) {#blockbuilding}
**ブロックビルディングはFMCにおける最重要のテクニックでしょう。**簡単なコンセプトですが、しっかり習得するにはたくさんの練習が必要です。前の章で書いたような、ブロックビルディングの考え方に基づく解法（Petrus、Roux、Heise、ZZ）を練習することで直接的にブロックビルディングのスキルを成長させることができます。

ここではいくつか基本となるテクニックで便利なものを並べてみましょう。一つ目はRyan Heiseのウェブサイト ([https://www.ryanheise.com/cube](https://www.ryanheise.com/cube))から取ってきたものです。ウェブサイトには実例がたくさんありますから、是非見てみましょう！
<!--
2.1 Blockbuilding
Blockbuilding is probably the most important technique in FMC. It is a simple concept, but
it requires a lot of practice to be mastered. Practicing blockbuilding-based methods (Petrus,
Roux, Heise and ZZ), in the ways previously described, is the most direct way to improve at
blockbuilding.
Here I will list some fundamental techniques that will come in handy; the first ones are taken
from Ryan Heise’s website (www.ryanheise.com/cube), which is full of examples: look them up!
-->
#### 2.1.1 並べて、つなげる(Align then Join) {#ch2-1-1}
ソース：[http://www.ryanheise.com/cube/align_join.html](http://www.ryanheise.com/cube/align_join.html)

基本テクニック：**コーナーとエッジのペア（最も簡単なブロック）を作るためには、まず整列(align)して、一手でつなげられるようにしなければなりません。**

さらに一般的に言ってみると、この考え方は2x2x1よりも大きなブロックを作るときにも適用できます。たとえば、コーナーとエッジのペアと、2x2x1の四角を合わせて3x2x1ブロックを作りたいときなどにも使えます。

こういう言い方をすると平凡なことを言っているように見えますが、重要なことは**二つのピースがいつ整列しているかを認識しておいて、それを一手でつなげることです。** こうすることで、あるムーブによって2つのピースをつなげることができるかどうかを将来的に判断できるようになります。

{% capture display_text %}
L2 //Align
U2 //Join
{% endcapture %}
{% include solvebox.html
title = "並べて、つなげる(Align then Join) - Example"
scramble = "F U' D2 L D L2 D F R2 B U2 R2 D L2 D L2 D R2 U' L2 F2"
text = display_text
solution = "alg.cubing.net"
img_src="../../../assets/img/alg-211.png"
algcubing = "https://alg.cubing.net/?alg=L2_%2F%2FAlign%0AU2_%2F%2FJoin&setup=F_U-_D2_L_D_L2_D_F_R2_B_U2_R2_D_L2_D_L2_D_R2_U-_L2_F2"
%}

上記の例では、二つのペアがすでにできています。`L2 U2`と回すことで青-赤エッジと青-赤-黄コーナーがペアになります。

訳注：`L2`と回すことで青-赤エッジがB面の青センターと合うことを、ここでは整列(align)すると言っています。日本語では「センター合わせ」「エッジセンターペアに合わせる」と言うこともあります。
{: .notice--info}

<!--
2.1.1 Align then Join
Source: http://www.ryanheise.com/cube/align_join.html
Basic technique: to build a corner/edge pair, the simplest kind of block, you have to align
them first, making them joinable by a single move, and then join them with that move.
This concept can be applied, in a more general meaning, to the case of building bigger blocks,
for example when you want to match a pair and 2x2x1 square to get a 3x2x1
1A partial solution, where only a few pieces (usually from 2 to 6) are left to be solved.
2Technique that allows to solve a few pieces by inserting moves somewhere earlier in the solve. It will be
explained soon, be patient!
3
http://www.speedsolving.com/forum/threads/fewest-moves-tips-and-techniques.1566/#post-16209
15
16 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
All of this may look trivial, and in some way it is; the important thing to learn is to recognize
when two pieces are aligned and can be therefore joined with one move. This way you will
be able to realize in advance whether a certain move will join 2 pieces.
Align then Join - Example
Scramble: F U' D2 L D L2 D F R2 B U2 R2 D L2 D L2 D R2 U' L2 F2
L2 //Align
U2 //Join
See on alg.cubing.net
In the example above, two pairs are already built. The sequence L2 U2 pairs up the blue-red
edge with the blue-red-yellow corner.
-->
#### 2.1.2 別のところに持っていく (Move it out of the way)
ソース: [http://www.ryanheise.com/cube/move_it_out_of_the_way.html](http://www.ryanheise.com/cube/move_it_out_of_the_way.html)

ブロックを作りたいけれど、そのために必要なムーブが別のブロックを壊してしまうということがあるでしょう。そうしないために、**動かしたくないピースをあらかじめ別の場所に動かしておきましょう。**一つの方法として、まず壊したくないピースを先に動かして、壊れないように保存しておくことができます。そして、必要なら後で元通り戻すことができます。

{% capture display_text %}
U2 R2 D R2 //2x2x1の四角ができる
U' //赤-白-青のペアを別のところに持っていく
F' D' //四角を拡張して2x2x2を作る
{% endcapture %}
{% include solvebox.html
title = "別のところに持っていく (Move it out of the way) - Example"
scramble = "F R2 B D2 F D2 L2 B2 F' D2 F' L B U' F2 U2 L2 U B R2 F"
text = display_text
solution = "alg.cubing.net"
img_src="../../../assets/img/alg-212.png"
algcubing = "https://alg.cubing.net/?setup=F_R2_B_D2_F_D2_L2_B2_F-_D2_F-_L_B_U-_F2_U2_L2_U_B_R2_F&alg=U2_R2_D_R2_%2F%2F2x2x1_square%0AU-_%2F%2FMove_the_red%26%2345%3Bwhite%26%2345%3Bblue_pair_out_of_the_way%0AF-_D-_%2F%2FExpand_the_square_to_a_2x2x2_block"
%}

もし2x2x1ブロックを作ったあとすぐに`F' D'`と回したとしても、同じ2x2x2ブロックを作ることができます。しかし、赤-白-青のペア壊してしまうことになります。ただし、念のため補足しておきますが、このケースでは「別のところに持っていく」は最高のアイディアではないかもしれません。赤-白-青のペアを保存する過程で、黄-橙-青ペアを壊してしまっています！

<!--
2.1.2 Move it out of the way
Source: http://www.ryanheise.com/cube/move_it_out_of_the_way.html
It can happen that we want to build a block, but the move required to build it breaks other
blocks, or moves away pieces that we don’t want to move. One of the ways to bypass this
problem is to move away such pieces first, saving them from the breaking move, and then, if
necessary, put them back together once the move has been performed.
Move it out of the Way - Example
Scramble: F R2 B D2 F D2 L2 B2 F' D2 F' L B U' F2 U2 L2 U B R2 F
U2 R2 D R2 //2x2x1 square
U' //Move the red-white-blue pair out of the way!
F' D' //Expand the square to a 2x2x2 block
See on alg.cubing.net
If we did F' D' right after building the 2x2x1 block we would still get the same 2x2x2 block,
but we would break the red-white-blue pair. Notice however that in this case “moving it out of
the way” doesn’t seem to be the best idea: in the process of saving that pair, we are breaking
the yellow-orange-blue one!
-->
#### 2.1.3 壊して元通りにする (Destroy and Restore)
ソース: [http://www.ryanheise.com/cube/destroy_restore.html](http://www.ryanheise.com/cube/destroy_restore.html)

この問題を解決するための別の方法とは、一時的にブロックを壊してから、あとで元通りつなげるというものです。同様に「別のところに持っていく」テクニックを使います。

基本的な例として、`R U R' U'`の「スクランブル」をした状態を考えましょう。

![](../../../assets/img/alg-213.png){:width="500px" height="auto" class="align-center"}

`U R U' R'`という手順で元に戻りますが、これを知らないふりをして、Last Layerの状態も無視してください。最初の二段目だけを見ると、`R'`することで既にできたペアをF面にある別のピースの隣に動かせることがわかります。しかし、既に完成している別のF2Lスロットを壊してしまいます。このとき、次のように「壊して元通りにする」ことができます。

{% capture display_text %}
R' //既にできているペアを「壊す」
F //「別の所に持っていく」
R //「元通りにする」
F' //Fをして動かしたピースを戻す
{% endcapture %}
{% include solvebox.html
title = "壊して元通りにする (Destroy and Restore) - Example"
scramble = "R U R' U'"
text = display_text
img_src="../../../assets/img/alg-213.png"
%}

<!--
2.1.3 Destroy and Restore
Source: http://www.ryanheise.com/cube/destroy_restore.html
Another approach to solve this problem is to temporarily break some blocks and join them
back later, using the “move it out of the way” technique.
A basic example is given by applying the “scramble” R U R' U'.
2.1. BLOCKBUILDING 17
Let’s ignore the last layer and pretend not to know that U R U' R' obviously solves the cube.
Looking at the first two layers only, we see that R' places the ready pair next to the other pieces
in the front layer, but breaks part of the F2L already built. We can use “Destroy and Restore”
this way:
R' //“Destroy”
F //“Move it out of the Way”
R //“Restore”
F' //Put back the pieces moved away with F
-->
#### 2.1.4 キーホール (Keyhole)
単独の解法として既に書いたことですが、キーホールはブロックを作るための戦略のひとつと見なすことができます。このテクニックの本質は未完成であるキューブの一部を活用してほかのピースを揃えることです。キーホールF2Lの練習をうまくやっていれば、私が言わんとしていることを理解するのに実例を出す必要はないでしょう。しかし、念のためにキーホールの例を書いておきます。
{% capture display_text %}
F' L' //コーナーが一つない一面が完成
F2 L' B' L //キーホール
F U' B U //キーホール、偶然にも最後のコーナーが揃う
F' R' B2 R //キーホール
F B L B L' //F2L
B' //LL
{% endcapture %}
{% include solvebox.html
title = "キーホール - Example (出典：Edoardo Disarò)"
scramble = "U' R' L F' B U2 R2 B2 L' B R D F2 D2 L2 F2 D' R2 F2"
solution = "alg.cubing.net"
text = display_text
img_src="../../../assets/img/alg-214.png"
algcubing="https://alg.cubing.net/?setup=U-_R-_L_F-_B_U2_R2_B2_L-_B_R_D_F2_D2_L2_F2_D-_R2_F2&alg=F-_L-_%2F%2FLayer_minus_one_corner%0AF2_L-_B-_L_%2F%2FKeyhole%0AF_U-_B_U_%2F%2FKeyhole,_accidentally_solving_the_last_corner%0AF-_R-_B2_R_%2F%2FKeyhole%0AF_B_L_B_L-_%2F%2FF2L%0AB-_%2F%2FLL"
%}

<!--
2.1.4 Keyhole
We talked about it earlier as a standalone method, but keyhole can be considered a particular
strategy to build blocks. This technique consists in exploiting unsolved parts of the cube to
solve some pieces. After some good Keyhole F2L practice you shouldn’t need any example to
understand what I mean, but I’ll leave here a Keyhole solve anyways.
Example (adapted from a solve by Edoardo Disar`o)
Scramble: U' R' L F' B U2 R2 B2 L' B R D F2 D2 L2 F2 D' R2 F2
F' L' //Layer minus one corner
F2 L' B' L //Keyhole
F U' B U //Keyhole, accidentally solving the last corner
F' R' B2 R //Keyhole
F B L B L' //F2L
B' //LL
See on alg.cubing.net
-->
#### 2.1.5 一つのムーブ、二つのゴール (One Move, Two Goals)
**一つのムーブで二つのブロックを作ることができる場合は多くあります。**一般的に言えば、キューブを回す上で「二つのことを同時にやる」ことができます。次の実例を見ることでよりはっきりとわかるでしょう。
{% capture display_text %}
L U' F2 D' //2x2x2 (4/4)
U2 B R2 B //疑似F2L-1 (4/8)
F' * U F R U2 R' //疑似F2L (6/14)
U2 R2 //3コーナー以外完成 (2/16)
* = B' U F2 U' B U F2 U' //Last 3 corners (8-5/19)
{% endcapture %}
{% include solvebox.html
title = "Example (by Mirek Goljan and Guus Razoux-Schultz)"
scramble = "D U' F2 U' R' F R2 B D' B R F B' U R' D2 L' R2 F2 B' U' B D B2 F2
U L F U' B2"
solution = "L U' F2 D' U2 B R2 F' U F2 U' B U F' R U2 R' U2 R2 (19)"
text = display_text
img_src="../../../assets/img/alg-215.png"
algcubing="https://alg.cubing.net/?setup=D_U-_F2_U-_R-_F_R2_B_D-_B_R_F_B-_U_R-_D2_L-_R2_F2_B-_U-_B_D_B2_F2_U_L_F_U-_B2&alg=L_U-_F2_D-_%2F%2F2x2x2_(4%2F4)%0AU2_B_R2_B_%2F%2FPseudo_F2L%26%2345%3B1_(4%2F8)%0AF-_(B-_U_F2_U-_B_U_F2_U-)_U_F_R_U2_R-_%2F%2FPseudo_F2L_(6%2F14)%0AU2_R2_%2F%2FAll_but_3_corners_(2%2F16)"
%}[^2-1-5] [^2-1-5-2]

もしあなたがインサーションについてまだわかっていないなら、最後の行は無視してください。**今回注目すべきは最初の行、特に`F2`をしているところです。この一手でDFに2x2x1ブロックを作り、同時に橙-緑エッジを合わせています。**次の一手で2x2x2ブロックができるようになりました。

このような状況は偶然に生まれることがありますが、そうでない場合でも「どう認識するものなのか」を知っておくと役に立つでしょう。

<!--
2.1.5 One Move, Two Goals
It is often possible to use only one move to build two blocks or, in general, to “get two things
done”. An example will make this clearer.
Example (by Mirek Goljan and Guus Razoux-Schultz4)
Scramble: D U' F2 U' R' F R2 B D' B R F B' U R' D2 L' R2 F2 B' U' B D B2 F2
U L F U' B2
L U' F2 D' //2x2x2 (4/4)
U2 B R2 B //Pseudo F2L-1 (4/8)
F' * U F R U2 R' //Pseudo F2L (6/14)
U2 R2 //All but 3 corners (2/16)
* = B' U F2 U' B U F2 U' //Last 3 corners (3/19)
Solution: L U' F2 D' U2 B R2 F' U F2 U' B U F' R U2 R' U2 R2 (19)
See on alg.cubing.net
18 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
If you don’t know about insertions yet, ignore the last line. In fact the only line we are
concerned with is the first one, especially the red F2 move: notice how that single move builds
the 2x2x1 block in DF and places the orange-green edge at the same time, which allows to build
the 2x2x2 with the next move.
Situations like this may arise without forcing them, but it useful to learn to recognize them,
in case they don’t.
-->
#### 2.1.6 あとのステップに影響を与える(Influence Later Steps)
F2Lを完成させるときにLLに影響を与える点についてはすでに（少しだけ）話しました[^2-1-6-1]。このアイディアはブロックビルディングにも適用できます。つまり、**ブロックを準最適(sub-optimally)[^2-1-6-2]に作っておくか、あるいは「不要な」ムーブを加えることで後の繋がりをよくしたり、簡単にブロックを作ったりすることができます。**

たとえば、次のスクランブルを考えてみましょう。
{% capture display_text %}
L2 B R B //２つの 2x2x1 ブロック
{% endcapture %}
{% include solvebox.html
title = "あとのステップに影響を与える - Example"
scramble = "L2 D2 U R2 F2 D2 B2 U' R2 B2 U B U F D B2 U L D' R' F"
solution = "alg.cubing.net"
text = display_text
img_src="../../../assets/img/alg-216.png"
algcubing="https://alg.cubing.net/?setup=L2_D2_U_R2_F2_D2_B2_U-_R2_B2_U_B_U_F_D_B2_U_L_D-_R-_F&alg=L2_B_R_B_%2F%2FTwo_2x2x1_blocks"
%}

見てわかるように、`L2 R B`で赤-青-白の四角を作ることができますが、`L2 B R B`と一手加えることで、四角が二つになります。

<!--
2.1.6 Influence Later Steps
We have already (quickly) talked about influencing the LL step while finishing the F2L5
. This
idea also applies to blockbuilding: it is often better to build a block sub-optimally6
, or to
add some “unnecessary” moves to have a better continuation, blockbuilding or else (i.e., edge
orientation).
For example, consider the following scramble.
Influence Later Steps - Example
Scramble: L2 D2 U R2 F2 D2 B2 U' R2 B2 U B U F D B2 U L D' R' F
L2 B R B //Two 2x2x1 blocks
See on alg.cubing.net
As you can see, the sequence L2 R B builds the red-blue-white square, but adding only one
move (the red B) the square become 2.
-->
#### 2.1.7 EOに気をつけよう (Pay Attention to EO) {#ch2-1-7}
ここでいう**EO**とはエッジの向き(Edge Orientation)を略したものです。

複数の異なる解法を学ぶなかで既にお気づきの方もいるかもしれませんが、Edge Orientationというのは再帰的なステップなのです。前述のように、**Bad edgeが多ければ多いほど、解くのは困難になっていきます。**通常、ソルブの最後に最後にエッジの向きをそろえることは、効率的ではありません。ZZでそうするように、まず最初にエッジの向きを揃えることが手軽ですが、ブロックビルディングのフェイズで制約が増えることになります。

部分的にでも、**Edge Orientationをブロックビルディングの途中で終わらせるのが良い方法です。**ZZやPetrusなどの解法に習熟すると、数手動かしたあとでエッジの向きが正しいかどうかを簡単に判定できるようになります。もしまだ判定ができないのだとしても、FMCにおいてはいつでも望むときに戻って修正できるということを忘れないでおきましょう。つまり、EOがうまくいかないときには、前に戻って、何手か加えたり変えたりして、よい方向に進むかどうかを確認すればいいのです。（[2.6.1節](#ch2-6-1)もご参照ください）

**訳注**  
ここでいうEOに注目したアプローチを「EOファーストアプローチ(EO first approach)」ということがあります。[João Pedro Batista Ribeiro Costa](https://www.worldcubeassociation.org/persons/2013COST02)(世界大会2015のFMCチャンピオン)や[Grzegorz Łuczyna](https://www.worldcubeassociation.org/persons/2005LUCZ01)(ヨーロッパ大会2010のFMCチャンピオン)、[Sébastien Auroux](https://www.worldcubeassociation.org/persons/2008AURO01)(世界大会2011のFMCチャンピオン)などの著名なキューバーは、ほとんど常にEOファーストアプローチを使うようです。原著者のSebastiano Trontoも非常によく使うということが第二版には記載がありました。EOファーストアプローチについては、[2.5節](#ch2-5)に詳細が書かれています。
{: .notice--info}


<!--
2.1.7 Pay Attention to EO
Here EO is the common shortcut for Edge Orientation.
Someone may have noticed, while studying different methods, that “Edges Orientation” is a
recurring step. As said before, the more bad edges there are, the harder things will be.
Orienting edges at the end is usually not efficient. Orienting them first, as in ZZ, is convenient,
but it can be limiting for the blockbuilding phase.
One of the best things to do is trying to solve, at least partially, edges orientation during the
blockbuilding step. Experience with methods such as ZZ and Petrus can lead to being able to
easily spot if an edge will be correctly oriented after some moves. If you don’t have this ability
yet, remember that in FMC solves you can go back and modify your solution every time you
wish: if you have troubles with EO, try going back and add/change some moves to see if things
get better (see also Section 2.5.1).
However, don’t dismiss the “EO first approach” too quickly: notable cubers such as Jo˜ao
Pedro Batista Ribeiro Costa (2015 World Champion) and Grzegorz Luczyna (2010 European
Champion) almost always start with edge orientation and other like S´ebastien Auroux (2011
World Champion) and myself do it very often. For more details and examples see section 4.1.
-->
#### 2.1.8 どのブロックを作るべきか？ (Which Block Should I Build?)
様々な状況を活用せよ、ということが黄金律です。つまり、2x2x2ブロック、3x2x1ブロック、2つの2x2x1の四角、ほかの様々なブロックから始めることができます。全ての可能性を試しましょう。

可能な２つのアプローチとしては次のようなものがあります。
1. 2x2x3やF2L-1のような大きなブロックを作ろうとする
1. 小さなステップで前に進み、たくさんの小さなブロックを作って最後につなげる

Erik Jernqvistは「よいスタート」を切るための指標として、次の手数の表を作りました。[^2-1-8]

|ブロックの種類                  |手数|
|:------------                  |:---:|
|2x2x1四角＋コーナー／エッジペア  |3|
|2x2x2ブロック                  |4|
|2つの2x2x1四角                 |5|
|2x2x3ブロック                  |9|
|F2L-1                          |14|
|F2L                            |17|

個人的には、この表の手数はちょうどよい推計だと思います。特に最初の３つについて当てはまります。しかし、**よいスタートを切れたかどうかはその後のつながりがどうなるかにかかっている**ということを覚えておかなければなりません。もしF2L-1が12手でできたけれど、bad edgeが4つも残っていて、最後のF2Lのエッジが反転して入っているとしたらどうするでしょう。すぐに投げ捨てるだろうと思います。一方で、全てのエッジの向きが揃った2x2x3ブロックが12手でできたならもっとよいでしょう。もちろんEOだけが考慮すべきことではありませんが、最も重要なものの一つです。

もう一つのルールは**決してLast Layerに影響を与えずにF2Lを完成させてはならない**[^2-1-8-2]ということです。理由は単純です。つまり、Last layerが悪い状態であるなら、どんなに多くのアルゴリズムを知っていたとしても多くの手数が必要になります。また、F2Lを完成させてしまうことはキューブ全体を操作する自由度が減るということです。一方で、**F2L-1を目指すことは良い部分解です。**これは、多くのピースが既に配置されているにも関わらず、より多くの自由度があるからです。

<!--
2.1.8 Which Block Should I Build?
The golden rule is to exploit different situations: a 2x2x2 block, a 3x2x1, two 2x2x1 squares and
many other kind of blocks can be a good start. Try out every possibility.
5Notable examples are ZBLS (sometimes less properly called ZBF2L) and Winter Variation, but there are
many more: look them up!
6
“Sub-optima” (with or “suboptimal”, without the -) refers to a solution (complete or partial) that uses more
moves than the best possible one.
2.1. BLOCKBUILDING 19
Two possible approaches are:
1. Try completing big blocks, like a 2x2x3 or a F2L-1.
2. Proceed in small steps, building many small blocks and joining them at the end.
Erik Jernqvist proposes the following number of moves as good starts7
:
Type of Blocks Number of Moves
2x2x1 square + corner/edge pair 3
2x2x2 block 4
Two 2x2x1 squares 5
2x2x3 block 9
F2L-1 14
F2L 17
Personally, I think these are good estimations, especially for the first 3 cases. But always
have to remember that how good a start is depends on the possible continuations. If
you build an F2L-1 in 12 moves, but you have 4 bad edges, one of which is the last F2L edge
flipped in place, you may have to throw it away. On the other hand, a 2x2x3 in 12 moves with
all edges oriented can be a better alternative. Obviously EO is not the only thing you have to
consider, but it’s one of the most important.
Another rule is: never8 complete the F2L without influencing the last layer. The
reason is simple: a bad last layer can require many moves, no matter how many algorithms
you know, and a completely built F2L gives a little freedom to manipulate the cube. On the
other hand, an F2L-1 is a good partial goal, because it leaves you more with more freedom,
despite the many pieces already placed.
-->
#### 2.1.9 既にブロックがある：どうすればいいか？(Ready-Made Blocks: How to Deal with Them?) {#ch2-1-9}
キューブをスクランブルしたときに既にいくつかブロックができていたり、最初の何手かで意図せず新しいブロック（コーナーとエッジのペアなど）ができてしまったりすることがあります。こういうときは、元々考えていたやりかたを続けるよりも、できてしまったブロックを活用するのが望ましいです。どうやって？3つの方法があります。

1. **まず既にできているブロックを拡張する**　（当たり前のことです）
1. 既にできているブロックを拡張するが、**他のピースも同時に見ながら同時に別のブロックができるようにする** (これが最良の方法です)
1. **既にできているブロックを拡張せず、できればそれを壊さずに新しいブロックを探す**

さらに言うなら、**保存する価値があるブロックなのかを理解することはとても重要で難しいことです。**新しいブロックを作るためには既存のブロックを壊す必要があります。個人的には、ブロックを「諦めて」「捨てる」ことはとても難しく、同時にトラブルのもとになります。タイムマネジメントをする上ではなおさらです。

<!--
2.1.9 Ready-Made Blocks: How to Deal with Them?
It can happen that you find some blocks already built after scrambling the cube, or that with
the first moves you unintentionally build some more blocks (mostly corner/edge pairs). In this
cases it is preferable to exploit those blocks rather than giving them and up and going on your
own way. How? There are three ways:
1. Expand / match the ready-made blocks first; the obvious thing to do.
2. Expand / match the ready-made blocks, but watching other pieces too and trying to
build other blocks at the same time; this is usually the best thing to do.
3. Don’t expand the ready-made blocks, but try to make new ones, possibly saving the others.
Moreover, it is very important, but terribly difficult, to understand when it is not worth
to save a block, and you should break it to make new ones. Personally, I find it very hard to
“give up” and “throw away” a block, but I realize this often causes troubles, especially in time
management.
7Taken from this post on speedsolving.com. Obviously, what a “good start” depends on your level. The given
move counts are to be considered a good goal for someone who wants to become an expert. If you are not this
good yet you can go on with less efficient blocks. Don’t waste too much time looking for a good start: it’s the
final result that counts!
8But a more important rule is: never say never!
20 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
-->
#### 2.1.10 速くなるためのコツ、高度なテクニック(Tricks to Get Fast and Advanced Techniques)
「速くなること」はスピード解法のような意味ではなく、「よいブロックビルディングを速くやること」という意味です。よいスタートを速く見つけることはとても重要です。そうすることで時間が節約できます（1時間はそんなに長くありません！）し、全ての将来有望なスタート地点を探して見つけるべきです。見つけられないにしても、気付くべきです。

最も簡単なブロックはコーナー／エッジのペア（2x1x1ブロック）です。スクランブル後に何も動かさなくても、一つできていることもあるでしょう。もし一つでも（二つ以上でも）あったなら、[2.1.9節](#ch2-1-9)で書いたように、これをうまく使ってもよいでしょう。もし一つもなかったとしたら、見えるところにあるもので一手でペアになるものを認識できるようにしましょう（[2.1.1節](#2-1-1)を参照）。もしまだすぐにわからなくて、楽をしようとするなら[^2-1-10-1]、「総当たり戦略」をやってみるのもよいでしょう。つまり、**すべての可能なムーブ試すのです。`U`、`U2`、`U'`と順番に試してから、次に`R`、`R2`、`R'`と続けていき、ペアができたかどうかを確認すればいいのです。**

もっと高度で役立つテクニックがあります。検討する時間はかかりますが、**全ての可能な2x2x2ブロック（8通り）をチェックするとよいでしょう。**やり方はこうです。**全てのコーナーピースについて、一致するエッジを3つ全て探して、**どうすればつなげて2x2x2ブロックが作れるかを考えます。実際に動かして「テスト」しないようにすることで、再度スクランブルせずに他のコーナーについても同じことを繰り返すことができます。通常、非常に悪い2x2x2ブロック（とてもたくさんの手数がかかる）を見つけたとき、私はそれを無視して次に進みます。このテクニックを使うことで、全てのピースがキューブのどこに位置しているかということがわかり、さらに最適な2x2x2ブロック（これはよいスタートになることが多い）を見つけられるようになるでしょう。

実際にキューブを回さずに2x2x2ブロックを作るムーブを考えることは他にもよい意味があります。より速く上手にブロックビルディングできるようになるためには、**実際の動きを見ずにピースの動きを「頭の中で計算できる」ようになる**[^2-1-10-2]ことが大切です。  
[Alexander Lau](https://www.worldcubeassociation.org/persons/2011LAUA01) (2014 年のヨーロッパチャンピオンであり、Rouxメソッドの達人)は15秒間のインスペクションタイムで3x2x1ブロック(Rouxの最初のステップ)を読むことができます。この読みは非常に正確で、ブロックを作りながら先読み(look-ahead)をして、Second Block(の一部)を読むことができるようです。

この先を読む能力は次のようなゲームでトレーニングすることができます。  
**友人にキューブを3手[^2-1-10-3]でスクランブルしてもらってから、それを受け取ったら3手の解答を探しましょう。**これは簡単なはずです。次に4手をやってみる、5手に増やす、という風に続けます。あなたのレベルによりますが、6手、7手、8手と行くにつれて難しく感じていくでしょう。続けていくうちに9手や10手のものでも苦労なく解けるようになりましたか？ おめでとうございます！

**訳注：**  
この「詰めキューブ」問題は非常に難しいので、9手や10手のものが苦労なくできるというのはかなりのレベルです！Sebastiano Trontoにとっては簡単なのかもしれませんが…。  
本チュートリアルの巻末には、Retoによる詰めキューブの問題がいくつか収録されています！　日本国内では、[うえしゅう](https://twitter.com/uesyuu_cube)氏による[詰めキューブ生成](https://uesyuu.com/tsume-cube/)のサービスがあり、**3手から14手までの詰めキューブの問題をランダム生成して楽しむことができます。**（Retoの問題も含まれています）  
自分で面白い詰めキューブの問題ができたら、[詰めキューブスクランブル生成器](https://uesyuu.com/tsume-cube/generate-scramble.html)でスクランブルを生成して、知り合いのキューバーに問題を出してみましょう！
{: .notice--info}

<!--
2.1.10 Tricks to Get Fast and Advanced Techniques
“Getting fast” is not to be intended as in speedsolving, but as “finding faster a good blockbuilding
start9
”. Being fast at finding a good start is very important, because it saves time (one hour
isn’t that long!) and you should try to explore, or at least to notice, every promising start.
The simplest kind of block is the corner/edge pair, or 2x1x1 block. There will probably be
one already made in a scramble, without making any move. If there is one (or more than one),
you can deal with it in one of the ways described in the previous section 2.1.9. If there isn’t any,
you should learn how to recognize at the sight pairs that can be made with one move (see 2.1.1
“Align Then Join”). If you are not fast at recognizing them yet, or if you want to avoid some
effort10, you can use the “Brute Force” strategy: try all possible moves, starting with U, U2, U',
then R, R2, R', and so on, checking after each move if you did build a pair.
A more advanced technique, more useful but requiring more thinkin, consists in checking
every possible 2x2x2 (there are 8 of them). You can do it this way: for each corner, look for
its three matching edges and try to see which way you can join them to make that 2x2x2
block. Try not to make any “test” moves, so that you can do the same for the other corners
without re-scrambling. Usually, if I see a very bad 2x2x2 block (one that requires too many
moves) I just ignore it and go on. This technique, beside enabling you to find, most of times, an
optimal 2x2x2 block (which is usually a good starting point), gives you an idea of where every
piece is on the cube.
Another reason why I suggest trying to “see” every move for making the 2x2x2 without
performing is that to get faster and better at blockbuilding it is useful to be able to “calculate”11 pieces’ movements without seeing them. Alexander Lau (2014 Rubik’s Cube European
Champion and Roux method master) is able, in the 15 seconds given to inspect the cube before
a speedsolve, to plan a whole 3x2x1 block (Roux first step). His planning is so accurate that
while solving this block he can look-ahead12 and (partially) plan the second block.
You can train your planning ability with this game: ask a friend to scramble your cube with
3 moves and then try to find those 3 moves13 (it should be easy). Then try with 4 moves, and
so on. Depending on your level, you may find it difficult once you reach 6, 7 or 8 moves. If you
get without problem to 9 or 10 moves, congratulations!
-->
### 2.2 よいスケルトンを見つけよう(Find a Good Skeleton) {#find-skelton}

F2L-1など、ブロックビルディングがうまくいきそうなところまで到達したなら、上に書いたようなテクニックを使って進めるのは難しくなるでしょう。**次なるゴールは「スケルトン」と呼ばれるものを見つけることです。**

これは何かと言うと、**いくつかのピースが未完成な状態のままである部分的な解法のことです。**数あるスケルトンの中で最も良いのは、3つのコーナーだけ残って3-cycle[^2-2]で交換できる状態ですが、4つや5つのコーナー、3つのエッジが残る場合も悪くありません。この良し悪しはスケルトンを作るのに何手かかったかによって変わります。

次にやることは何でしょう。これまで見てきたブロックビルディングのテクニックを、既に作ったブロックを壊さずに使うことができるでしょうか？まずHeiseを参照してみるのがよいでしょう。これはHeiseメソッドのステップ3を見よ、という意味でもありますし、彼のウェブサイトという意味でもあります。特にウェブサイトの「2つのペアによるアプローチ」に記述があります。[http://www.ryanheise.com/cube/two_pairs.html](http://www.ryanheise.com/cube/two_pairs.html)

Heiseのステップ3はF2L-1だけでなく、全てのエッジの向きが揃っていることを仮定しています。もし揃っていないなら、次のようなやり方があります。

1. まずエッジの向きを揃える。手数が非常に少なくない限り、非推奨。
1. 既にやった手順を修正して、全てのエッジの向きが最後に揃うようにする。
1. スケルトンを完成させるときにエッジの向きを揃える。

まとめると、よいスケルトンを作るための可能なアプローチはたくさんあます。この場合の最も良い方法は、**オンラインでFMC熟練者のソルブ例を見ることです。**オンラインで例を探すのはいい習慣です。熟練者のソルブを見るとわかりますが、ほとんどの場合、スケルトンを作って解いています。熟練者のソルブは、たとえばオンライン大会の記録やspeedsolving.comのフォーラムで見つけることができるでしょう。

さらに深く考える練習も役に立つでしょう。qqTimer ([http://www.qqtimer.net/](http://www.qqtimer.net/))では3x3x3のスクランブルのサブセットとして、Last SlotとLast Layerを選ぶことができます。

当たり前のことですが、スケルトンを完成させる前にF2L-1を作ることは必須ではありませんが、これが最も簡単であることが多いです。どんなケースでも、偶然にLast Layerのピースで小さなブロック(ペア、2x2x1など）ができたなら、残しておきましょう。

<!--
2.2 Find a Good Skeleton
Once you have reached good point (i.e.: and F2L-1) with blockbuilding, it is hard to go on with
the techniques just described. Your goal now is to find a so-called “skeleton”, i.e. a partial
solution that only leaves a few pieces unsolved. The best situation is the one with 3 corners
unsolved, where the pieces form a 3-cycle14, but also 4 or 5 corners or 3 edges can be good,
depending on how many moves you need to build the skeleton.
What should we do then, if the blockbuilding techniques we have seen are difficult to use
without destroying what we have just built? Heise is an excellent starting point. And I mean
both the method and the website: step 3 is accurately described, in particular the “Two Pairs
Approach”: see http://www.ryanheise.com/cube/two_pairs.html.
Heise’s step 3 requires not only an F2L-1, but also all edges to be oriented. If they are not,
you can:
1. orient them now; usually not recommended, unless it takes very few moves;
9A “start” can be a 2x2x2, a 3x2x1, some smaller blocks or, in some cases, a 2x2x3; in general, anything from
the first 2 to the first 7 moves.
10Since you need to keep thinking for an hour, avoiding efforts is a good habit.
11The word “calculate” should be intended as in chess: a player is said to “calculate” 6, 7 or 8 moves if he can
think of the possible moves and counter-moves for a total of 6, 7 or 8 moves.
12In speedsolving, “look-ahead” (with or without the -) is the ability to think about later step while you are
solving another one.
13You can choose between HTM, QTM or STM, but agree on which metric to use first!
14A 3-cycle is a cycle of 3 pieces. For example, the A and U perm PLL cases are 3-cycles, as well as the
algorithm L F R F' L' F R' F' (Niklas).

2.3. COMMUTATORS 21
2. modfy the steps you have already solved, to get all edges oriented at the end;
3. orient them while finishing your skeleton.
To sum it up, the possible approaches to get a skeleton are many and the best way to train
in this case (and always a good habit) is to look online (for example in websites hosting online
competitions or on speedolving forums) for expert FMCers’ solves; most of times, they build a
skeleton.
Some deliberate practice can also be helpful: on qqTimer (http://www.qqtimer.net/) you
can choose the scramble type 3x3x3 subsets → last slot + last layer.
You obviously don’t have to build an F2L-1 before completing your skeleton, but is often the
easiest way. In any case, try to save small blocks (pairs or 2x2x1 squares) made by LL pieces,
if some of them happen to get built.
-->
### 2.3. コミュテータ(COMMUTATORS) {#commutators}
speedsolving.comの定義[^2-3-1]によれば、コミュテータとは次のような形で記述する手順です。

`A B A' B'`
{: .text-center}

`A`と`B`はそれぞれ手順を示す配列で、`X'`は`X`という手順の逆手順(inverse)[^2-3-0]です。このようなコミュテータは次のような記法で短く書くことができます。

`[A, B]`
{: .text-center}

コミュテータの名称や記法は数学、特に群論から来たものです。たとえばWikipediaの記事をご覧ください。[https://en.wikipedia.org/wiki/Commutator](https://en.wikipedia.org/wiki/Commutator)

**訳注：**  
数学用語としてのコミュテータは、日本語では**交換子（こうかんし）**と書かれます。しかし、キューブ用語としてはコミュテータあるいはコミュテーターとして定着しているため、ここではカタカナで記載します。  
詳しくは[「交換子 - Wikipedia」](https://ja.wikipedia.org/wiki/%E4%BA%A4%E6%8F%9B%E5%AD%90)をご参照ください。
{: .notice--info}

たとえばA=`R`、B=`U`であると考えると、「セクシームーブ(sexy move)」がコミュテータであることに気づくでしょう。

`[R, U]` = `R U R' U'`
{: .text-center}

A=`R`、B=`U' L' U`と考えると、「Niklas」手順になります。

`[R, U' L' U]` = `R U' L' U R' U' L U`
{: .text-center}

慣習として、「コミュテータ」は「3点の巡回交換(3-cycle)を解くコミュテータ」として使われることが多いです。なので、たとえば「セクシームーブ」は通常コミュテータとみなされませんが、「Niklas」はコミュテータとみなされます。この先も、この慣習に従って使っていきます。

「コミュテータとは何か」という点については、WRCCやTRCCのFMC解説記事のなかにわかりやすく記述されています。簡単に言うと、FMCにおいては**任意の3点だけを8手で自由に入れ替えることができる手順**のことです。これが8手では実現できない場合もあります。詳細は下記の記事を参照してください。  
[FMC解説 - 7. Commutator (WRCC)](http://wrcc.main.jp/commentary_fmc/fmc/7)  
[4. ピュア・コミュテーター - 東京大学ルービックキューブサークル](http://trcc.sub.jp/solution/fmc/commutator.html)
{: .notice--info}

<!--
2.3 Commutators
According to speedsolving’s definition15, a commutator is a sequence of moves of the form
A B A' B'
where A and B are move sequences and X' is the inverse sequence of X
16. Such a commutator can be written in compact notation as
[A, B]
The name and notation for commutators come from Mathematics, in particular from Group
Theory. See https://en.wikipedia.org/wiki/Commutator.
For example taking A=R and B=U realizes the “sexy move” as a commutator:
[R, U] = R U R' U'
Taking instead A = R and B = U' L' U gives the “Niklas”:
[R, U' L' U] = R U' L' U R' U' L U
Often, in practice, “commutator” is used as “commutator that solves a 3-cycle”. So for
example the “sexy move” is not usually regarded as a commutator, while the “Niklas” is. In
what follows, we will use this meaning too.
In contrast with blockbuilding, that solves a lot pieces but heavily influencing the rest of
the cube, commutators solve fewer pieces (usually 3) leaving all the others where they were.
Therefore, together with blockbuilding and insertions (which we will see in the next section),
commutators are the basis for a good FMC solve.
-->
#### 2.3.1 コーナーコミュテータ(Corner Commutators)
コーナーコミュテータはFMCにおいて最も役に立つコミュテータです。既に「Niklas」というコミュテータを見ました。PLLのA permである`R2 B2 R F R' B2 R F' R`という手順も、（ほぼ）コミュテータです。

`R2 B2 R F R' B2 R F' R` = `R2 [B2, R F R'] R2`
{: .text-center}

ここでは`R' R2`という配列がキャンセル[^2-3-1]して`R`になっています。

組み合わせが変わる3つのコーナーは同じ面にある必要はありません。`[L D' L', U2]` = `L D' L' U2 L D L' U2` という手順も3-cycleです！

全ての種類のコーナーコミュテータ（このチュートリアルでは解説しません）を学ぶなら、Speedsolving.comの[Brian Yuのチュートリアル](https://www.speedsolving.com/threads/bh-tutorial.12268/)を見てみるとよいでしょう。文書と動画での解説があり、どちらも非常によくできていましたが、残念ながら動画にはアクセスできなくなってしまいました。

FMCをやる上では、**8手の「ピュアコミュテータ」**だけを覚えればいいでしょう。たとえば、Niklasはピュアコミュテータですが、A permは違います。必要ならA9やほかのケースを見てください。しかし、インサーションのところでも話しますが、FMCにおいてはピュアコミュテータ以外はほとんど必要ありません[^2-3-1-2]。

ごく稀に、10手の「スレッジ・インサーション」のコーナーコミュテータ(`[R' F R F', D2]`)が役に立つことがあります。これは8手のコミュテータを使うよりも多くのキャンセルができる場合があるからです。

**訳注：**  
上記のBrian Yuのチュートリアルにおいては、コミュテータの種類として次のものを上げています。8手のものがピュアコミュテータです。ここでは、A9(9手コミュテータ)以上のコミュテータを覚えても、FMCではあまり使わない、ということを言っています  
Pure (8 moves)  
A9 (9 moves)  
Orthogonal (10 moves)  
Cyclic Shift (10 moves)  
Columns (11 moves)  
Per Special (12 moves)
{: .notice--info}

**訳注：**  
「ピュアコミュテータ以外はFMCにおいてはほとんど必要ない」ことの例外として、Tomoaki Okayama (岡山友昭)による[実例](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-21#post-440873)が脚注に上げられています。ここでは`F2 (R F' L2 F R' F' L2 F) F2`という、`F2`セットアップして1手キャンセルする9手のインサーションをしていますが、8手のピュアコミュテータによるインサーションがまったく見つからないという状況が議論されています。
{: .notice--info}

<!--
2.3.1 Corner Commutators
Corner commutators are the most useful kind of commutators in FMC. We have already seen
the “Niklas” as a commutator. Also the A perm PLL case R2 B2 R F R' B2 R F' R is (almost)
a commutator:
R2 B2 R F R' B2 R F' R = R2 [B2, R F R'] R2
15http://www.speedsolving.com/wiki/index.php/Commutator
16For example, the inverse of U R is R' U', not U' R' or R U!
22 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
where we have cancelled17 the sequence R' R2 to R.
The 3 corners to be permuted need not be on the same layer: [L D' L', U2] = L D' L'U2
L D L' U2 is also corner 3-cycle!
To learn all kinds of corner commutator (which I will not explain in this tutorial) is advise
looking up Brian Yu’s tutorial on speedsolving.com. It consists of both a written part and some
videos, and it is very well made.
For FMC you only need to know “pure” 8 moves commutators. For example, the Niklas is
a pure commutator, while the A perm is not. Take a look at A9s and other cases if you want,
but, as we will see when talking about insertions, you will almost never18 need them in FMC.
-->
#### 2.3.2 エッジコミュテータ(Edge Commutators)
コーナーコミュテータを学んだら、エッジコミュテータの仕組みを理解するのも難しくないでしょう。たとえば次の例を見てみましょう。

`[U R U', M']` = `U R U' M' U R' U' M`
{: .text-center}

残念ながら、上記のようなコミュテータがよい結果につながるのはごく稀です。その理由は**M列を使うので、2手として数えられてしまうからです。**

全ての人が知っておくべきエッジコミュテータは

![](../../../assets/img/alg-232.png){:width="200px" height="auto" class="align-center"}
`[M', U2]` = `M' U2 M U2` (DF->UB->UF)
{: .text-center}

です。これはセットアップすることでとても役立ちます。たとえば、次のような形です。

`[U: [M', U2]]`[^2-3-2] = `U M' U2 M U2 U'` = `U M' U2 M U`
{: .text-center}

公式大会においては中層回転（スライスムーブ）を書くことはできませんから、`[M', U2]`のコミュテータは次のように書きます。

`M' U2 M U2` = `R' L x U2 R L' x' U2` = `R' L F2 R L' U2`
{: .text-center}

最初の`R' L`というムーブは交換可能であることがわかると思います。このことは全ての並行な（つまり対面にある）ムーブについて言えます。

もう一つ知っておかなければならないのは、**最初の2手は交換したい3つのエッジにまったく影響を及ぼさないということです。**なので、`R' L F2 R L' U2`は`L F2 R L' U2 R'`、`F2 R L' U2 R' L`、`R' F2 R L' U2 L`と等しいのです。

**訳注：** `[M', U2]`はDF->UB->UFの3点を交換するコミュテータです。
{: .notice}

**特に、この性質はキャンセルを探しているときに役に立ちます。**コミュテータの最初のムーブと、後続のムーブの逆手順とを対応させることでキャンセルが起きます(あるいはその逆もあります)。一般的にはコミュテータでなくともこのような探索を使うことができます。

<!--
2.3.2 Edge Commutators
Once you have learned corner commutators, it should not be hard to understand how edge
commutators work, especially the ones like
[U R U', M'] = U R U' M' U R' U' M
Sadly, commutators like this only occasionally give a good result, because they use M layer
moves, which are actually two moves in our metric.
The edge commutator everyone should know is:
[M', U2] = M' U2 M U2
Which is also very useful with some setup move, for example:
[U: [M', U2]]19 = U M' U2 M U2 U' = U M' U2 M U
Remember that in official competitions you can’t write a inner layer moves, so the [M', U2]
commutator becomes:
M' U2 M U2 = R' L x U2 R L' x' U2 = R' L F2 R L' U2
Notice how the first two moves (R' L) can be swapped. This is true for every pair of parallel
(i.e. opposite) moves.
Another thing you need to notice is that the first two moves don’t affect any of the 3 edges
we want to cycle: R' L F2 R L' U2 is therefore equivalent to L F2 R L' U2 R' , to F2 R L' U2
R' L and, since we can invert R' and L, to R' F2 R L' U2 L.
These observations are particularly useful when you want to cancel moves, that is making
the first moves of our commutator (or, in general, any sequence of moves we want to apply)
correspond to the inverse of the preceding moves (or that the last moves correspond to the
inverse of the following ones).
-->
#### 2.3.3 その他のエッジ3-cycle(Other Edge 3-cycles)
中層回転を使わないエッジの3-cycleもあります。実際にはコミュテータですらないものも含まれます！HTMで8手の例を2つ上げましょう。

![](../../../assets/img/alg-233.png){:width="200px" height="auto" class="align-center"}
`R2 Fw2 R2 U R2 Fw2 R2 U` = `R2 B2 L2 D L2 B2 R2 U`  
`R2 Fw2 R2 Uw R2 Fw2 R2 Uw` = `R2 B2 L2 U B2 R2 F2 D`
{: .text-center}

**訳注：** 一つ目も二つ目もDF->UF->ULを交換する三点交換です。途中の`U`が`Uw`に変わっただけです。
{: .notice}

一つ目の最初の2手は交換したい3つのエッジにまったく影響しません。なので、これを先ほどの`R' L F2 R L' U2`と同じように「シフト」することができます。

しかし、エッジ3-cycleのジャングルはこれよりもさらに複雑なのです。たとえば、次の10手のアルゴリズムをチェックしてみましょう。

`U L D R F R' D' L' U' F'` (UF->RU->RF)
{: .text-center}

さらに10手の2-gen 3-cycle[^2-3-3]もあります。

`U R U R U R' U' R' U' R'`  (UF->BR->UR)  
`U R U R U' R' U' R' U' R`  (UF->BR->DR)  
`U R U R U2 R' U' R' U' R2` (UF->BR->FR)  
{: .text-center}

**訳注：**  
この節は特に説明が希薄なので、訳注で補足します。  
Speedsolving.comの[元のスレッド](https://www.speedsolving.com/threads/2-gen-edge-cycles.56224/)でJanWが言っていることは、次のような`[U R U R, X]`型と`[R U R U, X]`の2種類の2-genコミュテータの計6種類を基本手順として、（目隠し解法における）エッジの3-cycleのシステムを作ろうというものです。学ぶべきアルゴリズムの数が非常に少なくなるので効率的なのではないか、という提案です。その後、どの程度使われるようになったかは正確にはわかりません。しかし、3x3x3目隠し競技のトップ層は**呼吸をするようにエッジとコーナー合わせて818種類のコミュテータを使いこなす**(さらに平気でバッファ移行をする)ような記憶オバケですから、あまり流行らなかったのでしょう。もしかすると、3x3x3片手目隠し競技をやりたい方にとっては2-genであることが役立つかもしれません。  
`[U R U R, U]` (UF->BR->UR)  
`[U R U R, U']` (UF->BR->DR)  
`[U R U R, U2]` (UF->BR->FR)  
`[R U R U, R]` (UF->UR->BR)  
`[R U R U, R']` (UF->UL->BR)  
`[R U R U, R2]` (UF->UB->BR)  
{: .notice--info}

<!--
2.3.3 Other Edge 3-cycles
There are also edge 3-cycles that don’t use inner layer moves. In fact, there are some that are
not even commutators! Here are two that are 8 HTM long:
R2 Fw2 R2 U R2 Fw2 R2 U = R2 B2 L2 D L2 B2 R2 U
R2 Fw2 R2 Uw R2 Fw2 R2 Uw = R2 B2 L2 U B2 R2 F2 D
17In a sequence of moves, we say that one or more moves cancel if there are consecutive moves that can be
merged together (as in our example R' R2=R) or that are one inverse to the other (such as L L'). For example,
if our F2L ends with . . . U R2 F', and we want to use the algorithm F R U R' U' F', 3 moves cancel: . . . U R2 F
F' R U R' U' F' = U R' U R' U' F'
18Even in this case there are exceptions: see for example this post by Tomoaki Okayama and the following
discussion: https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-21#post-440873.
19The notation [A:B] = A B A' stands for a conjugate. The sequence A is usually called “setup moves”.
Notice how the first two moves of the first one don’t affect our 3 edges: we can therefore
“shift” it, as we have done before with R' L F2 R L' U2.
But the jungle of edge 3-cycles is more intricated than this. For example, check out this 10
HTM algorithm:
U L D R F R' D' L' U' F'
and some 10 HTM 2-gen 3-cycles20
U R U R U R' U' R' U' R'
U R U R U' R' U' R' U' R
U R U R U2 R' U' R' U' R2
-->
#### 2.3.4 ブロックコミュテータ(Block Commutators)
Ryan Heiseのウェブサイトを注意深く読んだなら、**「ペア3-cycle」**あるいは**「ブロックコミュテータ」**というものについても既にわかっていることでしょう。コーナーコミュテータについて既に知っているなら、これを直感的に理解するのは難しくはありません。たとえば次の例を見てみましょう。

![](../../../assets/img/alg-234-1.png){:width="200px" height="auto" class="align-center"}
`[L Dw' L', U']` = `L Dw' L' U' L Dw L' U`
{: .text-center}

これはHeiseのステップ3でとても役立つ手順です。しかしこれは、コーナー3-cycleとエッジ3-cycleを同時に揃えることができます。たとえば、Last layerのアルゴリズムである`M F U F' U' F' L F R'`は次のように書くことができます。

![](../../../assets/img/alg-234-2.png){:width="200px" height="auto" class="align-center"}
`[R: [L' Dw L, U']]` = `R L' Dw L U' L' Dw' L U R'`
{: .text-center}

これはペアコミュテータにセットアップを加えたものです。PLLのJ permも次のようなペア3-cycleとして書くことができます。

![](../../../assets/img/alg-234-3.png){:width="200px" height="auto" class="align-center"}
`[R2: [Fw2, D B2 D']]` = `R2 Fw2 D B2 D' Fw2 D B2 D' R2`
{: .text-center}
<!--
2.3.4 Block Commutators
If you have read Ryan Heise’s website carefully, you already know something about the so-called
“pair 3-cycles”, or block commutators. If you know corner commutators, it will not be hard to
find them intuitively. For example:
[L Dw' L', U'] = L Dw' L' U' L Dw L' U
They are very useful in Heise’s third step, but also to solve a corner 3-cycle and an edge
3-cycle at the same time. For example, the last layer algorithm M F U F' U' F' L F R' can be
seen as:
[R: [L' Dw L, U']] = R L' Dw L U' L' Dw' L U R'
That is a pair commutator with a setup move.
The J-perm PLL can also be seen as a pair 3-cycle:
[R2: [Fw2, D B2 D']] = R2 Fw2 D B2 D' Fw2 D B2 D' R2
-->
### 2.4 インサーション(Insertions) {#insersions}
このチュートリアルを通じて何度も触れてきましたが、(ようやく)インサーションについて詳しく見るところに来ました。

さて、どうにかしてよいスケルトンを見つけることができたとしましょう。コーナー3-cycleを1回やれば完成するという状態です。ここで何をすればいいでしょうか？　もちろんコミュテータを使ってそのまま3点交換をするとキューブは揃います。しかし、全てのケースを学んでいればわかることですが、コーナーコミュテータは最大で12手もかかります。最もいい場合では8手ですから、そこから4手も増えるのはあまりよくありません。**ところが、コーナー3-cycleをほとんど確実に8手以内でやる方法があるのです！**それが**インサーション**です。

**訳注：**ここではInsertionをそのままインサーションと訳しています。日本語の解説記事では「インサート」と書かれることが多いです。単純に訳すなら「挿入」「差し込み」のことです。スケルトンの中のどこかに8手の3点交換を差し込むことでキューブを完成させることができます。
{: .notice--info}

<!--
2.4 Insertions
After mentioning them multiple times throughout this tutorial, it is (finally) time for looking at
insertions in detail.
We have somehow found a good skeleton; let’s suppose we need to solve a corners 3-cycle to
finish. What do we do now? We can obviously directly solve the cycle with a commutator. But,
if you have studied all the cases, you know that a corner commutator can need up to 12 moves.
Knowing that the best case only needs 8, those 4 more moves are not really nice. But there is
a way to solve a corners 3-cycle almost certainly with fewer than 8 moves: insertions.
-->
#### 2.4.1 単純インサーション(Simple Insertions)
インサーションの背後にある考え方はあまり難しいものではありません。**もしあと3つのコーナーを揃えたら完成するような状態であるとき、スケルトン全体を一手ずつ見ていって、その場所に対応する8手のコミュテータを挿入すれば完成させることができます。**コミュテータは対象となるピース以外にはまったく影響しませんから、3つのコーナー以外の部分（つまりスケルトン）は元々そうであったように全て完成します。そして、3つのコーナーもインサートされたコミュテータによって揃うのです！

これが3-cycleのコーナーをほとんど常に8手で解く仕組みです。では、8手よりももっと短くするにはどうすればいいでしょうか？ 3つのコーナーを揃えることができるコミューテータで、スケルトンの途中にインサートできるものはたくさんあります。**その中から最も多くのキャンセルが起こるものを選びましょう。**通常は、3つのコーナーを揃えるピュアコミュテータ(8手)をチェックするだけで十分です。そのあとで一番いいものを選びましょう。ごく稀に、一番いいインサーションが9手（あるいはそれ以上）のコミュテータであることがありますが、そういう状況はあまり起こらないので、全ての種類のコミュテータをチェックするのはあまり意味がありません。

スケルトンを作ってから、3つのコーナーの動きを追いかけやすくするため、キューブに白いステッカー[^2-4-1]を貼って1、2、3のような番号（あるいはA、B、Cのような文字）[^2-4-1-2]を書くすることを勧めます。以前は、暗めのステッカーがある安いキューブを用意して、その上に鉛筆で書いてしまうことをしていましたが、これもよい方法でしょう。

ソルブの実例を見るともっとわかりやすくなるでしょう。次のスケルトンを安いキューブで回してみましょう。（もしステッカーを貼るなら、どんなキューブでもよいです）

{% capture display_text %}
B' U' D L' F' //EO + blocks
D2 L2 D' L //疑似 2x2x3
U2 R2 U' R' //疑似 2x2x1
U L' U R' U' L U2 R' L' //3コーナー以外完成
{% endcapture %}
{% include solvebox.html
title = "単純コーナーインサーション - Example (スケルトン)"
scramble = "D B2 U' F2 L2 D2 R2 U F2 U2 L2 R' D2 B L' U' R2 F2 R B F2"
text = display_text
solution = "alg.cubing.net"
img_src="../../../assets/img/alg-241.png"
algcubing = "https://alg.cubing.net/?setup=D_B2_U-_F2_L2_D2_R2_U_F2_U2_L2_R-_D2_B_L-_U-_R2_F2_R_B_F2&alg=B-_U-_D_L-_F-_%2F%2FEO_%26%232b%3B_blocks%0AD2_L2_D-_L_%2F%2FPseudo1_2x2x3%0AU2_R2_U-_R-_%2F%2FPseudo_2x2x1%0AU_L-_U_R-_U-_L_U2_R-_L-_%2F%2FAll_but_3_corners"
%}

さて、ステッカーを持ってきて貼り、青-赤-黄コーナーの赤ステッカー(ULB)の上に「1」、青-黄-橙コーナーの橙ステッカー(RDB)に「2」、橙-青-白コーナーの白ステッカー(LDB)に「3」と書きましょう[^2-4-1-3]。キューブを揃えて、またスクランブルしましょう。（たとえば`L B2 L F L' B2 L F' L2`などで揃います）[^2-4-1-3-2]

スクランブル後、3つのコーナーを最初からすぐに揃えることもできますが、9手かかります。(`R2 F R B2 R' F' R B2 R`)　なので、まずはスケルトンの最初の1手(`B'`)を回してもっとよいケースがないかを探しましょう。さらに次のムーブ(`U'`)[^2-4-1-4]を回すと、ターゲットの3つのコーナーを8手コミュテータで揃えられます！(`L2 F R F' L2 F R' F'`)　もしこれを採用したいなら、最終解答は次のようになります。

`B' U'` `L2 F R F' L2 F R' F'`{: .codestrong} `D L' F' D2 L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'`
{: .text-center}

実際に試してみて、ちゃんと揃うことを確認してみましょう。

何にせよ、もっとうまくやることができます。次のムーブ(`D`)を回すと9手のコミュテータが必要であることがわかります[^2-4-1-5]。この調子で何手か進んでいくと、やがて`L' F' D2`までたどりつきます。ここで3つのコーナーを8手(`D' F2 D B2 D' F2 D B2`)[^2-4-1-6]で揃えてみましょう。しかし、これで終わりではありません。最後の1手とコミュテータの最初でキャンセルがあります！これを採用するなら、次のように書きましょう。

`B' U' D L' F' D2` `D' F2 D B2 D' F2 D B2`{: .codestrong} `L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'`
{: .text-center}

これは次のようにまとめても同じことです。

`B' U' D L' F'` `D F2 D B2 D' F2 D B2`{: .codestrong} `L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'`
{: .text-center}

**1手少なくなりましたね！**　3つのコーナーを7手で揃えることができました。

ちゃんと網羅するために、スケルトンの最後までもっとよいインサーションがないかを探してみましょう。実は、一番いいインサーションは後ろのほうにあります。

`B' U' D L' F' D2 L2 D' L U2 R2 U' R' U L' * U R' U' L U2 R' L'`  
`*` = `L F' L' B L F L' B'`
{: .text-center}

この書き方は、一行目の`*`と書かれたところを二行目の内容で置き換えるという意味です。最終解答は次のようになります。

`B' U' D L' F' D2 L2 D' L U2 R2 U' R' U L'` `L F' L' B L F L' B'`{: .codestrong} `U R' U' L U2 R' L'`
{: .text-center}


明らかに`L`と`L'`でキャンセルします。なので、

`B' U' D L' F' D2 L2 D' L U2 R2 U' R' U F' L' B L F L' B' U R' U' L U2 R' L'`
{: .text-center}

となります。さらに説明を重ねなくても、エッジ3-cycleでのインサーションの探し方はわかることでしょう。同じことを、次のアルゴリズムで揃えられるようなエッジ2-cycleを二回繰り返すことでもできます。

`M2 U2 M2 U2`  
`R2 U2 R2 U2 R2 U2`  
`U2 L2 D2 R2 D2 L2`  
{: .text-center}

ここに書いたもののほかに、様々なバリエーションがあります。シフトしてみてください[^2-4-1-7]。エッジを揃えるほかのもっと発展的な方法はフリースライス(free slices)を使うことです。([3.8節](chapter3#freeslice)を参照のこと)

最後にもう一つだけヒントを書いておきましょう。180度のムーブ(`U2`など)は8手コミュテータの最初や最後にあるのは、それがインターチェンジ(interchange)である場合です。つまり、同じ面にある2点交換をしているということです。この事実がわかっていると時間を節約できます。2手以上のキャンセルを狙っているとき（これは常に狙うべきです！）、2点交換がない限り、このようなムーブは完全にキャンセルすることはないと推測できます。前後でキャンセルをするようなコミュテータだけを探せばいいでしょう。

<!--
2.4.1 Simple Insertions
The idea behind insertions is not too difficult: if there are only 3 corners left to solve, I can go
through my whole skeleton move by move and solve them when the corresponding commutator
only requires 8 moves. Since that commutator doesn’t affect anything but the pieces that need
to be affected, the rest of the solution will solve every other piece, as it did before, and those 3
corners will also be solved, since I have cycled them with the inserted commutator.
This is how to solve almost always a 3-cycle of corners with 8 moves. How can we improve
this? Among all possible inserted commutators that solve our 3-cycle, we simply choose the one
that cancels the most moves. Uusually, it is enough to just check the cases where our 3 corners
can be solved with a “pure” commutator, and then choose the best one. It happens extremely
20For these cases, this thread by JackW on speedsolving.com gives some explanation: https://www.
speedsolving.com/forum/threads/2-gen-edge-cycles.56224/
rarely that the best insertion is given by a 9 move commutator (or longer), but situations like
this are so unlikely that it is not worth to check every possible type of commutator.
In order to make it easier to follow the movements of the 3 corners while going through your
skeleton, many suggest stickering the cube with white stickers21 on which writing numbers 1, 2
and 3 (or letters A, B and C if you prefer)22. Personally, I suggest taking a cheap cube with
non-bright stickers and writing on it with a pencil.
An example solve will make everything clearer. Try the following skeleton on your cheap
cube (or any cube, if you use stickers).
Simple Corner Insertion - Example (Skeleton)
Scramble: D B2 U' F2 L2 D2 R2 U F2 U2 L2 R' D2 B L' U' R2 F2 R B F2
B' U' D L' F' //EO + blocks
D2 L2 D' L //Pseudo 2x2x3
U2 R2 U' R' //Pseudo 2x2x1
U L' U R' U' L U2 R' L' //All but 3 corners
See on alg.cubing.net
At this point, grab a pencil and write “1” on the red sticker of the blue-red-yellow corner,
“2” on the orange sticker of the blue-yellow-orange corner and “3” on the white sticker of the
orange-blue-white corner.23 Solve the cube (for example with L B2 L F L' B2 L F' L2) and
re-scramble it.
We could solve the three corners right at the beginning, but we would need 9 moves (R2 F
R B2 R' F' R B2 R). So lets perform the first move of the skeleton (B') and see if we have a
better case: no, still 9 moves. Perform the following move (U')
24 we can now solve our three
corners with an 8 moves commutator (L2 F R F' L2 F R' F')! If we wanted to use it, the final
solution to submit would be:
B' U' L2 F R F' L2 F R' F' D L' F' D2 L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'
Try it out and convince yourself it works.
Anyways, we can do better. Perform the next move (D) and notice that this case requires 9
moves25. Go on this way for some more move, until you reach . . . L' F' D2. We can again solve
our three corners with 8 moves (D' F2 D B2 D' F2 D B2)
26. But there is more: the last moved
performed and the first of our commutator cancel! If we wanted to solve the three corners now,
we should write:
B' U' D L' F' D2 D ' F2 D B2 D' F2 D B2 L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'
Which is equivalent to:
B' U' D L' F' D F2 D B2 D' F2 D B2 L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'
21This is why you are allowed to bring with you “unlimited colored stickers” at a competition.
22Sticker need to be attached so that the 3-cycle that moves 1 to 2, 2 to 3 and 3 to 1 is the one that solves the
cube.
23There are many equivalent enumerations: you can start from the corner and from the sticker you wish, you
just have to be coherent.
24Watch out: when in a skeleton there are two consecutive parallel layers moves try swapping them too see if
this gives better insertions. This is not the case, but you never know.
25The last 2 moves (U' D) are equivalent to an inner-layer move (E'), so they don’t affect corners: it is reasonable
that, before and after these moves, our 3-cycle is the same, modulo a rotation (y'/y in this case).
26Also B2 U' F' U B2 U' F U
One move less, yay! So we got to solve 3 corners with 7 moves.
For the sake of completeness, we should continue until the end of the skeleton looking for
better insertions. Actually, the best insertion is towards the end:
B' U' D L' F' D2 L2 D' L U2 R2 U' R' U L' * U R' U' L U2 R' L'
* = L F' L' B L F L' B'
The notation above means that you should replace the * in the first line with sequence of
moves in the second line. The final solution is
B' U' D L' F' D2 L2 D' L U2 R2 U' R' U L' L F' L' B L F L' B' U R' U' L U2 R' L'
Where L and L' obviously cancel, so:
B' U' D L' F' D2 L2 D' L U2 R2 U' R' U F' L' B L F L' B' U R' U' L U2 R' L'
Without further explanation you should understand how to find insertions for edges 3-cycles.
You do the same also for double edges 2-cycles, solvable with one of the following algorithms:
M2 U2 M2 U2
R2 U2 R2 U2 R2 U2
U2 L2 D2 R2 D2 L2
and variations (try shifting)27
.
One last tip: 180 degrees moves (such as U2) can be found at the beginning or at the end of
an 8-moves corner commutator only when they are the interchange move, i.e. when they swap
two cycle pieces on the same layer. This fact can be used to seva some time: if you are aiming
at cancelling two or more moves (and you should be) you can assume such a move won’t cancel
completely, unless it swaps two of you pieces, and only look for commutators that cancel with
moves after (or before) that one.
-->
#### 2.4.2 複数インサーション：別々のサイクル(3エッジ、3コーナー) (Multiple Insertions: Separated Cycles (3 Edges and 3 Corners))
スケルトンは常に3-cycleだけが残ったものとは限りません。インサーションはもっと多くの（もっと長い）サイクルでも使うことができます。

既に見たように、3-cycle（コーナーとエッジ）が2回あるような場合は、**ペアコミュテータ**（必要ならセットアップも含めて）で揃えることができます。別のやり方は、「セクシームーブ」や「Sune」(`R U R' U R U2 R'`)やその派生を使ってエッジを揃えることです。これによって必要なコーナーだけに影響を与えることができます[^2-4-2]。これについては2.4.8節を参照してください。どのやり方も頭にとどめておくとよいですが、簡単に使えることはあまりありません。「標準的な」手法は**2つのコミュテータをインサートすることです。**

コーナーとエッジに番号を振ったあとで[^2-4-2-2]、一手ずつ単純なインサーションを探して進んでいきますが、全ての箇所でコーナーとエッジの解法を見ていきましょう。さらにペアコミュテータとSuneもチェックします。終わったら、2つのインサーションによる最終解答を書くこともできますが、別のやり方を試してみることもできます。たとえば、コーナーコミュテータを残しておきたいけれど、もっといいエッジの交換を探したいとき、コーナーコミュテータだけをインサートした解答をまず作りましょう。ここでできたものが、**3つのエッジだけが残り、数手だけ長くなった新しいスケルトンです。** ここからは単純な(エッジ)インサーションで揃えられます。他の方法もあるなかで、こうすべき理由はなんでしょうか？ それは、**他のコミュテータの手順の中に、エッジコミュテータをインサートするよいポイントが見つかることもあるからです。** 逆に、エッジの交換をインサートしてからコーナーのインサーションをやることもできます。

次のソルブが単純な実例です。

{% capture display_text %}
B' R' * F2 U F2 //2x2x1 (5/5)
R //もう一つ2x2x1 (1/6)
F R U2 F R B R + B' R //F2L-1 + pair (9/15)
D' B' L B L' //3エッジ3コーナー以外完成 (5/20)
* = U B U' F2 U B' U' F2 //3コーナー, 4手キャンセル(8-4/24)
+ = R B' F D' B' D B F' R' B //3エッジ, 5手キャンセル(10-5/29)
{% endcapture %}
{% include solvebox.html
title = "別々の交換をインサートする - Example"
scramble = "B2 D' R2 D' F2 R2 D B2 U' L2 D2 R' U' R L' D' F D2 B R U2 R'"
text = display_text
solution = "B' R' U B U' F2 U B' F2 R F R U2 F R B R2 B' F D' B' D B F' D'
B' L B L' (29)"
img_src="../../../assets/img/alg-242.png"
algcubing = "https://alg.cubing.net/?alg=B-_R-_(U_B_U-_F2_U_B-_U-_F2)_F2_U_F2_%2F%2F2x2x1_(5%2F5)%0AR_%2F%2FAnother_2x2x1_(1%2F6)%0AF_R_U2_F_R_B_R_(R_B-_F_D-_B-_D_B_F-_R-_B)_B-_R_%2F%2FF2L%26%2345%3B1_%26%232b%3B_pair_(9%2F15)%0AD-_B-_L_B_L-_%2F%2FAll_but_3_edges_and_3_corners_(5%2F20)%0A%0A&setup=B2_D-_R2_D-_F2_R2_D_B2_U-_L2_D2_R-_U-_R_L-_D-_F_D2_B_R_U2_R-"
%}

**ここでは `(8-4/24)` という記法を使いました。これはインサートされた手数は8手であり、そのうちの4手がキャンセルされたという意味です。**

2つ以上ある別々の交換が必要なケースについても、全く同じアプローチをすることができますが、もっと複雑になるでしょう。たとえば、6つのコーナーが残って、2つのコミュテータで揃えられるような場合です。

<!--
2.4.2 Multiple Insertions: Separated Cycles (3 Edges and 3 Corners)
A skeleton doesn’t have to always leave one 3-cycle: insertions can also be used to solve more
(or longer) cycles.
As we have already seen, two 3-cycles, a corner 3-cycle and an edge 3-cycle, can be solved
with a pair commutator (with setup moves, if necessary). Another way is to solve the edges
with a “Sune” (R U R' U R U2 R') or a variation of it, so that the only corners affected are the
ones we need to cycle28. Both these ways should be kept in mind, but they are rarely easy to
use. The “standard” solution is to insert two commutators.
After having numbered both the corners and the edges29, proceed move by move as you
would do with simple insertions, but at every spot you look both for a solution for corners and
one for edges, besides checking for pair commutators and Sunes. Once you are done, you can
write down the final solution with two insertions, but you can also do another pass: if you
want to keep, for example, the corner commutator, but you want to look for a better edge cycle,
you can write down your solution with only the corner commutator inserted. What you have
now is a new skeleton, a few moves longer, which only leaves 3 edges. At this point you can
solve them with one simple insertion. Why should we do this, when we could get anything to
work with only one pass? Because a good place to insert the edge commutator can be inside
the other commutator. You can also insert the edge cycle first and then look for a corner
insertion.
The following solve is a simple example.
27You can also solve this case with a double insertion, as with corners double 2-cycles, see later sections.
28Which still need to be solved somehow, possibly with another insertion.
29I prefer to use numbers for corners and letters for edges, so that I can’t mistake one for another.
26 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
Separated Cycles Insertions - Example
Scramble: B2 D' R2 D' F2 R2 D B2 U' L2 D2 R' U' R L' D' F D2 B R U2 R'
B' R' * F2 U F2 //2x2x1 (5/5)
R //Another 2x2x1 (1/6)
F R U2 F R B R + B' R //F2L-1 + pair (9/15)
D' B' L B L' //All but 3 edges and 3 corners (5/20)
* = U B U' F2 U B' U' F2 //3 corners, 4 moves cancel
(4/24)
+ = R B' F D' B' D B F' R' B //3 edges, 5 moves cancel
(5/29)
Solution: B' R' U B U' F2 U B' F2 R F R U2 F R B R2 B' F D' B' D B F' D'
B' L B L' (29)
See on alg.cubing.net
You can use exactly this approach for other cases that require you to solve two or more
cycles (3 cycles or double 2-cycles) that are separated. In all other cases, things get a bit more
complicated.
-->
#### 2.4.3 複数インサーション: 2つあるいは3つのねじれコーナー(Multiple Insertions: 2 or 3 Twisted Corners)

2つのねじれたコーナーが残ったとき、どこかで`[F L' D2 L F', U2]`(12手) というコミュテータを試してみるといいでしょう。3つある場合は、`U' B U' F U2 B2 D' R2 U D F' U' B`(13
手)も使えます。しかし、特に2つ目については最良ではないことが多いです。

2つあるいは3つのねじれはコーナーを揃える古典的手法は、**コーナーコミュテータを2回インサートすることです。** 1回目のコミュテータでは、3つのねじれたコーナー（あるいは2つのねじれたコーナーと、それ以外のコーナー）を交換するだけで十分です、通常、多くのキャンセルが見込めます。そこから先は、新しくできたスケルトンに単純なコーナーコミュテータをインサートすればよいだけです。

こうするためには、ねじれたコーナーに「X」などの記号を描いたりステッカーを貼ったりしておけばよいだけです。上に書いたような、「純粋に反転させる（pure flip）」アルゴリズムを使いたい場合は、矢印を描いておいて、どの方向（時計回り、反時計回り）に回転させるべきなのかわかるようにしておくといいでしょう。

1つめの交換が見つかったら、描いた記号を消して（単純なインサーションを探すのと同じように）1、2、3と番号を書きましょう。

2つのエッジがねじれているときにも同じことができますが、おすすめしません。エッジコミュテータはもっと手数がかかることが多いからです。

インサーションを2回行うお勧めのアプローチをするときには、次にことに気を付けてください。**それぞれのピースの一つのステッカーに印をつけたとしても、印のついていない別のステッカーとのコミュテータを探してしまうことがあります。** この問題を避けるために、私はねじれたピースのすべてのステッカーに印をつけています。

<!--
2.4.3 Multiple Insertions: 2 or 3 Twisted Corners
When you need to twist 2 corners, you can try to insert the commutator [F L' D2 L F', U2]
(12 HTM) somewhere; for three corners, you can use U' B U' F U2 B2 D' R2 U D F' U' B (13
HTM). But this is usually not the best way, especially in the second case.
The classic way to solve 2 or 3 twisted corners is to use two inserted corner commutators.
The first one only needs to cycle in any way the three twisted corners (or the two twisted corners
+ one random corner) and will usually lead to many cancellations. Then you only need to insert
a simple corner commutator in the new skeleton you have got.
To do this, you only need to draw an X or any other symbol on the twisted corners; if you
want to try to use one of the “pure flip” algorithms written above, I suggest drawing an arrow,
so that you can tell which way you need to twist your corner (clockwise or counterclockwise).
After finding the first cycle, erase the symbols you have drawn and number the stickers 1, 2
and 3.
You can do the same with two flipped edges, but I suggest avoiding such a case, because
edge commutators usually require more moves.
-->
#### 2.4.4 複数インサーション:4つのコーナー(Multiple Insertions: 4 Corners)
唯一の悪いケースである、3回のインサーションが必要な4つのコーナーが残った場合は、**コーナーの位置は正しいけれどねじれているという状態です。**なるべくなら避けたいですが、もし避けられない（あるいはスケルトンが本当に短い）なら、前の節で書いたような1つ目のインサーションをやって、4つのコーナーがよい配置になるようにしてもいいでしょう。この状況に関しては、speedsolving.comによいディスカッションがあります[^2-4-4]。
<!--
2.4.4 Multiple Insertions: 4 Corners
If you have 4 corners left, the only bad case, requiring three inserted commutators, is when the
corner are all placed but twisted. Try to avoid it, but if you can’t (or if the skeleton is really
short), you can proceed as in the previous section for te first insertion, in order to reduce to a
better 4 Corners case. About this situation, there is a nice discussion on speedsolving.com30
.
-->

その他に次の3つのケースがあります。

1. **1つのコーナーの場所はあっているがねじれている。**他の3つのコーナーは「ねじれた3点交換」になっている。つまり、向きを考えずに位置だけを考えた3点交換。
1. **2つのコーナーのペアが違いに入れ替わっており、向きが合っている。**（2回のスワップ、あるいは回の2点交換）  
後で話をするやり方でも解けますし、コーナーの2回スワップをエッジの2回スワップに組み替えることでも解けます。たとえば、H perm (`M2 U M2 U2 M2 U M2`)に1手（`U2`)加えることで、コーナーの位置合わせに変えられることがわかるでしょう。`(R U R' U') x 3` (トリプルセクシー)や`(R' F R F') x 3`(トリプルスレッジ)、`(R2 U' Rw2 U F2) x 2`のようなアルゴリズムでも2つのコーナーペアをスワップできます。
1. **ねじれたコーナーの2回スワップ**

これらのケースは全て**2回のコミュテータで揃えらえます。** 1回目で4つのコーナーのうち1つを揃えて、他の3つのコーナーに適当な影響を与えましょう。そして、1回目のインサーションで新しいスケルトンができますから、2回目では残った3つのコーナーを揃えればいいのです。

この1回目のインサーションについて、1つめのケース（場所はあっているがねじれている）ではもう一つ制約があり、**「場所は合っているけれどねじれている」コーナーを1回目のコミュテータに含めなければなりません。** 含めないと、2つあるいは3つのねじれたコーナーがある状態が残り、さらに2回インサートしなければならなくなります。

これを間違いなくやるために、私は次のようにコーナーに印をつけます。

1. **ねじれた3点交換 + ねじれたコーナー x 1** : ねじれたコーナーに「X」と印をつけます。ねじれている向きは気にしません。そして、他の3つのコーナーに1から3までの番号を振ります。このとき、ねじれた交換なので、**1は2になり、2は3になりますが、3は1ではなく同じコーナーの別のステッカー[^2-4-4-2]になります。**これは大したことではなく、その別のステッカーに4と番号を振れば大丈夫です。
1. **ダブルスワップ** : 最初のコーナーのペアにXと印をつけて、次のコーナーのペアにAと印をつける。
1. **ねじれたダブルスワップ** : ねじれた3点交換には4つの番号を振る必要があり、ねじれた2点交換には3つの番号を振る必要があるので、2点交換には1から3までの番号を、それ以外にはAからCを振る。

たとえば、1つ目のケースでは、可能な「最初のサイクル」は**Xを3に、3を4に、4をXに、**というものがあります。1->2->3->1というのはよいサイクルではなく、3点交換ではなく2つのねじれたコーナーが残ってしまいます。

素晴らしい例は次のソルブです。これは、**João Pedro Batista Ribeiro Costaの南アフリカ記録のものです。**解答の説明は私が少し修正しました。元々のものはプリムーブ(premove)を使っていました。プリムーブ(premove)については、次の章の[3.2.2節](chapter3#premove)で説明します。

{% capture display_text %}
F D' + U2 * R //EO
D' F' L2 //疑似 2x2x2
F2 D F2 //疑似 F2L-2
B' D B //疑似 F2L-1
F' D' F' L2 //4コーナー以外完成
* = U R D' R' U' R D R' //1つ目のコミュテータ
+ = L' U' R' U L U' R U //2つ目のコミュテータ
{% endcapture %}
{% include solvebox.html
title = "João Pedro Batista Ribeiro Costaの元南アフリカ記録(SAR)"
scramble = "L' U2 D' L' U2 B' D B' L U2 F2 R2 F' R2 L2 F' U2 D2 F"
text = display_text
solution = "F D' L' U' R' U L U' R2 D' R' U' R F' L2 F2 D F2 B' D B F' D' F' L2 (25)"
img_src="../../../assets/img/alg-244.png"
algcubing = "https://alg.cubing.net/?alg=F_D-_(L-_U-_R-_U_L_U-_R_U)_U2_(U_R_D-_R-_U-_R_D_R-)_R_%2F%2FEO%0AD-_F-_L2_%2F%2F2x2x2%0AF2_D_F2_%2F%2FPseudo_F2L%26%2345%3B2%0AB-_D_B_%2F%2FF2L%26%2345%3B1%0AF-_D-_F-_%2F%2FAll_But_4_Corners&setup=_L_U2_D-_L-_U2_B-_D_B-_L_U2_F2_R2_F-_R2_L2_F-_U2_D2_F"
%}

最初ほうにインサートされたコミュテータ（2つ目のコミュテータ、＋）は後で見つけられたものです。2つ目のコミュテータのほうが早い段階でインサートされています。これでもまったく問題ありません！

さらに、2つのコミュテータの間でお互いに何手かキャンセルをしています。

<!--訳者TODO：この節は全般に文字だけでわかりにくく感じるので、追加の絵を入れてもよい-->

<!--
There are three other cases:
1. One corner is placed but twisted, the other 3 form a “twisted 3-cycle”, i.e. a 3-cycle if you only regard permutation, without considering orientation. A twisted cycle always depends on some other twisted piece (or cycle).
2. Two pairs of corners that need to be swapped, correctly oriented (double swap or double
2-cycle). This case can be solved, besides using the method that will soon be described,
also by transforming the corner double swap in an edge double swap: remember that an
H perm (M2 U M2 U2 M2 U M2) can be transformed in a corner permutation with only
one move (U2). Another way it so use algorithms such as (R U R' U')*3 (“triple sexy”)
or (R' F R F')*3 (“triple sledge”), that swap two corner pairs.
[^2-4-4]: http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-126#post-1009830
2.4. INSERTIONS 27
3. A “twisted double swap”.
All these cases can be solved with two commutators: the first one has to solve one of the
4 corners, freely affecting the other 3, while the second one, which should be inserted in the new
skeleton obtained after the first insertion, has to solve the 3 corners left. For the first step, you
have only one morelimitation in the first of the three cases: the “twisted in place” corner has
to be affected by the first commutator. If it isn’t, you are going to end up with two or three
twisted corners, still requiring two insertions.
To do so, I mark the corners as follows, depending on the case:
1. 1. I mark the twisted corner with and X (I don’t care which way it needs to be twisted),
then I number the other three from 1 to 3. At this point, since the cycle is “twisted”, 1
belongs to 2, 2 to 3 while 3 doesn’t belong to 1, but to another sticker on that corner31
.
No problem: just mark that sticker with a 4.
2. I mark the first pair of corner with two Xs and the second one with two As.
3. Since we needed 4 numbers for a twisted 3-cycle, for a twisted 2-cycle we will need 3:
reasoning as in the first case, number one of the 2-cycles 1 to 3 and the other A to C.
In the first case, for example, a possible “first cycle” is the one that sends X to 3, 3 to 4 and
4 to X. The cycle 1 → 2 → 3 → 1 is not good, because it leaves 2 twisted corners instead of a
3-cycle.
An excellent example is the following solve, previous South American Record by Jo˜ao Pedro
Batista Ribeiro Costa. I have slightly modified the explanation of the solution: the original one
made use of a premove, a technique treated in the next Chapter.
Former SAR (by Jo˜ao Pedro Batista Ribeiro Costa)
Scramble: L' U2 D' L' U2 B' D B' L U2 F2 R2 F' R2 L2 F' U2 D2 F
F D' + U2 * R //EO
D' F' L2 //Pseudo 2x2x2
F2 D F2 //Pseudo F2L-2
B' D B //Pseudo F2L-1
F' D' F' L2 //All But 4 Corners
* = U R D' R' U' R D R' //First commutator
+ = L' U' R' U L U' R U //Second commutator
Solution: F D' L' U' R' U L U' R2 D' R' U' R F' L2 F2 D F2 B' D B F' D' F' L2 (25)
See on alg.cubing.net
A further comment on the solve. Notice that the commutator inserted earlier in the solve
(the one labelled with +) is actually the one one found for last, even if just by one move. Vice
versa the second one in the solve was inserted earlier. That’s perfectly fine!
Moreover, the two commutator cancel some move with one another.
-->
#### 2.4.5 複数インサーション: 5つのコーナー (Multiple Insertions: 5 Corners)
5つのコーナーが残ったケースの中で、2回のコミュテータだけで揃えられるのはピースが5点交換になっている場合のみです。それ以外のケースでは、3回のコミュテータが必要です。ただし、5つのコーナーの配置は合っているがねじれているという場合には、4回必要となります。ここでは、3回以上のコミュテータが必要なケースについては触れず、最初のケースについてだけ見てみることにします。（3回のインサーションをやってみたいときもあるでしょうけれど）

さて、こういうときに最も簡単でよく使われる手法は、**4つのコーナーのとき同様に、2段階で解くことです。**コーナーに1から5までの番号を振ったあと、スケルトンを最初から1手ずつ追いかけていき、3つのつながったコーナーの交換を揃えられるコミュテータがないかを探していくわけです。このサイクルは、たとえば次のようなパタンがあります。

`1 → 2 → 3 → 1`  
`2 → 3 → 4 → 2`  
`3 → 4 → 5 → 3`  
`4 → 5 → 1 → 4`  
`5 → 1 → 2 → 5`
{: .text-center}

<!--
2.4.5 Multiple Insertions: 5 Corners
Among all the cases with 5 corners left, the only one that requires 2 commutators is the one
where the pieces make a 5-cycle. All other cases require 3 commutators, except when you have
5 corners placed but twisted: in that case you need 4. Here I will ignore any case requiring 3 or
more commutators (although in some cases you may want to go for 3 insertions) and only look
at the first one.
The easiest and probably the most used way to deal with this situation is a two-pass way,
as for 4 corners. After having numbered the corners 1 to 5, you go through the skeleton move by move and look for any commutator that solves a three consecutive corners cycle.These cycles
are:
1 → 2 → 3 → 1
2 → 3 → 4 → 2
3 → 4 → 5 → 3
4 → 5 → 1 → 4
5 → 1 → 2 → 5
-->
当然、単にコーナーの交換をひとつだけ探すよりも時間がかかります。ここでも変わらずピュアコミュテータを探すだけで十分です。いいコミュテータが見つかるたびに、どこかにメモしておきましょう。

この1段階目が終わった時点で、**見つかったコミュテータのなかから一番いいもの（一番多くキャンセルするもの）を選びましょう。**次にそのコミュテータをインサートして、コーナーの3点交換だけが残った新しいスケルトンを得ます。ここからどうすればいいかはわかるでしょう。

一番いいものは一つではないこともあります。たとえば、3手キャンセルするコミュテータを2つ見つけることもあるでしょう。では、どちらを選べばいいでしょうか？ 時間がないときには、適当に決めてしまいましょう。時間に余裕があるなら、両方のインサーションを試してみて、2つ目のコミュテータがよくなるものを選びましょう。
<!--
This will obviously take longer than looking for just one corner cycle. It is still enough to just look for “pure” commutators. Every time you find a good commutator write it down somewhere.
Once you are done with this first pass, choose the best commutator you have found (the one
cancelling the most moves)1. Insert that commutator; now you have a new skeleton that only
leaves a corner 3-cycle: you know what to do.
The best choice may not be unique (for example, if you have found two different commutators
canceling 3 moves). Which one should we choose? If you are short on time, just randomly choose
any of them. If you have some time left, you can try both insertions and which one leads to the
best second commutator.
-->

この手法を使うとき、**最適な解答が見けられたかどうか、確信も持つことはできないでしょう。**なので、安全を取って、1段階目で見つかった全てのコミュテータ（あるいはそのほとんど）をチェックして、2段階目をたくさん（ほとんど意味のないものも）試してみるといいでしょう。通常、これはとても時間の無駄になりますし、よい解答になることは滅多にありません。解答をもっとよくできるかどうかわからないときは、基準として**「5つのコーナーの交換を10手か11手で揃えられれば満足できる結果である」**ということを覚えておきましょう。

<!--
With this method you can’t be sure you have found the optimal solution: to be safer, you
should check all (or at lest most) of the commutators you have found in the first pass and do
many other (probably useless) passes. This usually leads to a huge waste of time and rarely to
a better solution.
If you don’t know whether you can improve your solution, keep in mind that 10 or 11 moves total are a good goal for a corner 5-cycle.
There is also a faster, but slightly more complex, way that only requires one-pass. It is
almost identical to the first pass of the two-pass way, but besides taking note of any commutator
you have found, you should also write down which corner cycle it solves. At this point, without
even touching the cube anymore, you are already able to choose a pair of commutators that will
solve the corner 5-cycle.
-->

仕組みを理解するには、置換理論(permutation theory)が少し必要です。心配しないでください、本当に重要なところだけに絞ります[^2-4-5]。

まずは、置換の標準的な記法にしたがって、ここでの交換を次のように書きます。

`(1 2 3 4 5)`
{: .text-center}

これはコーナー1はコーナー2になり、2は3になり…5は1になる、ということを表しています。この記法を使うとき、この交換は`(2 3 4 5 1)`、`(3 4 5 1 2)`などと等価です。3点交換`(a b c)`を書くうえで、3つの数字は`1 2 3 4 5 1 2`と連続しているというルールを使いましょう。

ここでやりたいことは、5点交換を2つの3点交換に分けることです。たとえば

`(1 2 3) (3 4 5)`
{: .text-center}

のように書きます。

しかし、上に示した分解は間違いです。理由を知りたい方は、脚注に書いたいくつかのspeedsolving.comの投稿を読んでみてください。あるいは、もっと実用的なアプローチをしたいのであれば、実際にやってみてください！（うまくいきません！）

重要なことは、正しい分解（の例）は次のようになるということです。

`(1 2 3) (4 5 1)`  
`(2 3 4) (5 1 2)`  
`(3 4 5) (1 2 3)`  
`(4 5 1) (2 3 4)`  
`(5 1 2) (3 4 5)`
{: .text-center}

つまり、**1つ目の交換の最初の数字は、2つ目の交換の最後の数値と同じでなければなりません。**

**順序が大切であることも忘れないようにしてください。**見てわかるように、`(1 2 3)`は、後に`(4 5 1)`が来るか、前に`(3 4 5)`が来るかしかありません。これはどういうことかというと、たとえば、`(1 2 3)`を揃えるいいコミュテータを見つけたなら、`(4 5 1)`を揃えるコミュテータをその後のどこかで使うか、`(3 4 5)`を揃えるコミュテータをその前のどこかで使うか、選ばなければならない、ということです。ここに挙げた交換の組について、同じようにやることができます。

この手法は他のものより速くできますが、**「ネストされたインサーション (nested insertions)」、つまり別のインサーションの中にインサートするときには使うことはできません。** そのため、時間がない時にだけ使うか、予備的な分析としてやるといいでしょう。つまり、こうやると何手くらいかかるのかを確認して、2段階目でいい結果になるコミュテータだけをチェックするというやり方です。
<!--
To understand how, we need some permutation theory; don’t worry, I will cut it down to
the essential.32
First of all, written with the usual notation, our cycle is:
(1 2 3 4 5)
which means that the corner 1 belongs to 2, 2 to 3,. . . and 5 to 1. With this notation, this
cycle is equivalent to (2 3 4 5 1), (3 4 5 1 2) and so on. In writing down our 3-cycles (a b c) we
will use the rule that our 3 digits must be consecutive in the string 1 2 3 4 5 1 2.
What we want to do is to break this 5-cycle into two 3-cycles, for example:
(1 2 3) (3 4 5)
But this decomposition doesn’t work. If you want to know why you can read some of the
posts I have linked in the footnote. Or, if you prefer a more practical approach. . . try it out!
The important thing is that the correct possible decompositions are:
32An interesting further reading is the discussion started by this post [1] in the FMC thread on speedsolving.com.
In particular this post [2], a mathematical proof of the “rule” for finding a 3-cycle combination to solve a 5-cycle;
this other one[3], which is the same explanation I give here (it is where I have learned this technique); and this
[4] is an example solve using this method.
[1]: https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666185
[2]: https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666199
[3]: https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666209
[4]: https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-51#post-666313
2.4. INSERTIONS 29
(1 2 3) (4 5 1)
(2 3 4) (5 1 2)
(3 4 5) (1 2 3)
(4 5 1) (2 3 4)
(5 1 2) (3 4 5)
So, the first number of the first cycle must be the same as the last number of
the second cycle.
Notice that the order is important: as you can see, (1 2 3) can be followed by (4 5 1) or
preceded by (3 4 5). This means that once you have found a good commutator that solves, for
example, (1 2 3), to complete the solve you can choose between a commutator that solves (4 5
1) somewhere after it or for a commutator that solves (3 4 5) somewhere before it. You can do
the same with any of the listed pairs of cycles.
This method, although faster than the other one, doesn’t allow you to check for “insertions
inside insertions”. Therefore, I advise using it only if you are short on time, or as “preliminary
analysis”: try to see how many moves you can get this way, and in the second pass only check
for commutators that may lead to something better.
-->
#### 2.4.6 複数インサーション: 5つのエッジ(Multiple Insertions: 5 Edges)
通常、5点交換の場合でもエッジのケースは避けることが望ましいです。それでもやるなら、コーナーについて説明したのと同じ手法を使うこともできます。しかし、非常に少ない手数で揃えられるケースが一つあります。5点交換を6手でやるときに

`M' U M U'`
{: .text-center}

が使えます。セットアップが何手かかかる場合でも、非常にいいでしょう。どんなケースで使えるのか、派生はどんなものがあるか、調べてみるといいでしょう。これをシフトした`L F L' R U' R'`というものもあります。エッジの5点交換が残ったスケルトンを得たなら、ステッカーに番号を振ってすぐにこの類のアルゴリズムが使えるかどうか調べてみましょう。しかし、探すのにあまり時間を掛けすぎないようにしてください。

エッジの5点交換を揃える別の方法は、**3点交換とダブルスワップ(2点交換の繰り返し)を組み合わせることです。**たとえば、最初の3点交換で5つのうち1つのエッジだけが揃うならば、ダブルスワップが残ることになります。逆に考えても同じで、最初にダブルスワップをインサートして2つのエッジだけが揃ったとすると、3点交換が残ることになります。このテクニックは最初にエッジの向きを揃えておいたときによい結果をもたらすことでしょう。

さらに発展的なエッジのインサーションについては、[3.8節](chapter3#freeslice)で触れます。

<!--
2.4.6 Multiple Insertions: 5 Edges
As usual, even for 5-cycles the edge case is preferably to avoid. If you decided to go that way,
you can use the same method described for corners. But there is one case that can be solve in
very few moves: when you can use the 6 moves 5 cycle
M' U M U'
even with some setup move, it can be really nice. Try to learn which cases it solves and
possibly also some variations, like the “shifted” L F L' R U' R'. If you get a skeleton that leaves
an edge 5-cycle, it is a good idea to number the stickers and quickly go through the solve to see
if you can insert one of these algorithms. But don’t waste to much time looking for it.
For more about edge insertions, see Section 4.2 about corner-first methods.
-->
#### 2.4.7 その他のインサーション:2コーナー、2エッジ(Other Insertions: 2 Corners and 2 Edges)

2つのコーナーと2つのエッジがそれぞれ交換するようなスケルトンになることがあるでしょう。(つまり、PLLのJ、T、Vなどです)

このような場合、いくつかの**10手アルゴリズム**を知っておくと役立ちます。

`Fw2 R D R' Fw2 R D' R D R2 (J perm)`  
`Rw' U Rw' U2 R B' R' U2 Rw2 B' (T-perm + ねじれコーナー)`
{: .text-center}

11手のものも多くあります。

`R U2 R' U' R U2 L' U R' U' L (J perm)`  
`R2 D B2 D' Fw2 D B2 D' Fw2 R2 U' (J perm)`  
`R2 Uw R2 Uw' R2 F2 Uw' F2 Uw F2 U' (T perm)`  
`R' U R U2 L' R' U R U' L U2 (J perm + ねじれコーナー)`
{: .text-center}

<!--
2.4.7 Other Insertions: 2 Corners and 2 Edges
Sometimes you may find a skeleton leaving 2 corners and 2 edges in a double swap (i.e.: a PLL
such as J, T, V and so on).
In these cases, it is very useful to know a few 10 moves algorithms:
Fw2 R D R’ Fw2 R D' R D R2 (J perm)
Rw' U Rw' U2 R B' R' U2 Rw2 B' (T-perm + corner twist)
There are also many 11 moves ones; some of them are:
R U2 R' U' R U2 L' U R' U' L (J perm)
R2 D B2 D' Fw2 D B2 D' Fw2 R2 U' (J perm)
R2 Uw R2 Uw' R2 F2 Uw' F2 Uw F2 U' (T perm)
R' U R U2 L' R' U R U' L U2 (J perm + corner twist)
-->
全てを載せたわけではありませんが、このアルゴリズムに加えて、この逆手順やシフトしたものでも2コーナー＋2エッジがそれぞれ交換されます。**このアルゴリズムの逆手順は全く同じように作用することがわかるでしょう。** つまり、このことを知っていれば新しいアルゴリズムを学ぶことなく、キャンセルする確率が二倍になるのです。あまり多くの手数をキャンセルすることは望めませんが、多くのアルゴリズムを知っていれば知っているほどよいでしょう。

一つ例をあげましょう。次のソルブを見てください。

{% capture display_text %}
B' F D2 //疑似2x2x1 (3/3)
L' B * R2 //疑似3x2x2 (3/6)
F2 D F' D2 F //NISSを使って発見 (5/11)
R' D' R D2 F U2 //NISSを使って発見 (6/17)
* = B2 L B L' B D2 F' R F D2 //2c2e insertion (9/26)
{% endcapture %}
{% include solvebox.html
title = "2C2E Insertion - Example"
scramble = "B' L' D2 R U F' U' L U2 D R2 U2 F B R2 B U2 B L2 B2 U2"
text = display_text
solution = "B' F D2 L' R2 B R B' R2 F R' B R F' R2 F2 D F' D2 F R' D' R D2 F U2 (26)"
img_src="../../../assets/img/alg-247.png"
algcubing = ""
%}

<!--
Besides all of these algorithms (this is not a complete list anyway), also their inverses and
“shifted” versions solve a 2 corners - 2 edges double swap.
Note that the inverses of these algorithms solve exactly the same case. Just by
noting this you double your chances of cancellations without the need to learn more algorithms.
Don’t expect lots of cancellations, but the more algorithms you know, the better.
As an example, see the following solve.
30 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
2C2E Insertion - Example
Scramble: B' L' D2 R U F' U' L U2 D R2 U2 F B R2 B U2 B L2 B2 U2
B' F D2 //Pseudo 2x2x1 (3/3)
L' B * R2 //Pseudo 3x2x2 (3/6)
F2 D F' D2 F //Found using NISS (5/11)
R' D' R D2 F U2 //Found using NISS (6/17)
* = B2 L B L' B D2 F' R F D2 //2c2e insertion (9/26)
Solution: B' F D2 L' R2 B R B' R2 F R' B R F' R2 F2 D F' D2 F R' D' R D2
F U2 (26)
See on alg.cubing.net
-->
スケルトンの最後のところはNISSを使って見つけたものなので、ここまで読んだだけでは少し意味がわからないことでしょう。「`*`」と書かれた場所には、準最適なJperm `B' R2 B R B' R2 F R' B R F'` を挿入することができ、2手がキャンセルして1手になり、最終解答になります。
<!--
The end of the skeleton was found using NISS, so it will be a bit mysterious until you get
to that section. Notice that in the same spot marked by * you can insert the sub-optimal Jperm B' R2 B R B' R2 F R' B R F', cancelling 2 moves instead of 1 and getting the same final
result.
-->
#### 2.4.8 その他のインサーション:3エッジ、いくつかのコーナー(Other Insertions: 3 Edges and Some Corners)

3つのエッジと、4つか5つ（あるいはもっと）のコーナーが残ったスケルトンが少ない手数（たとえば13手）でできることもあるでしょう。このときエッジ3-cycleのエッジをインサートしていくつかコーナー3-cycleを必要なだけインサートして解くこともできます。

しかし、別のやり方もあります。**「セクシームーブ」（`R U R' U'`）ではエッジの3-cycleと歪んだコーナーの2-cycleを2回繰り返すことになることがわかると思います。** この短いアルゴリズムやその派生をインサートすることで、エッジの3-cycleをとても効率的に解くことができるのです。もちろん、一回のインサーションでコーナーも完全に揃うのは、4つのコーナーとねじれたダブルスワップが残っているときのとてもラッキーなときだけです。コーナーにこういった影響を与えて、4つか5つかよいコーナーが残るようにする、というのが望み得る最良のことになる場合が多いです。
<!--
2.4.8 Other Insertions: 3 Edges and Some Corners
In some cases you can get short skeletons (say 13 moves) that leave a 3-cycle of edges and 4 or
5 corners (or even more). Of course you can solve this case by inserting and edge 3-cycle and
whatever number o corner 3-cycles is needed.
But there is another way: notice that the “sexy move” R U R' U' solves a 3-cycle of edges
and a skew doubl 2-cycle of corners. By inserting this short algorithm and its variations you
can solve the edge 3-cycle in a very effcient way. Of course the case of also geting the corners
completely solved with one insertion is a very lucky accident. Often the best you can hope for is
to affect the corners in such a way that you are left with one of the “good” 4 or 5 corners cases.
-->
こういうとき役立つのは「セクシームーブ」だけではありません。ブロックコミュテータもよいツールです。speedsolving.comのこのポストの中で、Cale Schoonはこの類のインサーションについての実例を3つ挙げています。彼の解答はすべてNISSを使っていますが、スケルトンを作るまでのステップは無視して構いません。インサーションだけを見てください。

もう一つのアプローチはreverse NISS([3.3節](chapter3#ch3-3)も参照)です。これは、セクシームーブをインサートすることで何をしているのかを理解する助けになるでしょう。


<!--
The “sexy move” isn’t the only algorithm that can help in this cases: also block commutators
are a very good tool. In this post33 on speedsolving.com Cale Schoon gives 3 different examples
of this kind of insertion. All of his solutions use NISS, but you can ignore the intermediate steps
that produce the skeleton and just look at the insertions.
Another approach to this reverse NISS (Section 3.3), which can help you understand what
you are actually doing when you insert a sexy move.
-->
#### 2.4.9 その他のインサーション: Conjugateをして揃える(Other Insertions: Conjugate and Solve) {#ch2-4-9}

**訳注:**  
**Conjugate**の適切な訳語が思いつかないので保留しています。別の箇所でも書きましたが、数学用語としては共役という意味があります。そのままコンジュゲートとカタカナで訳出してもよいかもしれません。インターチェンジもそのまま使われていますし。
{: .notice--info}

4つのエッジと4つのコーナーがあり、それぞれ4点交換されるとき（あるいはダブルスワップがあるとき）に、一つのインサーションだけで揃えることができる状況というものがあります。このケースは次のように揃えられます。

揃っていない8つのピースをすべて同じ面に集めます(セットアップ)。これで集めた面での単一のムーブで4点交換ができます。そして、8つのピースを元の場所に戻します(逆セットアップ)。8つのピースが2点交換を4つ組み合わせたものであるときにも、このテクニックは使えます。そのときは、「インターチェンジ」は180度のもの、たとえば `U2` などになります。もしピースの数が8つちょうどでなかったり、適切な交換ができない場合には、[3.3節](chapter3#ch3-3)で説明するreverse NISSをまた使うことができます。
<!--
2.4.9 Other Insertions: Conjugate and Solve
A particular situation you can solve with only one insertion is when you have 4 edges and 4
corners left and both sets make a 4-cycle.
You can solve this case as follows: place all your 8 unsolved pieces on one layer (setup), so
that a single move of that layer solves both the 4-cycles, perform that move (solve) and then put
the 8 pieces back (anti-setup). The same technique works when the 8 pieces make four 2-cycles
in total: in this case, the “interchange” will be a 180° one (for example U2). If the pieces are
not exactly 8, or do not form the right cycles, you can again use reverse NISS after the setup
moves, as explained in Section 3.3.
-->

実例を見てみましょう。[^2-4-9]

{% capture display_text %}
U2 F B' L2 D2 //2つの2x2x1ブロック (5/5)
F' * R F2 R' L2 B //4エッジと4コーナー以外完成 (6/11)
* = U + L' B L' D L B' L $ U' //4 エッジ (9/20)
+ = F2 L' B2 L F2 L' B2 L //3 コーナー (5/25)
$ = L' D L U L' D' L U' //3 コーナー (5/30)
{% endcapture %}
{% include solvebox.html
title = "コンジュゲートして揃える Conjugate and Solve - Example"
scramble = "R2 L2 D2 F2 D' R2 U' B2 D' F2 U2 F' D2 L' F U B F2 U2 F2 L"
text = display_text
solution = "U2 F B' L2 D2 F' U F2 L' B2 L F2 L' B' L' D L B' D L U L' D' L U2 R F2 R' L2 B (30)"
img_src="../../../assets/img/alg-244.png"
algcubing = "https://alg.cubing.net/?alg=F_D-_(L-_U-_R-_U_L_U-_R_U)_U2_(U_R_D-_R-_U-_R_D_R-)_R_%2F%2FEO%0AD-_F-_L2_%2F%2F2x2x2%0AF2_D_F2_%2F%2FPseudo_F2L%26%2345%3B2%0AB-_D_B_%2F%2FF2L%26%2345%3B1%0AF-_D-_F-_%2F%2FAll_But_4_Corners&setup=_L_U2_D-_L-_U2_B-_D_B-_L_U2_F2_R2_F-_R2_L2_F-_U2_D2_F"
%}

<!--
Let’s see an example.
33https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-214#post-1247800

Conjugate and Solve - Example
Scramble: R2 L2 D2 F2 D' R2 U' B2 D' F2 U2 F' D2 L' F U B F2 U2 F2 L
U2 F B' L2 D2 //Two 2x2x1s (5/5)
F' * R F2 R' L2 B //All but 4 edges and 4 corners (6/11)
* = U + L' B L' D L B' L $ U' //4 edges (9/20)
+ = F2 L' B2 L F2 L' B2 L //3 corners (5/25)

$ 2. = L' D L U L' D' L U' //3 corners (5/30)
Solution: U2 F B' L2 D2 F' U F2 L' B2 L F2 L' B' L' D L B' D L U L' D'
L U2 R F2 R' L2 B (30)
See on alg.cubing.net
-->

見てわかるように、この場合のインサーションは、4点交換を揃えているわけではなく、「通常の」インサーションでコーナーが完成しています。ところが、Mirek Goljanがここで提案しているのは、たった一回のインサーションで全てを揃えられるということなのです。そのためには、同じスケルトンの`*`部分に次の手順をインサートします。

`(B D R2 B R'B2 D U2 F') U (F U2 D' B2 R B' R2 D' B')`
{: .text-center}

この長いインサーションでも同じ結果(30手)になります。

同じようなLast layerのアルゴリズムもいくつかあります。その一つは次のようなものです。

`(R B2 R2 U2 R) B (R' U2 R2 B2 R')`
{: .text-center}

その他のアルゴリズムはこちらの投稿[^2-4-9-2]を参照してください。

> Here's one example alg for each relevant OLL case. (Invert the middle move to set up the case.)
> 
> `(R B2 R2 U2 R) B (R' U2 R2 B2 R')`  
> `(L' B2 L2 U2 L') B' (L U2 L2 B2 L)`  
> `(R U' R2 D' L) F' (L' D R2 U R')`  
> `(R U2 L' B L) U2 (L'B' L U2 R')`  
> `(R U2 R' F' L') U2 (L F R U2 R')`  
> `(L' F U2 B' R) U2 (R' B U2 F' L)`  
> 
> (found using JACube)
> 
> I note there are 5 other 11f* OLLs (besides the ones that flip 4 edges), of which 2 can also be solved with this type of conjugation.  
> `(R' F2 R2 U2 R') F2 (R U2 R2 F2 R)`  
> `(R' U F2 D' F) U2 (F' D F2 U' R)`  

<!--
As you can see, the insertion in question doesn’t actually solve both the 4 cycles and the corners are completed with “normal” insertions. However, as suggested by Mirek Goljan, we
could have solved everything with only one insertion, as explained above. To do so, insert in
the same skeleton, at *:
(B D R2 B R'B2 D U2 F') U (F U2 D' B2 R B' R2 D' B')
This longer insertion produces the same result (30 moves).
There are also some Last Layer algorithms that work in this way. One of them is:
(R B2 R2 U2 R) B (R' U2 R2 B2 R')
and you can find some more here34
.
-->

#### 2.4.10 手数カウント(見積もり) (Move Count (an Estimate))

ここでは、普通のインサーションにおいてどのくらいの手数がかかるのか、見積もってみましょう。数学的に証明したわけではないヒューリスティックな見積もりですし、手数は次のようなことによって決まることを覚えておいてください。

- **どのくらい多くのコミュテータやアルゴリズムを知っているか。**また、その認識能力。
- **スケルトンの長さ。**スケルトンが長ければアルゴリズムをインサートする箇所が多いので、より多くのキャンセルを狙えます。（しかし、この理由のために長いスケルトンを選んではいけません！）

見積もりを持つことは、インサーションを探すのに時間をかける価値があるのか、そうでないのかを判断するうえで役に立ちます。もし30手より短い解答を達成したいとして、3つのコーナーが残ったスケルトンを23手で作れたなら、おそらく達成できるでしょう。25手だったら、少し幸運が必要です。

異なるスケルトンで比較することもできます。18手かかる4コーナーのスケルトンなら、25手かかる3コーナーのスケルトンよりよいでしょう。

参考になる数字を出しておきます。[^2-4-10]

|          インサーションの種類           | 手数  |
| :-------------------------------------: | :---: |
|             コーナー3-cycle             |  5/6  |
|              エッジ3-cycle              |   7   |
| 2つのねじれたコーナー (2コミュテータ) |   8   |
| 3つのねじれたコーナー (2コミュテータ) |   9   |
|       4コーナー(ダブルスワップ)        |  9/10   |
|       4コーナー(3コーナー+1ねじれコーナー)        |  10   |
|             コーナー5-cycle             | 10/11 |
|     2コーナー、2エッジ(2点交換を2貝)     |  10   |


<!--
2.4.10 Move Count (an Estimate)
Here I will give an estimate of how many moves are usually needed for the most common types
of insertions. It is a heuristic estimate, not a mathematical proven one, and keep in mind that
these number also depend on:
• How many commutators/algorithms you know and your ability to recognize them.
• The skeleton’s length: longer skeletons give more spots where you can insert an algorithm,
and so better chance of cancellations (but you shouldn’t choose a long skeleton instead of
a short one because of this!).
These estimates are useful if you want to know whether it is worth or not to spend some
time looking for insertions: if you goal is to achieve a solution shorter than 30 moves, if you have
a skeleton leaving 3 corners in 23 moves you will probably get it, if your skeleton is 25 moves
long you will need some luck.
You can also compare different kind of skeletons: a skeleton leaving 4 corner in 18 moves is
probably better than one leaving 3 corners in 25.
So here are the numbers35
Type of insertion Moves
Corner 3-cycle 5/6
Edge 3-cycle36 7
2 Twisted Corners (2 comms) 8
3 Twisted Corners (2 comms) 9
4 Corners (2 comms) 10
Corner 5-cycle 10/11
2 Corners and 2 Edges (double 2-cycle) 10
34http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-28#post-488378
35Mostly taken from here [1], slightly adjusted to match my personal opinion.
http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-42#post-614593
32 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
-->

#### 2.4.11 インサーションファインダー (Insertion Finder)
Baiqiang Dongによって開発された**[Insertion Finder](https://fewestmov.es/if)**[^2-4-11]は、インサーションを探して解答の中で何かを見逃していなかったかを確認するために役立つツールです。スケルトンを与えると、最大で4つのインサーションを探すことができます。

特に、3コーナーや3エッジなどの簡単なケースで役に立ちます。複雑なものについては、人間には発見不可能(あるいはとても困難)な解答を見つけることがありますから、利用は自己責任で！

**訳注：**  
インサーションファインダーを使うと、自分が見つけられなかったインサーションを見つけることができるので、自分のFMCのソルブを振り返るときに使うといいでしょう。下記に出力される画面の例を下記の追加します。インサーションに使われる記号はなぜか絵文字なのでかわいく見えます。
{: .notice--info}

![Insertion Finder](../../../assets/img/if.png){:width="auto" height="200px" class="align-center img-thumbnail"}
インサーションファインダーの出力画面例
{: .text-center}

<!--
2.4.11 Insertion Finder
Insertion Finder37, developed by Baiqiang Dong, is a useful tool to find insertions and check if
you have failed to see something in your solutions: it finds up to 4 insertions to solve a skeleton.
It is especially useful for easy cases (3 corners or 3 edges) but in complex situation it may
find solution that are not possible (or very difficult) to find for humans: use it responsibly!
-->

### 2.5 EOから始めよ (Starting with EO) {#ch2-5}
ZZでのソルブのように、**全てのエッジの向きを揃える(Edge Orientation, EO)ことからスタートする**のはいつも頭に入れておくべき可能性でしょう。このチュートリアルの初版のころから、自分のソルブの中で何度も繰り返してこのやり方を使ってきました。試技の一番最初にはまずノーマルスクランブルと逆スクランブル全てのEOを探して、試す価値があるのかを見ていました。（多くの場合）試す価値はあります！ [2.1.7節](#ch2-1-7)で書いたように、多くの著名なFMCerがEOから始めています。

**エッジの向きを揃える方向という点から言えば、エッジには3つの向きがありうるのです。** F/B軸 (＜R, L, U, D＞を除く)、R/L軸、そしてU/D軸です。通常のZZのソルブをした場合、それぞれについて4つの異なる向きでF2Lを作ることができるでしょう。EOから始めるのが好みではなくても、（カラーニュートラルの）ZZを練習してEOの認識を成長させましょう。

さて、ここからはZZとは違ったやり方に取り掛かりましょう。

**訳注**  
FMCにおけるEOとは何か？については、うえしゅう氏の記事に詳しく記述があります。  
[FMCにおけるEOについて（加筆修正版） - uesyuu's Blog (2018年11月12日)](https://uesyuu.com/blog/?p=28)
{: .notice--info}

<!--
2.5 Starting with EO
Starting by orienting all edges, as you would do in a ZZ solve, is a possiblity to always keep
in mind. Since the first version of this tutorial I have used it more and more in my solves, to
the point that at the beginning of an attempt I always look for all possible EOs on normal and
inverse scramble to see if they are worth a try: they often are. As mentioned in Section 2.1.7,
there are many notable FMCers that often start with EO.
Remember that there are 3 possible orientation with respect to which you can orient edges:
with respect to F/B (reduce to <R, L, U, D>), to R/L and to U/D. If you procede with a
normal ZZ solve, for each of these you can build the F2L on 4 different sides. Even if you don’t
like starting with EO, I suggest practicing some (color neutral!) ZZ to improve EO recognition.
From here you have at continue in different ways.
-->
#### 2.5.1 EO + ブロックビルディング
全てのエッジの向きを揃えたら、次はブロックビルディングに進むのが一般的です。利点は **悪いエッジ("bad edge")が全くないということです。** しかし、EOを崩さないようなムーブをしなければなりません[^2-5-1]。これは比較的小さな制約です。

ある向きでキューブを持ったときに、エッジの向きを揃えるよい方法を複数知っているでしょうから、EOのステップでは可能な限り多くのペアやブロックを作ることを心がけましょう。別のアプローチは、2x2x2ブロックなどを作るときにEOにも注意を払いつつ、ブロックができてからエッジの向きを揃えるというやり方です。

<!--
2.5.1 EO + blockbuilding
After having oriented all edges, the most common way to go on is blockbuilding. The pro is
that we don’t have any “bad” edge, but this forces40 us not to use moves that break the EO,
and this is a (relatively small) limit.

Since you have usually more than one (nice) way to orient edges for a given orientation, you
should also try to build as many pairs/blocks as you can during the EO step. As an alternative
approach, you can pay attention to EO while you build the first block(s) (for example, a 2x2x2)
and orient edges immediately after that.

-->
ヨーロッパ大会2010でのGregorz Łuczynaのソルブを見てみましょう。まずキューブを好みの向きに回転させているということがわかるでしょう。こうすることで、カラーニュートラルでなかったとしてもブロックを見つけるのが簡単になりますが、私個人としてはあまり好きなやり方ではありません。5.1節では解答の書き方について詳しく書いています。

{% capture display_text %}
x y2 L2 D F' //EO (3/3)
R L2 D * //EOLine (3/6)
R' U2 B2 R2 B2 //2x2x3 (5/11)
L2 U' R' U L U' L' R U2 L' U' //3コーナー以外完成 (11/22)
* = D2 R' U' R D2 R' U R //3c (4/26)
{% endcapture %}
{% include solvebox.html
title = "EOファースト - Example 1"
scramble = "L D2 B' D2 B R' B' U B L B L2 B2 U2 F2 U R2 D' B2 D' B2"
text = display_text
solution = "x y2 L2 D F' R L2 D' R' U' R D2 R' U' B2 R2 B2 L2 U' R' U L U' L' R U2 L' U' (26)"
img_src="../../../assets/img/alg-251-1.png"
algcubing = "https://alg.cubing.net/?setup=L_D2_B-_D2_B_R-_B-_U_B_L_B_L2_B2_U2_F2_U_R2_D-_B2_D-_B2&alg=x_y2_L2_D_F-_%2F%2FEO%0AR_L2_D_%2F%2FEOLine%0A(D2_R-_U-_R_D2_R-_U_R)_R-_U2_B2_R2_B2_%2F%2F2x2x3%0AL2_U-_R-_U_L_U-_L-_R_U2_L-_U-_%2F%2FAll_but_3_corners"
%}

<!--
Here is the solve that made Gregorz Luczyna the 2010 European Champion. Notice that he
starts by rotating the cube to his preferred orientation. This makes it easier to spot blocks if
you are not used to color neutrality, but I dislike this habit. See Section 5.1 for more about how
to write down a solution.
38Warning: this varies a lot! If edges are oriented early in the solve, you have better chances of finding a good
insertion (6 or 8 movers). If you do a domino reduction solve (see Section 2.5.2 and Appendix D), edge insertions
become much more efficient!
39https://fewestmov.es/if
40Obviously, no one is forcing you to do anything, but orienting edges and then destroying what you have just
done doesn’t look like a smart thing to do. You can also start with a partial EO if you wish.

EO first - Example 1
Scramble: L D2 B' D2 B R' B' U B L B L2 B2 U2 F2 U R2 D' B2 D' B2
x y2 L2 D F' //EO (3/3)
R L2 D * //EOLine (3/6)
R' U2 B2 R2 B2 //2x2x3 (5/11)
L2 U' R' U L U' L' R U2 L' U' //All but 3 corners (11/22)
* = D2 R' U' R D2 R' U R //3c (4/26)
Solution: x y2 L2 D F' R L2 D' R' U' R D2 R' U' B2 R2 B2 L2 U' R' U L U' L' R U2 L' U' (26)
See on alg.cubing.net
-->


別の例を見てみましょう。João Pedro Batista Ribeiro Costaが世界大会2015で最初に行ったソルブです。平均25.67手を出し、優勝しました。

{% capture display_text %}
U2 R' U2 * R' //EO (4/4)
B F2 U2 F //疑似2x2x3 (4/8)
(B L2) //2x2x3 (2/10)
B2 U' B2 U' B2 U' B2 U' B' U //3コーナー以外完成 (10/20)
* = U R' D2 R U' R' D2 R //3c (6/26)
{% endcapture %}
{% include solvebox.html
title = "EOファースト - Example 2"
scramble = "L2 U' B2 L2 D' F2 L2 D U' L2 U2 B' R2 B' R B R' D' B' F2"
text = display_text
solution = "U2 R' U' R' D2 R U' R' D2 B F2 U2 F B2 U' B2 U' B2 U' B2 U' B' U L2 B' (26)"
img_src="../../../assets/img/alg-251-2.png"
algcubing = "https://alg.cubing.net/?setup=L2_B-_L2_U-_B2_L2_D-_F2_L2_D_U-_L2_U2_B-_R2_B-_R_B_R-_D-_B-_F2&alg=%2F%2FPremoves_(NISS)_added_to_the_scramble%0AU2_R-_U2_(U_R-_D2_R_U-_R-_D2_R)_R-_%2F%2FEO%0AB_F2_U2_F_%2F%2F2x2x3%0AB2_U-_B2_U-_B2_U-_B2_U-_B-_U_%2F%2FAll_but_3_corners"
%}

このソルブ実例では２つの**短くて良いEOステップ**がありました。しかし、**長いEOしか見つからないときには諦めるしかないわけではなく、より多くのブロックができるなら使えます！**

<!--
Here is another example: the first solve of Jo˜ao Pedro Batista Ribeiro Costa at World
Championship 2015, part of his 25.67 winning mean of 3.
EO first - Example 2
Scramble: L2 U' B2 L2 D' F2 L2 D U' L2 U2 B' R2 B' R B R' D' B' F2
U2 R' U2 * R' //EO (4/4)
B F2 U2 F //Pseudo 2x2x3 (4/8)
(B L2) //2x2x3 (2/10)
B2 U' B2 U' B2 U' B2 U' B' U //All but 3 corners (10/20)
* = U R' D2 R U' R' D2 R //3c (6/26)
Solution: U2 R' U' R' D2 R U' R' D2 B F2 U2 F B2 U' B2 U' B2 U' B2 U' B' U L2 B' (26)
See on alg.cubing.net
One last thing: in the examples above there are two nice and short EO steps. But this
doesn’t mean you should discard a longer EO, if you can build a lot of blocks while doing it!
-->
#### 2.5.2 ドミノリダクション (Domino Reduction) {#ch2-5-2}
**エッジの向きを揃えることは、キューブの持ち替え(rotation)を法とする＜R, L, U, D＞のムーブによる部分集合への還元 (reduction)とみなすことができます。＜R, L, U, D, F2, B2＞と考えても等価です。** 言い換えると、エッジの向きを揃えることでキューブを`R`, `L`, `U`, `D`, `F2`, `B2`だけで解ける状態に変換してしまうことができる、ということです。

このような考え方をすると、＜U, D, R2, L2, F2, B2＞のムーブによる部分集合に還元させるやり方も可能となります。そのためには下記のことが必要となります。

- E列のエッジはE列に配置する
- コーナーの向きを揃える

**このような条件が満たされる還元を「ドミノリダクション (Domino Reduction)」（略して 「DR」)と呼びます。**これは、ルービックキューブを3x3x2のキューブ(Domino Cube、[Rubik's Domino](https://www.speedsolving.com/wiki/index.php/Rubik%27s_Domino)とも言う)とみなして解けるようにすることから名前がついています。

ここ最近、2018年から2019年にかけて、ドミノリダクションの人気は高まってきました。この手法を単独で使うだけでもよい結果を安定して出すことができるということがわかってきています。

ドミノリダクションに関するよいチュートリアルを書こうとすると、非常に長くなるので別のドキュメントが必要になるでしょう。**実際、作られました。**もしこの手法に興味があるなら、**Alexandros FokianosとTommaso Raposioによる[素晴らしいチュートリアル](https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S)[^2-5-2]を読むとよいでしょう。**この中で、特に重要な考え方については付録Dにまとめています。

**訳注**  
このDomino Reductionに関するチュートリアルは2019年8月に公開されました。原著者のSebastiano Trontoも協力しています。フォーラムの投稿はこちらです。  
[A Domino Reduction Guide for FMC](https://www.speedsolving.com/threads/a-domino-reduction-guide-for-fmc.74828/) by Alexandros Fokianos, Tommaso Raposio
{: .notice--info}

 Per Kristen Fredlundによる実例を見てみましょう。

 {% capture display_text %}
R' B U' D F //EO (5/5)
L' F2 L //Domino reduction (3/8)
D2 L2 F2 D F2 D L2 U' R2 D2 R2 //完成 (11/19)
{% endcapture %}
{% include solvebox.html
title = "DR - Example 2"
scramble = "R2 F2 L2 D' R' U' R D' F B R U B2 L2 D2 F2 L2 D B2"
text = display_text
solution = "R' B U' D F L' F2 L D2 L2 F2 D F2 D L2 U' R2 D2 R2 (19)"
img_src="../../../assets/img/alg-252.png"
algcubing = "https://alg.cubing.net/?setup=R2_F2_L2_D-_R-_U-_R_D-_F_B_R_U_B2_L2_D2_F2_L2_D_B2&alg=R-_B_U-_D_F_%2F%2FEO_(5%2F5)%0AL-_F2_L_%2F%2FDomino_Reduction(3%2F8)%0AD2_L2_F2_D_F2_D_L2_U-_R2_D2_R2_%2F%2FFinish_(11%2F19)"
%}

<!--
2.5.2 Domino Reduction
Edge orientation can be considered, modulo rotations, a reduction to the subgroup generated
by the moves <R, L, U, D> or, equivalentely, <R, L, U, D, F2, B2>. In other words, by
orienting edges you reduce the cube to a case that can be solved using only the moves R, L,
U, D, F2 and B2. Another step in this direction leads to reducing the cube to the subgroup
generated by <U, D, R2, L2, F2, B2>; in order to do so you have to:
• Place E layer edges on the E layer;
• orient corners.
This reduction is also called “domino reduction” (often shortened to DR), because it makes
a Rubik’s Cube solvable as a 3x3x2 “cube” (also called “Domino Cube”).
Recently (2018-2019), domino reduction has gained a lot of popularity, and it has been shown
that one can reach consistently good results with this method alone.
A good tutorial on domino reduction could easily fill another long document. And in fact
it does: if you are interested in the method, I suggest you read this wonderful tutorial41 by
Alexandros Fokianos and Tommaso Raposio. I have tried to sum up the most important ideas
of that document in Appendix D.
Here is an old example solve by Per Kristen Fredlund.
41https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S
36 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
DR - Example
Scramble: R2 F2 L2 D' R' U' R D' F B R U B2 L2 D2 F2 L2 D B2
R' B U' D F //EO (5/5)
L' F2 L //Domino reduction (3/8)
D2 L2 F2 D F2 D L2 U' R2 D2 R2 //Finish (11/19)
Solution: R' B U' D F L' F2 L D2 L2 F2 D F2 D L2 U' R2 D2 R2 (19)
See on alg.cubing.net
-->

**訳注**  
日本語でのDomino Reductionに関する記事としては、Rami氏のアドカレ記事があります。  
[Domino Reduction 入門編 - きゅーぶぶろぐ (2019年12月02日)](http://minayauninareyo.seesaa.net/article/drtanoshii.html)
{: .notice--info}

#### 2.5.3 部分的ドミノリダクション (Partial Domino Reduction, PDR)
##### 古典的PDR
**部分的ドミノリダクション (Partial Domino Reduction, PDR)**の考え方を最初に提案したのは[Alexandre Campos](https://www.speedsolving.com/threads/introducing-a-variation-for-fewest-moves.67299/)[^2-5-3-1]です。これは、EOを2つの軸に対して揃えることで、いくつか揃っていないコーナーのあるドミノリダクションの状態に持ち込む、という考え方です。また、最初のアイディアには含まれていませんが、PDRという用語は部分的DRの中でも特に **「全てのエッジとコーナーの向きが揃っているが、E列のエッジが全てE列にあるわけではない」** という状態を指すものとして使われます。

<!--
2.5.3 Partial Domino Reduction
Classic PDR
The idea of Partial Domino Reduction, shortened to PDR, was first introduced by Alexandre
Campos42. It consists in solving EO with respect to two axes, which can also be seen as a
domino reduction with (some) misoriented corners. Although not included in his original idea,
the term PDR can also refer to a partial DR where the edges and corners are all oriented, but
not all E-layer edges are in the E-layer.
-->

たとえばF/B軸を考えてEOを揃えたあと、L/R軸などの別のEOを揃える、という風に進めることができるでしょう。この2つ目のEOステップを「E列のエッジをE列に配置する」と見なすこともできます。これはDRのソルブでやることと同じですが、コーナーは無視しています。1つ目のステップで揃えたEOをそのままにして置きたいので、`F`や`B`などの1/4回転のムーブは2つ目のステップでは使えません。

2つの軸に対するEO(PDR)を考えるなら、まずブロックビルディングをしてから、ドミノムーブ（＜U, D, R2, L2, F2, B2＞）だけを使って揃えられるスケルトンを作るのが自然なやり方でしょう。こうするとEOが崩れることはありません。

しかし、制約もあります。**ドミノムーブだけを使う場合には、向きの揃っていないコーナーを揃えることができないのです。**ですので、このコーナーを揃えないままにしておいて、後からインサートして揃える必要が出てきます。こうならないようにするために、向きの揃っていないコーナーをたくさん残しておくべきではありません。

[AlexandreはDRのソルブ例をいくつか収集しています](https://docs.google.com/document/d/1oZwr2aSllFBL5lhbLTiWKQWplfk4i0LN0wA0uskeLJs)[^2-5-3-2]から、そのうちの一つを見てみましょう。

<!--
After a normal EO, say with respect to F/B, one can procede with a second EO, say on
L/R. This second EO step can also be seen as placing the E-layer edges on the E-layer, much
like you would do in a DR solve, but ignoring corners. Since you want to keep the EO you did
in the first step, you should not use F and B quarter turn moves during this second step.
When you have EO on two axes (PDR) a normal way to finish your solve is to build blocks
and find a skeleton using only “domino moves” <U,D,R2,L2,F2,B2> (i.e. moves that don’t break
any of your EOs). However, there are some restrictions: using only domino moves you have no
hope to solve the misoriented corners, so you are forced to leave them unsolved and solve them
later with insertions. That’s why not leaving many misoriented corners is usually a good idea.
Alexandre has collected some PDR solves in a document43. Let’s look at the first one as an
example:
-->

{% capture display_text %}
D' * R' U' F + //EO (4/4)
L R2 U R //PDR4 (4/8)
D F2 D2 B2 //Corner line + edge line (4/12)
U2 L2 D R2 U //AB5C (5/17)
* = D' R' U2 R D R' U2 R //(8-4/21)
+ = F2 R B2 R' F2 R B2 R' //(8-2/27)
{% endcapture %}
{% include solvebox.html
title = "古典的PDR - Example"
scramble = "R' U' F L2 U2 B' L2 F' U2 B L2 B R' B2 L U B L2 B' D' F2 R F R' U' F"
text = display_text
solution = "D2 R' U2 R D R' U F' R B2 R' F2 R B2 R L U R D F2 D2 B2 U2 L2 D R2 U (27)"
img_src="../../../assets/img/alg-253-1.png"
algcubing = ""
%}

<!--
Classic PDR - Example
Scr: R' U' F L2 U2 B' L2 F' U2 B L2 B R' B2 L U B L2 B' D' F2 R F R' U' F
D' * R' U' F + //EO (4/4)
L R2 U R //PDR4 (4/8)
D F2 D2 B2 //Corner line + edge line (4/12)
U2 L2 D R2 U //AB5C (5/17)
* = D' R' U2 R D R' U2 R //(8-4/21)
+ = F2 R B2 R' F2 R B2 R' //(8-2/27)
Solution: D2 R' U2 R D R' U F' R B2 R' F2 R B2 R L U R D F2 D2 B2 U2 L2 D R2 U (27)
See on alg.cubing.net
-->
##### EO+CO PDR
別の種類の「PDR」は「見せ掛けDR」とでも呼ぶべきアプローチです。これに対して、上に書いたような古典的は「EO＋ブロックビルディング」のアプローチに近いものです。

EOを揃えたあと、DRを作るのと同じようなアプローチでコーナーの向きを揃えることができるでしょう。その後で、コーナーを揃えてエッジだけが残ったスケルトンを作ることができます。こうするといいことが起こります。DRとしてはあまりよい状態ではありませんが、EOが揃っているならエッジのインサートは非常によいものになります。特に、3.8節に書くような発展的なテクニックを使うとよいでしょう。

<!--
This second type of “PDR” approach is probably closer to being a “mock DR”, whereas the
classical PDR described above is closer to an EO + blockbuilding approach.
42https://www.speedsolving.com/threads/introducing-a-variation-for-fewest-moves.67299/
43https://docs.google.com/document/d/1oZwr2aSllFBL5lhbLTiWKQWplfk4i0LN0wA0uskeLJs
2.6. OTHER SIMPLE STRATEGIES 37
After EO is solved, you can try solving corner orientation using the same type of triggers
that are used to get a DR. After that, you can solve corners and get an edges-only skeleton.
This often turns out to be good: although not as nice as with DR, edge insertion can still be
very good when EO is solved, especially when combined with the advanced techniques described
in Section 3.8.

-->

{% capture display_text %}
F D R2 U' F' //EO (5/5)
R' //Lucky CO (1/6)
F2 B2 U2 R2 D U2 * B2 D U' //3e+3e left (9/15)
* = U R2 U' F2 B2 + D L2 D' F2 B2 //10-3/22)
+ = U' L' D2 F2 D2 L' U D L2 D' //(10-6/26)
{% endcapture %}
{% include solvebox.html
title = "EO+CO PDR - Example"
scramble = "F' U R U' F2 R' U2 F' U D' L B' L2 F2 U2 R2 L' U2 B2 U2 R F2 L' F' U R"
text = display_text
solution = "F D R2 U' F' R' F2 B2 U2 R2 U' D R2 U' F2 B2 U' L' D2 F2 D2 L' U F2 U' D (27)"
img_src="../../../assets/img/alg-253-2.png"
algcubing = "https://alg.cubing.net/?setup=F-_U_R_U-_F2_R-_U2_F-_U_D-_L_B-_L2_F2_U2_R2_L-_U2_B2_U2_R_F2_L-_F-_U_R_&alg=F_D_R2_U-_F-_%2F%2FEO_(5%2F5)%0AR-_%2F%2FLucky_CO_(1%2F6)%0AF2_B2_U2_R2_D_U2_B2_D_U-_%2F%2F3e_%26%232b%3B_3e_left"
%}

<!--
EO+CO PDR - Example
Scr: F' U R U' F2 R' U2 F' U D' L B' L2 F2 U2 R2 L' U2 B2 U2 R F2 L' F' U R
F D R2 U' F' //EO (5/5)
R' //Lucky CO (1/6)
F2 B2 U2 R2 D U2 * B2 D U' //3e+3e left (9/15)
* = U R2 U' F2 B2 + D L2 D' F2 B2 //10-3/22)
+ = U' L' D2 F2 D2 L' U D L2 D' //(10-6/26)
Solution: F D R2 U' F' R' F2 B2 U2 R2 U' D R2 U' F2 B2 U' L' D2 F2 D2 L' U F2 U' D (27)
See on alg.cubing.net
-->

### 2.6 その他の簡単な戦略(Other Simple Stragies) {#other-simple-stragies}
#### 2.6.1 戻ってやり直そう(Go Back and Change Your Solve) {#ch2-6-1}
**よいスタートを切ったあとで詰まってしまったら、「そこまでのソルブを一手ずつ見ていく」ということをしてみましょう。** まだ揃えていないピースしかない面が、少なくとも1面、出てくるのを探しながらやってみましょう。見つかったら、その面を動かしてみましょう(すでに揃えたブロックは崩れません)。可能性は3種類(`U`、`U2`、`U'`など)あります。こうすると、元々のものよりほんの少し(1手)だけ長くなって、3通りのスタートが得られるでしょう。次へのつながりがよくなるなら、たった1手は安いものです！

自由に動かせる面が2つ見つかったなら、もちろん両方使ってみても構いません。追加するムーブはランダムなものでよいですし、そうしなくてもよいです。新しいペアができたり、EOがもっとよくなるのなら、それで十分です。しかし、何手か追加してもすぐにわからず、しばらく進んでいってようやく何が起こったかわかることもあるでしょう。
<!--
2.5 Other Simple Stragies
2.5.1 Go Back and Change Your Sove
If you get stuck after a good start, you can try this: go through your solve move by move,
looking for a spot where there is at least one layer containing only pieces that you have not
solved yet. When you find it, you can move that layer (this is not going to affect any of the
blocks you have already built). You have 3 choices (for example U, U2, U) and this way you will
get 3 different starts that are just slightly (one move) longer than the previous. One move can
be a good price to pay for a better continuation!
Of course, if you find a spot where there are two “free” layers, you can use both of them.
The moves can, but don’t have to, be random: if you can see a pair forming or the EO gettig
better with some moves, good for you, but sometimes you might as well try random moves and
see what happens later.
-->
#### 2.6.2 幸運を手に入れろ！ (Get Lucky!)
当たり前ですが、幸運は学べるスキルではありません。しかし、FMCにおいては**幸運を求めるべきなのです。** LLスキップで終わる「単純な」ソルブは、複雑でアンラッキーなものと同じくらい価値があります。つまり、可能な限りたくさんの代替案を試してみるのがよいということです。10回や20回だけやってみるよりも、100回やったほうがスキップする確率は高くなります。

**訳注：**  
LLスキップを引き当てる幸運値はトレーニングできませんが、**LLのアルゴリズムやサブステップをたくさん知っている人ほど、その確率を高くすることができます。**開眼3x3x3のスキルはFMCには直接影響しないと言われますが、速い人はそもそもたくさんのアルゴリズムを知っていて、制限時間内に何度も試行錯誤をすることができるので、有利かもしれません。他の競技を学ぶことでFMCに生きてくることがある、というのは面白いですね。たとえば、原著者であるSebastiano Trontoは**目隠し競技の達人(3x3x3目隠し、4x4x4目隠し、5x5x5目隠しのイタリアNRホルダー)でもあります。**
{: .notice--info}


<!--
2.5.2 Get Lucky!
Obviously, luck is not a skill to be learned, but remember that in FMC you have to go for
it: a “simple” solve ending with an LL skip is not less worthy than a complex unlucky one, if
they have the same length. This is one of the reasons why you need to try as many different
alternatives as you can: you are more likely to get a skip if you try 100 solutions than if you try
10 or 20.
-->
##### 一つ目の例: 最後のペアをインサート(First Example: Insert Last Pair(s))

F2L-1が完成したあと、最後のペアをインサートすることでF2Lが終わります。これは、幸運が振ってこない限り、あまりよいやり方ではありません。幸運を引き当てるチャンスを高めるには、**考えうる全ての方法で最後のペアをインサートしましょう。**

たとえば、最後のペアが既にできているとすれば、少なくとも3つの違う方法でインサートすることができます。`U R U' R'`、`U2 R U2 R'`、そして `R' F R F'`です。VHF2LやZBF2Lのアルゴリズムをいくつか知っていれば、スキップを引くチャンスを高めるのに役立つでしょう。しかし、単に暗記するよりも、どういう仕組みでうまくいくかを学ぶとよいでしょう。

ペアをインサートする別の方法の例として、次のソルブを考えてみましょう。（このスクランブルはGerman Forum Competitionのもので、premovesを使わないようにしたものです）

{% capture display_text %}
U2 F' U' //2x2x2
B' D B //2つのエッジの向き合わせ
D2 L D2 B2 //2x2x3 + 6 ペア
B' //ペアを一つ保存 (F2L on R)
L F L' F' //別のペアをインサート
B D L' D' //保存しておいたペアをインサート
U' L2 U L U' L U L' //Last Layer
{% endcapture %}
{% include solvebox.html
title = "Insert Last Pairs - Example"
scramble = "D' R' U' F U2 F2 L2 D' B2 F2 D' L R' D F' U' R' B' R2 F D U' B' R' U' F"
text = display_text
solution = "U2 F' U' B' D B D2 L D2 B L F L' F' B D L' D' U' L2 U L U' L U L'(27)"
img_src="../../../assets/img/alg-263.png"
algcubing = "https://alg.cubing.net/?setup=D-_R-_U-_F_U2_F2_L2_D-_B2_F2_D-_L_R-_D_F-_U-_R-_B-_R2_F_D_U-_B-_R-_U-_F&alg=U2_F-_U-_%2F%2F2x2x2%0AB-_D_B_%2F%2FOrient_two_edges%0AD2_L_D2_B2_%2F%2F2x2x3_%26%232b%3B_6_pairs%0AB-_%2F%2FSave_one_pair_(for_F2L_on_R)%0AL_F_L-_F-_%2F%2FInsert_other_pair%0AB_D_L-_D-_%2F%2FInsert_saved_pair%0AU-_L2_U_L_U-_L_U_L-_%2F%2FLast_Layer"
%}

このとき、最後のペアのインサートをどうやって選んだかというと、最後にPLLスキップをしたからです。ところが、実はもっとよいインサート方法があって、Cube Explorer (PCのソフトウェア)見つけたものがこちらです。

**訳注:**  
元々の解答の27手でも十分すごいのですが、ペアの保存方法と最後のインサート方法を変えることで、20手の解答ができました。上記に示すように、`U R U' R'`、`U2 R U2 R'`、`R' F R F'`といった手順を順番に試してみるだけでも価値はあります。
{: .notice--info}

{% capture display_text %}
U2 F' U' //2x2x2
B' D B //2つのエッジの向き合わせ
D2 L D2 B2 //2x2x3 + 6 ペア
B' U' //ペアを一つ保存  (F2L on R)
L F L' F' //別のペアをインサート
L U L B //保存しておいたペアをインサートして、スキップ！
{% endcapture %}
{% include solvebox.html
title = "Insert Last Pairs - Example"
scramble = "D' R' U' F U2 F2 L2 D' B2 F2 D' L R' D F' U' R' B' R2 F D U' B' R' U' F"
text = display_text
solution = "U2 F' U' B' D B D2 L D2 B U' L F L' F' L U L B (20)"
img_src="../../../assets/img/alg-263.png"
algcubing = "https://alg.cubing.net/?setup=D-_R-_U-_F_U2_F2_L2_D-_B2_F2_D-_L_R-_D_F-_U-_R-_B-_R2_F_D_U-_B-_R-_U-_F&alg=U2_F-_U-_%2F%2F2x2x2%0AB-_D_B_%2F%2FOrient_two_edges%0AD2_L_D2_B2_%2F%2F2x2x3_%26%232b%3B_6_pairs%0AB-_U-%2F%2FSave_one_pair_(for_F2L_on_R)%0AL_F_L-_F-_%2F%2FInsert_other_pair%0AL_U_L_B_%2F%2FInsert_saved_pair_and_skip"
%}


<!--
2.5.3 First Example: Insert Last Pair(s)
After completing an F2L-1, you can finish the F2L by inserting the last pair. This isn’t usually a
good way to continue, unless you get lucky. To improve your chances to get lucky, try to insert
the last pair in all the ways you can think of.
For example, if your last pair is already built, you can insert it in at least 3 different ways:
U R U' R', U2 R U2 R' and R' F R F'. Knowing some VHF2L or ZBF2L algs can be useful
to improve your chances of skip, but rather than memorizing them you should learn how they
work.
As an example of alternative ways to insert pairs, consider this solve (scramble adapted from
one of the German Forum Competition to avoid using premoves).
Insert Last Pairs - Example
Scramble: D' R' U' F U2 F2 L2 D' B2 F2 D' L R' D F' U' R' B' R2 F D U' B' R' U' F
U2 F' U' //2x2x2
B' D B //Orient two edges
D2 L D2 B2 //2x2x3 + 6 pairs
B' //Save one pair (F2L on R)
L F L' F' //Insert other pair
B D L' D' //Insert saved pair
U' L2 U L U' L U L' //Last Layer
Solution: U2 F' U' B' D B D2 L D2 B L F L' F' B D L' D' U' L2 U L U' L U L'
See on alg.cubing.net
37https://fewestmov.es/cube/if.cube?lang=en
2.5. OTHER SIMPLE STRAGIES 33
Note how I have choosen this way to insert the pairs because in the end I got a PLL skip.
There was actually a better way to insert the last two pairs, which I have found using Cube
Explorer (a PC software).
Insert Last Pairs - Example
Scramble: D' R' U' F U2 F2 L2 D' B2 F2 D' L R' D F' U' R' B' R2 F D U' B' R' U' F
U2 F' U' //2x2x2
B' D B //Orient two edges
D2 L D2 B2 //2x2x3 + 6 pairs
B' U' //Save one pair (F2L on R)
L F L' F' //Insert other pair
L U L B //Insert saved pair and skip
Solution: U2 F' U' B' D B D2 L D2 B U' L F L' F' L U L B
See on alg.cubing.net
-->
##### 二つ目の例: アルゴリズムの使い方(Second Example: How to Use Algorithms)
まず最初に対称なアルゴリズムを識別できるようにしておきましょう（もっと正確にいえば、対称なケース）。つまり`F R U R' U' F'`で揃うOLLはSプレーンについて対称なので、同じケースは`B' R' U' R U B`でも揃います。もし使いたいのであれば、対称なケースも使えるようにして、スキップ（あるいはよいケース）のチャンスを二倍にしましょう。

このトリックがうまくいくのは、二つのアルゴリズムは同じOLLケースを揃えるためのものであって、ピースの交換に異なった影響を与えるものだからです。しかし、CLLについては少し違います。同じCLLケースを揃えるアルゴリズムがあって、コーナーが揃わないなら、ほかのアルゴリズムを使ってもコーナーは揃いません。

極端な例を見てみましょう。`R U2 R' U' R U R' U' R U' R'`で揃うOLLを考えます。これと左右対称の`L' U2 L U L' U' L U L' U L`を使うことで、同じケースを4つの向きから揃えることができます（ほかの2つは逆手順です）。「2-gen」のLast layerアルゴリズムに当てはまることですが、このアルゴリズムは、コーナーの相対的な位置関係には影響しません。

次に、学んだときの目的と同じようにアルゴリズムを使う必要はありません。`F R U R' U' F'`について考えると、おそらくOLLのひとつとして覚えている手順でしょう。ところが、コーナーを無視してこれを使うこともできます。すると、F2L完了時点で2つの悪いエッジ（bad edge）が残っているときに、このアルゴリズムを4つの向きから使うことでスキップするか（あるいは簡単なケースになるか）どうかを試すことができます。
<!--
First of all, you need to be able to recognize symmetries in algorithms (more precisely, in
cases): the OLL that is solved by F R U R' U' F' is symmetrical about the S plane, so the
same case can be solved by B' R' U' R B U. If you want to use it, try also its symmetrical to
double your chances of getting a skip (or a good case). This trick works exactly because the
two algorithms solve the same OLL the case, but affect the permutation of pieces in a different
way. Notice however that they solve the same CLL case, so if the corners are not solved by one,
they aren’t solved by the other either.
An extreme example is the OLL solvable with R U2 R' U' R U R' U' R U' R': with this
algorithm and its symmetrical L' U2 L U L' U' L U L' U L you can solve the same case from 4
different angles, and from other 4 if you use their inverses. These algorithms, as all “2-gen” last
layer algorithms (i.e. algorithms that only move 2 layers), doesn’t affect the relative permutation
of corners.
Secondly, you don’t need to use an algorithm for the purpose you have learned it for. Sticking
to F R U R' U'F', you probably know it as an OLL. But you can decide to use it ignoring
corners: if you complete the F2L and are left with 2 bad edges, you can try this algorithm from
4 different angles to see if you get a skip, or at least an easy case.
34 CHAPTER 2. HOW TO PROCEED DURING A SOLVE
-->

<!-- 通常コンテンツここまで-->

[戻る：第1章](chapter1){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第3章](chapter3){: .btn .btn--inverse}


[^2-0]: 訳注:ノルウェーのキューバー。2004-2006年にFMCのノルウェーNRを達成。2005年の世界大会でFMC第2位。
[^2-0-1]: スケルトンとは、部分的な解法で、いくつかのピース（通常は2つから6つ）を未完成の状態で残しておくものを言います。
[^2-0-2]: ソルブのより前の段階で数手をインサートすることで完成させるテクニックです。これもすぐに解説します！もうちょっと待って！
[^2-0-3]: [http://www.speedsolving.com/forum/threads/fewest-moves-tips-and-techniques.1566/#post-16209](http://www.speedsolving.com/forum/threads/fewest-moves-tips-and-techniques.1566/#post-16209)
[^2-1-5]: [19 HTM Solve by Mirek Goljan and Guus Razoux Schultz](https://fmcsolves.cubing.net/?p=107)
[^2-1-5-2]: この解法は二人の競技者によって独立に見つけられたものです。念のため。
[^2-1-6-1]: 著名な例はZBLS(ZBF2Lとも呼ばれる)やWinter Variationです。これに限らず非常に沢山あります。調べてみましょう！
[^2-1-6-2]: 「準最適」とは最良の解法よりも多くの手数がかかる解法のことです。
[^2-1-8]: speedsolving.comの投稿による。もちろん、何が「よいスタート」であるかはあなたのレベルによって変わります。ここでの手数は、熟練者を目指す人にとってのよいゴールとなるように考えられています。もしあなたがそこまで上達していないなら、あまり効率的でないブロックを作って進めてもいいでしょう。「よいスタート」を探すのに多くの時間を使わないようにしてください。最終結果だけがカウントされます！
[^2-1-8-2]: もっと重要なルールは**「決して『決して』と言わない！」**ということです。
[^2-1-10-1]: 一時間のあいだ考え続けなければならないので、楽をすることは非常によい習慣です。
[^2-1-10-2]: ここでいう「計算する」とはチェスの用語のような意図があります。つまり、チェスプレイヤーは6-8手を「計算して」いると言われています。可能なムーブを考えて、そのカウンタームーブを考えて、総計で6-8手ということです。
[^2-1-10-3]: 手数の数え方はHTM(ハーフターン法(Half Turn Method)：180度も1手と数える)でもQTM(クオーターターン法(Quarter Trun Method)：90度で1手と数える)でもSTM(スライスターン法(Slice Turn Method)：Mなどのスライスムーブも1手と数える)でも構いませんが、どの数え方を使うかは先に決めておきましょう！（訳注：一般的にはHTMが使われます）
[^2-2]: 3-cycleとは３つのピースによる巡回交換です。たとえば、PLLのA permとU permは3-cycleですし、`L F R F' L' F R' F'` (Niklas)のアルゴリズムも同じです。
[^2-3-0]: たとえば、`U R`という手順の逆手順は`R' U'`です。`U' R'`や`R U`ではありません！
[^2-3-1]: 連続する二つの統合して一緒にできるムーブがある(たとえば`R' R2`=`R`)ときや、逆手順が含まれる(`L L'`のような場合)とき、1手以上のムーブが**キャンセルする**と言います。たとえば、F2Lの最後が`...U R2 F'`で終わって`F R U R' U' F'`というアルゴリズムを使うとき、**3手キャンセル**します。`...U R2 F' F R U R' U' F'`=`U R' U R' U' F`となります。
[^2-3-1]: [https://www.speedsolving.com/wiki/index.php/Commutator](https://www.speedsolving.com/wiki/index.php/Commutator)
[^2-3-1-2]: 例外はあります。たとえば、[Tomoaki Okayama (岡山友昭)](https://www.worldcubeassociation.org/persons/2009OKAY01)による次の実例と、そのディスカッションを読んでみてください。[https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-21#post-440873](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-21#post-440873)
[^2-3-2]: `[A:B]` = `A B A'`という記法は**conjugate**(共役、対になった、結合)を表します。`A`という手順は**セットアップムーブ**とも呼ばれます。
[^2-3-3]: これらのケースについては、speedsolving.comでのJackWのスレッドが説明してくれます。[https://www.speedsolving.com/forum/threads/2-gen-edge-cycles.56224/](https://www.speedsolving.com/forum/threads/2-gen-edge-cycles.56224/)
[^2-4-1]:  大会規則で「無制限の色付きステッカー」の持ち込みが許可されているのはこのためです。
[^2-4-1-2]: ステッカーは3-cycleの動きが1から2、2から3、3から1へとわかるように貼ります。
[^2-4-1-3]: 順番を決めるやりかたは他にも同様のものがあります。まずコーナーから始めたり、好きなステッカーから始めたりすることができます。首尾一貫してさえいればよいです。
[^2-4-1-3-2]: 注意事項：もしスケルトンの中に連続した2手の平行な回転(R、Lなど)があるなら、試しに入れ替えてみて、もっといいインサーションができないかを探してみましょう。この実例ではそういうことはありませんが、やってみるまでわかりません。
[^2-4-1-4]: 気を付けること：スケルトンにおいて二つの連続した平行な層の回転があるときには、相互に入れ替えてみて、よりよいインサーションがないかを探すこと！今回はそうではありませんが、決してわかりません。
[^2-4-1-5]: 最後の2手(`U' D`)はE列の中層回転(`E'`)と等価ですから、コーナーには影響しません。このムーブをする前後で3-cycleは持ち替えを法(modulo)として同じものです。（この場合はy'/y持ち替え）
[^2-4-1-6]: `B2 U' F' U B2 U' F U`もある。
[^2-4-1-7]: コーナーの2-cycleが2つあるなら、インサーションを2回繰り返して揃えてもよいです。あとの節を参照してください。
[^2-4-2]: これは別の何らかの方法で揃える必要があります。もう一回インサーションをする、など。
[^2-4-2-2]: 私はコーナーには番号を振って、エッジには文字を振るのが好みです。こうすれば取り間違えることがありません。
[^2-4-4]: [http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-126#post-1009830](http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-126#post-1009830)
[^2-4-4-2]: コミュテータについて話すときには、「ピース」と「ステッカー」は違うものであることに気をつけましょう。
[^2-4-5]: もっと知りたい読者のためには、speedsolving.comのFMCスレッドでの[この投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666185)から始まるディスカッションが興味深いでしょう。特に、[2つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666199)では**5点交換を揃えるための3点交換の組み合わせを見つける「法則」についての数学的証明があります。**[3つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666209)では、私が本書で行った説明と同じようなことが書いてあります。（私がこのテクニックを学んだのもこの投稿からです）[4つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-51#post-666313)にはこの手法を使ったソルブの実例が載っています。
[^2-4-9]:[https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-214#post-1247800](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-214#post-1247800)
[^2-4-9-2]: [https://www.speedsolving.com/threads/the-fmc-thread.13599/page-28#post-488378](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-28#post-488378)
[^2-4-10]: ほとんどの例はこの投稿からです。 [http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-42#post-614593](http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-42#post-614593)。一部、私の個人的な意見を加えて調整しています。
[^2-4-11]: [https://fewestmov.es/if](https://fewestmov.es/if)
[^2-5-1]: もちろん(FMCにおいては)何かをしてはいけないということはまったくありませんが、**エッジの向きを揃えてからそれをまた崩してしまうのはあまり賢いやり方ではありません。** 望むなら「部分的なEO (Partial EO)」からスタートしてもいいでしょう。
[^2-5-2]: [https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S](https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S)
[^2-5-3-1]: https://www.speedsolving.com/threads/introducing-a-variation-for-fewest-moves.67299/
[^2-5-3-2]: https://docs.google.com/document/d/1oZwr2aSllFBL5lhbLTiWKQWplfk4i0LN0wA0uskeLJs