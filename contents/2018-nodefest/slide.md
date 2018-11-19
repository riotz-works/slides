name: Vue.js/Nuxt.js で 実現できた PWA の リアルタイム動画ラップ・バトル・アプリ
count: false
class: cover, center, middle
# Vue.js/Nuxt.js と TypeScript で 実現する
# PWAなリアルタイム動画ラップバトルアプリ
.english[
  A Mobile PWA of real-time video streaming for freestyle rap battle app, **powered by Vue.js/Nuxt.js & TypeScript**
]

.subtitle[～ フル Node.js エコシステム で 戦った モバイルアプリのハッカソン～]

.footer[@東京Node学園祭2018 / 30 min<br> Slides are posted on .url[[`https://bit.ly/2ORPubz`](https://bit.ly/2ORPubz)]<br> Demo application is here .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]]


---
count: false
class: preface, agenda
### Agenda
1. 導入 .english[
  Introduction
]
2. Vue.js/Nuxt.js で開発するスマホ向け PWA アプリ .english[
  Dive into PWA development for smartphone with Vue.js/Nuxt.js
]
3. サーバーレス Web API w/AWS Lambda + TypeScript  .english[
  Serverless Web API developed with AWS Lambda + TypeScript
]
4. Vue.js/Nuxt.js PWA と プレゼン スライド の CI/CD .english[
  CI/CD tricks of Vue.js/Nuxt.js PWA and Presentation slide
]
5. まとめ .english[
  Wrap-up
]
.footer[Slides are posted on .url[[`https://bit.ly/2ORPubz`](https://bit.ly/2ORPubz)]<br> Demo application is here .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]]



---
class: center, middle
## About us
---
layout: false
### About us
.center[
  .text-large-48[.marker[Riotz Works]], a cheerful engineering team !!  
  〝サーバーレス は アプリ開発者 に とって最強の武器″ を 標榜するエンジニア集団

  .resize-h320-box[.resize-w240-h320[![](bio/lulzneko/photo.jpg)] .img-text[lulzneko]]
  .resize-h320-box[.resize-w240-h320[![](bio/lopburny/photo.jpg)] .img-text[lopburny]]
  .resize-h320-box[.resize-w240-h320[![](bio/javaponny/photo.jpg)] .img-text[javaponny]]
]
.footnote[※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。また Riotz Works は 開発チームの名称です。  ]


---
class: center, middle
## 導入 .english[
  Introduction
]
---
layout: false
### lulzneko .small[*a.k.a ジャイアンの歌声*] | About us
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
]

.footnote[
  ※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
  　 また Riotz Works は 開発チームの名称です。  
]]


---
### アプリ「ラップ、タップ、アップ 🎶」概要
- ハッカソン制作作品

- 競演者２名の動画中継 と 観戦者への同時配信を行う  
  リアルタイムの動画バトル・アプリ

- 観戦者からライブ感あるフィードバックにより、  
  競演者と観戦者が一体となって盛り上がれる演出

<section class="video">
<div class="frame-container"><iframe src="https://riotz.works/rap-tap-app/" frameborder="0" align="left" style="transform-origin: 0px 0px 0px;"></iframe></div>
</section>

.footnote[
デモ・アプリ は こちら .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]  
※ Android と PC で 動作します(iOS 11, macOS Safari 11 は 制約あり)  
　 *Safariへの対応状況 – SkyWay サポート - .url[`https://bit.ly/2D7wOT0`]*
]


---
### 「ラップ、タップ、アップ 🎶」デモ！
Enjoying our **rap of "Rap, Tap, App".**  
Listen. **You listen to our rap.** Just for a minutes.  

<section class="video">
<div class="frame-container"><iframe src="https://riotz.works/rap-tap-app/" frameborder="0" align="left" style="transform-origin: 0px 0px 0px;"></iframe></div>
</section>

.footnote[
デモ・アプリ は こちら .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]  
※ Android と PC で 動作します(iOS 11, macOS Safari 11 は 制約あり)  
　 *Safariへの対応状況 – SkyWay サポート - .url[`https://bit.ly/2D7wOT0`]*
]


---
### 「ラップ、タップ、アップ 🎶」デモ！
Enjoying our ~~rap~~ .marker[short story of "Rap, Tap, App"].  
~~Listen. You listen to our rap. Just for a minutes.~~ .text-large-32[🙇]  
.jaian[![](contents/2018-nodefest/images/jaian.png)]

<section class="video">
<div class="frame-container"><iframe src="https://riotz.works/rap-tap-app/" frameborder="0" align="left" style="transform-origin: 0px 0px 0px;"></iframe></div>
</section>

.footnote[ 
デモ・アプリ は こちら .url[[`https://bit.ly/2Fed4Qb`](https://bit.ly/2Fed4Qb)]  
※ Android と PC で 動作します(iOS 11, macOS Safari 11 は 制約あり)  
　 *Safariへの対応状況 – SkyWay サポート - .url[`https://bit.ly/2D7wOT0`]*
]


---
### 参加した ハッカソン
- 全国規模のモバイルアプリ開発ハッカソン予選

- テーマは当日発表、24 時間で作成のち発表･審査

- Riotz は ハッカソン自体初参加、  
  チーム５名編成のところを ３人と少人数参戦

.spajam-slide[![](contents/2018-serverless-conf/images/100.png)]
.spajam-photo-2-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-2[![](contents/2018-serverless-conf/images/102.jpg)]
.spajam-photo-3-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-3[![](contents/2018-serverless-conf/images/103.jpg)]



---
### ハッカソンの開発で Vue.js/Nuxt.js を 採用した経緯
- Riotz は サーバーレス な サーバサイド (⁉) 開発 を 主とするエンジニアのチーム  
  　Java, TypeScript, Web など が 中心で、モバイル アプリ は Android ネイティブ の 開発を少々

- フロントエンドの開発では Riot.js を 使ったことがある  
  　Vue.js は 情報として知っていて、「良さそう、使ってみたい」と 思っていた

- ハッカソンでは、当時話題に上がり始めた PWA での 挑戦を決めていた

- PWA で 挑むにあたり Vue.js を 使うことを考えた
  - Riot.js より 高機能で PWA サポートがある
  - React.js より 生産性が高い


---
### ハッカソンの開発で Vue.js/Nuxt.js を 採用した経緯
- Riotz は サーバーレス な サーバサイド (⁉) 開発 を 主とするエンジニアのチーム  
  　Java, TypeScript, Web など が 中心で、モバイル アプリ は Android ネイティブ の 開発を少々

- フロントエンドの開発では Riot.js を 使ったことがある  
  　Vue.js は 情報として知っていて、「良さそう、使ってみたい」と 思っていた

- ハッカソンでは、当時話題に上がり始めた PWA での 挑戦を決めていた

- PWA で 挑むにあたり Vue.js を 使うことを考えた
  - Riot.js より 高機能で PWA サポートがある
  - React.js より 生産性が高い .small[.marker[(※ **個人の感想**です)]]

.vote-photo[![](contents/2018-nodefest/images/vote.jpg)]


---
### ハッカソンの開発で Vue.js/Nuxt.js を 採用した経緯
- Riotz は サーバーレス な サーバサイド (⁉) 開発 を 主とするエンジニアのチーム  
  　Java, TypeScript, Web など が 中心で、モバイル アプリ は Android ネイティブ の 開発を少々

- フロントエンドの開発では Riot.js を 使ったことがある  
  　Vue.js は 情報として知っていて、「良さそう、使ってみたい」と 思っていた

- ハッカソンでは、当時話題に上がり始めた PWA での 挑戦を決めていた

- PWA で 挑むにあたり Vue.js を 使うことを考えた
  - Riot.js より 高機能で PWA サポートがある
  - React.js より 生産性が高い .small[(※ **個人の感想**です)]

- Vue CLI 3.0 RC を使うも、Vue.js の 開発経験が少なく苦戦  

- Nuxt.js を 発見、秒速で使いこなす！ .small[(というより.marker[**使いこなしやすい**])]

.spajam-photo-4-pin[![](contents/2018-serverless-conf/images/pin.png)] .spajam-photo-4[![](contents/2018-serverless-conf/images/104.jpg)]


---
### 「ラップ、タップ、アップ 🎶」の アーキテクチャ
.center[.resize-hx[![](contents/2018-serverless-conf/images/110.png)]]

---
### 「ラップ、タップ、アップ 🎶」の アーキテクチャ
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
class: center, middle
## Vue.js/Nuxt.js で開発するスマホ向け PWA アプリ .english[
  Dive into PWA development for smartphone with Vue.js/Nuxt.js
]

---
layout: false
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
  .social[.fa[.fa-github[]] [@lopburny](https://github.com/lopburny)]  
  .social[.fa[.fa-twitter[]] [@lopburny](https://twitter.com/lopburny)]  
]
]

.footnote[
※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
　 また Riotz Works は 開発チームの名称です。  
]

---
### ハッカソンで作ったアプリの機能
.ui.grid[
.eight.wide.column[
#### バトルを募集する
<br />
- 対戦ルームが作られ、対戦者向けの画面と観戦者向けの画面へ飛べるリンクが発行される

- その場で QR コードを読み取るか、リンクをコピーして共有することができる
] <!-- eight.wide.column -->
.seven.wide.column[
.center[.resize-w280[![バトル募集](contents/2018-vue-fes-reject-con/images/screenshot_host_room.jpg)]]
] <!-- .seven.wide.column -->
] <!-- .ui.grid -->

---
### ハッカソンで作ったアプリの機能
.ui.grid[
.eight.wide.column[
#### 対戦／観戦ルームへ入場
<br />
ニックネームを入力して入場する
] <!-- eight.wide.column -->
.seven.wide.column[
.center[.resize-w280[![バトル募集](contents/2018-vue-fes-reject-con/images/screenshot_enter_battle_room.jpg)]]
] <!-- .seven.wide.column -->
] <!-- .ui.grid -->

---
### ハッカソンで作ったアプリの機能
.ui.grid[
.eight.wide.column[
#### バトルをする・バトルを見る（リアルタイム）
- （対戦モード）対戦ルームへ入場、STARTボタンを押して、相手が入場したら、対戦開始

- （観戦モード）観戦ルームへ入場、対戦者が揃ったら、観戦開始

#### フィードバックを見る・フィードバックを送る <br />（リアルタイム）
観戦者からグッドボタン、バッドボタン、チャットによるリアルタイムのフィードバックをもらう

] <!-- eight.wide.column -->
.seven.wide.column[
.center[.resize-w280[![バトル募集](contents/2018-vue-fes-reject-con/images/screenshot_battle_room.jpg)]]
] <!-- .seven.wide.column -->
] <!-- .ui.grid -->

---
### アプリの構成とポイント
.ui.grid[
.eight.wide.column[
.center[
<br>
#### PWA(Progressive Web Apps)
<br><br>
#### Nuxt.js(Vue.js) / SPA
<br><br>
#### WebRTC Service (SkyWay)
<br><br>
#### Firebase Realtime Database
]<!-- center -->
]<!-- .seven.wide.column -->

.seven.wide.column[
.center[
<br>
.resize-w180[![バトル募集](contents/2018-vue-fes-reject-con/images/PWA_logo.png)]

.resize-w240[![バトル募集](contents/2018-vue-fes-reject-con/images/nuxt_js_logo_horizontal.png)]

.resize-w240[![バトル募集](contents/2018-vue-fes-reject-con/images/skyway_logo.png)]

.resize-w240[![バトル募集](contents/2018-vue-fes-reject-con/images/firebase_realtime_database_logo.png)]

]<!-- center -->
]<!-- .eight.wide.column -->
]<!-- .ui.grid -->

---
### PWA (Progressive Web Apps) / SPA with Nuxt.js
PWA
  - ウェブアプリでモバイルアプリのようなUI/UXを提供できる仕組み
  - Service Worker によるコンテンツのキャッシュ、オフラインでの表示が可能
  - Android端末であれば Push通知、Bluetooth、位置情報等が使える
  
Nuxt.js
  - 注目されている Vue.js フレームワーク
  - Vue.js アプリケーションを開発する上で必要な各種設定が盛り込まれている
  - 開発環境セットアップが非常に簡単

---
### Nuxt.js の PWA対応
.ui.grid[

.six.wide.column[
PWA Module セットアップ
```shell
yarn add '@nuxtjs/pwa'
```

nuxt.config.js 設定
```javascript
module.exports = {
  // ...
  modules: [
    '@nuxtjs/pwa'
  ],
  workbox: {
    dev: true,
    // Workbox options
  }
}
```
]
.nine.wide.column[
.resize-w640[![バトル募集](contents/2018-vue-fes-reject-con/images/developer_console_sw.jpg)]
]
]

---
### Nuxt.js の TypeScript対応
.ui.grid[

.eight.wide.column[
**Nuxt 1.x**
- 型定義は提供されず、 Vue の型定義を拡張したものを自分で書く必要がある
- Rap Tap App では、Nuxt の [Context API](https://nuxtjs.org/api/context) と [Pages 拡張部分](https://nuxtjs.org/api)を書いて対応

**Nuxt 2.x**
- 現時点 (2018/11/23, `v2.3.2`) ではまだ提供されていない
- Nuxt.js GitHub リポジトリ [#4164](https://github.com/nuxt/nuxt.js/pull/4164) でマージされたので、そのうちリリースされると思われる💡
]<!-- .seven.wide.column -->

.seven.wide.column[

.resize-w420[![Nuxt 型定義サンプル](contents/2018-nodefest/images/nuxt_type_def_sample.jpg)]

]<!-- .eight.wide.column -->

]<!-- .ui.grid -->

---
### WebRTCを利用したリアルタイム通信
WebRTC(Web Real-Time Communication)
 - ブラウザ間で音声、映像、データをリアルタイム送受信する仕様
 - P2P通信が基本だが、SFU (Selective Forwarding Unit、サーバー経由で配信する仕組み）によって、端末やネットワーク負荷を抑えつつ、多人数への配信が可能

SkyWay
 - 製品化された WebRTC サービス
 - WebRTC(SFU)に必要なサーバーを運用・構築することなく、Community Edition なら無料で利用できる
 - iOS/Android/JavaScript SDK が提供されており、導入が用意

---
### SkyWay JavaScript SDK
 - ドキュメントが用意されていて読みやすい
 - GitHubにサンプルコードあり

```javascript
const peer = new Peer({ key: 'skyway_api_key' });
peer.on('open', () =>

  navigator.mediaDevices.getUserMedia({ video: true, audio: true }).then(localStream =>
    //localStream を video 要素の srcObject にセット

    peer.joinRoom('roomName', {
      mode: 'sfu',
      stream: localStream

    }).on('stream', stream => {
      // Room にいる他の人の stream が流れてくる
      // peerId を使って識別可能
    })
  );
);
```

---
### SkyWay JavaScript SDK
![Safari対応](contents/2018-vue-fes-reject-con/images/safari_support.jpg)

.text-align-right[
[※2018.11.23時点](https://support.skyway.io/hc/ja/articles/115012750968-Safari%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C%E7%8A%B6%E6%B3%81)
]<!-- .text-align-right -->

---
### Firebase Realtime Database によるリアルタイムなデータ同期
Firebase
  - サーバーレスなモバイル (＋ウェブ) アプリ開発にフィットする、Googleの統合プラットフォーム
  - 認証、ストレージ、ホスティング、データ同期、FaaS、分析等、幅広くサーバーレスで実現可能

Realtime Database
  - リアルタイムでデータを保管、同期できる NoSQL データベース
  - 導入・運用が用意、オフライン対応、トランザクション機能もあり便利
  - ラップ・タップ・アップでは、SkyWayとのルームデータを同期・チャット・フィードバック機能に活用

#### AWS IoT MQTT over WebSocket, AWS AppSync など同じことを実現する方法はいくつもあるが、<br>スピード・シンプルさ・モバイル最適化という点で Realtime Databse を採用



---
class: center, middle
## サーバーレス Web API w/AWS Lambda + TypeScript .english[
  Serverless Web API developed with AWS Lambda + TypeScript
]
---
### Web API で 提供している主な機能 と アーキテクチャ図
.cloudcraft[
.text[
**対戦ルーム作成**
- WebRTC SFU ルーム の ID 発行
- 対戦の募集者を登録

**対戦者登録**
- ルームに対戦の挑戦者を登録

**対戦ルームリスト取得**
- ルームのリストを、観戦可能、挑戦者募集をフィルタして取得

**対戦ルーム取得**
- WebRTC SFU の ルームに入るための情報を取得
]]

---
### Web API で 提供している主な機能 と アーキテクチャ図
.cloudcraft[
.text[
**対戦ルーム作成**
- WebRTC SFU ルーム の ID 発行
- 対戦の募集者を登録

**対戦者登録**
- ルームに対戦の挑戦者を登録

**対戦ルームリスト取得**
- ルームのリストを、観戦可能、挑戦者募集をフィルタして取得

**対戦ルーム取得**
- WebRTC SFU の ルームに入るための情報を取得
]
![](contents/2018-serverless-conf/images/300.png)
]

---
### 利用した主な技術
.cloudcraft[
.text[
**AWS**
- API Gateway
- Lambda (Node.js Runtime)
- DynamoDB

**フレームワークやライブラリ**
- TypeScript
  - .marker[Lambda の コールドスタートに強い ※] (Node.js Runtime)
  - 型付けによるチーム開発の支援 (API と Vue.js で 型が明確)
  
- Serverless Framework
  - AWS の 環境構築とデプロイが手軽に行える
  - Infra as Code で AWS 環境をコードとして定義・管理できる

.small[※ [Java チームが選択した TypeScript による AWS Lambda 開発](https://riotz.works/slides/?2017-serverless-conf) @Serverlessconf Tokyo 2017]
]
![](contents/2018-serverless-conf/images/300.png)
]




---
class: center, middle
## Vue.js/Nuxt.js PWA と プレゼン スライド の CI/CD .english[
  CI/CD tricks of Vue.js/Nuxt.js PWA and Presentation slide
]
---
### PWA の CI/CD の 構成
- GitHub + CircleCI の 一般的な構成

- PWA アプリ は Web アプリ と 変わらないので特別な仕掛けは不要

- ホスティング は GitHub Pages を 使用
  - 今回は SPA の 静的ホスティング (SSR を 使っていない)
  - プロダクション として スケール させるなら S3 に 置いて CloudFront  

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.center[.text-large-32[
実はなんてことないけど、なんてことないことでモバイルアプリが作れ  
CI/CD が 簡単に回ることが PWA アプリ の 強味  
モバイルアプリなのに常時アクセスが簡単にできる

ハッカソンでは、こういった仕掛け仕組みが有用にも
]]



---
### プレゼン スライド と CI/CD
- この プレゼン スライド、実は Web アプリ
  - remark.js を 使っている (次の Google Chrome で 動かなくなるかも💦)
  - GitPitch、reveal.js と 同種の技術
  - ブラウザの印刷から PDF 出力することで通常 の プレゼン スライド としても利用可能

- スライド コンテンツ は Markdown で 記述
  - 表現力は落ちるが、逆にあきらめがつく
  - 頑張りたい場合は HTML/CSS で 補強可能

- GitHub で 管理、CircleCI で Pages へ デプロイ
  - スライドのバージョン管理ができる
  - 複数人で作業する場合も Git の マージ でできる
.img-md[![](contents/2018-vue-fes-reject-con/images/003.png)]


---
### PWA アプリ と プレゼン スライド アプリ
- Web アプリ である PWA と Web アプリ な プレゼン スライド を  
  　　組み合わせることで、プレゼンの中にデモを組み込むことができる！

- モバイル アプリ の デモを カメラ や エミュレーターなしで簡単に実現  
  .small[(注: ハッカソンでは実機でのデモが必須だったため カメラ＆スマホ で デモしました)]

```html
<iframe
　　src="https://riotz.github.io/rap-tap-app/"
　　align="left"
　　style="transform-origin: 0px 0px 0px;"></iframe>
```
.img-001[![](contents/2018-vue-fes-reject-con/images/001.png)]
.img-002[![](contents/2018-vue-fes-reject-con/images/002.png)]



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
- **Vue.js/Nuxt.js を 活用することで高速にアプリを実装できる**

- ハッカソンで体験したように、想いをすぐに形にできる

- 創りたいものに集中できる技術を使うことで、  
  　　より良いサービスやイノベーションを生み出すことができる
---
class: wrapup
### まとめ .english[
  Wrap-up
]
- **Vue.js/Nuxt.js を 活用することで高速にアプリを実装できる**

- ハッカソンで体験したように、想いをすぐに形にできる

- 創りたいものに集中できる技術を使うことで、  
  　　より良いサービスやイノベーションを生み出すことができる

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.center[
  **すごいぜ！ Vue.js/Nuxt.js！！**  
  **たすかるぜ！ TypeScript！！**  
  **さすがだぜ！ Node.js！！！**
]


---
count: false
class: bottom, center, backcover
## ご清聴いただき ありがとうございました。
.english[
  It's been a pleasure being with all of you today, thank you.
]

![](assets/riotz.png)
.footer[
  Slides are posted on .url[[`https://bit.ly/2ORPubz`](https://bit.ly/2ORPubz)]  
  Thank you for contacting [@lulzneko](https://twitter.com/lulzneko), [@lopburny](https://twitter.com/lopburny) on .fa[.fa-twitter[]]  
]
