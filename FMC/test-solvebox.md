---
title: solveboxtest
---

## ソルブ表示ボックスを作成する

{% capture display_text %}
これは表示テキストです。<br/>
これは表示テキストの二行目です。<br/>
三行目です。
{% endcapture %}

{% include solvebox.html
text = display_text
img_src="../assets/img/2C2E.png"%}

## 結果を確認する