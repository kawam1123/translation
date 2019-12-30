---
permalink: /about/
title: "About"
sidebar:
  nav: "leftnav"
---

## これは何？
これは、私 (@kawam1123) の開発に関するアクティビティをまとめるためのページです。

## やりたいこと

### 公開ページを作る
- [x] Github Pagesを作る
- [ ] jekyllのレイアウトをカスタマイズする（←いまここ。少しずつ修正中）
- [x] ローカルにjekyllのビルド環境を作る → (2019/12/07)成功。Gemfile以下は.gitignoreした。
    - 参考にした記事：[GitHub PagesにJekyllを使っていい感じのページを作る例](https://qiita.com/stkdev/items/0e2df27736acbea9bd26)

### ブログ記事を書く
- [FMC アドベントカレンダーの記事を書く](https://kawam1123.hatenablog.com/entry/FMC-Advent-Calendar-2019-day15) →2019/12/15 書いた。
- 日本大会2019で実施したライブ配信環境についてまとめる

### 翻訳する
- [x] 翻訳関連のリポジトリを作る→作った。[翻訳関連リポジトリ：kawam1123/translation](https://github.com/kawam1123/translation)
- [ ] Sebastiano Tronto氏の[FMC Tutorial](https://fmcsolves.cubing.net/fmc_tutorial_ENG.pdf)を日本語に翻訳する。→ 翻訳開始しました。翻訳用リポジトリを別途作成し、Markdownで日本語に翻訳しています。翻訳ページは[こちら](https://kawam1123.github.io/translation/FMC/FMC-tutorial.html)。
- [ ] WCA Documentsの中にある[WCA Cometition Tutorial](https://www.worldcubeassociation.org/files/WCA_Competition_Tutorial.pdf)を翻訳する。上と同じリポジトリに入れて管理する。ローカルでちょっと書いたものがあるので、どうせなら管理しつつ公開したほうがよかろう、と思った。→ [途中経過を公開しました。](http://kawam1123.github.io/General/Competitor-tutorial.html)


### 大会を運営する
- [ ] WCA公式大会を企画して主催する
- [ ] 非公式競技のある大会をやってみたい


## やったこと

- [WCAデータベースを用いた大会別初参加者の集計](https://github.com/kawam1123/wcadb)
    - 2019/05ごろにコードを書いて集計したもの。 **大会ごとに初参加者はどれくらいいるんだろう？** と思って集計したものです。日本国内で実施されている大会を対象に、SQLを雑に回しました。
- [Full OH PLL Guide from PianoCube93](https://kawam1123.github.io/one-handed/Full%20OH%20PLL%20Guide%20from%20PianoCube93.pdf)
    - 片手競技(OH)を始めたころに大変お世話になったOH PLLの手順集を画像付きで１枚にまとめました。自分自身の確認用。
    - オリジナルはRedditのu/PianoCube93氏が[投稿したポスト](https://www.reddit.com/r/Cubers/comments/7c2es2/full_oh_pll_guide/)です。元のポストでは、指使いのアニメーションGIF（ゆっくりバージョン／通常バージョン）が閲覧できます。OHのPLLはどうやって回すとよいのかを考える最初の一歩として非常に役立つと思います。
- [大人キューブ会のイベント説明ページを作成した](./otonacube/)

### キューブカバーの自作用図面
公開されている図面データを元に、キューブカバーの自作用図面を作りました。詳細は[こちら](./cubecover.html)。
![キューブカバー図面](/assets/img/cubecover_layout.png "cube cover")
![キューブカバー外観](/assets/img/cubecover_outline.jpg "cube cover")
- [印刷用図面(pdf)](/assets/pdf/cubecover_forprint_rev2.pdf) 
- [印刷用図面(dxf)](/assets/pdf/cubecover_forprint_rev2.dxf) 

### FMC
- [FMC アドベントカレンダーの2つめのスクランブルやる](./fmc/2019/12/08/FMCadvent_2nd.html)

## TODO
- [x] `FMC Tutorial` を通読する : 2019/12/09にようやく読みました。

## よく使うもの

### ブラウザベースのタイマーアプリ [csTimer](https://cstimer.net/)
デスクトップ/モバイルの両方で利用できるブラウザベースのタイマーアプリ。開発者はcs0x7f氏 (Chen Shuang)。開発速度が非常に早く、必要な機能は殆ど揃っている素晴らしいアプリ。私は主にこれを使っています。
- [csTimer翻訳プロジェクト (Crowdin))](https://crowdin.com/project/cstimer)
        - 翻訳文字列が追加されるたびに更新しています。誤訳やもっと適切な翻訳があればここから更新できます。
- [csTimerのソースコード(GitHub)](https://github.com/cs0x7f/cstimer)
        - aa
- [csTimerの機能リスト by topppits (Reddit)](https://www.reddit.com/r/Cubers/wiki/cstimer)
    - 非常にたくさんの機能があるので、topppits氏がまとめてくれたもの
- [csTimerのバーチャルキューブ機能についての記事](https://kawam1123.hatenablog.com/entry/2019/08/18/082542)
    - なぜか急に思い立ってバーチャルキューブ機能についてだけの記事を書いたもの。誰得。

### タイマーデータ可視化ツール [Kuebiko Cubing](http://www.kuebiko-cubing.com/)
csTimerなどのタイマーアプリからエクスポートしたデータをもとに、グラフを作って可視化できるようにしてくれるサービス。開発者はtussosedan氏 (Alex Friedman)。ある程度まとまった期間のソルブを俯瞰して進捗を確認したいときに使います。

>対応している形式／タイマーアプリ(2019年12月時点): WCA ID, cstimer, Block Keeper, ChaoTimer, Prisma Puzzle Timer, qqtimer, Twisty Timer, ZYX Timer

### Rouxの勉強に使っているもの
- [Block Trainer](https://cubegrass.appspot.com/block_trainer/)
    - FBとSBに分けてブロックづくりの練習ができる。FMCのブロックビルディングの練習にも使えるので、長くお世話になりそう。
- [CMLL Guide by Kian Mansour](https://sites.google.com/view/kianroux/cmll)
    - CMLL勉強中。ビデオも公開されているので非常に役に立つ。Rouxの解き方を覚えるにあたって、Kian MansourのRoux Tutorialが一番網羅的でわかりやすかった。

- - -
## プロフィール
- - -
関連するリンクを下記に貼っておきます。

- [これまでのキューブ歴まとめ(1年目) (2019-08-01)](https://kawam1123.hatenablog.com/entry/2019/08/01/130802)
- WCAID : [2018KAWA05](https://www.worldcubeassociation.org/persons/2018KAWA05)
- 非公式記録のまとめ : [CubePB/kawam1123](https://cubepb.com/user/313384)
- ブログ: [はてなブログ M'](https://kawam1123.hatenablog.com/)
- Twitter : [kawam1123](https://twitter.com/kawam1123)
- Instagram : [kawam1123cuber](https://www.instagram.com/kawam1123cuber)
- Youtube : [kawacube](https://www.youtube.com/channel/UChIJUW9WUwcijE8RYxFBf5A)
- GitHub : [GitHub/kawam1123](https://github.com/kawam1123/)
- Reddit ：[kawam11235](https://www.reddit.com/user/kawam11235)
- Speedsolving.com Forum : [kawam1123](https://www.speedsolving.com/members/kawam1123.48547/)