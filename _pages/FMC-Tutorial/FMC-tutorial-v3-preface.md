---
title: 序文 - 最少手数競技入門 by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 14:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/preface
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
[戻る：翻訳版序文](translation-preface){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：イントロダクション](introduction){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->
## 第三版への序文 (Preface to the Third Edition) {#third-preface}
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

## 第二版への序文 (Preface to the Second Edition) {#second-preface}
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
## 本書について (About this Book) {#about-this-book}
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

<!-- 通常コンテンツここまで-->
[戻る：翻訳版序文](translation-preface){: .btn .btn--inverse} [目次](../v3/){: .btn .btn--primary} [進む：イントロダクション](introduction){: .btn .btn--inverse}

[^0-1]: 訳注。[World Rubik's Cube Championship 2017](https://www.worldcubeassociation.org/competitions/WC2017)のこと。2年に1回の頻度で開催されるルービックキューブの世界大会を指す。2017年はパリ（フランス）、2019年はメルボルン（オーストラリア）で開催された。
[^0-2]: [Western Color Scheme](https://www.speedsolving.com/wiki/index.php/Western_Color_Scheme)
[^0-visualcube]: http://cube.crider.co.uk/visualcube.php
[^0-algcubingnet]: https://alg.cubing.net
