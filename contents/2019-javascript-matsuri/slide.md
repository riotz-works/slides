name: Gridsome で作る JAMStack な サーバーレス Web Front
count: false
class: cover, center, middle
# Gridsome で作る 
# JAMStack な サーバーレス Web Front
.event-logo[[![](../assets/logo/js-matsuri.png)](https://javascript-fes.doorkeeper.jp/events/90894)]
.english[
  JAMStack Serverless Web Front developed by Gridsome
]
.footer[[@初夏のJavaScript祭 in メンバーズキャリア](https://javascript-fes.doorkeeper.jp/events/90894) / 20 min]


---
count: false
class: preface, agenda
### Agenda
1. JAMStack とは .english[
  What is JAMStack
]
2. アーキテクチャ紹介 .english[
  Introducing the JAMStack architecture
]
3. Gridsome で作る JAMStack サイト .english[
  JAMStack site developed by Gridsome
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
## JAMStack とは .english[
  What is JAMStack
]
---
### JAMStack .small[(ジャムスタック)]？
- 最近 話題になりつつあり、フロントエンドやウェブの開発などで見聞きする機会が多いかも

- 2018年 の Qiita Advent Calendar に『[JAMstack Advent Calendar 2018](https://qiita.com/advent-calendar/2018/jamstack)』登場

- [Serverless Advent Calendar 2018](https://qiita.com/advent-calendar/2018/serverless) にも！  
　『[GridsomeをCodePipeLine + CodeBuild でDeployするServerlessなBlog](https://blog.seike460.com/2018/12/20/gridsome-deploy-serverless/)』 - [@seike460](https://qiita.com/seike460)
.img-jamstackconf[![](../contents/2019-javascript-matsuri/images/01.png)]


---
### JAMStack って、なに？ .small[(1/2)]
JAMStack 公式サイト - .url[[https://jamstack.org](https://jamstack.org/)]
.img-jamstack-def[![](../contents/2019-jaws-days/images/01.png)]
- ウェブサイト や アプリ を 構築するための新しいアーキテクチャ
- **クライアントサイドJavaScript**、**再利用可能なAPI**、**構築済みのマークアップ** が ベースとなる
- **J**avaScript, **A**PIs, **M**arkup の 頭文字 **JAM** の Stack
---
### JAMStack って、なに？ .small[(2/2)]
JAMStack 公式サイト - .url[[https://jamstack.org](https://jamstack.org/)]
.img-jamstack-def[![](../contents/2019-jaws-days/images/01.png)]
- ウェブサイト や アプリ を 構築するための新しいアーキテクチャ
- .marker[**クライアントサイドJavaScript**]、**再利用可能なAPI**、**構築済みのマークアップ** が ベースとなる
- .marker[**J**avaScript], **A**PIs, **M**arkup の 頭文字 **.marker[J]AM** の Stack
.img-matsuri[![](../contents/2019-javascript-matsuri/images/02.png)]


---
### どうすると JAMStack？
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
### どうすると JAMStack？ - アーキテクチャのイメージ
.img-jamstack-all[![](../contents/2019-jaws-days/images/05.png)]

.footnote[
  The JAM Stack - .url[[https://speakerdeck.com/biilmann/the-jam-stack](https://speakerdeck.com/biilmann/the-jam-stack)] (一部修正)  
]


---
### JAMStack の メリット
- **より良いパフォーマンス**  
  CDN を 活用することによる高速化  
  HTML 生成の省略による高速化  

- **より安価で簡単なスケーリング**  
  CDN の スケーラビリティを享受

- **より高いセキュリティ**  
  Web API 化 による 攻撃対象の局所化  
  HTML 生成処理 の オフライン化

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
### JAMStack を 構築する 静的サイトジェネレータ .small[(1/2)]
定義: **構築済みのマークアップ**、HTML は .marker[サイトジェネレータ や ビルドツール で] 事前生成する  
SSG、Static Site Generator と 呼ばれるツールを使うことが多い

.ui.grid[
.six.wide.column[
StaticGen - .url[.small[[https://www.staticgen.com](https://www.staticgen.com/)]]
.img-staitc-gen[![](../contents/2019-jaws-days/images/06.png)]
]
.nine.wide.column[.static-gen[
**サイト系**
- [Gatsby](https://www.gatsbyjs.org/)   - JavaScript, React, GraphQL

- [Hexo](https://hexo.io/)     - JavaScript, EJS, Pug, Haml, Swig...

- [VuePress](https://vuepress.vuejs.org/) - JavaScript, Vue.js, Vue.js-OFFICIAL

- [Gridsome](https://gridsome.org/) - JavaScript. Vue.js, GraphQL

**アプリ系**
- [Next.js](https://nextjs.org/)  - JavaScript, React

- [Nuxt.js](https://nuxtjs.org/)  - JavaScript, Vue.js
]]]

---
### JAMStack を 構築する 静的サイトジェネレータ .small[(2/2)]
定義: **構築済みのマークアップ**、HTML は .marker[サイトジェネレータ や ビルドツール で] 事前生成する  
SSG、Static Site Generator と 呼ばれるツールを使うことが多い

.ui.grid[
.six.wide.column[
StaticGen - .url[.small[[https://www.staticgen.com](https://www.staticgen.com/)]]
.img-staitc-gen[![](../contents/2019-jaws-days/images/06.png)]
]
.nine.wide.column[.static-gen[
**サイト系**
- [Gatsby](https://www.gatsbyjs.org/)   - JavaScript, React, GraphQL

- [Hexo](https://hexo.io/)     - JavaScript, EJS, Pug, Haml, Swig...

- [VuePress](https://vuepress.vuejs.org/) - JavaScript, Vue.js, Vue.js-OFFICIAL

- [Gridsome](https://gridsome.org/) - JavaScript. Vue.js, GraphQL

**アプリ系**
- [Next.js](https://nextjs.org/)  - JavaScript, React

- [Nuxt.js](https://nuxtjs.org/)  - JavaScript, Vue.js

.text-large-32[**SSG も JavaScript/Node.js 製が多数！！**]
.img-matsuri2[![](../assets/logo/js-matsuri.png)]
]]]



---
class: center, middle
## アーキテクチャ紹介 .english[
  Introducing the JAMStack architecture
]
---
### Nuxt.js アーキテクチャ - アプリ・パターン
.img-arch-02[![](../contents/2019-jaws-days/images/arch-02.png)]
---
### Gridsome アーキテクチャ - ウェブサイト・パターン
.img-arch-03[![](../contents/2019-jaws-days/images/arch-03.png)]



---
class: center, middle
## Gridsome で作る JAMStack サイト .english[
  JAMStack site developed by Gridsome
]
---
### Gridsome とは
Gridsome 公式サイト - .url[[https://gridsome.org/](https://gridsome.org/)]
.img-border[![](../contents/2019-javascript-matsuri/images/03.png)]
.img-release[![](../contents/2019-javascript-matsuri/images/05.png)]
- Vue.js ベースのウェブサイトやアプリを作るためのフレームワーク
- JAMStack サイト や PWA を容易に作ることができる
- 速い！ "builds ultra performance automatically", "almost perfect page speed scores by default."  
  構築済み HTML、コード分割、PRPL パターン、プリフェッチ、プログレッシブ画像、Vue.js SPA...



---
### Gridsome w/GraphQL
GraphQL で、あらゆるデータソースを "静的化 = JAMStack" にして、さまざまな環境へデプロイできる

.img-graphql[![](../contents/2019-javascript-matsuri/images/04.png)]


---
layout: false
### Gridsome の 特徴
.ui.grid[
.seven.wide.column[
- **ローカル開発が簡単**  
  JavaScript の エコシステムでできていて、ローカルで開発可能、コード変更は即座にホットリロードして開発を支援する  

- **デフォルトで高速**  
  PRPL パターンで各ページに高速機能を組み込み、デフォルトでほぼ完璧なページスピードスコアを出す  

- **PWA レディ**  
  静的 PWA を生成、重要な HTML/CSS/JS のみ最初にロード、以降はプリフェッチ  
]
.seven.wide.column[
- **JAMStack を 構築**  
  .marker[Web の 未来は JAMStack]、Gridsome は 驚くほど高速でモダンな Web エクスペリエンスを生み出す  

- **シンプルで安全なデプロイ**  
  ファイルのみのサイトで構成、全体を CDN にデプロイでき、数千から数百万のリクエストを容易に処理する  

- **SEO フレンドリー**  
  静的 HTML としてロードされた後に Vue.js に変換される。これにより検索エンジンはクロールでき、それでいて Vue.js の SPA としてすべての機能を利用することがでる  
]]


---
layout: false
### Gridsome で サイト構築 .small[(1/3)]
Node.js v8.3+ 必須  
プロジェクト構築は繰り返しやらないので、今回は `npx` で CLI を実行  
プロジェクト名は `samples-gridsome` とした

<pre class="prettyprint"><code class="console">
$ npx @gridsome/cli create samples-gridsome

npx: 55個のパッケージを26.283秒でインストールしました。
❯ Clone https://github.com/gridsome/gridsome-starter-default.git 5.7s
❯ Update project package.json 0.08s
❯ Install dependencies 800.09s

  - Enter directory cd samples-gridsome
  - Run gridsome develop to start local development
  - Run gridsome build to build for production
</code></pre>

.footnote[**参考:** [Getting started - Gridsome: .url[https://gridsome.org/docs]](https://gridsome.org/docs)]

---
layout: false
### Gridsome で サイト構築 .small[(2/3)]
プロジェクトを起動し `http://localhost:8080/` へ アクセス  
シンプルなページだが [Home] と [About] を爆速で行き来できる！！  
後は `/src/components`, `/src/layouts`, `/src/pages` に `.vue` ファイルを追加して開発  

.ui.grid[
.nine.wide.column[
<pre class="prettyprint"><code class="console">
$ cd samples-gridsome
$ yarn gridsome develop

Gridsome v0.6.3
...(省略)
Bootstrap finish - 5.07s


 DONE  Compiled successfully in 7144ms 18:47:23

 Site running at:         http://localhost:8080/
 Explore GraphQL data at: http://localhost:8080/___explore
</code></pre>
]
.five.wide.column[
.resize-w500[![](../contents/2019-javascript-matsuri/images/06.png)]
.img-score[![](../contents/2019-javascript-matsuri/images/07.png)]
]]

---
layout: false
### Gridsome で サイト構築 .small[(3/3)]
GraphQL の例 (.small[Plugin by [zefman/gridsome-source-instagram](https://github.com/zefman/gridsome-source-instagram) / Photo by [桃にゃんさん(.url[@ameshossumomo]) • Instagram](https://www.instagram.com/ameshossumomo/)])
.ui.grid[
.nine.wide.column[
<pre class="prettyprint"><code class="langue-html">
&lt;template>
  &lt;Layout>
    &lt;span v-for="edge in $page.cats.edges" :key="edge.node.id">
      &lt;g-image :src="edge.node.display_url" class="photo" />
    &lt;/span>
  &lt;/Layout>
&lt;/template>

&lt;page-query>
query {
  cats: allInstagramPhoto {
    edges {
      node {
        id
        display_url
}}}}
&lt;/page-query>
</code></pre>
]
.five.wide.column[
.resize-w500[![](../contents/2019-javascript-matsuri/images/08.png)]
.img-playground[![](../contents/2019-javascript-matsuri/images/09.png)]
]]


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

  e.g. Riotz.works サイトは Gridsome 製 .small[(v0.3.5 の頃から)]  
  .url[[https://riotz.works](https://riotz.works/)]  

- **ウェブアプリ の フレーム**  
  Web API に アクセスでデータが扱える範囲のもの  

  e.g. ラップ・バトル アプリ を Nuxt.js の SSG で開発  
  動画中継を API 利用に回すことで静的サイトでも実現  
  .url[[https://riotz.works/rap-tap-app](https://riotz.works/rap-tap-app/)]  

.img-left-riotz[![](../contents/2019-jaws-days/images/07.png)]
.img-left-rap-top[![](../contents/2019-jaws-days/images/08.jpg)]
.img-left-rap-vs[![](../contents/2019-jaws-days/images/09.jpg)]

---
### 銀の弾丸ではない
**SEO/OGP 重視 で CGM(Consumer Generated Media) や 変化の激しいコンテンツ には向かない**

CGM や コンテンツの変化が激しく、かつ そのコンテンツ の SEO/OGP が 大事な場合は厳しい  
SEO/OGP 関連 の ヘッダー は HTML 出なければならない (Google は JavaScript が 読めるらしいけど)  

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

- **Gridsome をはじめ、JavaScript は JAMStack に強い！**  
  ⇒JAMStack は JavaScript 祭り、素晴らしいツールがたくさんある  

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
count: false
class: bottom, center, eof
## EOF
![](../assets/riotz.png)
