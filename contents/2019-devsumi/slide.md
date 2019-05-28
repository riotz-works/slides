name: サーバーレスで最高に楽しめるアプリ開発
count: false
class: cover, center, middle
# サーバーレスで最高に楽しめるアプリ開発
.event-logo[[![](assets/logo/devsumi.png)](https://event.shoeisha.jp/devsumi/20190214/)]
.english[
  Application development with serverless is most fun !
]
.footer[[@Developers Summit 2019](https://event.shoeisha.jp/devsumi/20190214/) / 45 min]


---
count: false
class: preface, agenda
### Agenda
1. アイデアを即、形にできる 楽しみ .english[
  Fun to realize ideas as an application immediately
]
2. アプリの開発に専念できる 楽しみ .english[
  Fun to focus on developing applications
]
3. ピタゴラ装置を組み立てる 楽しみ .english[
  Fun to assemble Pythagorean Devices .small[(like the Rube Goldberg machine)]
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

  .resize-h320-box[.resize-w240-h320[![](bio/lulzneko/photo.jpg)] .img-text[lulzneko]]
  .resize-h320-box[.resize-w240-h320[![](bio/lopburny/photo.jpg)] .img-text[lopburny]]
  .resize-h320-box[.resize-w240-h320[![](bio/javaponny/photo.jpg)] .img-text[javaponny]]
]
.footnote[※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。また Riotz.works は 開発チームの名称です。  ]


---
layout: false
### lulzneko .small[(ラルズネコ)] | About us
.ui.grid[
.eleven.wide.column[
  新しい技術を見つけては試すことが大好きで技術を試すためには  
  目的を選ばない、IT好きで葉巻好き酒好きなだけの猫。

  アイデアを高速で形するアーキとして .marker[**サーバーレスが大のお気に入り**]。何かを作る時もサーバーレスでいけるかを最初に考える。

  Vue.js/Nuxt.js は 高速にフロントエンドの開発ができ、  
  .marker[**すごいぜ！ Vue.js/Nuxt.js！！** と 心酔]してる。

  ウェブサービスやアプリ開発だけでなく Raspberry Pi などの電子工作や Slack などのチャットボットなどと、いろいろと手を出す。
]
.four.wide.column[
  .resize-w240[![](bio/lulzneko/photo.jpg)]  
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
## アイデアを即、形にできる 楽しみ .english[
  Fun to realize ideas as an application immediately
]
---
### サーバーレスは、開発を高速に行える
- インフラ環境はクラウドにお任せ

- インスタンスもクラウドにお任せ

- キャパシティも、スケーラビリティも、ログも、~~み～んな~~ クラウドにお任せ

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  ロジック実行 や データ管理 など 使う機能の定義 と コード だけに 集中可能  
  いきなりプロトタイプのコーディングを始めてしまえる  
]

---
### どれほど速いか？ ハッカソンでの事例
- 全国規模のモバイルアプリ開発ハッカソン予選

- テーマは当日発表、24時間で作成のち発表･審査

- １チーム５名編成のところを ３人と少人数参戦  
  (ハッカソン自体も初参加)  

.spajam-slide[![](contents/2018-serverless-conf/images/100.png)]
.spajam-photo-2-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-2[![](contents/2018-serverless-conf/images/102.jpg)]
.spajam-photo-3-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-3[![](contents/2018-serverless-conf/images/103.jpg)]
.spajam-photo-4-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-4[![](contents/2018-serverless-conf/images/104.jpg)]


---
### ３人、24時間 で 作った アプリ「ラップ、タップ、アップ 🎶」
- 競演者２名の動画中継 と 観戦者への同時配信を行う  
  リアルタイムの動画バトル・アプリ

- 観戦者からライブ感あるフィードバックにより、  
  競演者と観戦者が一体となって盛り上がれる演出

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  リアルタイムの動画中継と同時配信を  
  サーバーレスで24時間以内に実現！！  
]

<section class="video">
<div class="frame-container"><iframe src="https://riotz.works/rap-tap-app/" frameborder="0" align="left" style="transform-origin: 0px 0px 0px;"></iframe></div>
</section>

.footnote[
デモ・アプリ は こちら .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]  
※ Android と PC で 動作します(iOS 11, macOS Safari 11 は 制約あり)  
　 *Safariへの対応状況 – SkyWay サポート - .url[`https://bit.ly/2D7wOT0`]*
]


---
### 「ラップ、タップ、アップ 🎶」の サーバーレスなアーキテクチャ
.center[.resize-hx[![](contents/2018-serverless-conf/images/110.png)]]
---
### 「ラップ、タップ、アップ 🎶」の サーバーレスなアーキテクチャ
- スマホ サイド
  - PWA (Progressive Web Apps) による 次世代モバイル アプリ 仕様
  - Nuxt.js、ユニバーサル/SPA/静的サイト な Vue.js アプリ構築のフレームワーク を 利用
  - クラウドへ REST API 呼出し、Firebase の Realtime Database 接続、SkyWay WebRTC 接続

- クラウド サイド
  - サーバーレス で フル マネージド な 構成 を AWS と Firebase で 構築
  - AWS は API Gateway, Lambda, DynamoDB などを利用
  - Firebase は Realtime Database、FCM などを利用

- リアルタイムコミュニケーション
  - SkyWay の サービス を 利用
  - SFU の 利用に より 競演者２名の動画中継 と 観戦者への同時配信を実現


---
### サマリー
- リアルタイムの動画やフィードバックを初めて扱う場合でも、24時間以内に作ることができる  
  （もちろん、ハッカソンという瞬発力が求められる場の力が働いたというのもあるが）

- このアプリ作成の速さ、手軽さは、高速なプロトタイピングはもとより  
  アイデアを即、形にして世に出すことができるということでもる

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  サーバーレスには、アイデアを即、形にする 楽しさ が ある！  
  思いついたら、すぐに作って、どんどん公開して、楽しみましょう♪
]



---
class: center, middle
## アプリの開発に専念できる 楽しみ .english[
  Fun to focus on developing applications
]
---
### サーバーレスは、実行ランタイムを手軽に扱える
- 様々なプログラミング言語の実行ランタイムが用意されている .small[(Java, C#, Python, Node.js, etc...)]

- 実行ランタイムは構成済みで使うランタイムを選択するだけで用意される

- 周辺システムとも統合されている .small[(オートスケール、監視、ログ、etc...)]

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  必要な時に、最適なランタイムを、すぐに使うことができる  
  コードだけに集中して作業を進めてしまえる  
]


---
### どれほど手軽か？ IoT バックエンド開発プロジェクトでの事例
- 数万台/年 で 増える スマートデバイス の IoT バックエンド基盤 .small[(アプリというよりプラットフォーム)]

- 本デバイス向け拡張開発プロジェクト ５名 で 約６ヶ月 .small[(認証等の共通機能は開発済み)]

- 既存 の オンプレ・システム と バッチ連携 および IP 制限 あり の Web API アクセス

.center[.arch[![](contents/2018-agile-and-devopts-study/images/103.png "クラウド連携に必要な仕掛け")]]


---
### ベースとなるシステムのアーキテクチャ
.cloudcraft[
.text[
#### スモールでシンプルなサーバレス構成
- CloudFront / S3 による 認証用 UI の 配信
- API Gateway / Lambda による REST Web API の 提供
- DynamoDB による データ管理

#### 構成の背景
- 元は EC2 + DynamoDB の 構成だった
- AWS Lambda の Java ランタイム の ローンチ を 待って移行
- ユーザーや機器の認証 と メタデータの管理が行える
- EC2 から Lambda へ 移行 約３年後に本 IoT 拡張案件に至る
]


![](contents/2017-serverless-conf/images/architecture-change-to-lambda.png "移行後システムのアーキ図")
]


---
### IoT 向け の エンハンス、そして
.cloudcraft[
.text[
#### エンハンス内容
- マイクロ・サービス型のアーキテクチャとして機能を追加
- ベース が Java なので、**自然と Java で 追加開発**
- **15** 近い マイクロ・システムを構築...

#### 不安要素
- 既存システム連携で 固定IP用 VPC Lambda が 必須
- マイクロ化が過剰で複雑になった

#### そして... ~~伝説へ~~
]
![](contents/2017-serverless-conf/images/enhanced-system.png "エンハンス後システムのアーキ図")
]


---
### 問題 と 原因
.cloudcraft[
.text[
#### 問題
- タイムアウトが多発、サービスとして公開は厳しい 😭

#### 原因
- １シーケンスのチェーンが長い（最大 6 と 5 がある）
- コールドスタート問題に加え、VPC Lambda の 遅延

#### つまり
- 分割しすぎ、パス長すぎ！
- コールドスタート、甘く見すぎ！
]
![](contents/2017-serverless-conf/images/enhanced-system-problem.png "エンハンス後システムのアーキ図 と 原因")
]


---
### 問題 と 原因
.cloudcraft[
.text[
#### 問題
- タイムアウトが多発、サービスとして公開は厳しい 😭

#### 原因
- １シーケンスのチェーンが長い（最大 6 と 5 がある）
- コールドスタート問題に加え、VPC Lambda の 遅延

#### つまり
- 分割しすぎ、パス長すぎ！
- コールドスタート、甘く見すぎ！

.text-large-32[
  **本番投入まで 残り1カ月弱**  
  **どうする😱**  
]
]
![](contents/2017-serverless-conf/images/enhanced-system-problem.png "エンハンス後システムのアーキ図 と 原因")
]


---
### [補足] コールドスタート問題
#### AWS Lambda の コンテナの動き
- AWS Lambda は トリガを受けて処理をするが、利用できるコンテナがない場合は新規に起動する
- 起動したコンテナは再利用されるが、ある程度の時間使われないと破棄される
- 完全にアクセスがなく全く新規の場合と、スケールして新規にコンテナを起動する場合がある

#### コールドスタート
- コンテナが再利用されず、新規のコンテナが割り当てられた状態で起動すること

#### 問題
- ネットワーク、コンテナ、アプリのロード、ランタイムの起動... 処理開始まで時間がかかる

.footnote[
  **参考**  
  　 全部教えます！サーバレスアプリのアンチパターンとチューニング - Taste of Tech Topics  
  　 [`https://d0.awsstatic.com/events/jp/2017/summit/devday/D4T7-2.pdf`](https://d0.awsstatic.com/events/jp/2017/summit/devday/D4T7-2.pdf)
]


---
### AWS Lambda 実行ランタイム(=開発言語) の 変更を決断
.ui.grid[
.eight.wide.column[
#### サーバーレスならイケル
- **サーバーレスの開発は速い！**  
- **サーバーレスのランタイム変更は手軽！**  

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

- コールドスタートの影響が小さい Node.js を 選択
- 開発親和性 と 型安全性 から TypeScript を 導入
- クリティカルパス に 絞って 再実装に注力

　.marker[**実行ランタイムを変えたが、周辺に影響なし**]
]
.seven.wide.column[
.small[
AWS Lambda の 処理時間比較
.resize-h[![](contents/2017-serverless-conf/images/lambda-perf-diff.png)]

AWS Lambda で 高CPU負荷時の処理時間比較
.resize-h[![](contents/2017-serverless-conf/images/lambda-perf-cpu.png)]
]
]
]

.footnote[
  **参考**  
  　 AWS Lambdaの処理性能を言語毎に測ってみた - Taste of Tech Topics  
  　 [`http://acro-engineer.hatenablog.com/entry/2016/08/02/120000`](http://acro-engineer.hatenablog.com/entry/2016/08/02/120000)
]


---
### Java - AWS Lambda の コールドスタート時レスポンスタイム
.cloudcraft[
.text[
.icon[
![](contents/2017-serverless-conf/images/time-yellow.png "Lambda not in VPC") **Lambda (Java) : 7s ~ 10s** ↑  

![](contents/2017-serverless-conf/images/time-red.png "Lambda in VPC") **VPC Lambda (Java) : 17s ~ 20s** ↑
]

呼び出しチェーンの中で 1回でも  
新しい Lambda コンテナの起動に当たったら  
（特にVPC Lambda）
ほぼタイムアウト　
]
![](contents/2017-serverless-conf/images/enhanced-system-improved-response-time-before.png "改善される前")
]


---
### Node.js/TypeScript 移行後
.cloudcraft[
.text[
.icon[
![](contents/2017-serverless-conf/images/time-green.png "Lambda not in VPC") **Lambda (Node.js) : 2s ~ 3s** ↑  

![](contents/2017-serverless-conf/images/time-yellow.png "Lambda in VPC") **VPC Lambda (Node.js) : 10s ~ 13s** ↑
]

VPC Lambda の場合、ある程度  
時間がかかってしまうのは仕方ないが、  
API Gateway のタイムアウトには  
何とか持ちこたえることができる
]
![](contents/2017-serverless-conf/images/enhanced-system-improved-response-time-after.png "改善される後")
]


---
### サマリー
- 実行ランタイム = 開発言語 の 変更でさえ手軽に行うことができる

- 実行ランタイムは構成済みで、周辺システムへの影響はほぼない  
  - 何も変わらない API Gateway, S3, DynamoDB, SNS, CloudWatch, etc...
  - もしインスタンスベースだったら... ミドルウェアは？スケールは？監視は？ 扱える.marker[** 人 **]は？？

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  サーバーレス環境は構成済み＆疎結合、手軽に切替えて使う楽しさがある！  
  必要時に最適なものに切替え、それでも "コードに専念" を 楽しみましょう♪
]




---
class: center, middle
## ピタゴラ装置を組み立てる 楽しみ .english[
  Fun to assemble Pythagorean Devices .small[(like the Rube Goldberg machine)]
]
---
### サーバーレスは、多様な機能と様々なサービスから組み立てられる
- 利用するクラウド内に多様な機能が用意されている  
  .small[(DNS, CDN, Web API, WebSocket, IoT, Function, Database, Queue, Storage, Notification, Mail, Logs, Alert, etc...)]  

- マルチクラウドで、各クラウドの強みや得意を引き出して組み立てられる .small[(AWS, Azure, GCP, Firebase, etc...)]

- サービス(SaaS) 連携することで、さらに様々な機能を組み込める

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  多種多様な機能の組み合わせが、ピタゴラ装置かのような楽しさを生む  
  一見複雑な実装かに感じるが、個々の役割はシンプルで逆にわかりやすい  
]

