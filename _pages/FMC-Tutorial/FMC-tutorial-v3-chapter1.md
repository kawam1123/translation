---
title: 第1章 - 最少手数競技入門 by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 22:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/chapter1
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
[戻る：イントロダクション](introduction){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第2章](chapter2){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->

## 既成概念にとらわれずに考える (Think Outside the Box)
あなたのメイン解法が何であれ、その一つの解法の知識だけで解こうとするのはFMCにおいて最悪のやり方です。**どんなときも一つの解法／メソッドに限定してはいけません。** FMCでは、あらゆる状況を活用するようにしましょう。

たとえば、あなたが2x3x3ブロックを作ったとしましょう。ここからどうソルブを勧めていくかには、いくつもの可能性があります。後の「クロス」エッジを揃えてからCFOPにおけるF2Lをやっても構いません。Petrusのようにエッジの向きを揃えもよいですし、FreeFOPやHeiseを使ってもっと自由にブロックを作ってもよいでしょう。どの解法を使ってもよい結果になるでしょう。なので、最もよいやり方は、**使える解法を全て使って解いてしまうということです。**（全部でなくてもよいですが、知っていることをなるべく多く使いましょう）

発想を柔軟にして「既成概念にとらわれず」に考えるには、少し逆説的ですが、**まず多くの既成概念を知ることが最良の方法です。**つまり、多くの解法を学びましょう。

この章では、FMCにおける最も有益（だと私が考える）な解法について簡単に説明します。

解法の開発された歴史やスピードソルブにおける利点／欠点については話しません。それぞれの解法について、オンラインで参照できるチュートリアルのリンクをつけますが、Googleやspeedsolving.comなどでさらなる情報を調べることをお勧めします。speedsolving.comのフォーラムにある[「初心者向けスピード解法の選び方ガイド(Beginner's Guide to Choosing a Speedsolving Method)」](https://www.speedsolving.com/threads/beginners-guide-to-choosing-a-speedsolving-method.43471/)はよく使われている4つの解法について知るよいきっかけになるでしょう。(スピード解法について考えるなら、という注意書きが付きます)

ここでは、以下の4つの解法についてそれぞれ書きます。
- Petrus
- Roux
- ZZ
- CFOP

<!--
Chapter 1
Think Outside the Box
Whatever your main method is, forcing yourself to only use that method is the worst thing
you can do in FMC. You should never restrict yourself to only one method, but try to
exploit every situation.
For example, suppose you have built a 2x2x3 block; now you have many possibilities: you
can place the last “cross” edge and finish the F2L (CFOP), you can orient edges (Petrus) or
try to build more blocks freely (FreeFOP, Heise) and so on. Any of this methods may lead to a
good solution, so the best thing to do is to try to use them all (or most of them at least).
The best way to open your mind and learn how to think outside the box is, maybe a little
paradoxically, to get into many “boxes”, that is to learn many methods. Here I will briefly
describe those that are, in my opinion, the most useful methods for FMC, without talking about
their development history nor their pro/cons in speedsolving. For each of these methods I will
provide a link to an online tutorial, but I suggest you look for more information about them
on google or speedsolving.com. The Beginner’s Guide to Choosing a Speedsolving Method1 on
speedsolving.com forum, although mainly thought for speedsolving, is a good starting point for
getting more information about the 4 most commonly used methods (CFOP, Roux, ZZ and
Petrus).
-->

### 1.1 Petrus
Petrusのステップは次のようなものです。
1. 2x2x2ブロックを作る
1. 2x2x2ブロックを2x2x3ブロックに拡張する
1. エッジの向きを揃える
1. 最初の二層を揃える(F2L)
1. Last Layer(LL)を揃える (本来は3つのステップに分割されています)

**ブロックビルディング[^1-1-Petrus]のスキルを高めることは、FMCの上達のために必須のものです。** Petrusを学ぶことでこのスキルが上達するでしょう。ステップ1とステップ2の解き方を効率よく学ぶためには、常にブロックの作り方をいくつもを探さなければなりません。つまり、**熟練のキューバーのソルブを見て、そのリコンストラクションから学ぶことが非常に役に立ちます。** 熟練者でれば、ほとんど常に最適な2x2x2ブロックを見つけることができるので、あなたの解答と(コンピュータで探索した)最適な解法[^1-1-Petrus-2]を比較してみること役に立つでしょう。

ステップ3では、エッジがキューブのどこに位置しているかに関係なく、エッジの方向を認識する手法を学ぶことができます。エッジが反転している状態はFMCをやる上で最悪のものですから、これもまた重要なスキルになります。このステップでは、ZZのほうがPetrusよりもわかりやすいかもしれません。

Last Layerのアルゴリズムを全て学ぶ必要はありません。他のメソッドについても同じです。次の章ではどのようにソルブを前に進めればいいのかを説明しますが、この時点では「Last Layer」を処理するステップは最少手数競技のソルブにおいてはあまり利用されないということを覚えておいてください。

Lars Petrus Website: [http://lar5.com/cube/](http://lar5.com/cube/)

<!--
1.1 Petrus
Petrus’ steps are the following:
1. Build a 2x2x2 block.
2. Expand the 2x2x2 block to a 2x2x3 block.
3. Orient edges.
4. Complete the first 2 layers (F2L).
5. Solve the last layer (originally divided into 3 steps).
Having a good blockbuilding2
skill is mandatory if you want to get good at FMC, and
practicing Petrus is the best way to acquire it. To learn how to solve steps 1 and 2 efficiently,
you need to think and try to explore different ways of building blocks every time; it is also very
useful to study reconstructions of expert cubers’ solves. For the first step it is also helpful
to compare your solutions with the optimal ones, given by an optimal solver3
, since for an expert
1
https://www.speedsolving.com/forum/threads/beginners-guide-to-choosing-a-speedsolving-method.
43471/
2
“Blockbuilding” or “block-building” is the technique consisting of making blocks of pieces and then joining
them together. It is often seen in opposition to the way of building the F2L used in CFOP (see below), but this
can also be seen as a kind of blockbuilding. A more suitable contrast is given by comparing it to other techniques,
such as edge orientation (Petrus, ZZ), “Corners First” solving, using algorithms or commutators. All of these
techniques are explained in this book.
3For example HARCS, freely available online: https://www.speedsolving.com/forum/threads/
harcs-jarcs-replacement-cube-solver.63241/
9
10 CHAPTER 1. THINK OUTSIDE THE BOX
it should be (almost) always possible to find an optimal 2x2x2 block.
Step 3 teaches you how to recognize an edge’s orientation regardless its position in the cube.
This is another important skill, since flipped edges are one of the worst thing you may come
across during an FMC solve. For this step, as well as for step 4, ZZ may be a better teacher
than Petrus.
You don’t have to learn every algorithm for solving the last layer (the same is true for other
methods too). In the next chapter I will explain in detail how you should proceed. For now it is
enough to be aware that the “last layer” step usually is not included in Fewest Moves solutions.
Lars Petrus Website: http://lar5.com/cube/.
-->

### 1.2 Roux
Rouxのステップは次のようなものです。
1. 3x2x1ブロック(FB, First Block)を作る
1. 最初のブロックの反対側に3x2x1ブロックをもう一つ作る　(SB, Second Block)
1. LLのコーナーを揃える。M列を気にする必要はない　(CMLL)
1. 残りの6つのエッジを揃える　(LSE, Last Six Edge)

Petrusはブロックビルディングを学ぶには素晴らしい解法ですが、Petrusだけを使うというのは間違いです。あわせてRouxのブロックビルディング（特に最初の2つのステップ、あわせてF2Bと呼ぶ）を学ぶことで、スキルが完成に近づくでしょう。また、この解法では熟練のキューバーの解法から学ぶことが多くあります。

PetrusのLast Layerについて書いたこと、Rouxのステップ3でもまったく同じです。ステップ4ではこの弊害を除くことができますが、Mのような中層回転は全て2手としてカウントされることは忘れないでください！（少なくとも、Rouxの標準的なLSEのやりかたは避けましょう。つまり、MとUだけで解くやりかたです）

- Waffle's Roux Tutorial: [http://wafflelikescubes.webs.com/](http://wafflelikescubes.webs.com/)
- Kian Mansour's Roux Tutorial: [https://sites.google.com/view/kianroux/home](https://sites.google.com/view/kianroux/home)

**訳注：**  
実際の最少手数競技においては、解答用紙に**M、S、Eの中層回転（スライスムーブ)**の記号を書くことは認められていません。[規則12a](https://www.worldcubeassociation.org/regulations/translations/japanese/#12a)に定義されている3x3x3の回転記号のみを使うようにしましょう。ここでは**「RouxメソッドのやりかたでM列を使う（解答用紙にはR L'のように書く）と2手としてカウントされ、手数が多くなりがちになるので避けたほうがよいですよ」**ということを言っています。  
ただし、後述するように、[スライスインサーション（フリースライス）](chapter3#freeclice)という手法によってこのデメリットを解消することもできます。
{: .notice--danger}

<!--
1.2 Roux
1. Build a 3x2x1 block.
2. Build another 3x2x1 block, opposite to the first one.
3. Solve the corners of the last layer, without necessarily preserving the M layer (CMLL).
4. Solve the last six edges (LSE).
Petrus is an excellent method to learn blockbuilding, but forcing yourself to only use Petrus
is still wrong: learning also Roux (especially the first 2 steps) will make your skill in some sense
more complete. Also for this method it will be useful to study solutions of more expert cubers.
For step 3 it still stands what was said about last layer algorithms, while step 4 is to be
avoided like plague (at least, avoid solving it in the “standard” way, i.e. using only M and U
moves): remember that every inner layer move, like M, is worth 2 moves in standard metric!
Waffle’s Roux Tutorial: http://wafflelikescubes.webs.com/.
-->

### 1.3. ZZ
ZZのステップは次のようなものです。
1. EOLine（全てのエッジの向きを合わせて、DFとDBに置くことで、キューブをRLU回転だけで解けるようにする）
1. F2L
1. Last Layer

前述のように、エッジオリエンテーション(EO)を認識して解くことは非常に有益なスキルであり、ZZは間違いなくこれを学ぶ最良の方法でしょう。「エッジの向きを揃える」というのは、「ブロックビルディング」よりも抽象的な概念ですから、最初は難しく感じるでしょう。しかし、パニックにならないでください。練習すれば徐々に簡単になっていきます！

ステップ2はPetrusのステップ4と同じものですが、R面とL面に同時にブロックを作らなければなりません[^1-3-ZZ]。これをやることで、さらにブロックビルディングのスキルが高まるでしょう。

<!--
1.3 ZZ
1. EOLine (orienting all edges and placing DF and DB, leaving the cube to be possibly solved
moving only the R, L and U layers).
2. F2L.
3. Last Layer.
As mentioned earlier, recognizing and solving edge orientation is a very useful skill and ZZ
is surely the best way to learn it. At first sight “orienting edges” can be hard, because it is a
more abstract concept than “building blocks”, but don’t panic, it gets way easier with practice!
Step 2 is more or less the same as Petrus’ step 4, but you have to build the blocks on both
R and L side at the same time4
. This is also going to improve your blockbuilding skills.
-->

### 1.4. CFOPとFreeFOP
古典的なCFOPのステップは次のようなものです。
1. クロスを作る
1. 4つのコーナーとエッジのペアを挿入する
1. OLL (Orient Last Layer)
1. PLL (Permute Last Layer)

古典的なCFOPは**FMC向きのあまりよい解法ではないと考えられています。**しかし、コーナーとエッジのペアを挿入するときに、いくつかの方法を使うということを知っておくと役に立つことがあります。

FreeFOPでは、最初の二つのステップは「自由な」ブロックビルディングF2Lに変わります。

何にせよ、スキップができない限り、Last LayerをOLLとPLLで解くことはまったくおすすめできない方法です。

Badmephisto's Tutorial: [http://badmephisto.com/](http://badmephisto.com/)

<!--
1.4 CFOP (Fridrich) and FreeFOP
In classic CFOP the steps are the following:
1. Cross (4 edges on the same side).
2. 4 corner/edge pair insertions.
3. OLL (Orient Last Layer).
4. PLL (Permute Last Layer).
Classic CFOP s not considered a good method for FMC, but in some situation it is useful
to know different ways to insert a corner/edge pair.
In FreeFOP, the first two steps are replaced by a “free” blockbuilding F2L.
Anyways, I strongly advise against solving the last layer with OLL + PLL, unless you get
to skip one of the two steps.
Badmephisto's Tutorial: http://badmephisto.com/.
4For speedsolving, it may be better to solve one block at the time, since it is usually more ergonomic. But this
is not the case for FMC, as efficiency (i.e. number of moves) is the only thing that matters!
-->

### 1.5 キーホールF2L
キーホールは厳密にはキューブの解法ではなく、最初の二段を解くためのテクニックです。LBL(Layer by Layer)からCFOPの中間にあたる解法として位置づけられています。ステップは次のようなものです。

1. クロス
1. 1段目に3つのコーナーを配置する
1. 3つの中層エッジをインサートする。「自由に」コーナースロットを使う
1. コーナーとエッジのペアをインサートする。CFOPやLBLと同様

最初の２ステップをブロックビルディングに置き換えることとができます。また、中層のエッジも同時に揃えることで効率化することもできるでしょう。クロスと3つの中層エッジを揃えてから、3つのコーナーを「自由な」エッジを使って揃えるというバリエーションもあります。

非常にシンプルですが、この解法はFMCにおいてはとても役に立ちます。

<!--

1.5 Keyhole F2L
Keyhole is not really a method to solve the cube, but a technique to solve the first two layers.
It is considerate an intermediate method between “Layer by Layer” and CFOP. The steps are
the following:
1. Cross.
2. Place 3 first layer corners.
3. Insert 3 middle layer edges, using the “free” corner.
4. Insert the last corner/edge pair, as in CFOP or as in LBL.
To improve efficiency you should replace the first two steps with blockbuilding and place a
few middle layer edges in the meantime. A variation consists in solving the cross and 3 middle
layer edges, and then placing 3 first layer corners using the “free” edge.
Despite its simplicity, this method can be very useful in FMC.
-->

### 1.6 Heise
1. 2x2x1の「四角」を作る
1. 「四角」を揃えてエッジを合わせることで、F2L-1の状態を作る。
1. 残った5つのエッジと2つのコーナーを揃える
1. 最後の3つのコーナーをコミュテータで揃える

もしあなたが熟練者のアドバイスを無視して、一つの解法だけを使ってFMCをやりたいというなら、Heiseを選ぶのがよいでしょう。**この解法を一直線[^1-6-Heise]に使うだけでも平均して40手以下で解くことができるでしょう。**非常に極端な解法ですが、同時に極めて効率的です。

最初の二つのステップは奇妙ですが、**F2L-1 [^1-6-Heise-2] を作ってから、全てのエッジの向きを揃えるという点では効率的なやり方です。**FMCの基本である「何も制限するな」「様々な状況を活用せよ」というコンセプトに完全に沿っており、ブロックを考えうる最高の方法で作ることができます。

三つ目のステップは複雑ですが、F2Lを完成させてLast Layerのアルゴリズムをやるよりずっと効率的です。これを練習することで、すでにたくさんのブロックが作られて使える動きが制限されているときでも、ブロックを作って動かすことができる能力が得られるでしょう。(同時に、このステップは非常に難しい理由でもあります)

最後のステップではコミュテータを使います。FMCにおいては、インサーションが使えるようになるということです。（コミュテータとインサーションについては、次の章で説明します）

Heise method's page on Ryan Heise's website: [http://www.ryanheise.com/cube/heise_method.html](http://www.ryanheise.com/cube/heise_method.html)

<!--
1.6 Heise
1. Build four 2x2x1 “squares” (all sharing one colour).
2. Match the squares and orient edges.
3. Solve the remaining 5 edges and 2 corners.
4. Solve the last 3 corners using a commutator.
If you decided not to follow the experts’ advice and use only one method for FMC, Heise
would be a good choice. This method alone can lead to and average of fewer than 40 moves for
linear5
solves. It is an extreme method, but also extremely efficient.
First two steps are a strange but efficient way of building an F2L-16 and orient all edges. The
“don’t restrict yourself” and “exploit different situations” concepts is perfectly applied, allowing
one to solve the blocks in whatever is the best way.
The third step is complex, but it is a more efficient alternative to finish the first two layers
and then solving the last layer using algorithms. Practicing it will give you the ability to build
and move around blocks when you are limited by the quantity of blocks already built (and this
is the reason why this step is so difficult).
For the last step you will need commutators; it allows, in an FMC solve, to use insertions
(both these techniques will be explained in the next chapter).
Heise method’s page on Ryan Heise’s website: http://www.ryanheise.com/cube/heise_
method.html. There you can find not only a detailed explanation of his method, but also other
useful information (see for example the Fundamental Techniques page).
5As in “linear” FMC, that is without trying different possibilities and/or cancelling or undoing moves.
6With “F2L-1” I mean an F2L minus a coner/edge pair.
12 CHAPTER 1. THINK OUTSIDE THE BOX
-->
### 1.7 何をどうやって学ぶか
当たり前のことですが、ここに書いたすべての解法を覚えて速くなることはゴールではありません。スピード解法でキューブを解くことはいくらか助けになることもありますし、それ自体が楽しいものです。しかし、**ここではスピードは気にしません。**ゴールは**できるだけ短い手順でキューブを解くことですから、効率的になるよう努めましょう。**  
**Color Neutral (CN)**[^1-7-1]であることも大切なことですし、**「不一致ブロック(Non Matching Blocks)」**(疑似ブロック、Pseudo-block)[^1-7-2]について取り組むのも役に立つでしょう。

しかし、スピード解法と最少手数競技用の解法の大きな違いは、**FMCではいくつもの異なる可能性を同時に試すことができるということです。**たとえばPetrusにおいては、2x2x3ブロックを作ったあとに6つの悪いエッジ(Bad edge)が残ったとき、最初から別のブロックを作り始めることもできますし、ブロックの作り方を途中で少し変えて状況をよい方向に持っていくこともできます。[^1-7-3]

それぞれの解法について少しだけアドバイスを書きます。
<!--
1.7 What and How to Learn
Obviously, getting fast with all of the methods described is not your goal. Doing some speedsolves
may help seeing some things faster and is fun, but we don’t care about speed. Since our
goal is to solve the cube with the fewest moves possible, you should try to be efficient. It is
also essential to be color neutral7 and it can be helpful trying to work with “Non Matching
Blocks”8
.
But the main difference between speedsolving and fewest moves solving is that in FMC you
can try different possibilities. If in Petrus, for example, you are left with 6 “bad” edges after
a 2x2x3, you can try to build a different block from scratch or to slightly modify the contruction
of the block you have found to improve your situation9
.
Here is some piece of advice for some of the methods described.
-->

#### 1.7.1 Petrus
- 2x2x2ブロックの完成後、拡張する方向は3通りあります。全ての場合を考えましょう！
- 2x2x2ブロックを作ってからやるよりも、2x2x3ブロックを直接作ってしまいましょう
- ステップ４では「不一致ブロック」を作ってみましょう
- ステップ４ではLast Layerをうまく変化させて簡単なケースを引きましょう（Heise Styleのラッキーケースでもよい）
<!--
• After completing a 2x2x2 block, you can expand it in 3 different directions. Make sure
to consider all of them!
• Try to build a 2x2x3 directly, instead of going through the 2x2x2 step.
• Try using Non Matching Blocks in step 4.
• In step 4 again, try influencing the last layer to get an easier case (even “Heise style”).
-->

#### 1.7.2 Roux
- 二つのブロックを同時に作ってみましょう
- 不一致ブロックを作ってみましょう
- SBを作るときにCMLLへの影響を考慮してみましょう。そして、CMLLのLSEへの影響を考慮してみましょう

<!--
• Try to build the two blocks at the same time.
• Try Non Matching Blocks.
• Influence the CMLL while finishing the second block, and the LSE during the CMLL.
-->

#### 1.7.3 ZZ
- エッジの向き(EO)を揃えたあと、「直線(Line)」を作らないほうがよいです。EOを壊さないように、直接ブロックビルディングをしましょう。直線を最初に作ること（ラインファースト）と左右のブロックを作ることの違いは、CFOPでクロス+F2LをやることとFreeFOPの違いと同じものです。
- エッジの向きを揃えたら、R、L、U、Dだけでキューブを揃えられる状態になったということです。F2Lをどんな向きからでもやることができます。
- PetrusやRouxと同じように、不一致ブロックを作ってみましょう。また、F2Lの途中ででLast Layerへの影響を考慮してみましょう。


<!--• After edges orientation, building the “Line” isn’t always a good idea: try blockbuilding
directly (without breaking the EO!). The difference between solving the line first and then
the right and left blocks is comparable to the difference between doing CFOP with cross
+ F2L pairs and doing FreeFOP.
• Once you have oriented the edges, you have reduced the cube to be solved moving only
the R, L ,U and D layers: you can build the F2L on any of these sides.
• As in Petrus and Roux, try using Non Matching Blocks and influencing the last layer while
building the F2L.
7Being able to solve the cube by starting with any “colour”; for example, starting from any cross in CFOP or
from any of the 8 possible 2x2x2s in Petrus.
8Sometimes also called “Pseudo Blocks”, especially in FMC. It is a useful technique in Roux, ZZ and Heise,
but it can be used in other methods as well. It consists of building blocks different from the ones you should build
if you are following the method, but that can be placed in the same “slots”. For example, in Roux, the second
3x2x1 block can be any of the 4 that can be built on the side opposed to the first one. This technique is very
powerful if combined with premoves, that will be explained in Chapter 3.
9Trying to influence a later step while solving another the current one is a good habit, which will be discussed
again later.
-->

#### 1.7.4 CFOP/FreeFOP
- 定義によって、少なくともCFOPはFreeFOPの特殊なケースですから、**FreeFOPはCFOPよりよいものです。** 少なくとも**XCross**[^1-7-4-1]を作ってみましょう
- 「4つのエッジが反転したケース」を避けつつ、Last Layerのエッジの向きに影響を与えてみましょう。いくつかのZBF2Lアルゴリズム[^1-7-4-2]が役に立ちますが、これを暗記する前に**どういう仕組みで機能しているのかを学びましょう。**
- 最適なペアのインサーションアルゴリズムはあまり知られていません。これを研究しましょう。繰り返しますが、単に学ぶよりも仕組みを理解してみましょう。
- **「マルチスロット」**を試してみましょう。これは複数のペアを同時に入れるということです。最も簡単なケースは、D面のムーブをセットアップとして使う場合です。（例：`D R U R' D'`）このテクニックのアルゴリズムはオンラインで閲覧できますが、「自由に」やってみることをおすすめします。たとえば、次のソルブ例で私が二つ目、三つ目、四つ目のペアをどのようにインサートしたかをご覧ください。: [https://www.
speedsolving.com/forum/threads/the-3x3x3-example-solve-thread.14345/page-238#post-1013053](https://www.
speedsolving.com/forum/threads/the-3x3x3-example-solve-thread.14345/page-238#post-1013053)
> Next: D2 F2 U' B2 D' B2 D2 F2 L2 F2 U' B' D2 R2 B2 R' D' B L2 F R
>
> こちらをどうぞ、CFOPers!
>
> x2  
> B2 D2 B' D' M D'  
> R F U F' R'  
> U R2 B' R' U R' U2 R U2 R' U B  
> R U Lw' D' R D B' D' R' D  
> R2 B E B2 E' B R2  



<!--
• FreeFOP is better than CFOP, at least because CFOP is a special case of FreeFOP,
by definition. Try at least to build and XCross10
.
• Try to influence the last layer edges’ orientation, avoid the “4 edges flipped” cases; some
ZBF2L algorithms can be useful, but instead of learning them by heart try to study them
to understand how they work.
• Some optimal pair insertion algorithms are not well known (for example F2 U R U' R' F2):
study them, again trying to understand them rather than learning them.
• Try “multislotting”, that is inserting more pairs at the same time. The easiest case is
when you use a D-layer move as setup, for example D R U R' D'. There are algorithms
for this technique available online, but I suggest trying in a “free” way: for example,
look at how I have inserted the second, third and fourth pair in this solve: https://www.
speedsolving.com/forum/threads/the-3x3x3-example-solve-thread.14345/page-238#
post-1013053.
10Cross and first pair, built at the same time. It can also be seen as a 2x2x2 block + 2 edges.
14 CHAPTER 1. THINK OUTSIDE THE BOX
-->

[戻る：イントロダクション](introduction){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：第2章](chapter2){: .btn .btn--inverse}

[^1-1-Petrus]: **ブロックビルディングとは、複数のピースからブロックを作り、つなげるテクニックのことです。**CFOPにおけるF2Lとは大きく違うものと見なされがちですが、F2Lも一種のブロックビルディングと見なすことができます。対比すべきものとしては、エッジオリエンテーション(EO、PetrusやZZで用いられる)や「コーナーファースト」、アルゴリズムやコミュテータの利用などがあります。これらのテクニックは全て本書で説明されます。
[^1-1-Petrus-2]: たとえば、HARCSというは無料で利用できます。 https://www.speedsolving.com/forum/threads/
[^1-3-ZZ]: スピード解法では、ブロックを一つずつ揃えていくほうが、人間工学に叶った動きになるため、望ましいです。しかし、FMCにおいてこれは当てはまりません。効率性（つまり、手数）だけを気にするべきです！
[^1-6-Heise]: ここでいう「一直線に」(Linear)解くとは、FMCにおいては別の可能性を考えたり、キャンセル／やり直しを考えないで解くことを言います。
[^1-6-Heise-2]: F2L-1とはF2Lの完成状態から、コーナーとエッジのペアを一つ欠く状態を言います。
[^1-7-1]: **Color Neutralとはキューブをどの色からスタートしても解くことができることを言います。**たとえば、CFOPのクロス色がどの色でもできる、あるいはPetrusの2x2x2ブロックを8つあるパタンからどれでもできるということです。
[^1-7-2]: 不一致ブロックは、特にFMCにおいて**「疑似ブロック」(Pseudo-block)**と呼ばれることがあります。これはRouxやZZ、Heiseにおいて役に立つテクニックですが、他の解法でも使うことができます。疑似ブロックは、作る必要があるものとは異なるブロックで構築されますが、同じ「スロット」に配置されます。たとえば、Rouxにおいては、3x2x1のSB(Second Block)はFBの反対側にある4つのいずれかのブロックです。このテクニックはpremoveと組み合わせることで非常に強力なツールになります。詳細は第三章で説明します。
[^1-7-3]: **現在のステップで工夫することで次のステップに何らかの影響をもたらす**のはよい習慣です。この点については後の章でまた書きます。
[^1-7-4-1]: XCrossとは、クロスと最初のペアを同時に作ることです。2x2x2ブロックと2つのエッジを同時に揃えることと見なすこともできます。
[^1-7-4-2]: 訳注。ZBF2LはEOLS (Edge Orientation Last Slot)とも呼ばれます。「F2Lの4つ目の手順を調節することでEOを同時に処理し、F2L終了時に必ず上面に十字が出来るようにするというSubstepです。VHLSとは違い、IT化の時点で手順を変える場合もあるというのが特徴です。」([CubeVoyage](https://cubevoyage.net/speedcubing/3x3x3/advancedsubsteps/)より)