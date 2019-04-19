name: Java チームが選択した TypeScript による AWS Lambda 開発
count: false
class: cover, center, middle
# Java チームが選択した
# TypeScript による AWS Lambda 開発
.event-logo[![](assets/logo/serverlessconf.png)]
.english[
  Development on AWS Lambda with TypeScript, which is promoted by Java developers
]
.footer[
  @Serverlessconf Tokyo 2017 / 40 min  
  Slides are posted on .url[[`https://goo.gl/Mn5xab`](https://goo.gl/Mn5xab)]  
]


---
count: false
class: preface, agenda
### Agenda
1. Java から TypeScript へ 移行した背景 .english[
  Background of migration from Java to TypeScript
]
2. TypeScript-Lambda 導入のポイント .english[
  Notes for changing over to TypeScript-Lambda
]
3. 移行にあたり、困ったこと と 解決方法 .english[
  Issues to be considered on changing over to TypeScript-Lambda
]
4. 移行した結果 .english[
  Improvements by switching over to TypeScript-Lambda
]
5. まとめ .english[
  Wrap-up
]

.footer[Slides are posted on .url[[`https://goo.gl/Mn5xab`](https://goo.gl/Mn5xab)]]



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
  　 また Riotz.works は 開発チームの名称です。  
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
　 また Riotz.works は 開発チームの名称です。  
]



---
class: center, middle
## Java から TypeScript へ 移行した背景 .english[
  Background of migration from Java to TypeScript
]
---
### 最初のシステム と 開発チーム .english[
  Initial system as server type & Development team
]
.cloudcraft[
.text[
#### 最初のシステム
- Java の アプリケーション
- Amazon EC2 ＋ Amazon DynamoDB の 半サーバーレスな環境

#### 開発チーム
- Java 歴 ウン十年 を 筆頭に、全員 Java の 開発者 で 数名
- Web の フロント開発経験 エンジニア １名
- DevOps 体制
]
![](contents/2017-serverless-conf/images/server-type-system-before-migration.png "移行前システムのアーキ図")
]


---
### AWS Lambda へ アーキテクチャ変更 .english[
  Change architecture to AWS Lambda
]
.cloudcraft[
.text[
#### 2014年、AWS Lambda 登場
- DynamoDB のように マネージドで運用できる！
- 処理時間に対しての課金で、処理しなければ無料！
- 使うしかない！!

#### アーキテクチャ変更
- Lambda の Java ランタイム が ローンチされるのを待って、移行開始
- フレームワークの変更や抽象化層の変更などを行うが、基本そのまま
]
![](contents/2017-serverless-conf/images/architecture-change-to-lambda.png "移行後システムのアーキ図")
]


---
### エンハンス、そして "問題" へ .english[
  Enhanced, and thus into the Problems...
]
.cloudcraft[
.text[
#### エンハンス
- 連携アプリの追加により、周辺機能としてのエンハンスが発生
- マイクロ・サービス型のアーキテクチャとして機能を追加
- Java チーム なので、自然と **Java** で 追加開発
- **15** 近い マイクロ・システムを構築...

#### 不安要素
- 既存システム連携に 固定IP =  VPC Lambda 必須
- マイクロ化が過剰で複雑になった

#### そして... ~~伝説へ~~
]
![](contents/2017-serverless-conf/images/enhanced-system.png "エンハンス後システムのアーキ図")
]



---
### 問題 と 原因 .english[
  Problems & Causes
]
.cloudcraft[
.text[
#### 問題
- タイムアウトが多発、サービスとして公開は厳しい orz

#### 原因
- １シーケンスのチェーンが長い（最大 6 と 5 がある）
- VPC Lambda での遅延がある
- コールドスタートの発生個所が多くなる

#### つまり
- 分割しすぎ、パス長すぎ！
- コールドスタート、甘く見すぎ！
]
![](contents/2017-serverless-conf/images/enhanced-system-problem.png "エンハンス後システムのアーキ図 と 原因")
]


