# 即売会の作り方

## 概要説明
技書博発の「即売会の作り方」です。

技術同人誌の即売会を念頭に、オフラインの同人誌即売会を開催するためのノウハウをまとめます。

## この本の目的

最近ますます盛り上がっている技術同人誌界隈ですが、オンリーイベントはそう多くありません。
そして、技術同人誌というジャンルでは、オールジャンルな感じではありますが、
イベント開催ノウハウとして整理してみたいと考えました。

事務局としては、各スタッフ業務がコアスタッフにきわめて属人化しています。
万一、業務都合などでそのスタッフがコミットできなくなったとき、その業務が滞ることになります。
それは、イベントの持続性として問題がありますので、ノウハウ共有のため、テキスト化することにしました。

もちろん同人イベントという、非常にノウハウの必要な業務であることは異論を待ちませんが、
それでも、それをテキスト化するというチャレンジングな活動を行うことで、
スタッフ、関係者各人が持つノウハウを、体系的に整理することができるでしょう。

## 執筆にあたってのお願い

原稿を書いたら、/src/に格納するとともに、/src/catalog.ymlにそのファイル名を記載ください。
catalog,ymlに書かないと、コンパイルされません。

CIでコンパイルが通ることを確認してください。エラーのまま放置はなるべくやめてください。

Confrictが発生した場合は、解決お願いします。

push -f等はやめましょう。（歴史を書き換えてはいけません。

相談事：
Issue立ててください。

## Re:VIEWの書き方

[Re:VIEWチートシート](https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838) を作ってみたので、参考にしてみてください。

## CI
https://app.wercker.com/oyakata2438/howtoSokubaikai/runs/
でPDFが書きだされます。
一番上のBuildをクリックすると展開されるので、
Output Artifactをクリックして、Download artifactをクリックすると、
tarで固めたpdfがダウンロードできます。

## インストール

細かい準備(TeX入れたり)は[『技術書をかこう！』](https://github.com/TechBooster/C89-FirstStepReVIEW-v2)に準じます。

### WindowsでReviewを使う方法

https://qiita.com/implicit_none/items/398c6e0bbedc8b160621
暗黙の型宣言さんが詳しく書いてくれてます。あるいは、技術同人誌を書こう‐アウトプットのススメ‐をご覧ください。

### Dockerを使う方法

Dockerを使うのが一番手軽です。

```sh
docker run --rm -v $PWD/src:/work vvakame/review:3.2 /bin/sh -c "cd /work && review-pdfmaker config-ebook.yml"
```

### Docker使わずビルド

```sh
$ npm install; npm run build
```

### 権利

ベースには、[TechBooster/ReVIEW\-Template: TechBoosterで利用しているRe:VIEWのテンプレート（B5/A5/電子書籍）](https://github.com/TechBooster/ReVIEW-Template) を使っています。

  * 設定ファイル、テンプレートなど制作環境（techbooster-doujin.styなど）はMITライセンスです
    * 再配布などMITライセンスで定める範囲で権利者表記をおねがいします。
