name: リアルタイム動画ラップ バトル アプリを短時間で作り上げた完全サーバーレスな秘技
count: false
class: cover, center, middle
# リアルタイム動画ラップ バトル アプリを
# 短時間で作り上げた完全サーバーレスな秘技
.english[
  Serverless tricks which real-time video rap battle application was built in a short time
]
.footer[@Serverlessconf Tokyo 2018 / 40 min<br> Slides are posted on .url[[`https://bit.ly/2Dx2frQ`](https://bit.ly/2Dx2frQ)]<br> Demo application is here .url[[`https://bit.ly/2DFL9Ie`](https://bit.ly/2DFL9Ie)]]


---
count: false
class: preface, agenda
.ratio48-9-center[
### Agenda
1. 導入 .english[
  Introduction
]
2. スマホ サイド の PWA アプリ 秘技 .english[
  PWA application tricks on Smartphone side
]
3. クラウド サイド の Web API 秘技 .english[
  Web API/Notification tricks on Cloud side
]
4. PWA アプリ と プレゼン スライド の CI/CD 秘技 .english[
  CI/CD tricks of PWA application and Presentation slide
]
5. まとめ .english[
  Wrap-up
]
]
.footer[Slides are posted on .url[[`https://bit.ly/2Dx2frQ`](https://bit.ly/2Dx2frQ)]<br> Demo application is here .url[[`https://bit.ly/2DFL9Ie`](https://bit.ly/2DFL9Ie)]]



---
class: center, middle
## About us
---
layout: false
.ratio48-9-center[
### About us
.center[
  .resize-h320-box[.resize-w240-h320[![](bio/lulzneko/photo.jpg)] .img-text[lulzneko]]
  .resize-h320-box[.resize-w240-h320[![](bio/lopburny/photo.jpg)] .img-text[lopburny]]
  .resize-h320-box[.resize-w240-h320[![](bio/javaponny/photo.jpg)] .img-text[javaponny]]
]
.footnote[※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。また Riotz Works は 開発チームの名称です。  ]
]


---
class: center, middle
## 導入 .english[
  Introduction
]
---
layout: false
.ratio48-9-center[
### lulzneko a.k.a ジャイアンの歌声 | About us
.ui.grid[
.eleven.wide.column[
  新しい技術を見つけては試すことが大好きで技術を試すためには目的を選ばない、IT好きで葉巻好き酒好きなだけの猫。

  サーバレスはアイデアを素早く形にできるアーキテクチャとして大のお気に入り。何かを作る時もサーバーレスでいけるかを最初に考える。

  ウェブサービスやアプリの開発だけでなく Raspberry Pi などの電子工作や Slack などのチャットボットなどと、いろいろと手を出す。
]
.four.wide.column[
  .resize-w240[![](bio/lulzneko/photo.jpg)]  
  .social[.fa[.fa-github[]] [@lulzneko](https://github.com/lulzneko)]  
  .social[.fa[.fa-twitter[]] [@lulzneko](https://twitter.com/lulzneko)]  
]
]

.footnote[
  ※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
  　 また Riotz Works は 開発チームの名称です。  
]
]


---
.ratio48-9-left[
### アプリ「ラップ、タップ、アップ 🎶」概要
- アプリ概要
  - ハッカソン制作作品
  - 競演者２名の動画中継 と 観戦者への同時配信を行う リアルタイム動画バトルアプリ
  - 観戦者からのライブ感あるフィードバックにより、競演者 と 観戦者 が 一体となって盛り上がれる

- 参加したハッカソン
  - 全国規模のモバイルアプリ開発ハッカソン予選
  - テーマは当日発表で 約 24 時間での作成時間のち発表･審査
  - Riotz は ハッカソン自体初参加、１チーム５名編成のところを ３人と少人数参戦  
  ⇒ **サーバーレスは最強の武器、サーバーレス ファースト で どこまでできるのか への 挑戦！**

.footnote[
デモ・アプリ は こちら .url[[`https://bit.ly/2DFL9Ie`](https://bit.ly/2DFL9Ie)]  
※ 本アプリは Android と PC で 動作します (iOS 11 および macOS の Safari 11 は 未対応)  
　 https://support.skyway.io/hc/ja/articles/115012750968-Safari%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C%E7%8A%B6%E6%B3%81
]
]
.ratio48-9-right[
  .spajam-slide[![](contents/2018-serverless-conf/images/100.png)]
  .spajam-photo-2-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-2[![](contents/2018-serverless-conf/images/102.jpg)]
  .spajam-photo-3-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-3[![](contents/2018-serverless-conf/images/103.jpg)]
  .spajam-photo-4-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-4[![](contents/2018-serverless-conf/images/104.jpg)]
]


---
.ratio48-9-left[
### 「ラップ、タップ、アップ 🎶」の アーキテクチャ
- スマホ サイド
  - PWA (Progressive Web Apps) による 次世代モバイル アプリ 仕様
  - Nuxt.js、ユニバーサル/SPA/静的サイト な Vue.js アプリ構築のフレームワーク を 利用
  - クラウドへは REST API 呼び出し、Firebase の Realtime Database 接続、SkyWay(WebRTC) 接続

- クラウド サイド
  - サーバーレス で フル マネージド な 構成 を AWS と Firebase で 構築
  - AWS は API Gateway, Lambda, DynamoDB などを利用
  - Firebase は Realtime Database、FCM などを利用

- リアルタイムコミュニケーション
  - SkyWay の サービス を 利用
  - SFU の 利用に より 競演者２名の動画中継 と 観戦者への同時配信を実現
]
.ratio48-9-right[
  .center[.resize-h620[![](contents/2018-serverless-conf/images/110.png)]]
]



---
class: center, middle
## スマホ サイド の PWA アプリ 秘技<br/> ~PWA(Progressive Web Apps), Vue.js/Nuxt.js~ .english[
  PWA application tricks on Smartphone side
]
---
layout: false
.ratio48-9-center[
### lopburny | About us
.ui.grid[
.eleven.wide.column[
  学生時代、スタートアップでのウェブサイト制作を始め、  
  現在はフロントエンド・バックエンドを問わずウェブアプリケーションの設計・開発に従事している。

  大好きなのは、IT技術と酒とロックミュージック。  
  仕事もプライベートも、一所懸命ロックンロールしたいと思っている、ウェブエンジニア。
]
.four.wide.column[
  .resize-w240[![](bio/lopburny/photo.jpg)]  
  .resize-w120[![](bio/certs/aws-solutions-architect-professional-badge.png)]  
  .social[.fa[.fa-github[]] [@lopburny](https://github.com/lopburny)]  
  .social[.fa[.fa-twitter[]] [@lopburny](https://twitter.com/lopburny)]  
]
]

.footnote[
※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
　 また Riotz Works は 開発チームの名称です。  
]
]


---
.ratio48-9-left[
### どんなアプリを作ったの?

#### バトルを募集する
対戦ルームが作られ、対戦者向けの画面と観戦者向けの画面へ飛べるリンクが発行される

#### バトルを呼びかける
対戦者／観戦者向けのリンクを共有

#### バトルをする・バトルを見る（リアルタイム）
- （対戦モード）対戦ルームへ入場、STARTボタンを押して、相手が入場したら、対戦開始
- （観戦モード）観戦ルームへ入場、対戦者が揃ったら、観戦開始

#### フィードバックを見る・フィードバックを送る（リアルタイム）
観戦者からグッドボタン、バッドボタン、チャットによるリアルタイムのフィードバックをもらう
]
.ratio48-9-right[
]


---
.ratio48-9-left[
### アプリの構成とポイント
<br>
.center[
## PWA(Progressive Web Apps)
## Nuxt.js / Vue.js / SPA

## WebRTC Service (SkyWay)
## Firebase Realtime Database
]

]
.ratio48-9-right[

]


---
.ratio48-9-left[
### PWA (Progressive Web Apps) / SPA with Nuxt.js
PWA
  - ウェブアプリでモバイルアプリのようなUI/UXを提供できる仕組み
  - Service Worker によるコンテンツのキャッシュ、オフラインでの表示が可能
  - Android端末であれば Push通知、Bluetooth、位置情報等が使える
  
Nuxt.js
  - 最近流行りの(?) Vue.js フレームワーク
  - Vue.js アプリケーションを開発する上で必要な各種設定、PWA対応が盛り込まれている
  - 開発環境セットアップが非常に簡単
  

.center[
  ** PWA + Nuxt.js の他にも PWA + React / React Native / Xamarin など、選択肢はいくつもある **

  **「リアルタイム」と「サーバーレス」そして「短時間」**

]

]
.ratio48-9-right[

]

---
.ratio48-9-left[
### WebRTCによるリアルタイム通信

WebRTC(Web Real-Time Communication)
 - ブラウザ間で音声、映像、データをリアルタイム送受信する仕様
 - P2P通信が基本だが、SFU (Selective Forwarding Unit、サーバー経由で配信する仕組み）によって、端末やネットワーク負荷を抑えつつ、多人数への配信が可能

SkyWay
 - 製品化された WebRTC サービス
 - WebRTC(SFU)に必要なサーバーを運用・構築することなく、Community Edition なら無料で利用できる
 - iOS/Android/JavaScript SDK が提供されており、導入が用意
  

.center[
  ** 動画、音声コンテンツの「サーバーレス」なリアルタイム送受信を「短時間」で構築 **
]
]
.ratio48-9-right[

]

---
.ratio48-9-left[
### Firebase Realtime Database によるリアルタイムなデータ同期
Firebase
  - サーバーレスなモバイル (＋ウェブ) アプリ開発にフィットする、Googleの統合プラットフォーム
  - 認証、ストレージ、ホスティング、データ同期、FaaS、分析等、幅広くサーバーレスで実現可能

Realtime Database
  - リアルタイムでデータを保管、同期できる NoSQL データベース
  - 導入・運用が用意、オフライン対応、トランザクション機能もあり便利

※ ラップ・タップ・アップでは、ユーザーとpeer情報の紐づけ・ルームデータ同期・チャット・フィードバック機能に活用

※ AWS IoT MQTT over WebSocket, AppSync 等、同じことを実現する方法はいくつもあるが、スピード・シンプルさ・モバイル最適化という点で優れている Realtime Databse を採用

]
.ratio48-9-right[

]

---
class: center, middle
## クラウド サイド の Web API 秘技<br/> ~AWS Lambda, SNS, DynamoDB ~ .english[
  Web API/Notification tricks on Cloud side
]
---
layout: false
.ratio48-9-center[
### javaponny | About us
.ui.grid[
.eleven.wide.column[
  ビールをこよなく愛するエンジニア。  

  インフラエンジニアとしてキャリアをスタートしたが、サーバーレスの魅力に惹かれ、アプリケーションエンジニアに転身。  

  現在はウェブアプリケーションのバックエンド開発に従事し、最近はフロントエンドに興味を持ち始め勉強中。  
]
.four.wide.column[
  .resize-w240-fit[![](bio/javaponny/photo.jpg)]  
  .resize-w120[![](bio/certs/aws-devops-professional-badge.png)]
  .resize-w120[![](bio/certs/aws-solutions-architect-professional-badge.png)]  
  .social[.fa[.fa-github[]] [@javaponny](https://github.com/javaponny)]  
  .social[.fa[.fa-twitter[]] [@javaponny](https://twitter.com/javaponny)]  
]
]

.footnote[
※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
　 また Riotz Works は 開発チームの名称です。  
]
]


---
.ratio48-9-left[
### WebAPI機能

#### 対戦ルーム作成
対戦ルームのID発行
#### 対戦者登録
- 対戦したい人が対戦ルームに入場する
- DBに対戦者を登録

#### 対戦ルーム取得
対戦・観戦ルームに入場する情報を取得する
#### 対戦ルーム一覧取得
対戦できる部屋、観戦できる部屋を確認できる

]
.ratio48-9-right[

]



---
.ratio48-9-left[
.cloudcraft[
### WebAPIの構成とポイント
#### 構成
- API Gateway
- Lambda
- DynamoDB
- よくあるシンプル構成

#### 短時間で作り上げたポイント
- __TypeScript__
- __dynamodb-data-mapper__
- __serverless framework__
![](contents/2018-serverless-conf/images/300.png)

]
]
.ratio48-9-right[
]

---
.ratio48-9-left[
### TypeScriptによる高速・安全なアプリケーション開発
## TypeScript
- JavaScriptながら、強力な静的型付けができる
  - 実行して初めて気が付くミスやバグ、ライブラリが返す型が分かりやすい
  - エディタ・IDEによる入力補完、リファクタリングができる
  - スクリプト言語のため、Lambdaコールドスタートでも起動が早い！

- 最新のJavaScript言語仕様を先取りして使える
  - Decorators構文、for-await-of構文... etc


]
.ratio48-9-right[
]


---
.ratio48-9-left[
### DynamoDB Data Mapper
- 定義したクラスをDyanmoDBテーブルにマッピング
- Java DynamoDB Mapperライクにモデル定義が可能
- 新しいJavaScriptの構文に合わせている
 - Decorators、for-await-of構文...
 - TypeScriptなら使える！
  
 .ui.grid[
 .eight.wide.column[
 <pre class="prettyprint"><code class="language-typescript">
 @table('table_name')
 class MyClass {
     @hashKey()
     id: string;

     @rangeKey({defaultProvider: () => new Date()})
     createdAt: Date;
 
     @attribute()
     completed?: boolean;
 }
 </code></pre>
 ]
 .seven.wide.column[
 <pre class="prettyprint"><code class="language-typescript">
 const iterator = mapper.query(MyClass, { 
       partitionKey: 'foo',
       rangeKey: between(0, 10)
       });
 for await (const record of iterator) {
     console.log(record, iterator.count,
      iterator.scannedCount);
 }
 </code></pre>
 ]
 ]

]

.ratio48-9-right[

]


---
.ratio48-9-left[
### と思っていたのに...
<img src="contents/2018-serverless-conf/images/301.png"　width="300" height="300" />
- tsconfig esnext.asynciterableも入れたのに…。
- 時間の制約上ここばかりに時間をかけられないため、queryは泣く泣くDynamoDB DocumentClientを使うことに
- とはいえ他の操作についてはクラスのマッピングなどは助けられた
]

.ratio48-9-right[

]


---
.ratio48-9-left[
### serverless framework

#### serverless frameworkで速攻Deploy
- コードを書いたら即Deploy
- すぐにAWS上で検証可能
- 何回やっても同じ環境にDeployされる
- 時間制限のあるアプリケーション開発では特に有効！

.center[
## TypeScript×serverless frameworkで
##   高速・安全なWebAPI開発！
]
]

.ratio48-9-right[

]



---
class: center, middle
## PWA アプリ と プレゼン スライド の CI/CD 秘技<br/> ~GitHub, CircleCI, GitHub Pages~ .english[
  CI/CD tricks of PWA application and Presentation slide
]
---
.ratio48-9-left[
### PWA アプリ の CI/CD の 構成
- GitHub + CircleCI の 一般的な構成

- PWA アプリ は Web アプリ と 変わらないので特別な仕掛けは不要

- ホスティング は GitLab Pages を 使用
  - プロダクション として スケール させるなら S3 に 置いて CloudFront
  - 今回は SPA の 静的ホスティング だが、Nuxt.js ＋ Lambda で SSR も 可能

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.center[.text-large[
実はなんてことないけど、なんてことないことでモバイルアプリが作れ  
CI/CD が 簡単に回ることが PWA アプリ の 強味  
モバイルアプリなのに常時アクセス可能にでき、CircleCI のArtifact
]]
]
.ratio48-9-right[
  .right-image-full[![](contents/2018-serverless-conf/images/400.png)]
]


---
.ratio48-9-left[
### プレゼン スライド と CI/CD
- この プレゼン スライド、実は Web アプリ
  - remark.js を 使っている (次の Google Chrome で 動かなくなるかも💦)
  - GitPitch、reveal.js と 同種の技術
  - ブラウザの印刷から PDF 出力することで通常 の プレゼン スライド としても利用可能

- スライド コンテンツ は Markdown で 記述
  - 表現力は落ちるが、逆にあきらめがつく
  - 頑張りたい場合は CSS で 補強可能

- Web アプリ なので GitHub で 管理、CircleCI で Pages へ デプロイ
  - スライドのバージョン管理ができる
  - 複数人で作業する場合も Git の マージ でできる
]
.ratio48-9-right[
  .right-image-full[![](contents/2018-serverless-conf/images/401.png)]
]


---
.ratio48-9-left[
### プレゼン スライド と CI/CD
- この プレゼン スライド、実は Web アプリ
  - remark.js を 使っている (次の Google Chrome で 動かなくなるかも💦)
  - GitPitch、reveal.js と 同種の技術
  - ブラウザの印刷から PDF 出力することで通常 の プレゼン スライド としても利用可能

- スライド コンテンツ は Markdown で 記述
  - 表現力は落ちるが、逆にあきらめがつく
  - 頑張りたい場合は CSS で 補強可能

- Web アプリ なので GitHub で 管理、CircleCI で Pages へ デプロイ
  - スライドのバージョン管理ができる
  - 複数人で作業する場合も Git の マージ でできる
]
.ratio48-9-right[
  .right-image-full[![](contents/2018-serverless-conf/images/402.png)]
]


---
.ratio48-9-left[
### PWA アプリ と プレゼン スライド アプリ
- Web アプリ である PWA と プレゼン スライド を  
  　　組み合わせることで、プレゼンの中にデモを組み込むことができる！

- モバイル アプリ の デモを カメラ や エミュレーターなしで簡単に実現
```html
<iframe
　　src="https://riotz.github.io/rap-tap-app/"
　　frameborder="0"
　　align="left"
　　style="transform-origin: 0px 0px 0px;"></iframe>
```
]
.ratio48-9-right[
  .right-image-full2[![](contents/2018-serverless-conf/images/403.png)]
]



---
class: center, middle
## まとめ .english[
  Wrap-up
]
---
class: wrapup
.ratio48-9-center[
### まとめ .english[
  Wrap-up
]]
.ratio48-9-center[
- **サーバーレスはアプリ開発者にとって最強の武器のひとつ**

- ハッカソンで体験したように、思いをすぐに形にできる

- 創りたいものに集中することで、より良いサービスやイノベーションが生まれる
]


---
class: wrapup
.ratio48-9-center[
### まとめ .english[
  Wrap-up
]]
.ratio48-9-center[
- **サーバーレスはアプリ開発者にとって最強の武器のひとつ**

- ハッカソンで体験したように、思いをすぐに形にできる

- 創りたいものに集中することで、より良いサービスやイノベーションが生まれる


.note[.wrapup-note[
ハッカソン中のアイデアで競演者に投げ銭できる機能を取り入れたかった。  
暗号通貨/仮想通貨 を 取り込みたかった が、さすがに作り切れなかった。。。  
]]
]


---
class: wrapup
.ratio48-9-center[
### まとめ .english[
  Wrap-up
]]
.ratio48-9-center[
- **サーバーレスはアプリ開発者にとって最強の武器のひとつ**

- ハッカソンで体験したように、思いをすぐに形にできる

- 創りたいものに集中することで、より良いサービスやイノベーションが生まれる


.note[.wrapup-note[
ハッカソン中のアイデアで競演者に投げ銭できる機能を取り入れたかった。  
暗号通貨/仮想通貨 を 取り込みたかった が、さすがに作り切れなかった。。。  
⇒ Next Session 「ブロックチェーン と フルサーバレスでのシステム構築」
]]
]


---
count: false
class: bottom, center, backcover
.ratio48-9-center[
## ご清聴いただき ありがとうございました。
.english[
  It's been a pleasure being with all of you today, thank you.
]

![](assets/riotz.png)
.footer[
  Slides are posted on .url[[`https://bit.ly/2Dx2frQ`](https://bit.ly/2Dx2frQ)]  
  Thank you for contacting [@lulzneko](https://twitter.com/lulzneko), [@lopburny](https://twitter.com/lopburny), [@javaponny](https://twitter.com/javaponny) on .fa[.fa-twitter[]]  
]
]