---
### AWS Lambda の 実行ランタイムを変更 .english[
  Change execution runtime of AWS Lambda
]
.ui.grid[
.eight.wide.column[
#### 実行ランタイムの種類
- C#,　Java,　Node.js,　Python

#### スクリプト系ランタイム は 速い！？
- スクリプト系ランタイム は Node.js と Python
- Java に 近い構文は Node.js / JavaScript だった
- 得意ではないが、何かと小さなものを作ることも

#### この選択は、後に苦労の種ともなる...
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
  **参考文献**  
  　 AWS Lambdaの処理性能を言語毎に測ってみた - Taste of Tech Topics  
  　 [`http://acro-engineer.hatenablog.com/entry/2016/08/02/120000`](http://acro-engineer.hatenablog.com/entry/2016/08/02/120000), (参照 2017.11.1)
]



---
class: center, middle
## TypeScript-Lambda 導入のポイント .english[
  Notes for changing over to TypeScript-Lambda
]
---
### 言語として TypeScript を選択することのメリット .english[
  Advantages of using TypeScript
]
#### スクリプト言語でありながら、静的型付け言語である
  - チーム開発・メンテナンスに強い
  - モジュール化しやすい・コードレビューしやすい・テストしやすい
  - 実行して初めて気がつくミスやバグを大幅に減らせる
  - エディタ・IDEによる入力補完、リファクタリングができる

#### 最新の JavaScript 言語仕様を先取りして使える
  - async-await, Decorators 構文  
    ※ AWS Lambda のランタイム (Node.js v6.10) は async-await 未対応

#### モダンな言語機能・Java ライクな型機能が充実
  - Nullable Types, Type Inference
  - Generics, Interface, Enum, Abstract Class ... etc.

---
### TypeScript を選択する上で注意すべきこと .english[
  Points to be aware of using TypeScript on server-side
]
#### 非同期処理との戦い
  - ある程度 JavaScript と JavaScript による非同期プログラミングの知識・経験がないと、大変
  - 非スクリプト系チームにとっては、そこそこ学習コストが高い
    - サーバーサイドの場合、特に Promise と async-await を上手に駆使する必要あり

#### 型定義の有無、ライブラリの選択に悩まされる
  - 既存JSライブラリを使いたい時、型定義(DefinitelyTyped)がないと大変
  - そもそも JS の生態系は変化が激しく追従が大変  
    - 可能な限り、寿命が長い・一貫して改良し続けている・実績が多いものを選ぶ  

---
class: center, middle
## 移行にあたり、困ったこと と 解決方法 .english[
  Issues to be considered on changing over to TypeScript-Lambda
]
---
### APIG (Lambda Proxy Integration) イベントハンドラーの選定 .english[
  Applying event handler for TypeScript-Lambda
]

Route機能、event(APIリクエスト)の前処理、requestContext ロギング ... など   
自分で書いてもいいけど、できるだけ公開されているものを使いたい。

- [@awslabs/aws-serverless-express](https://github.com/awslabs/aws-serverless-express) 
  - ちゃんとTypeScript用の型定義があり、既存 Express アプリをそのまま移植可能
  - 無難な選択肢だが、Node.js/Expressでの開発経験がないメンバーとしては、  
    もっとシンプルなものにしたかった

- [@claudiajs/claudia-api-builder](https://github.com/claudiajs/claudia-api-builder)  
  - 直感的でシンプルなインタフェースでお気に入りだが、DefinitelyTyped に 型定義がない orz  
  - 軽量なので、TypeScript経験者なら、自分で型定義を書いて使うことができるレベル

#### ⇛ claudia-api-builder に選定、仕様を確認して型定義を書きつつ、開発スタート

---
### APIG (Lambda Proxy Integration) イベントハンドラーの選定 .english[
  Applying event handler for TypeScript-Lambda
]

e.g. TypeScript-Lambda の エントリーポイント (claudia-api-builderの場合)
.ui.grid[
.fifteen.wide.column[
<pre class="prettyprint"><code class="language-typescript">
import * as ApiBuilder from 'claudia-api-builder';
import postContents    from './actions/postContents';
import SampleError     from './errors/sampleError';

const api: ApiBuilder = new ApiBuilder();

api.get('/version', (request: ApiBuilder.Request&lt;Empty&gt;) => '0.0.0');

api.post('/contents', (request: ApiBuilder.Request&lt;Contents&gt;) => postContents(request)
  .catch((err: SampleError) => new api.ApiResponse(err.body, { ... }, err.statusCode)));

module.exports = api;
</code></pre>
]
]

---
### 外部API呼出しの非同期処理 .english[
  Handling asynchronous methods/external API calls
]

