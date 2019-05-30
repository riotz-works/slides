name: サーバーレスなウェブフロントを実現する JAMStack
count: false
class: cover, center, middle
# サーバーレスなウェブフロントを実現する JAMStack
.event-logo[[![](../assets/logo/serverlesstokyo12.jpg)](https://serverless.connpass.com/event/130509/)]
.english[
  JAMStack, an architecture to realizes serverless web front
]
.footer[[@Serverless Meetup Tokyo #12](https://serverless.connpass.com/event/130509/) / 20 min]


---
count: false
class: preface, agenda
### Agenda
1. 今日の話の背景 .english[
  Background of today's story
]
2. JAMStack とは .english[
  What is JAMStack
]
3. アーキテクチャ紹介 .english[
  Introducing the JAMStack architecture
]
4. JAMStack の 可能性 .english[
  Possibility of JAMStack
]
5. まとめ .english[
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
  .small["サーバーレスはエンジニアにとって最強の武器" を 標榜するエンジニアチーム！]  

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
  新しい技術を見つけては試すことが大好きで技術を試すためには  
  目的を選ばない、IT好きで葉巻好き酒好きなだけの猫。

  アイデアを高速で形するアーキとして .marker[**サーバーレスが大のお気に入り**]。何かを作る時もサーバーレスでいけるかを最初に考える。

  Vue.js/Nuxt.js は 高速にフロントエンドの開発ができ、  
  .marker[**すごいぜ！ Vue.js/Nuxt.js！！** と 心酔]してる。

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
## 今日の話の背景 .english[
  Background of today's story
]
---
### どうして、JAMStack .small[(ジャムスタック)] の話
- JAMStack 最近話題になりつつあり、フロントエンドやウェブの開発などで見聞きします

- 2018年の Qiita Advent Calendar に『[JAMstack Advent Calendar 2018](https://qiita.com/advent-calendar/2018/jamstack)』登場

- [Serverless Advent Calendar 2018](https://qiita.com/advent-calendar/2018/serverless) にも！  
　『[GridsomeをCodePipeLine + CodeBuild でDeployするServerlessなBlog](https://blog.seike460.com/2018/12/20/gridsome-deploy-serverless/)』- [@seike460](https://qiita.com/seike460)

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.center[.text-large[
  ** つまり、フロントのお話だよね。 **  
  ** なんで Serverless Meetup で、お話するの？ 🤔 **  
]]

---
### そのフロント、サーバーレス？
- サーバーレスの話はサーバーサイドの話が多い .small[(と思う)]
- フロント？ CloudFront/S3 で！
  - それは CDN の話？ テンプレートエンジンは？ 💎 🍰 ☕ 🐪 🐍 .small[etc...]
  - どれも素晴らしい。しかしながら **必要ですよね、インスタンス**。

.text-large-32[**フロントも含めて、サーバーレスにしましょう！ JAMStack でね！！**]
.img-ref-slides[![](../contents/2019-serverless-meetup-tokyo12/images/01.png)]



---
class: center, middle
## JAMStack とは .english[
  What is JAMStack
]



---
### JAMStack って、なに？
JAMStack 公式サイト - .url[[https://jamstack.org](https://jamstack.org/)]
.img-jamstack-def[![](../contents/2019-jaws-days/images/01.png)]
- ウェブサイト や アプリ を 構築するための新しいアーキテクチャ
- **クライアントサイドJavaScript**、**再利用可能なAPI**、**構築済みのマークアップ** が ベースとなる
- **J**avaScript, **A**PIs, **M**arkup の 頭文字 **JAM** の Stack


---
### どうすると JAMStack ？
定義: クライアントサイドJavaScript、再利用可能なAPI、構築済みのマークアップ が **ベース**
.arrow-left-center[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

- **クライアントサイド JavaScript**  
  HTTP リクエスト/レスポンスのようなダイナミックな処理は、  
  完全にクライアント上で実行されるようにする。（フレームワークやバニラなどは問わない）  

- **再利用可能な API**  
  全てのサーバサイド処理、DB処理は HTTPS で アクセスできる再利用可能な Web API にする。  
  カスタムメイドでも、サードパーティーでも問わない。

- .marker[**構築済みのマークアップ**]  
  テンプレート用のマークアップ = HTML は、サイトジェネレータ や ビルドツール で、  
  デプロイ時に事前ビルドし生成している 必要(should) がある


---
### つまり？　これを
.img-jamstack-old[![](../contents/2019-jaws-days/images/02.png)]

.footnote[
  [Slide 20 - The Old Stack](https://speakerdeck.com/biilmann/the-jam-stack?slide=9)  
  The JAM Stack - .url[[https://speakerdeck.com/biilmann/the-jam-stack](https://speakerdeck.com/biilmann/the-jam-stack)]  
]

---
### つまり？　これを、こうして
.img-jamstack-new[![](../contents/2019-jaws-days/images/03.png)]

.top-right[.footnote[
  [Slide 20 - The Old Stack](https://speakerdeck.com/biilmann/the-jam-stack?slide=9)  
  [Slide 38 - How do web solve this?](https://speakerdeck.com/biilmann/the-jam-stack?slide=38) (一部編集)  
  The JAM Stack - .url[[https://speakerdeck.com/biilmann/the-jam-stack](https://speakerdeck.com/biilmann/the-jam-stack)]  
]]

---
### つまり？　これを、こうして、こうなる .small[(1/2)]
.img-jamstack-all[![](../contents/2019-jaws-days/images/04.png)]

.footnote[
  The JAM Stack - .url[[https://speakerdeck.com/biilmann/the-jam-stack](https://speakerdeck.com/biilmann/the-jam-stack)] (一部修正)  
]

---
### つまり？　これを、こうして、こうなる .small[(2/2)]
.img-jamstack-all[![](../contents/2019-jaws-days/images/05.png)]

.footnote[
  The JAM Stack - .url[[https://speakerdeck.com/biilmann/the-jam-stack](https://speakerdeck.com/biilmann/the-jam-stack)] (一部修正)  
]


---
### JAMStack の メリット
- **より良いパフォーマンス**  
  CDN を 活用することによる高速化  
  HTML 生成の省略による高速化  

- **より高いセキュリティ**  
  Web API 化 による 攻撃対象の局所化  
  HTML 生成処理 の オフライン化

- **より安価で簡単なスケーリング**  
  CDN の スケーラビリティを享受

- **より良質な開発者エクスペリエンス**  
  疎結合化による開発ターゲットと責務の明確化  

.img-jamstack-tr[![](../contents/2019-jaws-days/images/05.png)]


---
layout: false
### JAMStack プロジェクト の ベストプラクティス
.ui.grid[
.seven.wide.column[
- **CDN に 全部配置されている**  
  サーバサイドに依存しないため、すべてが CDN に 配置でき、それによってスピードとパフォーマンスを最大限に発揮させる  

- **全てが Git に 存在する**  
  誰もが `git clone` でき、標準的な手順でビルド、ローカルで実行できるようにする  

- **モダンなビルドツール**  
  変化を恐れずに最新のツールによるアドバンテージを受ける  
]
.seven.wide.column[
- **自動ビルド**  
  JAMStack は 特に 事前構築済みの HTML を 使うため、プロセスを自動化しておき、ビルド＆デプロイの負担を下げる  

- **アトミックなデプロイ**  
  不整合を避けるに全ファイルがアップロードされるまで変更が行われないようにする  

- **キャッシュの即時無効化**  
  デプロイの実行 が 実際に反映されるよう、CDN の キャッシュを消去する  
]]


---
### JAMStack を 構築する 静的サイトジェネレータ
定義: **構築済みのマークアップ**、HTML は .marker[サイトジェネレータ や ビルドツール で] 事前生成する  
SSG、Static Site Generator と 呼ばれるツールを使うことが多い

.ui.grid[
.six.wide.column[
StaticGen - .url[.small[[https://www.staticgen.com](https://www.staticgen.com/)]]
.img-staitc-gen[![](../contents/2019-jaws-days/images/06.png)]
]
.nine.wide.column[.static-gen[
サイト系
- [Hugo](https://gohugo.io/)     - Golang

- [Gatsby](https://www.gatsbyjs.org/)   - JavaScript, React, GraphQL

- [Hexo](https://hexo.io/)     - JavaScript, EJS, Pug, Haml, Swig...

- [VuePress](https://vuepress.vuejs.org/) - JavaScript, Vue.js, Vue.js-OFFICIAL

- [Gridsome](https://gridsome.org/) - JavaScript. Vue.js, GraphQL

アプリ系
- [Next.js](https://nextjs.org/)  - JavaScript, React

- [Nuxt.js](https://nuxtjs.org/)  - JavaScript, Vue.js
]]]



---
class: center, middle
## アーキテクチャ紹介 .english[
  Introducing the JAMStack architecture
]
---
### AWS x JAMStack アーキテクチャ - よく使うパターン
.img-arch-02[![](../contents/2019-jaws-days/images/arch-02.png)]
---
### AWS x JAMStack アーキテクチャ - ウェブサイト
.img-arch-03[![](../contents/2019-jaws-days/images/arch-03.png)]


---
class: center, middle
## JAMStack の 可能性 .english[
  Possibility of JAMStack
]
---
### JAMStack の 可能性
- **情報発信サイト**  
  公式サイト、ブログ、ドキュメント、etc...  
  様々なケースで、このようなサイトは必要  
  高速にサイトの情報を表示できる  
  
  例えば Riotz.works の 公式サイトは Gridsome 製  
  .url[[https://riotz.works](https://riotz.works/)]  

- **ウェブアプリ の フレーム**  
  Web API に アクセスでデータが扱える範囲のもの  
  例えば ラップ・バトル アプリは Nuxt.js で SSG 製  
  動画中継を API 利用に回すことで静的サイトとして構築  
  .url[[https://riotz.works/rap-tap-app](https://riotz.works/rap-tap-app/)]  

.img-left-riotz[![](../contents/2019-jaws-days/images/07.png)]
.img-left-rap-top[![](../contents/2019-jaws-days/images/08.jpg)]
.img-left-rap-vs[![](../contents/2019-jaws-days/images/09.jpg)]

---
### 銀の弾丸ではない
**SEO 重視 で CGM(Consumer Generated Media) や 変化の激しいコンテンツ には向かない**

CGM や コンテンツの変化が激しく、かつ そのコンテンツ の SEO が 大事な場合は厳しい  
SEO 関連 の ヘッダー は HTML 出なければならない (Google は JavaScript が 読めるらしいけど)  

JAMStack 要件 の 事前ビルド が、コンテンツの変化に追随できない場合に無理が生じる  
このようなケースでは SSR(Server Side Rendering) が 必要  

e.g.  
　ラップ・バトル アプリ で 対戦ルームを作り、  
　カスタムで名前や画像などを Twitter Card にして  
　ポストするような機能を作った場合   

とはいえ、何か他のケースは... 🤔

.img-left-rap-top[![](../contents/2019-jaws-days/images/08.jpg)]
.img-left-rap-vs[![](../contents/2019-jaws-days/images/09.jpg)]


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
- **JAMStack は ウェブサイト や アプリ を 構築するための新しい方法**  
  ⇒ より良いパフォーマンス、より高いセキュリティ、  
  　 より安価で容易なスケーリング、より良質な開発者エクスペリエンス

- **フロントも含めて、まるっとサーバーレス**  
  ⇒ 「CloudFront/S3 で～」、でなくアーキテクチャ、方法論として  

- **JAMStack と 名前が付き、認識されることで、伝わる**  
  ⇒ API Gateway と Lambda というのを使った REST API で～、  
  　 でなく "サーバレス" で REST API！、伝わる、JAMStack も これから   



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
class: appendix
### Appendix
**本イベント関連記事**
- [Serverless Meetup Tokyo 12 にて「サーバーレスなウェブフロントを実現する JAMStack」について発表をしました](https://riotz.works/articles/2019/05/27/made-presentation-about-jamstack-at-serverless-meetup-tokyo-12/)

**テーマ関連記事**
- [JAMStack、それはハイパフォーマンスなウェブフロントを実現するアーキテクチャ](https://riotz.works/articles/2019/01/23/jamstack-an-architecture-to-realize-fine-web-front/)
- [Riots.works での JAMStack の利用](https://riotz.works/articles/2019/01/29/how-jamstack-is-used-in-riots.works/)


---
count: false
class: bottom, center, eof
## EOF
![](../assets/riotz.png)
