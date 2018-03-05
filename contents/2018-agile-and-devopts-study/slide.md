name: スマートデバイス と クラウドサービス を 自動パーソナライズする IoT バックエンド開発チームにおける Agile と DevOps プラクティス
count: false
class: cover, center, middle
# スマートデバイス と クラウドサービス を
# 自動パーソナライズする
# IoT バックエンド開発チームにおける
# Agile と DevOps プラクティス
.english[
  Agile and DevOps practices in backend development team of systems to automatically personalize smart devices and cloud services
]
.footer[
  @Agile & DevOps Study 2018.02 / 25 min  
  Slides are posted on .url[[`https://goo.gl/9tUuvS`](https://goo.gl/9tUuvS)]  
]


---
count: false
class: preface, agenda
### Agenda
1. システム紹介
2. アーキテクチャ変更と影響
3. 変更の大波を乗り越えた Agile & DevOps プラクティス
4. まとめ

.footer[Slides are posted on .url[[`https://goo.gl/9tUuvS`](https://goo.gl/9tUuvS)]]



---
class: center, middle
## About us
---
layout: false
### lulzneko
.ui.grid[
.eleven.wide.column[
  手段のためには目的を選ばず、新しい技術を見つけては試すことが生きがいの、IT好きで葉巻好き酒好きなだけの猫。

  最近は Slack の ボット 作成や、Raspberry Pi などの電子工作にも手を染める。サーバレス は アイデアを素早く形にできる アーキテクチャ として 大のお気に入り。

  面白そうなら何でも手を出し、面白くなければ楽しくすることを考えて、日々を過ごす。
]
.four.wide.column[
  .resize-w240[![](bio/lulzneko/photo.jpg)]  
  .resize-w240[![](bio/certs/aws-solutions-architect-professional.jpg)]  
  .social[.fa[.fa-github[]] [@lulzneko](https://github.com/lulzneko)]  
  .social[.fa[.fa-twitter[]] [@lulzneko](https://twitter.com/lulzneko)]  
]
]

.footnote[
  ※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
  　 また Riotz Works は 開発チームの名称です。  
]
---
layout: false
### lopburny
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
class: center, middle
## システム紹介
---
### デバイス と サービス の 自動パーソナライズ IoT バックエンド
- ユーザ認証基盤 と デバイス認証基盤 の 提供
- 工場 と 販売 そして 配送 の それぞれで持っているデータの関連付け
  - 工場 に おける デバイス固有の情報 (e.g. デバイス固有 ID、シリアル番号)
  - 販売 に おける お客さま情報 (e.g. ユーザー ID、クラウドサービス加入情報)
  - 配送 に おける お客さま情報 と 配送するデバイスの情報 (e.g. ユーザ ID、シリアル番号)

.center[.arch[![](contents/2018-agile-and-devopts-study/images/103.png "クラウド連携に必要な仕掛け")]]


---
### アーキテクチャを構成する要素
#### 設計のポリシーは .marker[サーバーレス]
- サーバーの事前プロビジョニングや管理が不要  
- アプリケーションロジックに集中できる、クラウドネイティブな開発

#### WebAPIは 機能性ごとに切り出された .marker[マイクロサービス]
- モノリシックなアーキテクチャに比べて、激しい変更・変化に強い  
- 迅速なデプロイ、優れたスケーラビリティ  
- 問題箇所を特定・fix し易い

#### データ連携も .marker[イベント・ドリブン]
- サービス・システム間の相互作用をイベントとして表現することで、疎結合が保たれる
---
### サーバーレスとは？
.center[**<u>The Serverless Manifesto</u>**]  
.centering[
  Function are the unit of deployment and scaling  
  .marker[No machines, VMs, or containers visible in the programming model]  
  Permanent storage lives elsewhere  
  Scales per request; Users cannot over- or under-provision capacity  
  .marker[Never pay for idle (no cold servers/containers or their costs)]  
  Implicity fault-tolerant because functions can run anywhere  
  .marker[BYOC - Bring Your Own Code]  
  Metrics and logging are a universal right  
  ##### Apr 19 2016 [AWS Chicago Summit](https://www.slideshare.net/AmazonWebServices/getting-started-with-aws-lambda-and-the-serverless-cloud/29)
]


---
### マイクロサービス・アーキテクチャ
.cloudcraft[
.text[
- モノリシックなアーキテクチャに比べて、激しい変更・変化に強い  
- 迅速なデプロイ  
- 問題箇所を特定・fix し易い  
]
![](contents/2018-agile-and-devopts-study/images/200.png "エンハウンス後のシステムアーキ図")
]

---
### イベント・ドリブンなシステム連携
- データ連携やサービス間の相互作用に疎結合が保たれ、変更・変化に強い  

- 並行処理と組み合わせることが多く、優れたスケーラビリティを持つ  

- 本システムも購入データ連携に S3, SNS, DynamoDB Stream, Kinesis Data Firehose を積極活用  
  "バッチサーバー"を持たないデータ連携を実現
<br><br>
.center[.slide[![](contents/2018-agile-and-devopts-study/images/201.png "マイクロサービス")]]
---
class: center, middle
## アーキテクチャ変更と影響
---
### 変更前のアーキテクチャと不安要素
.cloudcraft[
.text[
#### 変更前のアーキテクチャ
  - デバイス対応含め システム連携が多く必要になるに連れ  
    マイクロサービスが増えていく  
  - Java チームなので、自然と Java で 追加開発
  - 15近いマイクロサービスを構築

#### 不安要素
  - システム連携に固定IPを要求される  
    (VPC Lambda 必須)
  - マイクロ化が過剰で複雑になった
]
![](contents/2017-serverless-conf/images/enhanced-system.png "エンハウンス後のシステムアーキ図")
]
---
### 問題と原因
.cloudcraft[
.text[
#### 問題
タイムアウトが多発、サービスとしてはやや厳しい状況に・・・

#### 原因
- 1シーケンスの呼び出しチェーンが長い(最大6と5がある)
- VPC Lambdaで遅延がある
- コールドスタートの発生個所が多くなる

#### つまり、
- 分割しすぎた...
- コールドスタートを甘く見てた  
⇛ リアーキを進めつつ、  
  コールドスタートの影響を  
  最小限に抑える必要があった
]
![](contents/2017-serverless-conf/images/enhanced-system-problem.png "エンハウンス後のシステムアーキ図")
]
---
### AWS Lambda の 実行ランタイムを変更

#### 実行ランタイムの種類
  - コンパイル系 - C#, Java, (Go)
  - スクリプト系 - Node.js, Python

#### スクリプト系ランタイムは早い!?
  - 一回温まれば、コンパイル言語の方が処理能力は高い
  - 一方スクリプト系の場合、コールドスタートの影響を "気にならない程度に" 抑えられる

#### 実行ランタイムは Node.js、開発言語は TypeScript に変更
  - Javaに近い構文は Node.js / JavaScript だった
  - それに加えて、開発言語を JS ではなく 強い静的型付けができる TypeScript を採用

---
### 変更のインパクト (!!)
#### 実行ランタイム及び開発言語の変更(Java -> TypeScript)により、新たな学習が必要
  - JavaScript, TypeScript の 言語仕様と生態系
  - Node.js、JS特有の非同期処理
    - Callback Hell? Promise? async-await? 😰💦
    - 非スクリプト系チームにとってはそこそこ学習コストが高い

#### 開発周りの仕組み全て再構築が必要
  - テストライブラリの選定
  - デプロイフレームワークの導入
  - CIのジョブ（ビルド・テスト・デプロイ）全て書き直し

#### 実戦投入までの時間 わずか 1 - 2 ヶ月
  - Production 環境構築と平行して、まずはクリティカルなマイクロサービスから置き換える
  - デバイス追加要件も続々と来ていたので、TypeScript-Lambda で 対応しつつ...

---
### Agile 開発体制で乗り切る！

#### GitHubを最大限活用したナレッジの共有、チーム開発
  - TypeScript/Node.js 経験者による テンプレートプロジェクト を作成
  - メンバーはテンプレートを参考に学習と開発を並行
    - みんなが同じ テンプレート を見るから、実装ルール・パターンが自然に統一
  - 個人の開発アイテムやタスクは、GitHub Projects / Issues をフル活用
    - 各自が見える化した上で、優先順位を変えるなど柔軟に対応
  - PRでレビュー
<br>

#### できるだけ自動化する！
  - もちろん Infrastructure as a code
  - 実装を進める前に、まずは自動化作業を優先
    - 開発環境の不備やビルド失敗によるメンバーの試行錯誤を大幅に減らせた
  - ビルド、テスト、デプロイ ほぼ全て自動化できた

---
### Agile 開発体制で乗り切る！

#### 日次スタンドアップミーティング
  - 昨日今日の状況がタイムリーに把握でき、困っているメンバーがいればすぐに(!)フォローする

#### 口頭による「今聞く」のコミュニケーション + 非同期チャットの組み合わせ
  - メンバー全員が同じロケーション、席も近いので、いつでも口頭で話せる
  - お願い事、困っている事、確認事項など、なんでも気軽に口頭 or チャットで話し合う
  - 例えば TypeScript バージョンアップ情報など、役に立つ記事をSlackでシェアすることで、  
    メンバー全員が同じ情報をインプットできる

#### やっぱり大事なのは...
  - 変化に対応する柔軟性と心構え
  - 技術に対する好奇心
  - チームとしての一体感、モチベーション
<br>

.center[ Agile開発じゃないとやってられない!! 😅 ]
---
### TypeScript-Lambda 移行前
.cloudcraft[
.text[
  #### コールドスタート時のレスポンスタイム

.icon[
![](contents/2017-serverless-conf/images/time-yellow.png "Lambda not in VPC") __Lambda (Java) : 7s ~ 10s__ ↑  

![](contents/2017-serverless-conf/images/time-red.png "Lambda in VPC") __VPC Lambda (Java) : 17s ~ 20s__ ↑
]

呼び出しチェーンの中で 1回でも  
コールドスタートに当たったら  
（特にVPC Lambda）
ほぼタイムアウト　
]
![](contents/2017-serverless-conf/images/enhanced-system-improved-response-time-before.png "改善される前")
]
---
### TypeScript-lambda 移行後
.cloudcraft[
.text[
  #### コールドスタート時のレスポンスタイム

.icon[
![](contents/2017-serverless-conf/images/time-green.png "Lambda not in VPC") __Lambda (Node.js) : 1s ~ 3s__ ↑  

![](contents/2017-serverless-conf/images/time-yellow.png "Lambda in VPC") __VPC Lambda (Node.js) : 11s ~ 13s__ ↑
]

VPC Lambda の場合、ある程度  
時間がかかってしまうのは仕方ないが、  
API Gateway のタイムアウトには  
何とか持ちこたえることができる
]
![](contents/2017-serverless-conf/images/enhanced-system-improved-response-time-after.png "改善される後")
]



---
class: center, middle
## 変更の大波を乗り越えた Agile & DevOps プラクティス
---
### 日次ミーティング と ふりかえり/KPT
- .marker[Agile プラクティス の 基本、とはいえ基本やっぱり大事！]
- 日々状況が変わる中で適切に情報共有できる
- 作業が明確化できること、認識の齟齬を早めにとらえられる


- 日次ミーティング
  - 11:00 開催 が ちょうどよく、スタンディング で 10分程度
  - 最近 は .marker[**AWS の 資格試験 の サンプル問題を１つ解くなど 学習タイムも追加！**]

- ふりかえり/KPT
  - 今回は定期開催でき無かったが、チーム・メンバーの思いをまとめるのに重要
  - 問題 や 新しい方向性 など、各々が.marker[ため込んでいるものが放出できる ➡ 新しい取り組みへ]

- 加えて、週次 の 「.marker[フリートーク会議]」
  - 自由にネタを持っていける定例会議も活用、レビュー や 新技術導入の相談など


---
### GitHub Projects / Issues による タスク管理
- .marker[基本的に GitHub で 管理]

- .marker[個人タスクなどでも GitHub Issues を 活用]
  - みんなで共有するほどのことでもないことなども GitHub の Issues で 個人管理
  - GitHub の Organization で 各自管理タスク用の Projects を 作る
  - GitHub に ToDo や Task などといった、Issues を まとめておくリポジトリを作る
  - リポジトリ に Issues を 入れて、自分の Projects に 関連付けておく


---
### Git/GitHub による ソースコード 管理
- ソースコード は Git/GitHub で 管理
  - Pull Request を 使った開発 ＆ レビュー

- .marker[設計 や インフラ定義、運用ドキュメント も Git/GitHub 管理]
  - UML は PlantUML ([`http://plantuml.com/`](http://plantuml.com/)) で コード化、S3 で ホスティング
  - インフラ定義 は Serverless Framework ([`https://serverless.com/`](https://serverless.com/)) で Infra as Code！
  - 運用ドキュメント は Markdown で 記述

- 実は、この プレゼン資料 も！
  - Markdown で 書かれているので、GitHub で 管理されてます！

- .marker[古いソースコード は Amazon CodeCommit へ 退避]
  - 開発が終了したプロダクトのソースコードは Amazon CodeCommit に 移すことでコスト削減
  - Pull Request が サポートされるも、日々使うものなので GitHub からの移行は未検討


---
### CircleCI による 継続的デリバリ
- .marker[常に利用できるものを、利用できる状態にしておく]

- コーディングのルールは最初から厳しくし徹底
  - カバレッジ C0 で 80% 以上、下回るとビルド失敗に
  - 警告はコンパイルエラー！
  - 結果、警告リストは常に空でレビューも本コードに集中可能

- ビルドがパスすると、AWS へ デプロイされ利用可能


---
### Slack を 活用したコミュニケーション と 情報統合
- .marker[今すぐの話と非同期のチャットの組み合わせで、コミュニケーションが円滑に]
  - ITニュース や アイデア の シェア、雑談、飲み会の企画 etc.
  - チームの席配置が近く、口頭コミュニケーション可能だが.marker[チャットツールは必須の道具]

- システム連携による各種情報を一元通知
  - GitHub の PR や レビューコメント
  - CircleCI に よるビルド失敗の通知(通常の成功は通知なし)
  - システム障害レポート



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
- Agile は 大きな変更に対して、柔軟に対処していくことができる  

- 変化はつきもの、受け入れる柔軟性と心構え、体制や仕組み が 必要

- 変化を楽しめるような、日々のコミュニケーションが重要  
⇒ 開発中にプログラミング言語を変更することすら楽しみたい♪


---
count: false
class: bottom, center, backcover
## ご清聴いただき ありがとうございました。
.english[
  It’s been a pleasure being with all of you today, thank you.
]

![](assets/riotz.png)
.footer[
  Slides are posted on .url[[`https://goo.gl/9tUuvS`](https://goo.gl/9tUuvS)]  
  Contact for slide is [@lulzneko](https://twitter.com/lulzneko) & [@lopburny](https://twitter.com/lopburny) by .fa[.fa-twitter[]]  
]
