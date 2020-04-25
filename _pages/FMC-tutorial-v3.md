---
title: "最少手数競技入門 - ルービックキューブを少ない手順で解く by Sebastiano Tronto 第三版"
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
header:
  teaser: /assets/img/333fm.jpg
permalink: /FMC/FMC-Tutorial/v3/
redirect_from: ../FMC/FMC-tutorial.html
layout: single
classes: wide
toc: false
tocright: true
toc_icon: "cog"
toc_sticky: true
author_profile: false
sidebar: true
footnote_script: true
---
<!--
訳注：原文はコメントアウトで表示し、必要に応じて参照できるようにしています。
-->
<!--
Fewest Moves Tutorial
Solving a Rubik’s Cube with as few moves as possible
v3.01
Sebastiano Tronto
April 17, 2020
-->

![333fm](../../../assets/img/333fm.jpg){:width="400px" height="auto" class="img-responsive align-center"}

[第三版](#){: .btn .btn-success}  

**Written by Sebastiano Tronto**  
Fewest Moves Tutorial - Solving a Rubik’s Cube with as few moves as possible  
v3.01  
Sebastiano Tronto  
April 17, 2020  
Original document (3rd edition): [Fewest Moves Tutorial](https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf)  
Older edition (2nd edition): [Fewest Moves Tutorial 2nd edition](https://fmcsolves.cubing.net/fmc_tutorial_ENG_v2.pdf)  
License under CC BY 4.0

Japanese Translated by kawam1123  
version 0.1  
April 20, 2020  
License under CC BY 4.0

**免責事項：**  
本ドキュメントは、**2020年にSebastiano Tronto氏によって書かれたFewest Moves Tutorial(version3.01)を日本語に翻訳したものです。** 2019年12月、本チュートリアルを日本語に翻訳されたものが公開されていなかったため、翻訳プロジェクトをスタートしました。本記事の内容については、最少手数競技に関する知識や用語を確認しながら翻訳を進めていますが、翻訳者の技量不足により不正確である場合があります。あらかじめご了承ください。  
また、すぐに最少手数競技のやりかたを覚えたいという方には、既に[WRCC](http://wrcc.main.jp/commentary_fmc/fmc/index)や[TRCC](http://trcc.sub.jp/solution/fmc/fmcindex.html)の素晴らしい解説記事がありますので、こちらもあわせてご参照ください。  
This documantion is a Japanese translated edition of Fewest Moves Tutorial (Third Edition) by Sebastiano Tronto. Since no translation in Japanese had been published at December 2019, I started a tranlation project for the tutorial. I am translating the document looking up the basic knowledges and the technical terms on FMC, but the translated content might be wrong by reason of my lack of translation and FMC skills. If you find any mistakes in the translation, please let me know!
{: .notice--warning}

**第3版の公開に際して**  
2020/01/14に本チュートリアルの第3版が公開されました！（2020/04/17に修正版v3.01が公開されました）  
この日本語版は、第3版の内容に沿って翻訳中のものです。[第2版を翻訳したもの](../v2/)もありますので、興味のある方はこちらもご参照ください。また、**原著者がGitHubにリポジトリを作成し、原文のLaTeXファイルや画像ファイルなどを公開しています。** 詳細は[こちら](https://github.com/sebastianotronto/fmctutorial)をご覧ください。
{: .notice--success}

**翻訳にあたっての謝辞：**  
この素晴らしいチュートリアルを無料で公開してくれているSebastiano Tronto氏に最大限の感謝を申し上げます！  
Special thanks to Sebastiano Tronto, a FMC superstar, for publishing this wonderful tutorial for free!  
Un ringraziamento speciale a Sebastiano Tronto, una superstar FMC, per aver pubblicato gratuitamente questo meraviglioso tutorial!
{: .notice--success}

**翻訳者注：**  
本ドキュメントは、未完成です。原文はコメントアウトされた状態で保存されています。翻訳に協力してくださる方は、コメントアウトを外して日本語の翻訳を書き込んでください。翻訳の進捗は[GitHubのリポジトリ](https://github.com/kawam1123/translation)で管理しており、画像ファイルなどもこちらに格納されています。
{: .notice--info}

<!-- 第二版進捗
**翻訳進捗**

|章|ページ|進捗|メモ|
|:---|:---:|:---:|:---:|
|序文                                   |1-8    |[完了](#){: .btn .btn-success}     |2019/12/31完了|
|1章 Think Outside the Box              |9-14   |[完了](#){:.btn .btn-success}      |2020/01/03完了|
|2章 How to Proceed During a Solve      |15-34  |[完了](#){:.btn .btn-success}     |2020/01/09完了|
|3章 Advanced Tools                     |35-44  |[作業中](#){: .btn .btn-danger}    |2020/01/11着手|
|4章 Some Other Methods                 |45-48  |[未着手](#){: .btn .btn-danger}    ||
|5章 How To Practice                    |49-50  |[完了](#){:.btn .btn-success}      |2020/01/03完了|
|6章 In Competitoin                     |51-52  |[作業中](#){: .btn .btn-warning}   |2020/01/03着手|
|付録A Other Resources                  |53-54  |[未着手](#){: .btn .btn-danger}    ||
|付録B Notation                         |55-56  |[未着手](#){: .btn .btn-danger}    ||
|付録C Last Layer Algorithms            |57-58  |[未着手](#){: .btn .btn-danger}    ||
{: .table-hover }
-->

<!-- TOC -->
<!--
## 目次
- [最少手数競技入門 - ルービックキューブを少ない手順で解く](#最少手数競技入門---ルービックキューブを少ない手順で解く)
    - [第二版への序文 (Preface to the Second Edition)](#第二版への序文-preface-to-the-second-edition)
    - [本書について (About this Book)](#本書について-about-this-book)
        - [前提条件](#前提条件)
        - [ソルブ実例について](#ソルブ実例について)
        - [謝辞](#謝辞)
        - [免責事項](#免責事項)
    - [目次](#目次)
    - [イントロダクション](#イントロダクション)
    - [第１章：既成概念にとらわれずに考える (Think Outside the Box)](#第１章既成概念にとらわれずに考える-think-outside-the-box)
        - [Petrus](#petrus)
        - [Roux](#roux)
        - [ZZ](#zz)
        - [CFOPとFreeFOP](#cfopとfreefop)
        - [KEYHOLE F2L](#keyhole-f2l)
        - [Heise](#heise)
    - [第２章 ソルブの進め方](#第２章-ソルブの進め方)
    - [第３章　高度なツール (Advanced Tools)](#第３章　高度なツール-advanced-tools)
    - [第４章　その他の手法 (Some Other Methods)](#第４章　その他の手法-some-other-methods)
    - [第５章　練習方法 (How To Practice)](#第５章　練習方法-how-to-practice)
    - [第６章　公式大会 (8)In Competition)](#第６章　公式大会-8in-competition)
    - [付録A　その他の参考資料 (Other Resources)](#付録a　その他の参考資料-other-resources)
    - [付録B　回転記号 (Notation)](#付録b　回転記号-notation)
    - [付録C　LLアルゴリズム (Last Layer Algorithms)](#付録c　llアルゴリズム-last-layer-algorithms)
-->
<!-- /TOC -->

## 第三版への序文 (Preface to the Third Edition)
**昨年(2019年はFMCにとって素晴らしい年になりました。**2年間、平均24.00手から更新されていなかった世界記録は、Reto Bubendorf (23.00), MarkやBoyanowski (22.33) や私自身(Sebastiano Tronto) (22.00)によって、2手も短くなりました。まとめると、2019年には11人が平均24手の壁を破ったのでした。単発世界記録は18手から16手になりました。

2019年は記録更新だけの年ではありません。**Domino Reduction(DR)が普及した年でもあります。**1年前まで、この手法はトップ競技者によってたまに使われる程度で、継続的に使うのは難しいと考えられていました。しかし、よくあることですが、これがそこまで難しいものではないと気付いた人々がいて、誰にとっても簡単なものになりました。わずか数か月の間で、この手法は多くのトップ競技者がほとんどのソルブで使うようになるまで流行してきました。FMCの新時代が始まったのです。

するとこのチュートリアルはどうなるでしょう？第三版のチュートリアルは「新時代」に向けたものでしょうか？実はそうではありません。「旧時代」のチュートリアルの最後のアップデートだと思うかもしれません。いくつか新しく追加したいことがありましたが、最近の発展を踏まえたものは少しだけです。

このチュートリアルはFMCを学ぼうとする人にとっては素晴らしい出発点であり続けると思います。しかし、新しい手法が開発されていくにつれて、ここに記載されたトピックやその説明方法は陳腐化していくでしょう。願わくば、この文書を最新にものにアップデートしつづけて、数年後にも役に立つガイドであり続けるようにします。

<!--
Last year has been incredible for FMC. After being stuck at 24.00 for almost two years, the
world record average has finally dropped by 2 moves, thanks to Reto Bubendorf (23.00), Mark
Boyanowski (22.33) and myself (22.00). In total, eleven different people broke the 24-moves
barrier for average in 2019. The world record single also dropped from 18 to 16.
But 2019 was not only the year of the records: it was also the year when domino reduction
became popular. Until a year ago, this method was only occasionally used by top solvers and
was considered difficult to use consistently. However, as often happens, it just takes a few people
that realize that something is not as difficult as it seems to make it easy for everyone. In a matter
of months, this method has grown in popularity to the point that many top solvers use in for
most of their solves. A new era of FMC has begun.
Where does this leave this tutorial then? Is version 3.0 the tutorial for this “new era”? Not
really. You might think of this as the last update of the “old era” tutorial. There were a few
things that I wanted to add, and only some of them are inspired by the recent developments.
I believe that this tutorial is still a great starting point for someone who wants to learn FMC.
However, as new methods get developped, the choice of topics included here or the way they are
explained may become obsolete. Hopefully I will be able to keep this document up to date, so
that it remains a useful guide for many years to come.
-->

### 変更点
前のバージョンから無数のタイポを修正し、多数の新しいことを加えました。.png形式の画像を.svgに入れ替えることにしたので、見た目がよくなっているはずです。

付録にあったLast Layerのアルゴリズムは省き、単にテキストファイルへのリンクにしました。EOに関するセクションは第二章に移動し、第四章の残りと第三章をマージしました。

その他、次のようなセクションを追加しました。それ以外は軽微な変更だけです。

- 2.4.6節、3.8節：エッジインサーションについて
- 2.5.3節：Partial Domino Reductionについて
- 3.4節：NISSを用いてよいEOを探す
- 3.7.1節： 歪んだセンターとNISS (Skew centers and NISS)
- 3.10節： 交換して短くする (Replace and shorten)
- 付録C：Reto Bubendorfによる演習問題 (Some exercises by Reto Bubendorf).
- 付録D：Domino Reduction概説

<!--List of changes
Since the last version of this tutorial I have fixed like a million typos and probably introduced
a lot of new ones. I have also decided to replace .png images with .svg ones, which look much
better.
I have removed the appendix with last layer algorithms and just linked a raw text file instead.
I have moved the general section on EO to Chapter 2 and merged the remainder of Chapter 4
with Chapter 3.
Other than that, I have added a few sections:
• Sections 2.4.6 and 3.8 on edge insertions.
• Section 2.5.3 about partial domino reduction.
• Section 3.4 about using NISS to find nice EOs.
• Section 3.7.1 “Skew centers and NISS”.
• Section 3.10, “Replace and shorten”.
• Appendix C, “Some exercises by Reto Bubendorf”.
• Appendix D, a short introduction to domino reduction.
All the rest is just minor changes.
-->

## 第二版への序文 (Preface to the Second Edition)
<!-- このセクションは第二版から修正しない -->
数年の間、このチュートリアルの新しいバージョンを作ろうと考えていました。いくつか修正や追加の必要な点があり、また、私自身の考え方が変わったことによって変更すべき点などがありました。

LaTeXで書き直そうとも考えました。LaTexのドキュメントは見た目がとても良くなるからです。ただし、唯一の欠点は、そうしてしまうと翻訳が難しくなるということです。このチュートリアルが高く評価されており、多くの他言語に翻訳をしてくれて、世界中で読めるようになっていくことを非常に嬉しく思います。翻訳者の皆さんそれぞれにお礼を言いたいのですが、ほとんどの方の名前を忘れてしまいました。

ですが、第二版を作るのをずっと後回しにしていました。大きな理由は、時間がなかったことではなく、モチベーションが足りなかったことです。しかし、2017年にパリで行われた世界大会 [^0-1]では、このチュートリアルについて感謝を言ってくださる方に多くお会いして、必要なモチベーションを得ることができました。全ての人が見返りを求めずにほかの人を助けている。このコミュニティの一員であることの素晴らしさを思い出して、私も再び「自分のやること」をやりたいと思いました。

<!--
Preface to the Second Edition
For a couple of years I have been thinking about making a new version of this tutorial. There
were small mistakes to correct, things to add somewhere and a couple of things to change, since
with time I have changed my point of view on a couple of things.
I also thought of rewriting in LaTeX, because LaTeX documents look way better than anything else. The only downside of this choice is that it may be more difficult to translate: I was
very happy to see that my tutorial was so much appreciated that people wanted to translate it
in many different languages to make it more accessible worldwide! I would like to thank them
all one by one, but I forgot most of their names.
But I have always postponed this second version. The main reason was that I din’t have
much time, but I also lacked motivation. At World Championship 2017 in Paris I have met
many people who thanked me for this tutorial, and this gave me the motivation I needed. I
remembered how nice it is to be part of such a nice community where everybody helps each
other without asking anything back, and I wanted to do my part - again.
-->

初版からの変更点のほとんどは見た目に関することです。最初のものよりけっこう長くなっていることに気づくかもしれません。この違いは、画像と空白ページによるものがほとんどです。文章を並べ替えて、単語のミスを修正しました（私の英語力はこの３年で成長してます！）。いくつか新しいことも加えたかもしれません。

次のような点を追加しました。

- 2.3.3節：「その他のエッジ3-cycle」（このケースについてはもっと書くことがありますが）
- 2.4.8節：「3エッジとコーナー」 インサーションについて
- 3.6節：「歪んだセンター(skew centers)」について
- 付録：回転記号とLLアルゴリズム

ほかにやったのは、ソルブ例にいい感じのボックスをつけたことです。（下のほうをご覧ください）

主な理由は、この本を自己完結型にしたいと思ったからです。初版では多くのソルブが単にリンクされていただけでした。ハイパーリンクをつけていますが、脚注に完全なリンクもあわせて書いています。これにより、この本は電子機器と紙の両方で読めるようになっています。

パーツの色について話すことがありますが、**配色は[標準配色](https://www.speedsolving.com/wiki/index.php/Western_Color_Scheme) [^0-2]で、標準の向き（白がU、緑がF）でスクランブルすることを想定しています。**

この第二版について言うことはこれぐらいです。次に進んでチュートリアルを楽しんでください！

<!--
The changes since the first version are mostly aesthetical. You may have notice that this
book is way longer than the first one: the difference is mostly pictures and blank pages. I have
rearranged a few sentences, corrected a few mistakes (my English got better in the last 3 years!)
and probably also added a few.
I have also added a couple of things:
• Section 2.3.3 Other Edge 3-cycles. But there is still much to be said about those cases.
• Section 2.4.8 about “3 edges and some corners” kind of insertions.
• Section 3.6 about solving with “skew centers”.
• Appendices for Notation and Last Layer algorithms.
Another thing I did was to add nice boxes for example solves - see below. This is mainly
because I wanted the book to be more self-contained, since many of the solves were just linked
in the first version. I have kept hyperlinks, but I have also almost always written the complete
link as a footnote. This makes this book suitable both to be read on an electronic device and
on paper.
When I occasionally talk about the colours of the pieces we are considering, I assume you
are using the standard color scheme1 and that you scramble in the standard orientation: white
on top and green on front.
I don’t have anything else to say about this second edition. Go on and enjoy the tutorial!
1
http://www.speedsolving.com/wiki/index.php/Western_Color_Scheme
3
-->
## 本書について (About this Book)
この本は、**WCA公式大会の公式競技のひとつである「最少手数競技（FMC、Fewest Moves Challenge）」と呼ばれる競技でよい結果を出すための指針となることを目的としています。**もしあなたが世界キューブ協会 (World Cube Association) やスピードキューブの公式大会について知らないのであれば、下記のイントロダクションを読んでみてください。

「最少手数競技」は、与えられたルービックキューブの状態(スクランブルされた状態)から、できる限り短い手数で解くものです。使えるのはいくつかのキューブ、ペン、そして紙だけです。コンピュータープログラムの利用は禁止されており、通常は時間制限があります。（WCA公式大会においては1時間、あるオンラインのものでは1週間など)

したがって、この本では一般的なアルゴリズムの説明はしません。一般的なアルゴリズムがFMCで役立たないということは、この本の残りの部分で繰り返し述べられており、次のようにまとめることができます。「たった一つのアプローチに限定することは、あまりにも窮屈！」

同様に、（短い）解法を生成するようなコンピュータープログラムについても言及しません。もしこのテーマに興味のある方は、www.jaapsch.netの[コンピューターパズルについてのページ](https://www.jaapsch.net/puzzles/index.htm)を一読することをおすすめします。

<!--
About this Book
This book is intended to be a guide to get good results in the so called “Fewest Moves Challenge”,
one of the official events in WCA competitions. If you don’t know about the World Cube
Association or speedcubing competitions, see the introduction a few pages ahead.
The “Fewest Moves Challenge” is about solving a specific (scrambled) position of the Rubik’s
Cube in as few moves as possible, using only some cubes, pen and paper. The use of computer
programs is not allowed, and there are usually time constraints (one hour in WCA competitions,
up to one week in some online ones).
In view of this, no general solving algorithm is described. The reason why it is not convenient
is repeatedly remarked during the rest of the book and can be summed up as follows: restricting
to a single approach is too limiting.
Likewise, there is no mention on how to program a computer to generate (short) solutions.
If one is interested in the subject I suggest taking a look a the Computer Puzzling page at
www.jaapsch.net.
-->

### 前提条件
**読者は（たとえ簡易LBLであったとしても）ルービックキューブの解き方を知っているものとします。**さらに、通常のOBTM（外層ブロック手数）法の記法（イントロダクション内のリンク、付録Bを参照）と、基本的な用語（たとえば「2x2x2ブロック」）について知っていることが求められます。ただし、多くの専門用語は本文中で解説されます。

<!--
Prerequisites
The reader is assumed to know how to solve a Rubik’s Cube, even with a beginner’s (LBL)
method. Additionally, familiarity with the standard OBTM notation (link in the introduction,
see also Appedix B) and with some basic terminology (for example, what is 2x2x2 block in a
Rubik’s Cube) is required, although many technical terms will be explained in the text.

-->

### ソルブ実例について
第二版からはいくつかのソルブ例を収録しています。これにより本書がもっと自己完結的なものになることを期待しています。これは次のような枠を作って表現します。

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
img_src="../../../assets/img/2C2E_alg.png"
algcubing = "https://alg.cubing.net/?setup=B-_L-_D2_R_U_F-_U-_L_U2_D_R2_U2_F_B_R2_B_U2_B_L2_B2_U2&alg=B-_F_D2_%2F%2FPseudo_2x2x1_(3%2F3)%0AL-_B_(B2_L_B_L-_B_D2_F-_R_F_D2)_R2_%2F%2FPseudo_3x2x2_(3%2F6)%0AF2_D_F-_D2_F_%2F%2FFound_using_NISS_(5%2F11)%0AR-_D-_R_D2_F_U2_%2F%2FFound_using_NISS_(6%2F17)"
%}

<!--
About Example Solves
In the second version of this book I have added some example solves, in order to make the text
more self-contained. They appear in nice boxes like the following:
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

このソリューションの記述のなかでは、決して`x`や`y2`などの**「持ち替え記号」**を使わずに書いていることがわかるでしょうか。解答を考えるときにキューブを持ち替えてはいけないということではありません。もし持ち替え記号を使わない記述がよくわからないなら、5.1節までスキップすることがオススメです。

<!--
You may notice that in writing the solution I almost never use “rotation” moves such as x or
y2. This doesn’t mean that you shouldn’t turn the cube around in your hands when trying the
solution. If you are not familiar with rotationless solution writing, I advise skipping to Section
5.1 before reading the rest of the book.
-->

### 謝辞
**世界中のスピードキューブコミュニティに対して、どんな時もテクニックやメソッドをオープンに広めていることに感謝を申し上げたいです。**これによって、誰もが（これまでに）見つかったすべてのことを自由に学ぶことができるようになります。このチュートリアルも同じように役に立つことを望みます。

<!--
Acknowledgements
I want to thank the whole international speedcubing community for always openly spread techniques and methods, enabling anyone to freely learn anything that has been discovered (until
now). I hope this tutorial will be helpful in the same way.
-->

**あわせて感謝を申し上げたいのは、改善点を指摘してくれた全ての方です。**間違いを指摘してくださったり、このチュートリアルを（古い版も含めて）翻訳してくださったりしました。いずれ忘れてしまうでしょうから、全ての方の名前を挙げるのは控えます。

この版では、[visualcube](http://cube.crider.co.uk/visualcube.php)[^0-visualcube]と[alg.cubing.net](https://alg.cubing.net)[^0-algcubingnet]を使いましたので、この２つのツールの作者であるConrad RiderとLucas Garronには、特に感謝を申し上げます。
<!--
I also want to thank everybody who gave me suggestions for improvements, pointed out
mistakes or translated this tutorial (or rather, the old version). I don’t want to name any of you
explicitly, because I know I will forget many.
For this second edition I made use of visualcube2 and alg.cubing.net3
, so a special thanks
goes also to the creators of this two tools, respectively Conrad Rider and Lucas Garron.
-->

### 免責事項
ご存じかもしれませんが、英語は私の母語ではありません。もし文章が下手だったり、間違いを見つけたりした場合、私にご連絡ください。 `sebastiano.tronto [at] gmail [dot] com`

**訳注：**  
英語は翻訳者の母語でもありません！　本文の内容ではなく、翻訳のミスを見つけた場合は、私にご連絡ください！
{: .notice--info}

<!--
Disclaimer
As you may know, English is not my first language. If you think that a certain part is poorly
written or if you find any mistake, please contact me at: sebastiano.tronto [at] gmail [dot] com.

Where to find this

This tutorial can be found at https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf. If a
new version is released, the link is updated automatically.
You can find the LaTeX source files, the pictures and more on my Github repository: https:
//github.com/sebastianotronto/fmctutorial.
License
This work is licensed under the Creative Commons Attribution 4.0 License (CC BY 4.0)4
. This
means that you are free not only to redistribute this document, but also to remix, transform,
and build upon it, as long as you give appropriate credit. For example, feel free to translate this
tutorial to another language!
-->

### 公開場所
このチュートリアルは[https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf](https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf)で公開しています。新しい版がリリースされたときは、このリンクは自動的に更新されます。LaTexのソースファイルと画像は私のGitHubリポジトリにあります。：[https:
//github.com/sebastianotronto/fmctutorial](https:
//github.com/sebastianotronto/fmctutorial)

### ライセンス
本ドキュメントは[Creative Commons Attribution 4.0 License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)で提供されます。つまり、このドキュメントを再配布することができるだけでなく、自由に別の言語に翻訳してもよいということです！

**訳注：**  
本翻訳も同様にCC BY 4.0で提供されます。
{: .notice--info}

## 目次

**訳注：**  
自動生成しましたので、本項目は省略します。
{: .notice--info}

<!--
Contents
1 Think Outside the Box 9
1.1 Petrus . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
1.2 Roux . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
1.3 ZZ . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
1.4 CFOP (Fridrich) and FreeFOP . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
1.5 Keyhole F2L . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
1.6 Heise . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
1.7 What and How to Learn . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
1.7.1 Petrus . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
1.7.2 Roux . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
1.7.3 ZZ . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
1.7.4 CFOP/FreeFOP . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2 How to Proceed During a Solve 15
2.1 Blockbuilding . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.1.1 Align then Join . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.1.2 Move it out of the way . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
2.1.3 Destroy and Restore . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
2.1.4 Keyhole . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.1.5 One Move, Two Goals . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.1.6 Influence Later Steps . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
2.1.7 Pay Attention to EO . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
2.1.8 Which Block Should I Build? . . . . . . . . . . . . . . . . . . . . . . . . . 18
2.1.9 Ready-Made Blocks: How to Deal with Them? . . . . . . . . . . . . . . . 19
2.1.10 Tricks to Get Fast and Advanced Techniques . . . . . . . . . . . . . . . . 19
2.2 Find a Good Skeleton . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.3 Commutators . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.3.1 Corner Commutators . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.3.2 Edge Commutators . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
2.3.3 Other Edge 3-cycles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
2.3.4 Block Commutators . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.4 Insertions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.4.1 Simple Insertions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.4.2 Multiple Insertions: Separated Cycles (3 Edges and 3 Corners) . . . . . . 25
2.4.3 Multiple Insertions: 2 or 3 Twisted Corners . . . . . . . . . . . . . . . . . 26
2.4.4 Multiple Insertions: 4 Corners . . . . . . . . . . . . . . . . . . . . . . . . 26
2.4.5 Multiple Insertions: 5 Corners . . . . . . . . . . . . . . . . . . . . . . . . 27
2.4.6 Multiple Insertions: 5 Edges . . . . . . . . . . . . . . . . . . . . . . . . . . 29
2.4.7 Other Insertions: 2 Corners and 2 Edges . . . . . . . . . . . . . . . . . . . 29
2.4.8 Other Insertions: 3 Edges and Some Corners . . . . . . . . . . . . . . . . 30
2.4.9 Other Insertions: Conjugate and Solve . . . . . . . . . . . . . . . . . . . . 30
2.4.10 Move Count (an Estimate) . . . . . . . . . . . . . . . . . . . . . . . . . . 31
2.4.11 Insertion Finder . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
2.5 Other Simple Stragies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
2.5.1 Go Back and Change Your Sove . . . . . . . . . . . . . . . . . . . . . . . 31
2.5.2 Get Lucky! . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
2.5.3 First Example: Insert Last Pair(s) . . . . . . . . . . . . . . . . . . . . . . 32
2.5.4 Second Example: How to Use Algorithms . . . . . . . . . . . . . . . . . . 33
3 Advanced Tools 35
3.1 Inverse Scramble . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
3.2 Pseudo Blocks, Premoves and NISS . . . . . . . . . . . . . . . . . . . . . . . . . . 36
3.2.1 Pseudo Blocks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
3.2.2 Premoves . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
3.2.3 NISS . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
3.3 Reverse NISS . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
3.4 Useful Algorithms . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
3.5 Pair Analysis . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
3.6 Solving with Skew Centers . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
4 Some Other Methods 45
4.1 Starting With EO . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
4.1.1 EO + Blockbuilding . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
4.1.2 Domino Reduction (and HTA) . . . . . . . . . . . . . . . . . . . . . . . . 46
4.2 Corners First . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
5 How To Practice 49
5.1 No Time Limit and Competition Simulation . . . . . . . . . . . . . . . . . . . . . 49
5.2 Compare Yourself to the Masters (and Study their Solves) . . . . . . . . . . . . . 49
5.3 Hard Scrambles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
5.4 Deliberate Practice . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 50
5.5 Fast Scrambling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 50
5.6 Study! . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 50
6 In Competition 51
6.1 How to Write a Solution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
6.2 Backup Solution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
6.3 Time Managment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 52
6.3.1 Don’t Get Stuck . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 52
6.3.2 (Don’t) Explore Every Possibility . . . . . . . . . . . . . . . . . . . . . . . 52
A Other Resources 53
B Notation 55
C Last Layer Algorithms 57
-->

## イントロダクション

ルービックキューブをできる限り速く解くということは面白いものですが、**さらに面白いのは一番少ない手数で解くということです。これが最少手数競技のゴールです。** 最少手数競技は**FMC**あるいは**Fewest Moves Challenge**と呼ばれます。
<!--
Introduction
Trying to solve a Rubik’s Cube (or, in general, any puzzle) as fast as possible is interesting, but
it is even more interesting trying to solve it using the fewest moves: this is the goal in “Fewest
Moves” solving (or FMC, “Fewest Moves Challenge”).
-->
### 公式大会
FMCはWCA(World Cube Association、世界キューブ協会)の公式種目として知られています。WCAはルービックキューブやそれに類するパズルの大会を統括する組織です。[WCA大会規則(第E条)](https://www.worldcubeassociation.org/regulations/translations/japanese/#article-E-fewest-moves)に書いてあることをまとめると次のようになります。

- スクランブルの書かれた紙が全競技者に与えられる
- 時間制限は60分
- 以下の道具を使用できる
    - 紙（ジャッジによって支給される）とペン（ジャッジによって支給される、任意で競技者が持参）
    - 最大3個のルービックキューブ（競技者が持参）
    - ステッカー（競技者が持参）
- 解法について
    - 解法は外層ブロック手数(OBTM記法)を用いて記述したものを提出する。
    - 持ち替え記号(x、y2など)、面操作(R、U2、L'など)、外層ブロック操作(Rw2、FW'など)が許可される。中層回転(M、E、S)は許可されない。
    - 持ち替え記号は0手とみなす。それ以外の操作は1手と数える。
    - 競技者の解法はスクランブル手順の任意の部分に直接由来してはならない。解法中の各手順の意図を説明できるようにしておかねばならない。

最後のルールを適用するために、2016年からFMC用のスクランブルには最初と最後に`R' U F`が加えられることになりました。

現在の大会における最高記録は、**Sebastiano Tronto(イタリア)による単発16手 (FMC 2019)**です。３回の試技の平均では、**Cale Schoon (アメリカ)による21.00手 (North Star Cubing Challenge 2020)**が世界記録です。2019年の世界大会での世界チャンピオンは、ともに平均25.33手を出したFirstian Fushada (符逢城)とChristopher Chiです。

**訳注：**  
翻訳時点(2020/04)では**Shuto Ueno (上野柊斗)が単発19手、平均24.00手の日本記録を保持しています。**この単発記録は、Baiqiang Dong (董百强)と並んでアジア記録(AsR)でもあります。
{: .notice--success}

<!--Article E: Fewest Moves Solving
Official Competitions
FMC is an official event recognized by the WCA (World Cube Association), the organization
that governs competitions for the Rubik’s cube and similar puzzles. Official regulations (Article
E
4
) can be summed up as follows:
• The scramble (sequence of moves to scramble the cube) is given to all competitors, written
on a sheet of paper.
• Time limit: 60 minutes.
• Allowed material:
– Paper and pens (provided by the judge);
– Up to 3 Rubik’s cubes (self-supplied);
– Unlimited colored stickers (self-supplied).
• The solution:
– Has to be submitted written in the OBTM5 notation: allowed moves are rotations
(x, y2, [u]. . . ), single-layer moves (R, U2, L'. . . ) and wide moves (Rw2, Fw'. . . ) but
not inner-layer moves (M, E, S. . . );
– for the final results, rotations are not counted, while each other move counts as 1;
– Has to be at most 80 moves long (including rotations);
– Must not be related to the scramble in any way; in addition, the competitor must be
able to explain each move in his solution.
In order to enforce the last rule, since 2016 scrambles are generated so that they begin and
end with the sequence R' U F.
The best result ever achieved in competition is 19 moves, by Tim Wong (USA), Marcel
Peters (Germany) and Vladislav Ushakov (Belarus). The world record for an average of three
attempts (in one competition) is 24.33 by Marcel Peters and Baiqiang Dong (China). Marcel
Peters also holds the World Champion title (2017).
-->

### このチュートリアルのゴール
このチュートリアルのゴールは、**FMCでよい結果を出すためによく知られたテクニックをまとめることです。** いくつかの説明は詳しく記述して実例もつけていますが、単に総合的な説明を書いて学習のためのリソースを提案しているだけのものもあります。

<!--訳者TODO：ここにFMCの解答用紙の画像をつける-->
![スクランブルシート](../../../assets/img/fmc_scramble_sheet.png){: class="img-responsive align-center"}
公式スクランブルシートの例
{: .text-center}

<!--
Goal of This Tutorial
The goal of this tutorial is to summarize the best known techniques that lead to good results in
fewest moves solving. In some cases the explanation will detailed and enriched with examples,
while in some other I will only provide a synthetic explanation and suggest other resources for
further study.
4
https://www.worldcubeassociation.org/regulations/#article-E-fewest-moves
5
https://www.worldcubeassociation.org/regulations/#12a
7
8 CONTENTS
Scramble: R' U' F R2 B2 D2 R2 D2 B R2 B F U B' R B R U2 L D F R' B R' U' F
Scrambles for 2017-07-27
3x3x3: Fewest Moves Round 1
Competitor: __________________
WCA ID: _ _ _ _ _ _ _ _ _ _
DO NOT FILL IF YOU ARE THE COMPETITOR
Graded by: _______________ Result: ______
Fewest Moves
- Notate your solution by writing one move per bar.
- To delete moves, clearly erase/blacken them.
- Face moves F, B, R, L, U, and D are clockwise.
- Rotations x, y, and z follow R, U, and F.
- ' inverts a move; 2 doubles a move. (e.g.: U', U2)
- w makes a face move into two layers. (e.g.: Uw)
- A [lowercase] move is a cube rotation. (e.g.: [u])
- You have 1 hour to find a solution.
- Your solution length will be counted in OBTM.
Your solution must be at most 80 moves, including
rotations.
-
Your solution must not be directly derived from any
part of the scrambling algorithm.
-
Figure 1: Example of official scramble sheet.

-->

## 第１章：既成概念にとらわれずに考える (Think Outside the Box)
あなたのメイン解法が何であれ、その一つの解法に縛られるのはFMCにおいて最悪のやり方です。**一つの解法／メソッドに限定してはいけません。** あらゆる状況を活用するようにしましょう。

たとえば、あなたが2x3x3ブロックを作ったとしましょう。ここからいくつもの可能性があります。最後の「クロス」エッジを揃えてからCFOPにおけるF2Lをやっても構いません。Petrusのようにエッジの向きを揃えもよいですし、FreeFOPやHeiseを使ってもっと自由にブロックを作ってもよいでしょう。どの解法を使ってもよい結果になるでしょう。なので、もっともよいやり方は、**これを全部使って解いてしまうということです。**（全部でなくても、その多くを使うのでもよいです）

発想を柔軟にして「既成概念にとらわれず」に考えるには、少し逆説的ですが、**まず多くの既成概念を知ることが最良の方法です。**つまり、多くの解法を学びましょう。

まずはFMCにおける最も有益（だと私が考える）な解法について簡単に書きましょう。  
解法の開発された歴史やスピードソルブにおける利点／欠点については話しません。それぞれの解法について、オンラインで参照できるチュートリアルのリンクをつけますが、Googleやspeedsolving.comなどでさらなる情報を調べることをお勧めします。speedsolving.comのフォーラムにある[「初心者向けスピード解法の選び方ガイド(Beginner’s Guide to Choosing a Speedsolving Method)」](https://www.speedsolving.com/threads/beginners-guide-to-choosing-a-speedsolving-method.43471/)はよく使われている４つの解法について知るよいきっかけになるでしょう。(スピード解法について考えるなら、という注意書きが付きます)

次の４つの解法についてそれぞれ書きます。
- CFOP
- Roux
- ZZ
- Petrus

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

**ブロックビルディング[^1-1-Petrus]のスキルを高めることは、FMCの上達のために必須のものです。** Petrusを学ぶことでこのスキルが高まるでしょう。ステップ1とステップ2の解き方を効率よく学ぶためには、常にブロックビルディングするための違ったやり方を探さなければなりません。つまり、**熟練のキューバーのソルブのリコンストラクションから学ぶことが非常に役に立ちます。** 熟練者は（ほとんどいつも）最適な2x2x2ブロックを見つけることができるので、あなたの解答と最適な解法[^1-1-Petrus-2]を比較してみること役に立つでしょう。

ステップ3では、エッジがキューブのどこに位置しているかに関わらず、エッジの方向を認識することを学ぶことができます。反転したエッジはFMCをやる上で最悪のものですから、これもまた重要なスキルです。このステップでは、ZZのほうがPetrusよりもわかりやすいかもしれません。

Last Layerのアルゴリズムを全て学ぶ必要はありません。他のメソッドについても同じです。次の章ではどのように前に進めばいいのかを説明しますが、この時点では「Last Layer」を処理するステップは最少手数競技のソルブにおいてはあまり利用されないということを覚えておいてください。

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

Petrusはブロックビルディングを学ぶには素晴らしい解法ですが、Petrusだけを使うというのは間違いです。あわせてRouxのブロックビルディング（特に最初の2つのステップ）を学ぶことで、スキルが完成に近づくでしょう。また、この解法では熟練のキューバーの解法から学ぶことが多くあります。

ステップ3ではLast Layerについて書いたことはここでも変わりません。ステップ4ではこの弊害を除くことができますが、Mのような中層回転は全て2手としてカウントされることは忘れないでください！（少なくとも、Rouxの標準的なLSEのやりかたは避けましょう。つまり、MとUだけで解くやりかたです）

- Waffle’s Roux Tutorial: [http://wafflelikescubes.webs.com/](http://wafflelikescubes.webs.com/)
- Kian Mansour’s Roux Tutorial: [https://sites.google.com/view/kianroux/home](https://sites.google.com/view/kianroux/home)

**訳注：**  
実際の最少手数競技においては、解答用紙に**M、S、Eの中層回転（スライスムーブ)**の記号を書くことは認められていません。[規則12a](https://www.worldcubeassociation.org/regulations/translations/japanese/#12a)に定義されている3x3x3の回転記号のみを使うようにしましょう。ここでは**「RouxメソッドのやりかたでM列を使う（解答用紙にはR L'のように書く）と2手としてカウントされ、手数が多くなりがちになるので避けたほうがよいですよ」**ということを言っています。
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

前述のように、エッジオリエンテーション(EO)を認識して解くことは非常に有益なスキルであり、ZZは間違いなくこれを学ぶ最良の方法でしょう。「エッジの向きを揃える」というのは、「ブロックビルディング」よりも抽象的な概念ですから、最初は難しく感じるでしょう。しかし、パニックにならないでください。練習すれば簡単になっていきます！

ステップ２はPetrusのステップ4と同じものですが、R面とL面に同時にブロックを作らなければなりません[^1-3-ZZ]。これをやることで、さらにブロックビルディングのスキルが高まるでしょう。

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

古典的なCFOPは**FMC向きのあまりよい解法ではないと考えられています。**しかし、コーナーとエッジのペアを挿入する別の方法をしっておくことは役に立つことがあります。

FreeFOPでは、最初の二つのステップは「自由な」ブロックビルディングF2Lに変わります。

何にせよ、スキップができない限り、Last LayerをOLLとPLLで解くことはまったくおすすめできない方法です。

Badmephisto’s Tutorial: [http://badmephisto.com/](http://badmephisto.com/)

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
Badmephisto’s Tutorial: http://badmephisto.com/.
4For speedsolving, it may be better to solve one block at the time, since it is usually more ergonomic. But this
is not the case for FMC, as efficiency (i.e. number of moves) is the only thing that matters!
-->

### 1.5 キーホールF2L
キーホールは厳密にはキューブの解法ではなく、最初の二段を解くためのテクニックです。LBL(Layer by Layer)からCFOPの中間にあたる解法として位置づけられています。ステップは次のようなものです。

1. クロス
1. 1段目に3つのコーナーを配置する
1. 3つの中層エッジをインサートする。「自由に」コーナースロットを使う
1. コーナーとエッジのペアをインサートする。CFOPやLBLと同様

最初の２ステップをブロックビルディングに置き換えることと、中層のエッジを同時に揃えることで、効率化するとよいでしょう。クロスと3つの中層エッジを揃えてから、3つのコーナーを「自由な」エッジを使って揃えるというバリエーションもあります。

非常にシンプルですが、この解法はFMCにおいてとても役に立ちます。

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

### 1.6. Heise
1. 2x2x1の「四角」を作る
1. 「四角」を揃えてエッジを合わせることで、F2L-1の状態を作る。
1. 残った5つのエッジと2つのコーナーを揃える
1. 最後の3つのコーナーをコミューテータで揃える

もしあなたが熟練者のアドバイスを無視して、一つの解法だけを使ってFMCをやりたいというなら、Heiseを選ぶのがよいでしょう。**この解法を一直線[^1-6-Heise]に使うだけでも平均して40手以下で解くことができるでしょう。**非常に極端な解法ですが、同時に極めて効率的です。

最初の二つのステップは奇妙ですが、**F2L-1 [^1-6-Heise-2] を作り、全てのエッジの向きを揃えるのに効率的なやり方です。**「何も制限するな」「様々な状況を活用せよ」というコンセプトに完全に沿っており、ブロックを考えうる最高の方法で作ることができます。

三つ目のステップは複雑ですが、F2Lを完成させてLast Layerのアルゴリズムをやるよりずっと効率的です。これを練習することで、すでにたくさんのブロックが作られて動きが制限されているときでも、ブロックを作って動かすことができる能力が得られるでしょう。（これはこのステップは非常に難しい理由でもあります）

最後のステップではコミューテータを使います。FMCにおいては、インサーションが使えるようになるということです。（コミューテータとインサーションについては、次の章で説明します）

Heise method’s page on Ryan Heise’s website: [http://www.ryanheise.com/cube/heise_method.html](http://www.ryanheise.com/cube/heise_method.html)

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
当たり前のことですが、ここに書いたすべての解法を覚えて速くなることはゴールではありません。スピード解法でキューブを解くことはいくらか助けになることもありますし、楽しいものです。しかし、**ここではスピードは気にしません。**ゴールは**できるだけ短い手順でキューブを解くことですから、効率的になるよう努めましょう。**  
**Color Neutral (CN)**[^1-7-1]であることも大切なことですし、**「不一致ブロック(Non Matching Blocks)」**（疑似ブロック (Pseudo-block)[^1-7-2]について取り組むのも役に立つでしょう。

しかし、スピード解法と最少手数競技用の解法の大きな違いは、**FMCではいくつもの異なる可能性を試すことができるということです。**たとえばPetrusにおいては、2x2x3ブロックを作ったあとに6つの悪いエッジ(Bad edge)が残ったとき、最初から別のブロックを作り始めるか、ブロックの作り方を少し変えて状況を改善させるかすることができます。[^1-7-3]

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

## 第２章 ソルブの進め方

[Per Kristen Fredlund](https://www.worldcubeassociation.org/persons/2004FRED02)[^2-0]の言葉を引用すれば、一般的な進め方は次の通りです。
> もっと次のように考えましょう。キューブを二段階で解くのだ、と。
>
> 一段階目では、可能な限り多くのピースを、可能な限り効率的に解きましょう。（つまり、よいスケルトン[^2-0-1]を作りましょう）  
> 二段階目では、未完成のピースを正しく直しましょう。多くの場合、スケルトンにインサートをするアルゴリズム[^2-0-2]を使います。[^2-0-3]
>

これは一般的なアプローチですが、常にこうする必要はありません。たとえば、F2LでブロックビルディングをしてLast Layerアルゴリズムをやるだけで、とても短い解答を見つけることも時にはあるでしょう。これとは違うやり方もあり、そのうち二つは第四章で解説します。

この記述があまりにも一般的すぎるように見えても、これ以外に書きようがないのです。（FMCで）常によい記録を出すような標準的な解法はありません。チャンスを逃さないためには、**いつでも可能な限り多くの戦略を試してみるしかありません。**

ここではFMCで用いられる基本的なテクニックをいくつか記載します。前の章で書かれた解法を練習しているなら、すでにいくつかは学んだことがあるでしょう。他の解法も学ばなければならないかもしれません。いくつかは詳細に解説しますが、単にさらなる学習のためのチュートリアルへのリンクを書くだけで留めるものもあります。

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
### 2.1 ブロックビルディング (Blockbuilding)
**ブロックビルディングはFMCにおける最重要のテクニックでしょう。**簡単なコンセプトですが、しっかり習得するにはたくさんの練習が必要です。前の章で書いたような、ブロックビルディングの考え方に基づく解法（Petrus、Roux、Heise、ZZ）を練習することで直接的にブロックビルディングのスキルを高めることができます。

ここではいくつか便利な基本となるテクニックを並べましょう。一つ目はRyan Heiseのウェブサイト ([https://www.ryanheise.com/cube](https://www.ryanheise.com/cube))から取ってきたものです。ウェブサイトには実例がたくさんありますから、是非見てみましょう！
<!--
2.1 Blockbuilding
Blockbuilding is probably the most important technique in FMC. It is a simple concept, but
it requires a lot of practice to be mastered. Practicing blockbuilding-based methods (Petrus,
Roux, Heise and ZZ), in the ways previously described, is the most direct way to improve at
blockbuilding.
Here I will list some fundamental techniques that will come in handy; the first ones are taken
from Ryan Heise’s website (www.ryanheise.com/cube), which is full of examples: look them up!
-->
#### 2.1.1 並べて、つなげる(Align then Join)
ソース：[http://www.ryanheise.com/cube/align_join.html](http://www.ryanheise.com/cube/align_join.html)

基本テクニック：コーナーとエッジのペア（最も簡単なブロック）を作るためには、まず整列(align)して、一手でつなげられるようにしなければなりません。

この考え方は、さらに一般的には、より大きなブロックを作るときにも適用できます。たとえば、コーナーとエッジのペアと、2x2x1の四角を合わせて3x2x1ブロックを作りたいときです。

こういう言い方をすると平凡なことを言っているように見えますが、重要なことは**二つのピースがいつ整列しているかを認識して、一手でつなげることです。** こうすることで、あるムーブによって2つのピースをつなげることができるかどうかを将来的に判断できるようになります。

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
{: .notice}
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

ブロックを作りたいけれど、そのために必要なムーブが別のブロックを壊してしまうということがあるでしょう。そうしないために、動かしたくないピースをあらかじめ別の場所に動かしておきましょう。一つの方法として、まず壊したくないピースを先に動かして、壊れないように保存しておいてから、（必要なら）あとで戻すことができます。

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

もし2x2x1ブロックを作ったあとすぐに`F' D'`と回したとしても、同じ2x2x2ブロックを作ることができます。しかし、赤-白-青のペア壊してしまうことになります。ただし、このケースでは「別のところに持っていく」は最高のアイディアではないかもしれない、と補足しておきます。赤-白-青のペアを保存する過程で、黄-橙-青ペアを壊してしまっています！

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
単独の解法として既に書いたことですが、キーホールはブロックを作るための戦略のひとつとして考えることができます。このテクニックの本質は未完成であるキューブの一部を活用してほかのピースを揃えることです。キーホールF2Lの練習をうまくやっていれば、私が言わんとしていることを理解するのに実例を出す必要はないでしょうけれど、念のためにキーホールの例を書いておきます。
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
**一つのムーブで二つのブロックを作ることができる場合は多くあります。**一般的には「二つのことを同時にやる」ことができます。実例を見ることでよりはっきりとわかるでしょう。
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

もしあなたがインサーションについてまだ知らないなら、最後の行は無視してください。**今回注目すべきは最初の行、特に`F2`をしているところです。この一手でDFに2x2x1ブロックを作り、同時に橙-緑エッジを合わせています。**次の一手で2x2x2ブロックができるようになりました。

このような状況は偶然に生まれることがありますが、そうでない場合でも認識の仕方を学んでおくことは役に立ちます。

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
F2Lを完成させるときにLLに影響を与える点についてはすでに（少しだけ）話しました[^2-1-6-1]。このアイディアはブロックビルディングにも適用できます。つまり、**ブロックを準最適(sub-optimally)[^2-1-6-2]に作っておくか、あるいは「不要な」ムーブを加えることで後の繋がりをよくしたり、よいブロックビルディングができたりします。**

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
#### 2.1.7 EOに気をつけよう (Pay Attention to EO)
ここでいう**EO**とはエッジの向き(Edge Orientation)を略したものです。

複数の異なる解法を学ぶなかで既にお気づきの方もいるかもしれませんが、Edge Orientationというのは再帰的なステップなのです。前述のように、**Bad edgeが多ければ多いほど、解くのは困難になっていきます。**通常、最後にエッジの向きをそろえることは、効率的ではありません。ZZでそうするように、まず最初にエッジの向きを揃えることが手軽ですが、ブロックビルディングのフェイズで制約が増えることになります。

部分的にでも、**Edge Orientationをブロックビルディングの途中で終わらせるのが良い方法です。**ZZやPetrusなどの解法に習熟すると、数手動かしたあとでエッジの向きが正しいかどうかを簡単に判定できるようになります。もしまだ判定ができないのだとしても、FMCにおいてはいつでも望むときに戻って修正できるということを忘れないでおきましょう。つまり、EOがうまくいかないときには、前に戻って、何手か加えたり変えたりして、よい方向に進むかどうかを確認すればいいのです。（2.6.1節もご参照ください）

**訳注**  
ここでいうEOに注目したアプローチを「EOファーストアプローチ(EO first approach)」ということがあります。[João Pedro Batista Ribeiro Costa](https://www.worldcubeassociation.org/persons/2013COST02)(世界大会2015のFMCチャンピオン)や[Grzegorz Łuczyna](https://www.worldcubeassociation.org/persons/2005LUCZ01)(ヨーロッパ大会2010のFMCチャンピオン)、[Sébastien Auroux](https://www.worldcubeassociation.org/persons/2008AURO01)(世界大会2011のFMCチャンピオン)などの著名なキューバーは、ほとんど常にEOファーストアプローチを使うようです。原著者のSebastiano Trontoも非常によく使うということが第二版には記載がありました。EOファーストアプローチについては、2.5節に詳細が書かれています。
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
#### 2.1.9 既にブロックがある：どうすればいいか？(Ready-Made Blocks: How to Deal with Them?)
キューブをスクランブルしたときに既にいくつかブロックができていたり、最初の何手かで意図せず新しいブロック（コーナーとエッジのペアなど）ができてしまったりすることがあります。こういうときは、元々考えていたやりかたを続けるよりも、できてしまったブロックを活用するのが望ましいです。どうやって？3つの方法があります。

1. まず既にできているブロックを拡張する　（当たり前のことです）
1. 既にできているブロックを拡張するが、**他のピースも同時に見ながら同時に別のブロックができるようにする。**（これが最良の方法です）
1. 既にできているブロックを拡張せず、できればそれを壊さずに新しいブロックを探す。

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

最も簡単なブロックはコーナー／エッジのペア（2x1x1ブロック）です。スクランブル後に何も動かさなくても、一つできていることもあるでしょう。もし一つでも（二つ以上でも）あったなら、2.1.9節で書いたように、これをうまく使ってもよいでしょう。もし一つもなかったとしたら、見えるところにあるもので一手でペアになるものを認識できるようにしましょう（2.1.1節を参照）。もしまだすぐにわからなくて、楽をしようとするなら[^2-1-10-1]、「総当たり戦略」をやってみるのもよいでしょう。つまり、**すべての可能なムーブ試すのです。`U`、`U2`、`U'`と順番に試してから、次に`R`、`R2`、`R'`と続けていき、ペアができたかどうかを確認すればいいのです。**

もっと高度で役立つテクニックがあります。検討する時間はかかりますが、**全ての可能な2x2x2ブロック（8通り）をチェックするとよいでしょう。**やり方はこうです。**全てのコーナーについて、3つの一致するエッジを探して、**どうすればつなげて2x2x2ブロックが作れるかを考えます。実際に動かして「テスト」しないようにすることで、再度スクランブルせずに他のコーナーについても同じことを繰り返すことができます。通常、非常に悪い2x2x2ブロック（とてもたくさんの手数がかかる）を見つけたとき、私はそれを無視して次に進みます。このテクニックを使うことで、全てのピースがキューブのどこに位置しているかということがわかり、さらに最適な2x2x2ブロック（これはよいスタートになることが多い）を見つけられるようになるでしょう。

実際にキューブを回さずに2x2x2ブロックを作るムーブを考えることは他にもよい意味があります。より速く上手にブロックビルディングできるようになるためには、**実際の動きを見ずにピースの動きを「計算できる」ようになる**[^2-1-10-2]ことが大切です。  
[Alexander Lau](https://www.worldcubeassociation.org/persons/2011LAUA01) (2014 年のヨーロッパチャンピオンであり、Rouxメソッドの達人)は15秒間のインスペクションタイムで3x2x1ブロック（Rouxの最初のステップ）を読むことができます。この読みは非常に正確で、ブロックを作りながら先読み(look-ahead)をして、Second Block（の一部）を読むことができるようです。

この先を読む能力は次のようなゲームでトレーニングすることができます。  
友人にキューブを３手[^2-1-10-3]でスクランブルしてもらって、3手の解答を探しましょう。（これは簡単なはずです）次に、4手をやってみる、という風に続けます。あなたのレベルによりますが、6手、7手、8手と行くにつれて難しく感じていくでしょう。9手や10手のものを苦労なくできるようになりましたか？おめでとうございます！

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
### 2.2 よいスケルトンを見つけよう(Find a Good Skeleton)

F2L-1など、ブロックビルディングがうまくいきそうなところまで到達したなら、上に書いたようなテクニックを使って進めるのは難しくなるでしょう。次なるゴールは**「スケルトン」**と呼ばれるものを見つけることです。つまり、いくつかのピースが未完成な状態のままの、部分的な解法のことです。最も良いのは、3つのコーナーだけ残って3-cycle[^2-2]で交換できる状態ですが、4つや5つのコーナー、3つのエッジが残る場合も悪くありません。スケルトンを作るのに何手かかったかによります。

次にやることは何でしょう。これまで見てきたブロックビルディングのテクニックを、既に作ったブロックを壊さずに使うことができるでしょうか？まずHeiseを見てみるのがよいでしょう。これはHeiseメソッドのステップ３という意味でもありますし、彼のウェブサイトという意味でもあります。特にウェブサイトの「２つのペアによるアプローチ」に記述があります。[http://www.ryanheise.com/cube/two_pairs.html](http://www.ryanheise.com/cube/two_pairs.html)

Heiseのステップ３はF2L-1だけでなく、全てのエッジの向きが揃っていることを仮定しています。もし揃っていないなら、次のようなやり方があります。

1. まずエッジの向きを揃える。手数が非常に少なくない限り、非推奨。
1. 既にやった手順を修正して、全てのエッジの向きが最後に揃うようにする。
1. スケルトンを完成させるときにエッジの向きを揃える。

まとめると、よいスケルトンを作るための可能なアプローチはたくさんあます。この場合の最も良い方法（であり、よい習慣でもあるもの）は、オンラインでFMC熟練者のソルブ例を見ることです。ほとんどの場合、スケルトンを作って解いています。たとえばオンライン大会やspeedsolving.comのフォーラムで見ることができます。

さらに深く考える練習も役に立つでしょう。qqTimer ([http://www.qqtimer.net/](http://www.qqtimer.net/))では3x3x3のスクランブルのサブセットとして、last slotとlast layerを選ぶことができます。

当たり前のことですが、スケルトンを完成させる前にF2L-1を作らなくてもよいですが、これが最も簡単であることが多いです。どんなケースでも、偶然にLast layerのピースで小さなブロック(ペア、2x2x1など）ができたなら、残しておきましょう。

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
### 2.3. コミューテータ(COMMUTATORS)
speedsolving.comの定義[^2-3-1]によれば、コミューテータとは次のような形で記述する手順です。

`A B A' B'`
{: .text-center}

`A`と`B`はそれぞれ手順を示す配列で、`X'`は`X`という手順の逆手順(inverse)[^2-3-0]です。このようなコミューテータは次のような記法で短く書くことができます。

`[A, B]`
{: .text-center}

コミューテータの名称や記法は数学、特に群論から来たものです。たとえばWikipediaの記事をご覧ください。[https://en.wikipedia.org/wiki/Commutator](https://en.wikipedia.org/wiki/Commutator)

**訳注：**  
数学用語としてのコミューテータは、日本語では**交換子（こうかんし）**と書かれます。しかし、キューブ用語としてはコミューテータあるいはコミューテーターとして定着しているため、ここではカタカナで記載します。  
詳しくは[「交換子 - Wikipedia」](https://ja.wikipedia.org/wiki/%E4%BA%A4%E6%8F%9B%E5%AD%90)をご参照ください。
{: .notice--info}

たとえばA=`R`、B=`U`であると考えると、「セクシームーブ(sexy move)」がコミューテータであることに気づくでしょう。

`[R, U]` = `R U R' U'`
{: .text-center}

A=`R`、B=`U' L' U`と考えると、「Niklas」手順になります。

`[R, U' L' U]` = `R U' L' U R' U' L U`
{: .text-center}

慣習として、「コミューテータ」は「3点の巡回交換(3-cycle)を解くコミューテータ」として使われることが多いです。なので、たとえば「セクシームーブ」は通常コミューテータとみなされませんが、「Niklas」はコミューテータとみなされます。この先も、この慣習に従って使っていきます。

「コミューテータとは何か」という点については、WRCCやTRCCのFMC解説記事のなかにわかりやすく記述されています。簡単に言うと、FMCにおいては**任意の3点だけを8手で自由に入れ替えることができる手順**のことです。これが8手では実現できない場合もあります。詳細は下記の記事を参照してください。  
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
#### 2.3.1 コーナーコミューテータ(Corner Commutators)
コーナーコミューテータはFMCにおいて最も役に立つコミューテータです。既に「Niklas」というコミューテータを見ました。PLLのA permである`R2 B2 R F R' B2 R F' R`という手順も、（ほぼ）コミューテータです。

`R2 B2 R F R' B2 R F' R` = `R2 [B2, R F R'] R2`
{: .text-center}

ここでは`R' R2`という配列がキャンセル[^2-3-1]して`R`になっています。

組み合わせが変わる3つのコーナーは同じ面にある必要はありません。`[L D' L', U2]` = `L D' L' U2 L D L' U2` という手順も3-cycleです！

全ての種類のコーナーコミューテータ（このチュートリアルでは解説しません）を学ぶなら、Speedsolving.comの[Brian Yuのチュートリアル](https://www.speedsolving.com/threads/bh-tutorial.12268/)を見てみるとよいでしょう。文書と動画での解説があり、どちらも非常によくできていましたが、残念ながら動画にはアクセスできなくなってしまいました。

FMCをやる上では、**8手の「ピュアコミューテータ」**だけを覚えればいいでしょう。たとえば、Niklasはピュアコミューテータですが、A permは違います。必要ならA9やほかのケースを見てください。しかし、インサーションのところでも話しますが、FMCにおいてはほとんど必要がありません[^2-3-1-2]。

ごく稀に、10手の「スレッジ・インサーション」のコーナーコミューテータ(`[R' F R F', D2]`)が役に立つことがあります。これは8手のコミューテータを使うよりも多くのキャンセルができる場合があるからです。

**訳注：**  
上記のBrian Yuのチュートリアルにおいては、コミューテータの種類として次のものを上げています。8手のものがピュアコミューテータです。ここでは、A9(9手コミューテータ)以上のコミューテータを覚えても、FMCではあまり使わない、ということを言っています  
Pure (8 moves)  
A9 (9 moves)  
Orthogonal (10 moves)  
Cyclic Shift (10 moves)  
Columns (11 moves)  
Per Special (12 moves)
{: .notice--info}

**訳注：**  
「ピュアコミューテータ以外はFMCにおいてはほとんど必要ない」ことの例外として、Tomoaki Okayama (岡山友昭)による[実例](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-21#post-440873)が脚注に上げられています。ここでは`F2 (R F' L2 F R' F' L2 F) F2`という、`F2`セットアップして1手キャンセルする9手のインサーションをしていますが、8手のピュアコミューテータによるインサーションがまったく見つからないという状況が議論されています。
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
#### 2.3.2 エッジコミューテータ(Edge Commutators)
コーナーコミューテータを学んだら、エッジコミューテータの仕組みを理解するのも難しくないでしょう。たとえば次の例を見てみましょう。

`[U R U', M']` = `U R U' M' U R' U' M`
{: .text-center}

残念ながら、上記のようなコミューテータがよい結果につながるのはごく稀です。その理由は**M列を使うので、2手として数えられてしまうからです。**

全ての人が知っておくべきエッジコミューテータは

![](../../../assets/img/alg-232.png){:width="200px" height="auto" class="align-center"}
`[M', U2]` = `M' U2 M U2` (DF->UB->UF)
{: .text-center}

です。これはセットアップすることでとても役立ちます。たとえば、次のような形です。

`[U: [M', U2]]`[^2-3-2] = `U M' U2 M U2 U'` = `U M' U2 M U`
{: .text-center}

公式大会においては中層回転（スライスムーブ）を書くことはできませんから、`[M', U2]`のコミューテータは次のように書きます。

`M' U2 M U2` = `R' L x U2 R L' x' U2` = `R' L F2 R L' U2`
{: .text-center}

最初の`R' L`というムーブは交換可能であることがわかると思います。このことは全ての並行な（つまり対面にある）ムーブについて言えます。

もう一つ知っておかなければならないのは、**最初の2手は交換したい3つのエッジにまったく影響を及ぼさないということです。**なので、`R' L F2 R L' U2`は`L F2 R L' U2 R'`、`F2 R L' U2 R' L`、`R' F2 R L' U2 L`と等しいのです。

**訳注：** `[M', U2]`はDF->UB->UFの3点を交換するコミューテータです。
{: .notice}

**このことは特にキャンセルを探しているときに役に立ちます。**コミューテータの最初のムーブと、後続のムーブの逆手順とを対応させることでキャンセルが起きます（あるいはその逆もあります）。一般的にはコミューテータでなくともこのような探索を使うことができます。

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
中層回転を使わないエッジの3-cycleもあります。実際にはコミューテータですらないものも含まれます！HTMで8手の例を2つ上げましょう。

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
Speedsolving.comの[元のスレッド](https://www.speedsolving.com/threads/2-gen-edge-cycles.56224/)でJanWが言っていることは、次のような`[U R U R, X]`型と`[R U R U, X]`の2種類の2-genコミューテータの計6種類を基本手順として、（目隠し解法における）エッジの3-cycleのシステムを作ろうというものです。学ぶべきアルゴリズムの数が非常に少なくなるので効率的なのではないか、という提案です。その後、どの程度使われるようになったかは正確にはわかりません。しかし、3x3x3目隠し競技のトップ層は**呼吸をするようにエッジとコーナー合わせて818種類のコミューテータを使いこなす**(さらに平気でバッファ移行をする)ような記憶オバケですから、あまり流行らなかったのでしょう。もしかすると、3x3x3片手目隠し競技をやりたい方にとっては2-genであることが役立つかもしれません。  
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
#### 2.3.4 ブロックコミューテータ(Block Commutators)
Ryan Heiseのウェブサイトを注意深く読んだなら、**「ペア3-cycle」**あるいは**「ブロックコミューテータ」**というものについても既にわかっていることでしょう。コーナーコミューテータについて既に知っているなら、これを直感的に理解するのは難しくはありません。たとえば次の例を見てみましょう。

![](../../../assets/img/alg-234-1.png){:width="200px" height="auto" class="align-center"}
`[L Dw' L', U']` = `L Dw' L' U' L Dw L' U`
{: .text-center}

これはHeiseのステップ3でとても役立つ手順です。しかしこれは、コーナー3-cycleとエッジ3-cycleを同時に揃えることができます。たとえば、Last layerのアルゴリズムである`M F U F' U' F' L F R'`は次のように書くことができます。

![](../../../assets/img/alg-234-2.png){:width="200px" height="auto" class="align-center"}
`[R: [L' Dw L, U']]` = `R L' Dw L U' L' Dw' L U R'`
{: .text-center}

これはペアコミューテータにセットアップを加えたものです。PLLのJ permも次のようなペア3-cycleとして書くことができます。

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
### 2.4 インサーション(Insertions)
このチュートリアルを通じて何度も触れてきましたが、（ようやく）インサーションについて詳しく見てみましょう。

さて、どうにかしてよいスケルトンを見つけることができたとしましょう。コーナー3-cycleを1回やれば完成するという状態です。ここで何をすればいいでしょうか？　もちろんコミューテータを使ってそのまま3点交換をしてもよいでしょう。しかし、全てのケースを学んでいればわかることですが、コーナーコミューテータは最大で12手もかかります。最もいい場合では8手ですから、4手も増えるのはあまりよくありません。**ところが、コーナー3-cycleをほとんど確実に8手以内でやる方法があるのです！**それが**インサーション**です。

**訳注：**ここではInsertionをそのままインサーションと訳しています。日本語の解説記事では「インサート」と書かれることが多いです。単純に訳すなら「挿入」「差し込み」のことです。
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
インサーションの背後にある考え方はあまり難しいものではありません。**もしあと3つのコーナーを揃えたら完成するような状態であるとき、スケルトン全体を一手ずつ見ていって、対応する8手のコミューテータを回して完成させることができます。**コミューテータは対象となるピース以外には影響しませんから、3つのコーナー以外の部分（つまりスケルトン）は元々そうであったように全て完成します。そして、3つのコーナーもインサートされたコミューテータによって揃うのです。

これが3-cycleのコーナーをほとんど常に8手で解く仕組みです。どうすればもっと改善するでしょうか？　3つのコーナーを揃えることができる全てのインサート可能なコミューテータのなかで選ぶべきは、**最も多くのキャンセルが起こるものです。**通常は、3つのコーナーを揃えるピュアコミューテータをチェックするだけで十分です。そのあとで一番いいものを選びましょう。ごく稀に、一番いいインサーションが9手（あるいはそれ以上）のコミューテータであることがありますが、そういう状況はあまり起こらないので、全ての種類のコミューテータをチェックするのはあまり意味がありません。

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

スクランブル後、3つのコーナーを最初からすぐに揃えることもできますが、9手かかります。(`R2 F R B2 R' F' R B2 R`)　なので、まずはスケルトンの最初の1手(`B'`)を回してもっとよいケースがないかを探しましょう。さらに次のムーブ(`U'`)[^2-4-1-4]を回すと、ターゲットの3つのコーナーを8手コミューテータで揃えられます！(`L2 F R F' L2 F R' F'`)　もしこれを採用したいなら、最終解答は次のようになります。

`B' U'` `L2 F R F' L2 F R' F'`{: .codestrong} `D L' F' D2 L2 D' L U2 R2 U' R' U L' U R' U' L U2 R' L'`
{: .text-center}

実際に試してみて、ちゃんと揃うことを確認してみましょう。

何にせよ、もっとうまくやることができます。次のムーブ(`D`)を回すと9手のコミューテータが必要であることがわかります[^2-4-1-5]。この調子で何手か進んでいくと、やがて`L' F' D2`までたどりつきます。ここで3つのコーナーを8手(`D' F2 D B2 D' F2 D B2`)[^2-4-1-6]で揃えてみましょう。しかし、これで終わりではありません。最後の1手とコミューテータの最初でキャンセルがあります！これを採用するなら、次のように書きましょう。

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

そのほか、バリエーションがあります（シフトしてみてください）[^2-4-1-7] エッジを揃えるほかの（もっと発展的な）方法はフリースライス(free slices)を使うことです。(3.8節を参照のこと)

最後のヒントです。180度のムーブ(`U2`など)は8手コミューテータの最初や最後にあるのは、それがインターチェンジ(interchange)である場合です。つまり、同じ面にある2点交換をしているということです。この事実がわかっていると時間を節約できます。2手以上のキャンセルを狙っているとき（狙うべきです！）、2点交換がない限り、このようなムーブは完全にキャンセルすることはないと推測できます。前後でキャンセルをするようなコミューテータだけを探せばいいでしょう。

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

既に見たように、3-cycle（コーナーとエッジ）が2回あるような場合は、**ペアコミューテータ**（必要ならセットアップも含めて）で揃えることができます。別のやり方は、「セクシームーブ」や「Sune」(`R U R' U R U2 R'`)やその派生を使ってエッジを揃えることです。これによって必要なコーナーだけに影響を与えることができます[^2-4-2]。これについては2.4.8節を参照してください。どのやり方も頭にとどめておくとよいですが、簡単に使えることはあまりありません。「標準的な」手法は**2つのコミューテータをインサートすることです。**

コーナーとエッジに番号を振ったあとで[^2-4-2-2]、一手ずつ単純なインサーションを探して進んでいきますが、全ての箇所でコーナーとエッジの解法を見ていきましょう。さらにペアコミューテータとSuneもチェックします。終わったら、2つのインサーションによる最終解答を書くこともできますが、別のやり方を試してみることもできます。たとえば、コーナーコミューテータを残しておきたいけれど、もっといいエッジの交換を探したいとき、コーナーコミューテータだけをインサートした解答をまず作りましょう。ここでできたものが、**3つのエッジだけが残り、数手だけ長くなった新しいスケルトンです。** ここからは単純な(エッジ)インサーションで揃えられます。他の方法もあるなかで、こうすべき理由はなんでしょうか？ それは、**他のコミューテータの手順の中に、エッジコミューテータをインサートするよいポイントが見つかることもあるからです。** 逆に、エッジの交換をインサートしてからコーナーのインサーションをやることもできます。

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

2つ以上ある別々の交換が必要なケースについても、全く同じアプローチをすることができますが、もっと複雑になるでしょう。たとえば、6つのコーナーが残って、2つのコミューテータで揃えられるような場合です。

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

2つのねじれたコーナーが残ったとき、どこかで`[F L' D2 L F', U2]`(12手) というコミューテータを試してみるといいでしょう。3つある場合は、`U' B U' F U2 B2 D' R2 U D F' U' B`(13
手)も使えます。しかし、特に2つ目については最良ではないことが多いです。

2つあるいは3つのねじれはコーナーを揃える古典的手法は、**コーナーコミューテータを2回インサートすることです。** 1回目のコミューテータでは、3つのねじれたコーナー（あるいは2つのねじれたコーナーと、それ以外のコーナー）を交換するだけで十分です、通常、多くのキャンセルが見込めます。そこから先は、新しくできたスケルトンに単純なコーナーコミューテータをインサートすればよいだけです。

こうするためには、ねじれたコーナーに「X」などの記号を描いたりステッカーを貼ったりしておけばよいだけです。上に書いたような、「純粋に反転させる（pure flip）」アルゴリズムを使いたい場合は、矢印を描いておいて、どの方向（時計回り、反時計回り）に回転させるべきなのかわかるようにしておくといいでしょう。

1つめの交換が見つかったら、描いた記号を消して（単純なインサーションを探すのと同じように）1、2、3と番号を書きましょう。

2つのエッジがねじれているときにも同じことができますが、おすすめしません。エッジコミューテータはもっと手数がかかることが多いからです。

インサーションを2回行うお勧めのアプローチをするときには、次にことに気を付けてください。**それぞれのピースの一つのステッカーに印をつけたとしても、印のついていない別のステッカーとのコミューテータを探してしまうことがあります。** この問題を避けるために、私はねじれたピースのすべてのステッカーに印をつけています。

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

この1回目のインサーションについて、1つめのケース（場所はあっているがねじれている）ではもう一つ制約があり、**「場所は合っているけれどねじれている」コーナーを1回目のコミューテータに含めなければなりません。** 含めないと、2つあるいは3つのねじれたコーナーがある状態が残り、さらに2回インサートしなければならなくなります。

これを間違いなくやるために、私は次のようにコーナーに印をつけます。

1. **ねじれた3点交換 + ねじれたコーナー x 1** : ねじれたコーナーに「X」と印をつけます。ねじれている向きは気にしません。そして、他の3つのコーナーに1から3までの番号を振ります。このとき、ねじれた交換なので、**1は2になり、2は3になりますが、3は1ではなく同じコーナーの別のステッカー[^2-4-4-2]になります。**これは大したことではなく、その別のステッカーに4と番号を振れば大丈夫です。
1. **ダブルスワップ** : 最初のコーナーのペアにXと印をつけて、次のコーナーのペアにAと印をつける。
1. **ねじれたダブルスワップ** : ねじれた3点交換には4つの番号を振る必要があり、ねじれた2点交換には3つの番号を振る必要があるので、2点交換には1から3までの番号を、それ以外にはAからCを振る。

たとえば、1つ目のケースでは、可能な「最初のサイクル」は**Xを3に、3を4に、4をXに、**というものがあります。1->2->3->1というのはよいサイクルではなく、3点交換ではなく2つのねじれたコーナーが残ってしまいます。

素晴らしい例は次のソルブです。これは、**João Pedro Batista Ribeiro Costaの南アフリカ記録のものです。**解答の説明は私が少し修正しました。元々のものはプリムーブ(premove)を使っていました。プリムーブ(premove)については、次の章で説明します。

{% capture display_text %}
F D' + U2 * R //EO
D' F' L2 //疑似 2x2x2
F2 D F2 //疑似 F2L-2
B' D B //疑似 F2L-1
F' D' F' L2 //4コーナー以外完成
* = U R D' R' U' R D R' //1つ目のコミューテータ
+ = L' U' R' U L U' R U //2つ目のコミューテータ
{% endcapture %}
{% include solvebox.html
title = "João Pedro Batista Ribeiro Costaの元南アフリカ記録(SAR)"
scramble = "L' U2 D' L' U2 B' D B' L U2 F2 R2 F' R2 L2 F' U2 D2 F"
text = display_text
solution = "F D' L' U' R' U L U' R2 D' R' U' R F' L2 F2 D F2 B' D B F' D' F' L2 (25)"
img_src="../../../assets/img/alg-244.png"
algcubing = "https://alg.cubing.net/?alg=F_D-_(L-_U-_R-_U_L_U-_R_U)_U2_(U_R_D-_R-_U-_R_D_R-)_R_%2F%2FEO%0AD-_F-_L2_%2F%2F2x2x2%0AF2_D_F2_%2F%2FPseudo_F2L%26%2345%3B2%0AB-_D_B_%2F%2FF2L%26%2345%3B1%0AF-_D-_F-_%2F%2FAll_But_4_Corners&setup=_L_U2_D-_L-_U2_B-_D_B-_L_U2_F2_R2_F-_R2_L2_F-_U2_D2_F"
%}

最初ほうにインサートされたコミューテータ（2つ目のコミューテータ、＋）は後で見つけられたものです。2つ目のコミューテータのほうが早い段階でインサートされています。これでもまったく問題ありません！

さらに、2つのコミューテータの間でお互いに何手かキャンセルをしています。

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
5つのコーナーが残ったケースの中で、2回のコミューテータだけで揃えられるのはピースが5点交換になっている場合のみです。それ以外のケースでは、3回のコミューテータが必要です。ただし、5つのコーナーの配置は合っているがねじれているという場合には、4回必要となります。ここでは、3回以上のコミューテータが必要なケースについては触れず、最初のケースについてだけ見てみることにします。（3回のインサーションをやってみたいときもあるでしょうけれど）

さて、こういうときに最も簡単でよく使われる手法は、**4つのコーナーのとき同様に、2段階で解くことです。**コーナーに1から5までの番号を振ったあと、スケルトンを最初から1手ずつ追いかけていき、3つのつながったコーナーの交換を揃えられるコミューテータがないかを探していくわけです。このサイクルは、たとえば次のようなパタンがあります。

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
当然、単にコーナーの交換をひとつだけ探すよりも時間がかかります。ここでも変わらずピュアコミューテータを探すだけで十分です。いいコミューテータが見つかるたびに、どこかにメモしておきましょう。

この1段階目が終わった時点で、**見つかったコミューテータのなかから一番いいもの（一番多くキャンセルするもの）を選びましょう。**次にそのコミューテータをインサートして、コーナーの3点交換だけが残った新しいスケルトンを得ます。ここからどうすればいいかはわかるでしょう。

一番いいものは一つではないこともあります。たとえば、3手キャンセルするコミューテータを2つ見つけることもあるでしょう。では、どちらを選べばいいでしょうか？ 時間がないときには、適当に決めてしまいましょう。時間に余裕があるなら、両方のインサーションを試してみて、2つ目のコミューテータがよくなるものを選びましょう。
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

この手法を使うとき、**最適な解答が見けられたかどうか、確信も持つことはできないでしょう。**なので、安全を取って、1段階目で見つかった全てのコミューテータ（あるいはそのほとんど）をチェックして、2段階目をたくさん（ほとんど意味のないものも）試してみるといいでしょう。通常、これはとても時間の無駄になりますし、よい解答になることは滅多にありません。解答をもっとよくできるかどうかわからないときは、基準として**「5つのコーナーの交換を10手か11手で揃えられれば満足できる結果である」**ということを覚えておきましょう。

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

**順序が大切であることも忘れないようにしてください。**見てわかるように、`(1 2 3)`は、後に`(4 5 1)`が来るか、前に`(3 4 5)`が来るかしかありません。これはどういうことかというと、たとえば、`(1 2 3)`を揃えるいいコミューテータを見つけたなら、`(4 5 1)`を揃えるコミューテータをその後のどこかで使うか、`(3 4 5)`を揃えるコミューテータをその前のどこかで使うか、選ばなければならない、ということです。ここに挙げた交換の組について、同じようにやることができます。

この手法は他のものより速くできますが、**「ネストされたインサーション (nested insertions)」、つまり別のインサーションの中にインサートするときには使うことはできません。** そのため、時間がない時にだけ使うか、予備的な分析としてやるといいでしょう。つまり、こうやると何手くらいかかるのかを確認して、2段階目でいい結果になるコミューテータだけをチェックするというやり方です。
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

さらに発展的なエッジのインサーションについては、3.8節で触れます。

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

しかし、別のやり方もあります。**「セクシームーブ」（`R U R’ U’`）ではエッジの3-cycleと歪んだコーナーの2-cycleを2回繰り返すことになることがわかると思います。** この短いアルゴリズムやその派生をインサートすることで、エッジの3-cycleをとても効率的に解くことができるのです。もちろん、一回のインサーションでコーナーも完全に揃うのは、4つのコーナーとねじれたダブルスワップが残っているときのとてもラッキーなときだけです。コーナーにこういった影響を与えて、4つか5つかよいコーナーが残るようにする、というのが望み得る最良のことになる場合が多いです。
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
こういうとき役立つのは「セクシームーブ」だけではありません。ブロックコミューテータもよいツールです。speedsolving.comのこのポストの中で、Cale Schoonはこの類のインサーションについての実例を3つ挙げています。彼の解答はすべてNISSを使っていますが、スケルトンを作るまでのステップは無視して構いません。インサーションだけを見てください。

もう一つのアプローチはreverse NISS(第3.3節も参照)です。これは、セクシームーブをインサートすることで何をしているのかを理解する助けになるでしょう。


<!--
The “sexy move” isn’t the only algorithm that can help in this cases: also block commutators
are a very good tool. In this post33 on speedsolving.com Cale Schoon gives 3 different examples
of this kind of insertion. All of his solutions use NISS, but you can ignore the intermediate steps
that produce the skeleton and just look at the insertions.
Another approach to this reverse NISS (Section 3.3), which can help you understand what
you are actually doing when you insert a sexy move.
-->
#### 2.4.9 その他のインサーション: Conjugateをして揃える(Other Insertions: Conjugate and Solve)

**訳注:**  
**Conjugate**の適切な訳語が思いつかないので保留しています。別の箇所でも書きましたが、数学用語としては共役という意味があります。そのままコンジュゲートとカタカナで訳出してもよいかもしれません。インターチェンジもそのまま使われていますし。
{: .notice--info}

4つのエッジと4つのコーナーがあり、それぞれ4点交換されるとき（あるいはダブルスワップがあるとき）に、一つのインサーションだけで揃えることができる状況というものがあります。このケースは次のように揃えられます。

揃っていない8つのピースをすべて同じ面に集めます(セットアップ)。これで集めた面での単一のムーブで4点交換ができます。そして、8つのピースを元の場所に戻します(逆セットアップ)。8つのピースが2点交換を4つ組み合わせたものであるときにも、このテクニックは使えます。そのときは、「インターチェンジ」は180度のもの、たとえば `U2` などになります。もしピースの数が8つちょうどでなかったり、適切な交換ができない場合には、3.3節で説明するreverse NISSをまた使うことができます。
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

- **どのくらい多くのコミューテータやアルゴリズムを知っているか。**また、その認識能力。
- **スケルトンの長さ。**スケルトンが長ければアルゴリズムをインサートする箇所が多いので、より多くのキャンセルを狙えます。（しかし、この理由のために長いスケルトンを選んではいけません！）

見積もりを持つことは、インサーションを探すのに時間をかける価値があるのか、そうでないのかを判断するうえで役に立ちます。もし30手より短い解答を達成したいとして、3つのコーナーが残ったスケルトンを23手で作れたなら、おそらく達成できるでしょう。25手だったら、少し幸運が必要です。

異なるスケルトンで比較することもできます。18手かかる4コーナーのスケルトンなら、25手かかる3コーナーのスケルトンよりよいでしょう。

参考になる数字を出しておきます。[^2-4-10]

|          インサーションの種類           | 手数  |
| :-------------------------------------: | :---: |
|             コーナー3-cycle             |  5/6  |
|              エッジ3-cycle              |   7   |
| 2つのねじれたコーナー (2コミューテータ) |   8   |
| 3つのねじれたコーナー (2コミューテータ) |   9   |
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

### 2.5 EOから始めよ (Starting with EO)

**訳注**  
2020/04/20 EOファーストアプローチについて理解しつつ翻訳中です。不正確な内容が含まれている可能性があります。
{: .notice--danger}

ZZでのソルブのように、**全てのエッジの向きを揃える(Edge Orientation, EO)ことからスタートする**のはいつも頭に入れておくべき可能性でしょう。このチュートリアルの初版のころから、自分のソルブの中で何度も繰り返してこのやり方を使ってきました。試技の一番最初にはまずノーマルスクランブルと逆スクランブル全てのEOを探して、試す価値があるのかを見ていました。（多くの場合）試す価値はあります！ 2.1.7節で書いたように、多くの著名なFMCerがEOから始めています。

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
#### 2.5.2 ドミノリダクション (Domino Reduction)
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

### 2.6 その他の簡単な戦略(Other Simple Stragies)
#### 2.6.1 戻ってやり直そう(Go Back and Change Your Solve)
**よいスタートを切ったあとで詰まってしまったら、「そこまでのソルブを一手ずつ見ていく」ということをしてみましょう。** まだ揃えていないピースしかない面が、少なくとも1面、出てくるのを探しながらやってみましょう。見つかったら、その面を動かしてみましょう(すでに揃えたブロックは崩れません)。可能性は3種類(`U`、`U2`、`U´`など)あります。こうすると、元々のものよりほんの少し(1手)だけ長くなって、3通りのスタートが得られるでしょう。次へのつながりがよくなるなら、たった1手は安いものです！

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
#### 2.6.3 一つ目の例: 最後のペアをインサート(First Example: Insert Last Pair(s))

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
#### 2.6.4 二つ目の例: アルゴリズムの使い方(Second Example: How to Use Algorithms)
まず最初に対称なアルゴリズムを識別できるようにしておきましょう（もっと正確にいえば、対称なケース）。つまり`F R U R' U' F'`で揃うOLLはSプレーンについて対称なので、同じケースは`B' R' U' R B U`でも揃います。もし使いたいのであれば、対称なケースも使えるようにして、スキップ（あるいはよいケース）のチャンスを二倍にしましょう。このトリックがうまくいくのは、二つのアルゴリズムは同じOLLケースを揃えるためのものであって、ピースの交換に異なった影響を与えるものだからです。しかし、CLLについては少し違います。同じCLLケースを揃えるアルゴリズムがあって、コーナーが揃わないなら、ほかのアルゴリズムを使ってもコーナーは揃いません。

極端な例を見てみましょう。`R U2 R' U' R U R' U' R U' R'`で揃うOLLを考えます。これと左右対称の`L' U2 L U L' U' L U L' U L`を使うことで、同じケースを4つの向きから揃えることができます。（ほかの2つは逆手順です）このアルゴリズムは、「2-gen」のLast layerアルゴリズムに当てはまることですが、コーナーの相対的な位置関係には影響しません。

次に、学んだときの目的に従ってアルゴリズムを使う必要はありません。`F R U R' U' F'`について考えると、おそらくOLLのひとつとして知っていることでしょう。ところが、コーナーを無視してこれを使うこともできます。すると、F2L完了時点で2つの悪いエッジ（bad edge）が残っているときに、このアルゴリズムを4つの向きから使うことでスキップするか（あるいは簡単なケースになるか）どうかを試すことができます。
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
## 第３章　高度なツール (Advanced Tools)
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

公式／非公式の試技で、始まったときにまず逆スクランブルを書いておく人もいますし、NISSなどを使うときに初めて書く人もいます。こうしておくと、特に努力することなく、使いたいときいつでも逆スクランブルを使いやすくなります。ただし、最初に紙に書いて間違いがないかを確認しなければなりません。私はこうする代わりに、**通常のスクランブルを右から左に読みながら、頭の中でそれぞれの記号を逆にして逆スクランブルを使います。** 最初は難しいでしょうけれど、最終的には普通のスクランブルと同じくらい速く回せるようになりますし、ほとんど苦労しないでしょう。このやり方をするかどうかはあなたの好み次第です。 

そのままでも役立つテクニックですが、ソルブの最初で詰まったときや単にもっと多くの可能性を探索したいときに、ここで説明したアイディアは次の節で話すことの基礎になります。


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
#### 3.2.2 プリムーブ (Premoves)
前の節で示した状況はそこまで難しいものではありませんが、「疑似性 (pseudoness)」を考え
たまま、ソルブを進めるのは難しいでしょう。**F2Lのペアの認識はすぐにはできませんし、F2Lがズレた状態でのOLLやPLLを認識することを考えると、通常はとんでもないことになります。**たとえば、`R`だけズレたものを考えてみましょう！

疑似ブロックを作ったまま進めるとよいと言う人もいるでしょうが、全てを簡単にしてしまうワザがあります。**全て揃った最後にやるべきムーブ（ここでは`D2`）をスクランブルの前にやるだけでよいのです。**（なので、この手法は**「プリムーブ」**と呼ばれます）さあ、やってみましょう！

{% capture display_text %}
R2 F L2 D' //2x2x2
B' U2 R' U2 R2 U R //Cross and second pair
U2 F' U F U' F' U' F //Third pair
L U2 L' //Fourth pair
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
R2 B' R2 B //2x2x2, found premove B2 here
D L2 F D F2 //2x2x3
L' D F' D2 F D' //F2L-1, found premove D2 here
L' D * L' F L' F' D' L' //All but 3 corners
* = B L' F L B' L' F' L //Last 3 corners
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

ここ説明する概要は、Tomoaki Okayamaによる素晴らしい投稿によるものです。[^3-2-3-1] 最も重要なのことは次のようにまとめられます。

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
たとえば、抽象化して、`A B C D`をスクランブル、`p q r s`をそれに対する解答と考えてみましょう。`A B C D p q r s `という配列で、キューブは完成状態に戻ります。ここで、同じように、「ズラした」配列を考えてみると、どれもキューブの状態に影響しないことがわかります。

`s (A B C D p q r s) s’` = `s A B C D p q r`  
`r s (A B C D p q r s) s' r'` = `r s A B C D`  
`q r s (A B C D p q r s) s' r' q'` = `q r s A B C D`  
`p q r s (A B C D p q r s) s' r' q' p'` = `p q r s A B C D`  
`D p q r s (A B C D p q r s) s' r' q' p' D'` = `D p q r s A B C`  
. . .
{: .text-center}

もちろん、逆手順にしてもキューブの状態に影響しません

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
`D2`を使う最初のプリムーブの例では、このループは次のようになっていました。

(スクランブル) `R2 F L2 D'` (他のムーブ) `D2`
{: .text-center}

言い換えれば、ここでの**「`R2 F L2 D'` (他のムーブ) `D2`」をスクランブルに対する解答と見なすことができるわけです。**つまり、「`R2 F L2 D'` (他のムーブ)」を「`D2` (スクランブル)」に対する解答と見なすこともできます。[^3-2-3-2]

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
### 3.3 Reverse NISS
これは広く知られたテクニックではありませんが、役に立つ場合もあります。「2.4.9節Conjugateをして揃える(Conjugate and Solve)」や「2.6.1節 戻ってやり直そう (Go Back and Change your Solve)」の両方を改善したものと考えてもいいでしょう。

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

しかし、ここでノーマルスクランブルに戻って、EO手順の最初の2手(`F B`のこと)をやったところで立ち止まってみましょう。この時点でF/B軸に対する悪いエッジは4つ(UL, RF, DL, DR)しかありません。しかし、最良の場所ではありません。ここでEOを逆スクランブルにスイッチすることで簡単になるでしょうか？やってみましょう！

プリムーブ：`F' B'`  
逆スクランブル：R' U' F L F L B2 L2 U2 B2 L B2 R B2 L2 U F' D U' F2 R' B R' U' F  
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
### 3.7 歪んだセンターで揃える (Solving with Skew Centers)
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

上記のインサートを含む解答を見つけた後で、**すべてのムーブをセンターファーストで解いていないかのよのように書き直さなければなりません。**これは簡単な変換です。`R`は`U`に、`D`は`F`に、という風に変換していくだけです。

翻訳
{: .notice--warning}

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
### 3.8 高度なエッジインサーション：フリースライス (Advanced edge insertions: free slices)

未着手
{: .notice--danger}

### 3.9 コーナーファースト (Corner First)
未着手
{: .notice--danger}

### 3.10 交換して短くする (Replace and shorten)

未着手
{: .notice--danger}

## 第４章　その他の手法 (Some Other Methods)

未着手
{: .notice--danger}

## 第５章　練習方法 (How To Practice)
多くの人は、上達するためには「練習と、練習と、練習が必要です！」と言うでしょう。これは真ですが、練習のやり方を知る必要もあります。ここでは、FMCで上達するための練習方法についていくつかアドバイスをします。
<!--
Chapter 5
How To Practice
Many people say that to get better you need to “practice, practice, practice”. It is true, but
you also need to know how to practice: here is some advice on how to practice to get better at
FMC.
-->
### 5.1 時間無制限と大会シミュレーション(No Time Limit and Competition Simulation)
常に大会をシミュレーションして1時間以内に解答を完成させるようにすることは一番よい方法ではありません。これと反対に、時間制限を設けないで、結果に満足するまで同じスクランブルを何度もやることをおすすめします。

1時間の時間制限を設けた練習が悪いわけではありません。自分のレベルを判別することができるようになるでしょうし、タイムマネジメントの戦略を探すのにも役立つでしょう[^5-1-1]。私がおすすめするのは、FMCのオンライン大会に参加することです。たとえば、David Adamsのウェブサイト[^5-1-2]やGerman Forum competition[^5-1-3]などがあります。

大会と同じように1時間を使ってやってみてから、よい結果を得るまで続けることが、ちょうどよい妥協点でしょう。

**訳注：** 2020年1月時点で、上記のDavid Adamsのウェブサイトは動作していないようでした。  
Speedcube(rs).deのフォーラム上での大会は継続されています。
{: .notice--warning}

**訳注：** 日本国内においては[Tribox Contest](https://contest.tribox.com)が毎週FMCを含むオンラインの大会を開催しています。  
Redditのr/Cubersコミュニティでは[Cubers.io](http://www.cubers.io/)というウィークリーの大会を開催しています。
{: .notice--info}

<!--
5.1 No Time Limit and Competition Simulation
Always trying to simulate a competition and forcing yourself to complete your solution in one
hour is not the best thing to do: on the contrary, I suggest not limiting your time and trying
the same scramble again and again until your are satisfied with your result.
This doesn’t mean doing one hour solves is bad: it tells you what your level is and it helps
you finding a good time management strategy1
. To train like this I suggest taking part in
online competitions such as the one hosted on David Adams’ website2 and the German Forum
competition3
.
Trying for one hour as it was a competition and then keep trying until you reach a good
result is a balanced compromise.
-->
### 5.2 上級者と比べよう (Compare Yourself to the Masters (and Study their Solves))
練習したいときは、既にどこかでFMC上級者が解いたスクランブル使ってみるとよいでしょう。あなたの解答と上級者のものを比べて、あなたが気付かなかった点を見つけることができます。全ての秘密を手中に収めましょう！

加えて、ブロックビルディングや他の解法の訓練をするのであれば、上級者の解答を研究することは必須です。オンライン大会の過去のラウンドの結果から見ることもできますし、speedsolving.comのFMCスレッドでも見つかるでしょう。数年前、ブログ型のウェブサイト[http://fmcsolves.cubing.net/](http://fmcsolves.cubing.net/)を始めて、FMCの素晴らしいソルブ例を集めています。しかし、ここ数年更新していません。

<!--
5.2 Compare Yourself to the Masters (and Study their Solves)
When you want to practice, I suggest trying a scramble that has already been solved by some
expert FMCer, so that you can compare your solution to their and find out whether you have
missed a good start or anything else. Steal all the secrets you can!
Moreover, to train blockbuilding and other methods it is mandatory to study the masters’
solutions: you can find many of the them lookig at the old rounds of the online competitions
cited before or on the FMC Thread on speedsolving.com. A couple of years ago I started a
blog-style website http://fmcsolves.cubing.net/ to collect nice FMC solves, but I haven’t
updated it in ages.
-->
### 5.3 Hard Scrambles
「最悪ケースのシナリオ」において何ができるかを知るために、上級者でも難しかったというスクランブルをやってみるのもよいでしょう。[ここ](
https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-88#post-842681)[^5-3]で難しいスクランブルのリストを得られます。
<!--
5.3 Hard Scrambles
To see what you can do in the “worst case scenario”, I suggest trying out some scrambles that
are considered by experts to be really hard. You can find a list of hard scrambles here4
.
1
I will talk about time management in Section 6.3.
2
https://www.ocf.berkeley.edu/˜dadams/fmc/
3
https://speedcube.de/forum/showthread.php?tid=5795
4
https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-88#post-842681
49
50 CHAPTER 5. HOW TO PRACTICE
-->
### 5.4 熟考する練習(Deliberate Practice)
よいスタートがなかなか見つからないと感じているのであれば、こういう練習をしてみましょう。スクランブルをして、2x2x2や2x2x3などを気が済むまで探します。そのあと、スクランブルを変えて、同じように続けます。同じ考えをF2L-1や他のサブステップについてやることもできます。
<!--
5.4 Deliberate Practice
If you think you have troubles in finding a good start, practice that: take a scramble, find a
2x2x2, 2x2x3 or something else until you are satisfied, then change scramble. You can apply
this idea to F2L-1 or any other substep.
-->
### 5.5 ファストスクランブル(Fast Scrambling)
必要ではないとしても、NISSのようなテクニックを使うときや、単に私と同じように、ソルブ中に何度もキューブをスクランブルすることがあるなら、「ゆっくり過ぎない」スクランブルを試してみるといいでしょう。最も重要なことは正確性です。（スクランブルを間違えないこと！）20手のスクランブルを10秒でできるようになれば上出来です。
<!--
5.5 Fast Scrambling
Even if it is not necessary, when using techniques like NISS, or simply if like me you tend to
solve and scramble the cube many times during a solve, you should try to be at least “not too
slow” at scrambling, and most important to be accurate (don’t make mistakes). 10 seconds for
a 20 moves scramble is fine.
-->
### 5.6 よく学べ！(Study!)
大事なことを言い忘れていました。**このガイドをよく読んで学び、他のリソースからも学び、既知のものも未知のものも含めてアルゴリズムやテクニックを学びましょう。**私はspeedsolving.comの「FMCスレッド」を二回、最初から最後まで読みました。

**アルゴリズムを学びましょう。**膨大な量のアルゴリズムがあります。たとえば、LLEF(Last Layes Edges First)[^5-6-1]やSummer Variation[^5-6-2]などがあります。繰り返しますが、**単に暗記するのではなく、どのように機能しているのかを理解するようにしましょう。**
<!--
5.6 Study!
Last but not least. Study this guide, study from other sources, study algorithms and techniques,
new or known. I have read “The FMC Thread” on speedsolving.com twice, from top to bottom.
Study algorithms: there are dozens of different sets, to mention some of them LLEF5
(Last
Layers Edges First) or Summer Variation6
. Remember that you shouldn’t just memorize them,
but also try to understand how they work.
5
https://www.speedsolving.com/wiki/index.php/LLEF
6
https://www.speedsolving.com/wiki/index.php/Summer_Variation
-->

## 第６章　公式大会 (In Competition)
<!--
Chapter 6
In Competition
-->
### 6.1 解答の書き方(How to Write a Solution)
大会のときでも練習のときでも、**解答は持ち替え記号なしで書くのがよいでしょう。**これにはいくつもの理由があります。
- 持ち替え記号を使うと、間違いを起こしやすい
- 持ち替え記号があるとキャンセルが見つけにくい。`R z' U'` のようなことをやるのはとんでもない手数のムダです！
- ソルブ中にキューブを持ち替える場合、どの面がどこにあるかを常に意識しておかなければならない

ではどうやって持ち替え記号なしで解答を書くのか？　B面でPLLを回すのは厄介でしょう。簡単なやり方があるのです。BOYカラースキーム（標準配色）で標準的な持ち方を維持したまま、**「白センターのある面は常にUだ」「緑はF」「黄色はD」と覚えておけばいいだけです。**

<!--
6.1 How to Write a Solution
Both in competition and while practicing, you should write down your solution without rotations. There are many good reasons to do so:
• Using rotations, it is easier to make mistakes.
• Rotations can hide cancellations: things like . . . R z' U' . . . are a terrible way to waste
moves!
• While solving, if you rotate the cube, you always need to keep in mind which side is where.
How to write a solution without rotations? A PLL in B is very awkward. There is an easy
way: keeping the standard orientation, with a BOY color scheme (the “standard” one), you just
need to remember that the white-centered layer is always U, the green-centered one is F, the
yellow-centered one is D and so on. Every time you move a layer, for example the white-centered
one, you don’t need to care about how you are looking at the cube at that moment: just write
U.
To help memorizing the scheme (not that it is hard), remember that Blue and Red begin
with the same letter as their layer. This trick actually works well in many other languages.
-->
### 6.2 バックアップ解答(Backup Solution)
<!--
6.2 Backup Solution
It is good habit, in time-limited competitions, to write a “backup solution”. It is usually a not
so good solution, but still better than a DNF, found before the last moments, when haste may
lead to making a mistake or not finding a solution at all. If, for example, you average about 35
moves, but after 20 minutes you have found and written down somewhere a 40 moves solution,
you will be more relaxed for the remaining 40 minutes. You can even write it down on the
official sheet: if you later want to change your solution, you can delete the backup solution and
write down the new one. There are many possible approaches to finding a backup solution:
• Force yourself to have found and written a solution, no matter how bad, in a fixed time
limit (i.e.: 35 minutes). I don’t do this, but it can be useful if you often find yourself at
the end of the hour without anything written down.
• If you casually come across some solution (i.e.: you have found a good start and solving
the cube to re-scramble it you get a PLL skip), take note of it somewhere.
• What I do: I don’t really find backup solutions, but many backup skeletons. For example,
my goal is usually sub-30; in this case, a skeleton leaving 3 corners in 26 moves is not
good, but if I find one I keep it somewhere. If I have, for example, 10 minutes left and I
don’t have anything better, I look for an insertion in that skeleton. A single 3c insertion
usually takes me about 5 minutes, so you should adjust my “10 minutes” to your speed.
51
52 CHAPTER 6. IN COMPETITION
What can a good backup solution be? Any solution! Anything is better than a DNF,
especially now that the preferred format for FMC (in official competitions) is “Mean of 3”: a
single DNF gives you a DNF mean.
-->
### 6.3 タイムマネジメント(Time Managment)
<!--
6.3 Time Managment
“How to manage your time” is a complex topic, and I don’t want to say that my advice is
absolutely good in any case: follow it carefully! In fact, I consider myself pretty bad at timemanagment. The best teacher, in this case, is personal experience.
-->
#### 6.3.1 ひっからないように(Don’t Get Stuck)
<!--
6.3.1 Don’t Get Stuck
It can happen to anyone: during a competition you get stuck on a certain start and don’t
seem to find any better continuation. The ability to quickly understand if a start can lead to
a good continuation would be as useful as being able to read other people’s mind (in the FMC
world only). My advice, maybe trivial, is: don’t get stuck. If you have tried every method and
technique you know and found nothing, don’t stare at the cube hoping it solves itself: go back
and try something else.
-->
#### 6.3.2 全ての可能性を調べようとしない((Don’t) Explore Every Possibility)
<!--
6.3.2 (Don’t) Explore Every Possibility
In the first version of this tutorial this section was called “Explore Every Possibility” - a radical
change! The content of the old section is still valid though:
If you are computer scientist, mathematicians or so I can tell you that exploring different
possible solution is actually a tree search1
: you can choose if you prefer a DFS (depth-first
search, trying to complete a solution before moving to another one) or a BFS (breadth-first
search, “advance” every solution in parallel) approach, or a mixed one. Keep in mind that form
a single partial solution can derive a lot of nice branches as well a none; for this reason I don’t
use a fixed method. It is also important to know when to prune a branch (that is, discarding
unpromising partial solutions).
Why did I change the title? Simply because in the last three years I have realized that
my obsession for not missing any (promising) start and/or continuation gave me a strange
(and wrong!) attitude during the solves: there were moments when I tried not to find a good
continuation for the most promising start(s), but to convinve myself that certain starts were
not good and had to be discarded. In the computer science language used above, I was trying
to hard to prune bad branches of the tree, while I should have been looking for the most fruity
ones.
For example, I used to always check both the normal and inverse scramble for EO and
blockbuilding starts. Now, if I find something very good immediately, I postpone or even skip
checking other stuff or the inverse scramble.
After years of practice, I still don’t know what is the best way to choose which partial
solutions to explore and which to discard. All I can do is tell you what the problems are, so
that you can try and find a way to solve them on your own.
1
https://en.wikipedia.org/wiki/Tree_(data_structure)
-->

## 付録A　その他の参考資料 (Other Resources)
<!--
Appendix A
Other Resources
Here is a list of the sources where I got all this information from and other useful links.
Speedsolving.com
The speedsolving.com forum is the place where all the knowledge come from. In particular:
• The FMC Thread: https://www.speedsolving.com/forum/threads/the-fmc-thread.
13599/
A thread dedicated to FMC, where people constantly post their results and ask for advice.
• Fewest Moves: Tips and Techniques: https://www.speedsolving.com/forum/threads/
fewest-moves-tips-and-techniques.1566/
A thread by Arnaud van Galen collecting the most useful techniques, already included in
this tutorial.
• A Tutorial for Corner Commutators by Brian Yu: https://www.speedsolving.com/
forum/threads/bh-tutorial.12268/
Other Tutorials
• A video by Daniel Sheppard with advice on how to get better at FMC: https://www.
youtube.com/watch?v=q0mrMD933rM
• A 5-part video tutorial by Ranzha, first part:
https://www.youtube.com/watch?v=-gKAzXYonHI
• A presentation by Pranav Maneriker:
https://prezi.com/cng_isud-im-/rubiks-cube-fewest-moves/
Online Competitions
Online competitions are useful not only for competing and testing yourself against other people
on the same scramble, but also to study multiple good solutions to the same scramble: have a
look at the past rounds!
• David Adams’ Online Competition: https://www.ocf.berkeley.edu/˜dadams/fmc/
• German Forum Competition: https://speedcube.de/forum/showthread.php?tid=5795
53
54 APPENDIX A. OTHER RESOURCES
Cube Solving Programs
Cube solving programs can be useful to compare your solution with the optimal one, especially
for the first blocks.
• Cube Explorer, a cube solving program by Herbert Kociemba: http://kociemba.org/
cube.htm
It can be used, for example, to find the optimal algorithm for a given case or the best
possible ending for a partial solution (see also the last example in Section 2.5.3). Pay
attention in this last case: you may beat the optimal solution with insertions!
• Insertion Finder, by Baiqiang Dong: https://fewestmov.es/cube/if.cube?lang=en
This tool is very useful to check if you have found optimal insertions for a given skeleton.
• HARCS, by Matt DiPalma (replacing JARCS by Johanes Laire):
https://www.speedsolving.com/forum/threads/harcs-jarcs-replacement-cube-solver.
63241/
This tool is useful to find optimal solution to substeps of common metods (in fact, of any
method).
Other Websites
• Ryan Heise’s website: http://www.ryanheise.com/cube/
– In particular, the Fundamental Techniqes section: http://www.ryanheise.com/cube/
fundamental_techniques.html
• Lars Petrus’ website, with useful blockbuilding examples: http://lar5.com/cube/
-->

## 付録B　回転記号 (Notation)
<!--
Appendix B
Notation
The standard (OBTM) notation is actually very simple to learn. The basic rules are the following:
• To each face is assigned a letter: R = Right, L = Left, U = Up, D = Down, F = Front and
B = Back.
• Without additional symbols, the letter means “turn that face 90 degrees clockwise”. Modification are: “2” (for example, U2) for 180 degrees turns; '(prime or apostrphe, for example:
U') for 90 degrees counter-clockwise turns.
In the following table you can see all the basic moves, that are the only ones you need to
write down your solution. See Section 6.1.
R R2 R' L L2 L'
U U2 U' D D2 D'
F F2 F' B B2 B'
55
56 APPENDIX B. NOTATION
Other Moves
Other moves include:
• Wide moves: denoted by a lowercase w after the letter (for example Uw or Rw’ or Dw2)
denote “wide turn”: you have to move the inner layer together with the outer one. For
example:
Rw
They are sometimes also denoted by a lowercase letter (The
move in the picure would be r), although this notation is not standard.
• Cube rotations: denoted by a lowercase letter in square brackets, or by x, y and z (with
the rule x = [r], y = [u], z = [f]) denote a rotation of the whole cube (3 layers, if you
want). The usual modificators can be used: for example, y2 and [u2] both denote a 180
degrees rotation of the cube along the U/D axis.
• Inner layer moves: M = R L' x', E = U D' y' and S = F' B z.
M E S
They cannot be used in official FMC solutions.
-->

## 付録C　LLアルゴリズム (Last Layer Algorithms)
<!--
Appendix C
Last Layer Algorithms
Here is a list of last layer algorithms requiring 10 moves or less, modulo inverses and rotations.
I have also excluded all the edge and corner 3-cycles, that are better learnt in that context.
6 to 9 Moves
ZBLLs (all edges oriented)
R U R' U R U2 R' (7)
R U2 R2 U' R2 U' R2 U2 R (9)
R2 D L' B2 L D' R' U2 R' (9)
R B2 L2 D L D' L B2 R' (9)
F2 R2 L2 B2 D B2 R2 L2 F2 (9)
Other Algorithms
F R U R' U' F' (6)
L F R' F R F2 L' (7)
R U R2 F R F2 U F (8)
R' U' R' F R F' U R (8)
R U R' U' R' F R F' (8)
R U2 R' U2 R' F R F' (8)
R U R' F' L' U' L F (8)
R U2 R2 F R F' R U2 R' (9)
R' F R U R' U' F' U R (9)
R' F R2 B' R2 F' R2 B R' (9)
R' B U2 B' U2 B' R2 B R' (9)
R B' R B2 L' B L B2 R2 (9)
57
58 APPENDIX C. LAST LAYER ALGORITHMS
10 Moves
ZBLLs (all edges oriented)
R U' B L U L' B2 R B R2
B2 L U L' B2 R D' R D R2
R2 U R2 D' F2 L2 U' L2 D F2
L' B L' D2 R F' R' D2 L2 B'
F U R U2 R' U R U R' F'
R U2 R' B' U R U R' U' B
R U' R' U2 R L U' R' U L'
R U' L U L2 D' B2 D R' L
R U' L' B2 U' B2 U B2 R' L
R B2 R2 U L U' R2 L' B2 R'
Other Algorithms
F U R U2 R' U F' L' U L
F U R U2 R' U' R U R' F'
F U R U2 R' U' F' L' U L
F U R U2 R' F' U' L' U2 L
F R B' R B R' U R' U' F'
F R U' B U B' U R' U' F'
F R U R' U' R U R' U' F'
F U R U' F' L F R' F' L'
F U R U' B R' F' R B' R'
F U R' U2 R2 U R2 U R F'
F U R2 D R' U' R D' R2 F'
F U R' U' R F' U' R' U2 R
F U R' F R F' R U' R' F'
R U R' U' B' R' F R F' B
R U2 R' U2 B' R' F R F' B
R U R2 F' U' F U R2 U2 R'
R U R' F D B' R' B D' F'
R U R' F2 D' B L' B' D F2
R U R' F2 B D' L' D F2 B'
R U R' B' R B U' B' R' B
R U L B L' U' L B' R' L'
R U2 F' U2 F R2 B' R2 B R'
R U2 R F2 L F L' F2 R2 F'
R U2 R2 F R F L F L' F
R U2 R' F2 L' B L' B' L2 F2
R U' F2 D2 L B2 D L' D F2
R U' F' L' U L F R U' R2
R U' L' U R' U2 B' U B L
R F' U' L' U F R' F' L F
R B U B2 U' R' U R B R'
R B U B' R' U' R' F R F'
L F L' R U R' U' L F' L'
R B R' F R B2 R B R2 F'
R B' R B R2 U2 F R' F' R
R L2 D' B' D B L B' R' L
R2 F2 R' U B U' B' R F2 R2
R2 F2 L D' F' D F L' F2 R2
-->
[^0-1]: 訳注。[World Rubik's Cube Championship 2017](https://www.worldcubeassociation.org/competitions/WC2017)のこと。2年に1回の頻度で開催されるルービックキューブの世界大会を指す。2017年はパリ（フランス）、2019年はメルボルン（オーストラリア）で開催された。
[^0-2]: [Western Color Scheme](https://www.speedsolving.com/wiki/index.php/Western_Color_Scheme)
[^0-visualcube]: http://cube.crider.co.uk/visualcube.php
[^0-algcubingnet]: https://alg.cubing.net
[^1-1-Petrus]: **ブロックビルディングとは、複数のピースからブロックを作り、つなげるテクニックのことです。**CFOPにおけるF2Lとは大きく違うものと見なされがちですが、F2Lも一種のブロックビルディングと見なすことができます。対比すべきものとしては、エッジオリエンテーション(EO、PetrusやZZで用いられる)や「コーナーファースト」、アルゴリズムやコミューテータの利用などがあります。これらのテクニックは全て本書で説明されます。
[^1-1-Petrus-2]: たとえば、HARCSというは無料で利用できます。 https://www.speedsolving.com/forum/threads/
[^1-3-ZZ]: スピード解法では、ブロックを一つずつ揃えていくほうが、人間工学に叶った動きになるため、望ましいです。しかし、FMCにおいてこれは当てはまりません。効率性（つまり、手数）だけを気にするべきです！
[^1-6-Heise]: ここでいう「一直線に」(Linear)解くとは、FMCにおいては別の可能性を考えたり、キャンセル／やり直しを考えないで解くことを言います。
[^1-6-Heise-2]: F2L-1とはF2Lの完成状態から、コーナーとエッジのペアを一つ欠く状態を言います。
[^1-7-1]: **Color Neutralとはキューブをどの色からスタートしても解くことができることを言います。**たとえば、CFOPのクロス色がどの色でもできる、あるいはPetrusの2x2x2ブロックを8つあるパタンからどれでもできるということです。
[^1-7-2]: 不一致ブロックは、特にFMCにおいて**「疑似ブロック」(Pseudo-block)**と呼ばれることがあります。これはRouxやZZ、Heiseにおいて役に立つテクニックですが、他の解法でも使うことができます。疑似ブロックは、作る必要があるものとは異なるブロックで構築されますが、同じ「スロット」に配置されます。たとえば、Rouxにおいては、3x2x1のSB(Second Block)はFBの反対側にある4つのいずれかのブロックです。このテクニックはpremoveと組み合わせることで非常に強力なツールになります。詳細は第三章で説明します。
[^1-7-3]: **現在のステップで工夫することで次のステップに何らかの影響をもたらす**のはよい習慣です。この点については後の章でまた書きます。
[^1-7-4-1]: XCrossとは、クロスと最初のペアを同時に作ることです。2x2x2ブロックと2つのエッジを同時に揃えることと見なすこともできます。
[^1-7-4-2]: 訳注。ZBF2LはEOLS (Edge Orientation Last Slot)とも呼ばれます。「F2Lの4つ目の手順を調節することでEOを同時に処理し、F2L終了時に必ず上面に十字が出来るようにするというSubstepです。VHLSとは違い、IT化の時点で手順を変える場合もあるというのが特徴です。」([CubeVoyage](https://cubevoyage.net/speedcubing/3x3x3/advancedsubsteps/)より)
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
[^2-4-4-2]: コミューテータについて話すときには、「ピース」と「ステッカー」は違うものであることに気をつけましょう。
[^2-4-5]: もっと知りたい読者のためには、speedsolving.comのFMCスレッドでの[この投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666185)から始まるディスカッションが興味深いでしょう。特に、[2つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666199)では**5点交換を揃えるための3点交換の組み合わせを見つける「法則」についての数学的証明があります。**[3つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-50#post-666209)では、私が本書で行った説明と同じようなことが書いてあります。（私がこのテクニックを学んだのもこの投稿からです）[4つ目の投稿](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-51#post-666313)にはこの手法を使ったソルブの実例が載っています。
[^2-4-9]:[https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-214#post-1247800](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-214#post-1247800)
[^2-4-9-2]: [https://www.speedsolving.com/threads/the-fmc-thread.13599/page-28#post-488378](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-28#post-488378)
[^2-4-10]: ほとんどの例はこの投稿からです。 [http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-42#post-614593](http://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-42#post-614593)。一部、私の個人的な意見を加えて調整しています。
[^2-4-11]: [https://fewestmov.es/if](https://fewestmov.es/if)
[^2-5-1]: もちろん(FMCにおいては)何かをしてはいけないということはまったくありませんが、**エッジの向きを揃えてからそれをまた崩してしまうのはあまり賢いやり方ではありません。** 望むなら「部分的なEO (Partial EO)」からスタートしてもいいでしょう。
[^2-5-2]: [https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S](https://drive.google.com/drive/folders/1mppifILqu9Bu2phr8zhXGcXasBsSkv_S)
[^2-5-3-1]: https://www.speedsolving.com/threads/introducing-a-variation-for-fewest-moves.67299/
[^2-5-3-2]: https://docs.google.com/document/d/1oZwr2aSllFBL5lhbLTiWKQWplfk4i0LN0wA0uskeLJs
[^3-2-3-1]: [https://www.speedsolving.com/threads/the-fmc-thread.13599/page-52#post-667292](https://www.speedsolving.com/threads/the-fmc-thread.13599/page-52#post-667292)
[^3-2-3-2]: 「スクランブル」を解答に対する解答としてみなすこともできます！
[^3-2-3-3]: Taken from here: [https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-10#post-258791](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-10#post-258791)
[^3-3]: じつはこのソルブでは、揃っていないピースに矢印やバツ印を書くことで簡単にアルゴリズムを認識できるようになるのです。なので、私はここではReverse NISSというテクニックを実際には使いませんでしたが、解答自体がよい実例になるので書きます。
[^3-4-1]: ノーマルスクランブルではそれぞれUR, RF, DL, DR にあたります。しかし、現時点では無視してよいです。
[^3-4-2]: 実はこのスクランブルは非常にレアな偶然が重なっています。F/B軸に対してノーマルスクランブルと逆スクランブルの両方で6手が最適手順であり、どちらから始めてNISSを使ったとしても5手が最適となっています。
[^3-6]: [https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62##post-721942](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-62##post-721942)
[^3-7-1]: パリティを避けるためにこの条件が必要です。
[^3-7-2]: 実はコミューテータです。`M E M' E'` = `[M, E]`で、`M E2 M' E2` = `[M, E2]`
[^5-1-1]: タイムマネジメントについては6.3節で話します。
[^5-1-2]: [https://www.ocf.berkeley.edu/˜dadams/fmc/](https://www.ocf.berkeley.edu/˜dadams/fmc/)
[^5-1-3]: [https://speedcube.de/forum/showthread.php?tid=5795](https://speedcube.de/forum/showthread.php?tid=5795)
[^5-3]: [https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-88#post-842681](https://www.speedsolving.com/forum/threads/the-fmc-thread.13599/page-88#post-842681)
[^5-6-1]: [https://www.speedsolving.com/wiki/index.php/LLEF](https://www.speedsolving.com/wiki/index.php/LLEF)
[^5-6-2]: [https://www.speedsolving.com/wiki/index.php/Summer_Variation](https://www.speedsolving.com/wiki/index.php/Summer_Variation)
*[CFOP]: Cross, F2L, OLL, and PLL
*[F2L]: First Two Layer
*[HTM]: Half Turn Method