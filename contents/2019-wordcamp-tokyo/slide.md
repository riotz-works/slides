name: WordPress と SSG(Static Site Generator) が織りなす、WordPress ウェブフロントの新世界
count: false
class: cover, center, middle
# WordPress と SSG が 織りなす
# WordPress ウェブフロントの新世界
.event-logo[[![](../assets/logo/wordcamp-tokyo-2019.png)](https://2019.tokyo.wordcamp.org/)]
.english[
  New world of WordPress Web Fronts woven by WordPress and SSG .small[(Static Site Generator)]
]
.footer[[@WordCamp Tokyo 2019](https://2019.tokyo.wordcamp.org/) / 45 min]


---
count: false
class: preface, agenda
### Agenda
1. SSG.small[(Static Side Generator)] の 世界 .english[
  What is SSG
]
2. WordPress ＋ SSG が 生み出す、さらなる新世界 .english[
  A further world created by WordPress + SSG
]
3. WordPress + SSG の 可能性 .english[
  Possibility of WordPress + SSG
]
4. まとめ .english[
  Wrap-up
]



---
class: center, middle
## About us
---
layout: false
### About us
.center[
  .text-large-48[.marker[Riotz.works]], a cheerful engineering team !!

  .resize-h320-box[.resize-w240-h320[![](../bio/lulzneko/photo.jpg)] .img-text[lulzneko]]
  .resize-h320-box[.resize-w240-h320[![](../bio/lopburny/photo.jpg)] .img-text[lopburny]]
  .resize-h320-box[.resize-w240-h320[![](../bio/javaponny/photo.jpg)] .img-text[javaponny]]
]
.footnote[※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。また Riotz.works は 開発チームの名称です。  ]


---
layout: false
### lulzneko .small[(ラルズネコ)] | About us
.ui.grid[
.eleven.wide.column[
  サーバーレスなサーバーサイド・エンジニア。 新しい技術が大好きで  
  試すためには目的を選ばない、IT好きで葉巻好き酒好きなだけの猫。

  アイデアを高速で形するアーキとして .marker[**サーバーレスが大のお気に入り**]。何かを作る時もサーバーレスでいけるか最初に考える。

  またフロントの技術として Vue.js/Nuxt.js の 高速な開発力に、  
  .marker[**すごいぜ Vue.js/Nuxt.js！！**] と、.marker[**JAMStack なフロントに興味津々**]。

  ウェブサービスやアプリ開発だけでなく Raspberry Pi などの電子工作や Slack などのチャットボットなどと、いろいろと手を出す。
]
.four.wide.column[
  .resize-w240[![](../bio/lulzneko/photo.jpg)]  
  .social[.fa[.fa-github[]] [@lulzneko](https://github.com/lulzneko)]  
  .social[.fa[.fa-twitter[]] [@lulzneko](https://twitter.com/lulzneko)]  
  .mail[.fa[.fa-envelope-o[]] lulzneko&#x40;riotz.works]  
]

.footnote[
  ※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
  　 また Riotz.works は 開発チームの名称です。  
]]



---
class: center, middle
## SSG.small[(Static Side Generator)] = JAMStack の 世界 .english[
  What is SSG, is the world of JAMStack
]
---
### SSG とは
- 静的サイトを生成するためのツール
- ウェブサイトをあらかじめ HTML 化し CDN から配信する
- GatsbyJS などが有名
※ 動的要素は Web API から JSON などを受け取り、JavaScript で描画

**SSG ではないケース**
- ブラウザ化のアクセス時に HTML を生成する、サーバーサイドレンダリング(SSR)
- HTML テンプレートなどもサーバーサイドレンダリング
- PHP も 同様 で、WordPress も SSG ではない


---
### SSG の メリット
- HTML 生成の処理が不要で、CDN がフル活用できる、高パフォーマンス

- HTML だけの配信、HTML 生成のオンフライン化、CDN による、セキュリティの確保

- データ と マークアップ の分離による、開発者の責任分担明確化

⇒ これらのメリットを享受できる環境を JAMStack とい


---
### JAMStack とは
- 最近、ウェブフロント界隈で話題になりつつあるキーワード

- JAMStack Conf が ニューヨーク、ロンドン、サンフランシスコで開催


---
class: center, middle
## WordPress ＋ SSG が 生み出す、さらなる新世界 .english[
  A further world created by WordPress + SSG
]
---
### WordPress と SSG を組み合わせる
- WordPress の REST API 経由で SSG と連携できる

- GatsbyJS, Gridsome などは Plugin で直接利用可能

- Nuxt.js などは HTTP Client 経由で利用可能


---
### WordPress ＋ SSG のメリット
- WordPress の エディターとコンテンツ管理が活かせる

- ウェブフロント を JAMStack にしてメリットを享受できる

- Headless CMS の 流れにマッチする


---
class: center, middle
## WordPress + SSG の 可能性 .english[
  Possibility of WordPress + SSG
]
---
### 作成中...



---
class: center, middle
## まとめ .english[
  Wrap-up
]
---
class: wrapup
### まとめ .english[
  Wrap-up
]
- **SSG = JAMStack なサイトはメリットが大きい**  

- **WordPress を Headless CMS として使い、JAMStack のメリットを享受**  

- **.marker[Headless WordPress + SSG/JAMStack の 世界(= 市場) 創出へ]**  



---
count: false
class: bottom, center, backcover
## ご清聴いただき ありがとうございました。
.english[
  It's been a pleasure being with all of you today, thank you.
]

![](../assets/riotz.png)
.footer[Thank you for contacting [@lulzneko](https://twitter.com/lulzneko) on .fa[.fa-twitter[]]]



---
count: false
class: bottom, center, eof
## EOF
![](../assets/riotz.png)
