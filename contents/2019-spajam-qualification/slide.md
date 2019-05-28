name: パーソナルニュースの配信と交換によって爆速で仲良くなるアプリ「📰NEWʑ Link」
count: false
class: cover, center, middle
# パーソナルニュースの配信と交換によって
# 爆速で仲良くなるアプリ「.marker[📰NEWʑ Link]」
.event-logo[[![](assets/logo/spajam.png)](https://spajam.jp/2019/entry/tokyo-a/)]
.footer[[@SPAJAM 2019 東京A予選 gumi](https://spajam.jp/2019/entry/tokyo-a/) / 8 min]


---
### SPAJAMテーマ と 作成アプリのコンセプト
#### SPAJAM テーマ： 「.marker[NEWS]」
----
#### アプリ作成 の 背景 と コンセプト
- ニュースとは、情報を通じて人々の**心を動かし**、**アクションにつなげる**ために配信するもの
- ニュースのソースは、ネットによりマスメディアから個人へ、**一億総メディア時代**
- 個人によるニュース配信には、マスメディア、ネットメディアと異なる機能があるはず
.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]
.center[.text-large[
  ** 個人がニュースを発信(配信) したくなり **  
  ** より明るく楽しくなれる話題で、みんな の 心を動かし **  
  ** たくさんの「うれしい」「ありがとう」を つなげていきたい！！ **  
]]

---
### 個人発信 の 嬉しいニュース 楽しいニュース は たくさん！
.center[.resize-w100p[![](contents/2019-spajam-qualification/images/01.png)]]
.center[.text-large[
  ** よいニュースが広がることで、よい心の動きへ **  
  ** お互いの よいニュースを知ることで、共感を！ **  
  ** 共感することで、より親密に！！ **
]]


---
### それを実現します「📰NEWʑ Link .small[(ニューズ リンク)]」！！
.center[
.resize-h320a[![](contents/2019-spajam-qualification/images/02.png)]
.resize-h320a[![](contents/2019-spajam-qualification/images/03.png)]
.resize-h320a[![](contents/2019-spajam-qualification/images/04.png)]
.resize-h320a[![](contents/2019-spajam-qualification/images/05.png)]
]


---
class: center, middle
## “デモンストレーション” .english[
  Enjoying our short story
]


---
### 「📰NEWʑ Link」機能概要
#### コンセプト： パーソナルニュースの配信と交換によって 爆速で仲良くなる アプリ  
　  
**主な機能**
- 個人のニュースをサマリー、通称 ".marker[オレオレ Times]" を生成 (ネガティブ・フィルター搭載！)
- 相手の良いニュースへ Like フィードバック、さらには **".marker[Amazon 欲しいもの" でお祝い！]** 
- "オレオレ Times" を **QR コードで交換**し共通の話題を即時に生成、  
　通称 ".marker[号外 ずっとも速報]" による共感から、親密さアップ **.marker[爆速で仲良く]**！ 

**今後の展望**
- ニュースソースを Twitter/Facebook 他、拡大と専用のポスト画面作成 (e.g. フォトフレ・カメラ)
- スマートスピーカーによる、通称 "号外 ずっとも速報" の生成と読み上げ
- マネタイズ (e.g. 投げ銭等による少額チップ、メーカー/セラー提携カスタマイズ商品によるお祝い)


---
### 「📰NEWʑ Link」システム概要
#### コンセプト： パーソナルニュースの配信と交換によって 爆速で仲良くなる アプリ  
　  
**アーキテクチャ**
- クライアント: **.marker[PWA (Progressive Web Apps)]** アーキテクチャ による 次世代アプリ仕様！！
- サーバサイド: **.marker[サーバーレス]** アーキテクチャ による 運用レス な 環境での実行  
昨年の予選アプリも元気にサーバレスで稼働中！ https://riotz.works/rap-tap-app/

**主な利用 技術/サービス**
- 実装言語は、クライアント HTML/CSS/JavaScript、サーバサイド TypeScript(= JavaScript)
- サーバサイドの実行環境は、AWS で API Gateway, Lambda, DynamoDB, DynamoDB Streams
- ~~.marker[マッチングの処理はサーバー内の形態素解析] (Google Cloud Natural Language API は課金が💦 )~~


---
count: false
class: center, backcover
## ご盛況いただき ありがとうございます。
.english[
  .marker[このあと 📰NEWʑ Link で、爆速で仲良くなってください！！]
]

.resize-h320-box[.resize-h320[![](bio/lulzneko/photo.jpg)] .img-text[lulzneko]]
.resize-h320-box[.resize-h320[![](bio/lopburny/photo.jpg)] .img-text[lopburny]]

.small[※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。また Riotz.works は 開発チームの名称です。  ]

.footer[
  Thank you for contacting [@lulzneko](https://twitter.com/lulzneko), [@lopburny](https://twitter.com/lopburny) on .fa[.fa-twitter[]]
]



---
class: appendix
### Appendix
**本イベント関連記事**
- [SPAJAM 2019 東京A予選 - ハッカソン戦記](https://riotz.works/articles/2019/05/20/spajam-2019-tokyo-a-pre-hackathon-chronicle/)

**テーマ関連記事**
- [CTO vs Hackers ハッカソン戦記](https://riotz.works/articles/2019/03/10/cto-vs-hackers-hackathon-chronicle/)


---
count: false
class: bottom, center, eof
## EOF
![](assets/riotz.png)
