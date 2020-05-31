---
title: 第5章 - 最少手数競技入門 - ルービックキューブを少ない手順で解く by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 17:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/chapter5
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
[戻る：第4章](chapter4){: .btn .btn--inverse} [目次](toc){: .btn .btn--primary} [進む：付録](appendix-a){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->
## 第５章　公式大会 (In Competition) {#ch5}
<!--
Chapter 6
In Competition
-->
### 5.1 解答の書き方(How to Write a Solution)
大会のときでも練習のときでも、**解答は持ち替え記号なしで書くのがよいでしょう[^5-1-0]。**これにはいくつもの理由があります。
- **持ち替え記号を使うと解答を書き間違えやすい**
- **持ち替え記号があるとキャンセルが見つけにくい。** `R z' U'` のようなことをやるのはとんでもない手数のムダです！ (これはキャンセルして0手になります)
- ソルブ中にキューブを持ち替える場合、どの面がどこにあるかを常に意識しておかなければならない

ではどうやって持ち替え記号なしで解答を書いたらいいのでしょう？　B面でPLLを回すのは厄介で難しいでしょう。しかし、簡単なやり方があるのです。標準配色(BOY配色)でいつもの向きでキューブを持ったときに、**「白センターのある面は常にUだ」「緑はF」「黄色はD」と覚えておけばいいだけです。**それぞれの面を回すとき、どの向きで持っていても関係なく「白面だからUだ」と書けばいいのです。これはそこまで難しくありませんが、覚えるためには「青(Blue)はB面」「赤(Red)はR面」と頭文字が同じ面から覚えていくといいでしょう。他の多くの言語でも同じように使えます。

**訳注：**  
ここで著者が言っているヒントはインド・ヨーロッパ語族（英語、ドイツ語、フランス語、イタリア語など）ならだいたい当てはまるものですが、日本語では役に立たないかもしれません。U面が白、F面が緑、という向きでなくてもよいですが、自分なりの覚え方を決めてみるといいでしょう。
{: .notice--info}

<!--
5.1 How to write a solution
Both in competition and while practicing, you should write down your solution without rotations1
. There are many good reasons to do so:
• Using rotations, it is easier to make mistakes.
• Rotations can hide cancellations: things like . . . R z' U'. . . are a terrible way to waste
moves!
• While solving, if you rotate the cube, you always need to keep in mind which side is where.
How to write a solution without rotations? A PLL on B is very awkward! There is an easy
way: keeping the standard orientation, with a BOY color scheme (the “standard” one), you just
need to remember that the white-centered layer is always U, the green-centered one is F, the
yellow-centered one is D and so on. Every time you move a layer, for example the white-centered
one, you don’t need to care about how you are looking at the cube at that moment: just write U.
To help memorizing the scheme (not that it is hard), remember that Blue and Red begin with
the same letter as their layer. This trick actually works well in many other languages too.

-->
### 5.2 バックアップ解答(Backup Solution)
**大会のように時間制限がある環境でFMCをやるなら、あらかじめ「バックアップ解答」を作っておくことを身につけましょう。**つまり、試技を始めてから早い段階(たとえば最初の30分以内)に見つけた解答で、最低限キューブを揃えることができるものを書いておきましょう。あまりよくないものでもよいです。どんなに手数がかかる解答でも、白紙で解答を出すよりはずっとよいです！

たとえば、平均35手が出そうなペースで進んでいるときに、20分考えて40手の解答を見つけたとしましょう。すると、残りの40分間は落ち着いた気持ちで取り組むことができるはずです。解答用紙にそのまま書き込んでも構いません。後で解答を変えたくなったら、バックアップ解答を消して新しいものを書き直せばいいだけですし、別の紙に書いて提出してしまうという手もあります。バックアップ解答を見つけるにはたくさんのアプローチがあります。

- 自分で決めた制限時間 (たとえば35分)の中で、どんなに悪いものでも必ず解答を見つけて書くようにしましょう。私はやりませんが、もし制限時間ギリギリになっても解答用紙が空白であることが多いなら、やってみると役立つでしょう。
- **偶然によい解答を見つけてしまったら、どこかにメモしておきましょう。**いいスタートを切ってからもう一度スクランブルしていたらPLLスキップを見つけてしまった！ということもあるでしょう。
- 私はバックアップ解答を準備することはあまりないです。**代わりにバックアップ用のスケルトンを作っておきます。**たとえば、28手以下を目指すとしましょう。このとき、3コーナーのスケルトン(24手)を見つけても、あまり使えないでしょうけれど、どこかにメモしておくようにします。制限時間まで残り10分になったとき、他によい解答を見つけられなかったら、このスケルトンを使ってインサートを探す、という風にします。3コーナーのインサートを1回やるだけなら、私はだいたい5分くらいしかかかりません。あなたのスピードにあわせて、制限時間までどれくらいになったら使うかを調整してみるといいでしょう。

よいバックアップ解答とはどういうものでしょう？　これは、なんでもよいのです！　解答が書いてあればDNFよりは何でもよいものです。**特に、現在の((公式大会の)FMC競技形式はMean of 3 (3回の試技の平均)という形式ですから、1回でもDNFをしてしまうと平均もDNFになってしまいます。**

<!--
5.2 Backup solution
It is good habit, in time-limited competitions, to write a “backup solution”. By this I mean a
solution that may be not so good, but at least works, that you have found at some point during
the attempt (say in the first 30 minutes). For how bad it can be, it is certainly better than not
having any solution at all!
For example, if you average about 35 moves, but after 20 minutes you have found and written
down somewhere a 40 moves solution, you will be more relaxed for the remaining 40 minutes.
You can even write it down on the official sheet: if you later want to change your solution, you
can delete the backup solution and write down the new one, or simply submit it on a different
sheet of paper. There are many possible approaches to finding a backup solution:
• Force yourself to have found and written a solution, no matter how bad, in a fixed time
limit (for example 35 minutes). I don’t do this, but it can be useful if you often find
yourself at the end of the hour without anything written down.
• If you come across some solution by chance (for example you have found a good start and
solving the cube to re-scramble it you get a PLL skip), take note of it somewhere.
1Rotations, as well as wide and slice moves, can be useful to write down certain steps (like edge insertions),
but can you always remove them from the final solution that you submit.
57
58 CHAPTER 5. IN COMPETITION
• What I do: I don’t really find backup solutions, but rather backup skeletons. For example,
my goal is usually sub-28; in this case, a skeleton leaving 3 corners in 24 moves is not good,
but if I find one I keep it somewhere. If I have, for example, 10 minutes left and I don’t
have anything better, I look for an insertion in that skeleton. A single 3c insertion usually
takes me about 5 minutes, so you should adjust my “10 minutes” to your speed.
What can a good backup solution be? Any solution! Anything is better than a DNF,
especially now that the preferred format for FMC (in official competitions) is “mean of 3”: a
single DNF gives you a DNF mean.
-->
### 5.3 タイムマネジメント(Time Managment) {#ch5-3}
「試技の間の時間管理をどうするか？」というのはちょっと複雑なトピックです。私のアドバイスがどんな場合も必ず役立つとは言えません。このアドバイスは注意深く読んで使ってください。

実際、2019年の前半まで自分自身はとても時間管理が下手なほうだと思っていました。「大会形式の練習」をたくさんしたことでようやく上手になってきたと思います。**残念ながら、時間管理のスキルを高めるには特別なテクニックはなく、「練習、練習、そして練習！」しかありません。**

<!--
“How to manage your time” is a complex topic, and I don’t want to say that my advice is
absolutely good in any case: follow it carefully!
In fact, until early 2019 I considered myself pretty bad at time management. Only after a lot
of “competition simualtion” practice I got better at it. I am afraid there is no special technique
other than “practice, practice, practice” to build up a better time management.

-->
#### 5.3.1 ひっかからないように(Don't Get Stuck) {#ch5-3-1}
誰にでも起こることですが、大会ではどこかで長く詰まったり、次の手へのよいつながりを見つけられずに時間が経ってしまうことがあります。

「いまやっているところから続けていくとよい手順が見つかるかどうか」を即座に判断する能力があれば、**他人の心の中を読み取る（ただしFMC中に限る）くらい役立つことでしょう！** 本当に大したことではありませんが、私からのアドバイスは**「どこかでひっかからないようにすること、止まらないようにすること」**です。知っているすべての手法とテクニックを使っても何も見つからないとしたら、キューブをじっと見つめて「勝手に解ければいいのに」と考えるのは一旦やめましょう。少し戻って、別のやり方を色々試してみましょう。

<!--
It can happen to anyone: during a competition you get stuck on a certain start and don’t
seem to find any better continuation. The ability to quickly understand if a start can lead to
a good continuation would be as useful as being able to read other people’s mind (in the FMC
world only). My advice, maybe trivial, is: don’t get stuck. If you have tried every method and
technique you know and found nothing, don’t stare at the cube hoping it solves itself: go back
and try something else.
-->
#### 5.3.2 全ての可能性を調べようとしない((Don't) Explore Every Possibility)
このチュートリアルの初版では「全ての可能性を調べよう！」という名前の章でした。正反対に変わりましたね！　しかし、前の版には今も役立つ内容が書いてあります。
> あなたがコンピュータサイエンティストや数学者なら、全てのありうる解答を探索していくのは木探索(tree search)[^5-3-2]のようなものだと説明するでしょう。
>
>**DFS(深さ優先探索) で「解答を見つけるまで次の分岐に行かない」**のか、**BFS(幅優先探索)で「全ての解答を並行して探索する」**のか、その混合なのか、好みに応じて選択できます。たったひとつの部分解答から、多くの有望な分岐ができることも、何も生み出さないこともあります。そのため、私は決まったやり方は取りません。どの段階で枝刈りをするかを決めるのも重要です。つまり、有望ではない部分解答を切り捨てるということです。

では、**なぜ章のタイトルを変えたのか？** それは単純なことで、去年あることに気付いたからです。有望なスタートやいいつながりを決して見逃さないようにしようということに取りつかれていて、ソルブに対する考え方が変な方向（間違った方向！）に向かっていました。あるとき、非常に有望なスタートを切ってから、その先のつながりを探索するのをやめようとしました。代わりに、特定のスタートから始めてもあまりよくないかもしれないし後で捨てることになるかもしれないぞ、と自分に言い聞かせたのです。**コンピュータサイエンスの用語で言えば、私は悪い分岐の枝刈りをしようとしすぎていて、最も実りある枝を探すのを怠っていたということです。**

たとえば、それまではノーマルスクランブルと逆スクランブルの両方からEOとブロックビルディングを探していました。しかし今では、よいものが短時間で見つかったなら、ほかの可能性をチェックすることは後回しにしたり、やめてしまうことさえあります。

何年もの練習を経ていますが、部分解答のうち、どれが深く探索すべきものでどれ捨てるべきものなのかを判断する一番良い方法はわからないままです。あなた自身のやり方でこの問題を解決することができるようにするには、私にはこういった問題があることを伝えることしかできません。

<!--
5.3.2 (Don’t) explore every possibility
In the first version of this tutorial this section was called “Explore every possibility” - a radical
change! The content of the old section is still valid though:
If you are computer scientist or mathematician I can tell you that exploring different possible
solutions is actually a tree search2
: you can choose if you prefer a DFS (depth-first search, trying
to complete a solution before moving to another one) or a BFS (breadth-first search, “advance”
every solution in parallel) approach, or a mixed one. Keep in mind that from a single partial
solution you can derive a lot of nice branches as well a none; for this reason I don’t use a fixed
method. It is also important to know when to prune a branch (that is, discarding unpromising
partial solutions).
Why did I change the title? Simply because in the last years I have realized that my obsession
for not missing any (promising) start and/or continuation gave me a strange (and wrong!)
attitude during the solves: there were moments when I tried not to find a good continuation for
the most promising start(s), but to convince myself that certain starts were not good and had
to be discarded. In the computer science language used above, I was trying too hard to prune
bad branches of the tree, while I should have been looking for the most fruity ones.
For example, I used to always check both the normal and inverse scramble for EO and
blockbuilding starts. Now, if I find something very good immediately, I postpone or even skip
checking for other stuff.
After years of practice, I still don’t know what is the best way to choose which partial
solutions to explore and which to discard. All I can do is tell you what the problems are, so
that you can try and find a way to solve them on your own.
2
https://en.wikipedia.org/wiki/Tree_(data_structure)
-->
<!-- 通常コンテンツここまで-->

[戻る：第4章](chapter4){: .btn .btn--inverse} [目次](toc){: .btn .btn--primary} [進む：付録](appendix-a){: .btn .btn--inverse}