﻿# smorking
喫煙所紹介サイト

コンセプト
タバコのポイ捨てを削減、旅行者に対して喫煙所がある喫茶店などを紹介して喫煙者にやさしいwebサイトを目指す。
最終的な目的は、店舗の掲載や広告から収益を取る事。

Express Generator というフレームワークを使えば少しは楽に開発できましたが、勉強の一環としてNode.jsで作成しました。
入力された住所から、位置情報を取得するのに使用したのは、https://www.geocoding.jp/のサイトにクエリデータを送信して
スクレイピングで取得するようにしました。APIを使えばシンプルに取得できますが、去年から料金がかかるようになったので
このような手段を取りました。
Node.jsはいちいちファイルのパスの指定を書かなければいけないのでかなり手間でした。

スクレイピングで使用したモジュール
cheerio-httpcli

client.fetch("https://www.geocoding.jp/", { q: word }, function （）｛
    lat = $("span[class=latlng]")
      .text()
      .split(" ", 2)[1];
    lng = $("span[class=latlng] b:nth-child(2)").text();
｝

urlを指定して、jQueryで値を選別して取得しています。
動的なページでなければ、簡単に取得できます。
jQueryの構造を最初理解してなかったのでくせんしました。

検索してもでで検索結果には表示されなかったので、GoogleにSearch Console	(site:　検索)を使いサイトを登録

のちに、スマホ版に対応するようにさせました。

メタタグを追加

googleアナリティクスや　search consoleなどでサイトも訪問者の数を確認しましたが、
ドメインパワーが足りず、競合サイトより情報が少ないので検索件数は伸びませんでした。
地図だけでなく写真をつけて差別化を図ろうと思ってます。（現在は松江のみ）

課題
ｘｍｌでサイトマップの作成の方法を勉強しなければならない