.footnote[
  ※ ピタゴラ装置、NHK Eテレの番組『ピタゴラスイッチ』に登場するからくり装置 - [Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%94%E3%82%BF%E3%82%B4%E3%83%A9%E8%A3%85%E7%BD%AE)  
  　 NHK アーカイブス - [http://www2.nhk.or.jp/archives/tv60bin/detail/index.cgi?das_id=D0009020048_00000](http://www2.nhk.or.jp/archives/tv60bin/detail/index.cgi?das_id=D0009020048_00000)
]


---
### 「ラップ、タップ、アップ 🎶」 の ピタゴラ装置例 .small[(1/2)]
.center[.img-full[![](contents/2019-devsumi/images/rap-arch-01.png)]]
---
### 「ラップ、タップ、アップ 🎶」 の ピタゴラ装置例 .small[(2/2)]
.center[.img-full[![](contents/2019-devsumi/images/rap-arch-02.png)]]

---
### IoT バックエンド の ピタゴラ装置例 .small[(1/2)]
.center[.img-full[![](contents/2019-devsumi/images/iot-arch-01.png)]]
---
### IoT バックエンド の ピタゴラ装置例 .small[(2/2)]
.center[.img-full[![](contents/2019-devsumi/images/iot-arch-02.png)]]

---
### CI/CD の ピタゴラ装置例 .small[(1/2)]
.center[.img-full[![](contents/2019-devsumi/images/cicd-arch-01.png)]]
---
### CI/CD の ピタゴラ装置例 .small[(2/2)]
.center[.img-full[![](contents/2019-devsumi/images/cicd-arch-02.png)]]



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
- アイデアを即、形にできる 楽しさ  
  ⇒ 圧倒的な速度でアイデアをアプリとして実現できる楽しさがある！  

- アプリの開発に専念できる 楽しさ  
  ⇒ 実行ランタイムを変更してもコードだけに集中できる楽しさがある！  

- ピタゴラ装置を組み立てる 楽しさ  
  ⇒ ひとつのトリガーから機能が次々と処理を流していく楽しさがある！  


---
class: wrapup
### まとめ .english[
  Wrap-up
]
.center[
  .text-large-48[サーバーレスには圧倒的な楽しさがある！]

  ハッカソン や プロトタイピング などの アプリから  
  数万デバイス の IoT 用 サービス ～ バックエンド、  
  サーバーレスで多様なソフトウェアを実現できる。  

  .text-large-36[様々な場面でサーバーレス開発を楽しみましょう😺]
]



