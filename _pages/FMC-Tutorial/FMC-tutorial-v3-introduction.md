---
title: イントロダクション - 最少手数競技入門 by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 14:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/introduction
layout: single
classes: wide
toc: false
tocright: true
toc_icon: "cog"
toc_sticky: true
author_profile: false
sidebar: true
sidebar:
  nav: "fmc-v3"
footnote_script: true
---
[戻る：翻訳版序文](translation-preface){: .btn .btn--inverse} [目次](toc){: .btn .btn--primary} [進む：第1章](chapter1){: .btn .btn--inverse}

<!-- 通常コンテンツここから -->

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

「解法はスクランブル手順の任意の部分に直接由来してはならない」というルールのために、2016年からFMC用のスクランブルには最初と最後に`R' U F`が加えられることになりました。

現在の大会における最高記録は、**Sebastiano Tronto(イタリア)による単発16手 (FMC 2019)**です。３回の試技の平均では、**Cale Schoon (アメリカ)による21.00手 (North Star Cubing Challenge 2020)**が世界記録です。2019年の世界大会での世界チャンピオンは、ともに平均25.33手を出したFirstian Fushada (符逢城)とChristopher Chiです。

**訳注：**  
翻訳時点(2020/05)では**Shuto Ueno (上野柊斗)が単発19手、平均24.00手の日本記録を保持しています。**この単発記録は、Baiqiang Dong (董百强)と並んでアジア記録(AsR)でもあります。
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

<!-- 通常コンテンツここまで-->

[戻る：翻訳版序文](translation-preface){: .btn .btn--inverse} [目次](toc){: .btn .btn--primary} [進む：第1章](chapter1){: .btn .btn--inverse}


[^0-1]: 訳注。[World Rubik's Cube Championship 2017](https://www.worldcubeassociation.org/competitions/WC2017)のこと。2年に1回の頻度で開催されるルービックキューブの世界大会を指す。2017年はパリ（フランス）、2019年はメルボルン（オーストラリア）で開催された。
[^0-2]: [Western Color Scheme](https://www.speedsolving.com/wiki/index.php/Western_Color_Scheme)
[^0-visualcube]: http://cube.crider.co.uk/visualcube.php
[^0-algcubingnet]: https://alg.cubing.net
