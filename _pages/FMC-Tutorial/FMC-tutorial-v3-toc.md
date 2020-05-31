---
title: "最少手数競技入門 第三版 by Sebastiano Tronto "
description: Sebastiano TrontoによるFMCチュートリアル(第三版)の日本語訳です。ルービックキューブの最少手数競技のための入門記事です。
date: 2020-05-31 20:00:00 +0900
header:
  og_image: /assets/img/fmc-tutorial-header.png
  teaser: /assets/img/fmc-tutorial-header.png
  image: /assets/img/fmc-tutorial-longheader.png
permalink: /FMC/FMC-Tutorial/v3/
redirect_from: ../FMC/FMC-tutorial.html
layout: single
classes: wide
toc: false
tocright: false
toc_icon: "cog"
toc_sticky: true
author_profile: false
sidebar: 
  nav: "fmc-v3"
footnote_script: true
---
本ドキュメントは、**Sebastiano Tronto氏のFewest Moves Tutorial(第三版)を日本語に翻訳したもので、最少手数競技の基本から応用までを網羅した入門記事です。** WCA公式競技のひとつである「最少手数競技（FMC、Fewest Moves Challenge）」に特化したチュートリアルであり、ルービックキューブをできるかぎり少ない手数で解くためのテクニックが詰まっています。2020年時点での、FMCに必要な知識のほとんどはここに記載されているでしょう。これはtocからの変換です。

このチュートリアルを読んでFMCに興味を持つ方が増えたり、自分自身のPBを更新する方が出てくることがあれば、非常に嬉しく思います。

**さあ、FMCを楽しみましょう！**

**この翻訳プロジェクトはまだ未完成です！まだすべての翻訳が終わっていません。** どうか温かい目でゆっくりとFMCをやりながらお待ちください。
{: .notice--danger}

## 目次
- [翻訳者序文](translation-preface)
- [序文](preface)
- [イントロダクション](introduction)
  - 公式大会でのWCA規則
  - このチュートリアルのゴール
- [第1章：既成概念にとらわれずに考える](chapter1)
  - Petrus
  - Roux
  - ZZ
  - CFOP
  - キーホールF2L
  - Heise
- [第2章：ソルブの進め方](chapter2)
  - ブロックビルディング
  - スケルトン
  - コミュテータ
  - インサーション
  - EOから始めよ
- [第3章：高度なツール](chapter3)
  - 逆スクランブル
  - 疑似ブロック、プリムーブ、NISS
  - Reverse NISS
  - ペア分析
  - 歪んだセンター
  - フリースライス
  - コーナーファースト
- [第4章：練習方法](chapter4)
  - 大会のシミュレーション
  - ペンと紙を使う
  - 上級者と比べよう
  - ハードスクランブル
  - 熟考する練習
  - ファストスクランブル
- [第5章：公式大会](chapter5)
  - 解答の書き方
  - バックアップ解答
  - タイムマネジメント
- [付録A：その他の参考資料](appendix#appendix-a)
- [付録B：回転記号](appendix#appendix-b)
- [付録C：詰めキューブ練習](appendix#appendix-c)
- [付録D：ドミノリダクション入門](appendix#appendix-d)

## 各章のサマリー
**これから本ドキュメントを読む日本語読者のために、それぞれの章の簡単な内容をお伝えしましょう。**一日で読み切れる分量ではありませんので、自分の興味あるところから少しずつ読み進めていくのもよいと思います。日本語読者にとって読みやすくなるように、日本のスピードキューブ事情にあわせた訳注を各所に付けています。ぜひご活用ください。

### [翻訳版序文](translation-preface)
翻訳者による本ドキュメントの翻訳プロジェクトの経緯を簡単に記載しています。

### [序文](preface)
**第二版および第三版での原著者による序文、およびこのドキュメントの目的や、読者に期待する前提知識などを記載しています。**謝辞や免責事項、ライセンスもこのセクションにまとめました。

### [イントロダクション](introduction)
最少手数競技とはどのようなものかを簡単に説明しています。ルービックキューブをできるかぎり短い手数で解く競技であることは想像できると思いますので、公式大会で規則について簡単に触れています。

### [第1章：既成概念にとらわれずに考える](chapter1)
**FMCに取り掛かる前に、ルービックキューブを揃えるにはどのような解法があるかを振り返ります。** CFOP、Roux、ZZ、Petru、Heisesなどの解法について概要を紹介し、FMCにおける特徴を説明します。FMCにおいては、使える解法やテクニックは使える限り使うことが推奨されます。

### [第2章：ソルブの進め方](chapter2)
**FMCで用いられる基本的なテクニックを紹介しています。** 主に「ブロックビルディング」「スケルトン」「コミュテータ」「インサーション」「EOファーストアプローチ」のテクニックについてそれぞれ解説をしており、本ドキュメントの中で最も分量の多いところです。これを身に着ければFMCらしいソルブができるようになるでしょう。ドミノリダクションについても簡単に触れています。

### [第3章：高度なツール](chapter3)
**逆スクランブル、疑似ブロック、プリムーブ、NISS、Reverse NISSなどのより高度なテクニックを解説します。**ここで記載されえちる、覚えておくと役に立つ短いアルゴリズム、ペア分析、センターを無視して揃える、フリースライス、コーナーファーストなどのテクニックが使えるようになれば、FMC上級者となる日も近いでしょう。

### [第4章：練習方法](chapter4)
上達するために必要な練習方法をいくつか記載しています。実際に時間を測って大会と同じような形式で練習をしてみることや、熟考しながら練習することの意義について簡単に触れています。

### [第5章：公式大会](chapter5)
公式大会でFMCの試技をする際のテクニックを説明しています。解答を書くときには持ち替え記号を使わずに書くとよいでしょう。また、時間制限があるときにはあらかじめバックアップの解答を用意しておくとよいことや、1時間という制限時間をどのように使うべきかといったことにも触れています。

### [付録](appendix)
第三版では付録として下記の4つが収録されています。
1. 学習のための参考資料：さらなる学習のためのリソースを紹介しています。
1. 回転記号：基本的な回転記号について説明しています。
1. Reto Bubendorfの詰めキューブ練習：Retoが作成した詰めキューブ問題が収録されています。
1. ドミノリダクション入門：ドミノリダクションの基本的な考え方についてさわりだけ触れています。

## 原著情報
Fewest Moves Tutorial - Solving a Rubik's Cube with as few moves as possible  
Written by Sebastiano Tronto  
v3.01 (April 17, 2020)  
第三版原文: [Fewest Moves Tutorial](https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf)  
第二版原文: [Fewest Moves Tutorial 2nd edition](https://fmcsolves.cubing.net/fmc_tutorial_ENG_v2.pdf)  

### ライセンス
本ドキュメントは[Creative Commons Attribution 4.0 License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)で提供されます。つまり、このドキュメントは自由に再配布することができます。自由に別の言語に翻訳しても大丈夫です。その際に、著作者の名前は必ず記載するようにして、原著からの変更点があれば明記するようにしてください。