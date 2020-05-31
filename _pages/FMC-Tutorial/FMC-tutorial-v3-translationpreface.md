---
title: 翻訳版序文 - 最少手数競技入門  by Sebastiano Tronto 第三版
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 09:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/translation-preface
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
[目次](../v3/){: .btn .btn--primary} [進む：序文](preface){: .btn .btn--inverse}

## このドキュメントは何？
本ドキュメントは、**2020年にSebastiano Tronto氏によって書かれたFewest Moves Tutorial(version3.01)を日本語に翻訳したものです。** 2019年12月、本チュートリアルを日本語に翻訳されたものが公開されていなかったため、翻訳プロジェクトをスタートしました。本記事の内容については、最少手数競技に関する知識や用語を確認しながら翻訳を進めていますが、翻訳者の技量不足により不正確である場合があります。あらかじめご了承ください。

また、すぐに最少手数競技のやりかたを覚えたいという方には、日本語での素晴らしい解説記事がありますので、こちらもあわせてご参照ください。
- [WRCC](http://wrcc.main.jp/commentary_fmc/fmc/index) : 早稲田大学スピードキュービングサークルによる解説記事(2016)
- [TRCC](http://trcc.sub.jp/solution/fmc/fmcindex.html) : 東京大学ルービックキューブサークルによる解説記事(2015)

This documantion is **a Japanese translated edition of Fewest Moves Tutorial (Third Edition) by Sebastiano Tronto.** Since no translation in Japanese had been published at December 2019, I started a tranlation project for the tutorial. I am translating the document looking up the basic knowledges and the technical terms on FMC, but the translated content might be wrong by reason of my lack of translation and FMC skills. If you find any mistakes in the translation, please let me know!
{: .notice--warning}

## Sebasiano Trontoって誰？
**[Sebastiano Tronto (2011TRON02)](https://www.worldcubeassociation.org/persons/2011TRON02)は、イタリアのスピードキューバーであり、最少手数競技の世界記録保持者(単発)です(2020年5月現在)。**

2019年10月22日に単発16手で世界記録を達成しました。平均記録も22.00であり、世界2位です。また目隠し競技においても有名な熟練者であり、3x3x3目隠し、4x4x4目隠し、5x5x5目隠しのイタリア記録保持者でもあります。3x3x3目隠し(平均)は世界15位の超実力者です。

![](../../../assets/img/sebastiano-tronto.png){:width="400px" height="auto" class="img-responsive align-center"}
Sebastiano Tronto (WCAプロフィールより)
{:.text-center}

どんな状態のルービックキューブであっても高々20手で完成状態にすることができる、ということが広く知られています。この数字を「神の数字(God's Nubmber)」と呼ぶことから、FMCにおいては20手以下で完成させた記録を持つ競技者を「神の領域」と冗談のように呼ぶことがあります。2020年5月時点では、**公式大会で20手以内の記録を持つのは下記の13人しかいません。** そんなFMCの達人が4年近くの歳月をかけて作っているのが本ドキュメントです。

1. Sebastiano Tronto : 16
1. Harry Savage : 17
1. Mark Boyanowski : 17
1. Cale Schoon : 18 **世界記録保持者(平均)**
1. Chad Batten : 19
1. Baiqiang Dong (董百强) : 19 **アジア記録保持者(平均)**
1. Kacper Rafalski : 19
1. Marcel Peters : 19
1. Robert Yau : 19
1. Shuto Ueno (上野柊斗) : 19 **アジア記録保持者(単発)**
1. Szymon Jeziorski : 19
1. Tim Wong : 19
1. Uladzislau Ushakov (Владислав Ушаков) : 19

## 第3版の公開に際して
2020/01/14に本チュートリアルの第3版が公開されました！(2020/04/17に修正版v3.01が公開されました)

この日本語版は、第3版の内容に沿って翻訳中のものです。[第2版を翻訳したもの](../v2/)もありますので、興味のある方はこちらもご参照ください。また、**原著者がGitHubにリポジトリを作成し、原文のLaTeXファイルや画像ファイルなどを公開しています。** 詳細は[こちら](https://github.com/sebastianotronto/fmctutorial)をご覧ください。

## 翻訳にあたっての謝辞
**この素晴らしいチュートリアルを無料で公開してくれているSebastiano Tronto氏に最大限の感謝を申し上げます！**原著はCC-BY-4.0というライセンスで提供されているため、自由に翻訳して再配布することができます！

また本ドキュメントの翻訳にあたり、内容を確認してタイポや内容のミスだけでなく、FMCの技術的な側面についても補足をしてくれた先輩FMCer諸氏にも合わせて感謝を述べさせてください。私はFMC初心者ですので、上級者たちからのアドバイスをいただけなかったら本翻訳の完成はなかったでしょう。

**Special thanks to Sebastiano Tronto, a FMC superstar, for publishing this wonderful tutorial for free!**  
Un ringraziamento speciale a Sebastiano Tronto, una superstar FMC, per aver pubblicato gratuitamente questo meraviglioso tutorial!


## 翻訳の進捗について
**本ドキュメントは、未完成です。**原文はコメントアウトされた状態で保存されています。翻訳に協力してくださる方は、コメントアウトを外して日本語の翻訳を書き込んでください。翻訳の進捗は[GitHubのリポジトリ](https://github.com/kawam1123/translation)で管理しており、画像ファイルなどもこちらに格納されています。


[目次](../v3/){: .btn .btn--primary} [進む：序文](preface){: .btn .btn--inverse}