Node.js 開発で最も悩まされる問題の一つ、コールバック地獄  
サーバレス WebAPIの開発では、シーケンシャルにAPIコールするケースが多々ある中  
Promise や Generator/Iterator だけでは、まだつらい部分がある
.ui.grid[
.seven.wide.column[
<pre class="prettyprint"><code class="language-typescript">
getData(params, (err, dataA) => {
  if (err) { 
    console.log(err); 
  }
  ...
  getData(params, (err, dataB) => {
    ...
    postData(params, (err, dataC) => {
      ...
    });
  });
});
</code></pre>
]
.seven.wide.column[
<pre class="prettyprint"><code class="language-typescript">
getData()
  .then(dataA => getData(dataA))
  .then(dataB => getData(dataB))
  .then(dataC => postData(dataC))

  ...

  .catch(err => console.log(err));
  // Promiseをリターンする関数内で
  // 更に非同期処理が重なると
  // エラーハンドリング大変

</code></pre>
]
]

---
### 外部API呼出しの非同期処理 .english[
  Handling asynchronous methods/external API calls
]
async-await パターンにして、必要な処理のみを簡潔に記述できる  
TypeScript を使えば、ES5 や ES2015 など色んな JS にトランスパイルできるので  
AWS Lambda の ランタイム (Node.js v6.10) でも使用できる
<pre class="prettyprint"><code class="language-typescript">
(async () => {

  const dataA: DataA = await getDataA();
  const dataB: DataB = await getDataB()
  const dataC: DataC = await getDataC();

  const res: PostDataResult = await postData(dataA, dataB, dataC);

  console.log(res);

})();

</code></pre>

---
### 外部API呼出しの非同期処理 .english[
  Handling asynchronous methods/external API calls
]
e.g. DynamoDBからデータを読み込むパターン
<pre class="prettyprint"><code class="language-typescript">
(async () => {

  const params: GetItemInput = {
    'Key': { 
      'userId' : 'User01' 
    },
    'TableName' : 'Users'
  };

  const result: GetItemOutput = await documentClient.get(params)
    .promise()
    .catch((err: AWSError) => { throw err; });

  console.log(result.Item);

})();
</code></pre>

---
class: center, middle
## 移行した結果 .english[
  Improvements by switching over to TypeScript-Lambda
]

---
### TypeScript-Lambda 移行前 .english[
  Before changing over to TypeScript-Lambda
]
.cloudcraft[
.text[
  #### コールドスタート時のレスポンスタイム

.icon[
![](contents/2017-serverless-conf/images/time-yellow.png "Lambda not in VPC") __Lambda (Java) : 7s ~ 10s__ ↑  

![](contents/2017-serverless-conf/images/time-red.png "Lambda in VPC") __VPC Lambda (Java) : 17s ~ 20s__ ↑
]

呼び出しチェーンの中で 1回でも  
新しい Lambda コンテナの起動に当たったら  
（特にVPC Lambda）
ほぼタイムアウト　
]
![](contents/2017-serverless-conf/images/enhanced-system-improved-response-time-before.png "改善される前")
]

---
### TypeScript-Lambda 移行後 .english[
  After changing over to TypeScript-Lambda
]
.cloudcraft[
.text[
  #### コールドスタート時のレスポンスタイム

.icon[
![](contents/2017-serverless-conf/images/time-green.png "Lambda not in VPC") __Lambda (Node.js) : 2s ~ 3s__ ↑  

![](contents/2017-serverless-conf/images/time-yellow.png "Lambda in VPC") __VPC Lambda (Node.js) : 10s ~ 13s__ ↑
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
## まとめ .english[
  Wrap-up
]
---
class: wrapup
### まとめ .english[
  Wrap-up
]
- **TypeScript は AWS Lambda 開発で良い選択肢になりうる**  
- アーキや処理特性に合わせて、ランタイムは選ぶ必要がある
- 変更する場合は小さく始める、今回はタイムアウト問題部分から

.note[
#### 補足
- Java ランタイムは悪くない！ 複雑なアーキが悪い！！（反省してます）  
- 過剰マイクロ化だが、Traditional環境依存を分離できた（後悔はしていない）
]


---
count: false
class: bottom, center, backcover
## ご清聴いただき ありがとうございました。
.english[
  It’s been a pleasure being with all of you today, thank you.
]

![](assets/riotz.png)
.footer[
  Slides are posted on .url[[`https://goo.gl/Mn5xab`](https://goo.gl/Mn5xab)]  
  Contact for slide is [@lulzneko](https://twitter.com/lulzneko) & [@lopburny](https://twitter.com/lopburny) by .fa[.fa-twitter[]]  
]