---
count: false
class: bottom, center, backcover
## ご清聴いただき ありがとうございました。
.english[
  It's been a pleasure being with all of you today, thank you.
]

![](assets/riotz.png)
.footer[Thank you for contacting [@lulzneko](https://twitter.com/lulzneko) on .fa[.fa-twitter[]]]



---
class: appendix
### Appendix
**本イベント関連記事**
- [デブサミ 2019 にて「サーバーレス開発の楽しさ」について発表をしました](https://riotz.works/articles/2019/02/27/made-presentation-about-enjoyment-of-serverless-at-devsumi-2019-winter/)
- [デブサミ 2019 Ask the Speaker にて頂いた QA まとめ](https://riotz.works/articles/2019/02/18/summary-of-qa-at-ask-the-speaker-of-devsumi-2019-winter/)
- [発表者は、その日何をしていたのか - 発表の舞台裏 DevSumi 2019 編](https://riotz.works/articles/2019/02/15/backstage-of-presentation-at-devsumi-2019-winter/)

**テーマ関連記事**
- [CSV ファイルのバッチ連携も AWS Lambda でサーバーレス](https://riotz.works/articles/2017/12/07/csv-batch-can-also-realized-with-serverless-impl-using-lambda/)
- [API Gateway の WebSocket でチャットを実装 w/Serverless Framework](https://riotz.works/articles/2018/12/22/implement-chat-using-websocket-of-api-gateway-with-serverless-framework/)
- [Serverless Framework と TypeScript でサーバレス開発事始め](https://riotz.works/articles/2018/02/01/beginning-serverless-dev-with-serverless-framework-and-typescript/)
- [Serverless Framework と TypeScript で Hello ＆ Version の Web API を実装](https://riotz.works/articles/2018/02/03/develop-hello-and-version-web-api-with-serverless-framework-and-typescript/)


---
count: false
class: bottom, center, eof
## EOF
![](assets/riotz.png)
