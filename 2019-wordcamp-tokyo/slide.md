name: WordPress と SSG(Static Site Generator) が織りなす、WordPress ウェブフロントの新世界
count: false
class: eyecatch
![](../contents/2019-wordcamp-tokyo/images/eyecatch.jpg)
---
count: false
class: cover, center, middle
# WordPress と SSG が 織りなす
# WordPress ウェブフロントの新世界
.event-logo[[![](../assets/logo/wordcamp-tokyo-2019.png)](https://2019.tokyo.wordcamp.org/)]
.english[
  A further world of WordPress Web Fronts woven by WordPress and SSG .small[(Static Site Generator)]
]
.footer[[@WordCamp Tokyo 2019](https://2019.tokyo.wordcamp.org/) / 45 min]


---
count: false
class: preface, agenda, no-logo
### Agenda
1. WordPress ウェブフロント の 世界 .english[
  WordPress webfront world
]

2. ウェブフロント開発における潮流、JAMstack & SSG .english[
  Trends in webfront development, JAMstack and SSG .small[(Static Site Generator)]
]

3. WordPress ＋ SSG が 織りなす新世界 .english[
  A further world woven by WordPress + SSG
]

4. Headless WordPress CMS と その可能性 .english[
  Headless WordPress CMS and its possibilities
]

5. まとめ .english[
  Wrap-up
]



---
class: center, middle, no-logo
## About us
---
layout: false
class: no-logo
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
  .marker[**サーバーレスなサーバーサイド・エンジニア**]。 新しい技術が大好きで  
  試すためには目的を選ばない、IT好きで葉巻好き酒好きなだけの猫。

  アイデアを高速で形するアーキとして .marker[**サーバーレスが大のお気に入り**]。何かを作る時もサーバーレスでいけるか最初に考える。

  またフロントの技術として Vue.js/Nuxt.js の 高速な開発力に、  
  .marker[**すごいぜ Vue.js/Nuxt.js！！**] と、.marker[**JAMstack なフロントに興味津々**]。

  ウェブサービスやアプリ開発だけでなく Raspberry Pi などの電子工作や Slack などのチャットボットなどと、いろいろと手を出す。
]
.four.wide.column[]
.prof[
  .resize-w240[![](../bio/lulzneko/photo.jpg)]  
  .social[.fa[.fa-github[]] [@lulzneko](https://github.com/lulzneko)]  
  .social[.fa[.fa-twitter[]] [@lulzneko](https://twitter.com/lulzneko)]  
  .mail[.fa[.fa-envelope-o[]] lulzneko&#x40;riotz.works]  

  .small[
  主な発表歴
  - Developers Summit 2019
  - CloudNative Days Tokyo 2019
  - JAWS Days 2019
  - 東京 Node 学園祭 2019
  - Serverlessconf Tokyo 2018
  - JJUG CCC 2018
  - Serverlessconf Tokyo 2017
  ]
]

.footnote[
  ※ 発言や投稿は私的なものであり、所属する企業や組織とは関係ありません。  
  　 また Riotz.works は 開発チームの名称です。  
]]



---
class: center, middle, no-logo
## WordPress ウェブフロント の 世界 .english[
  WordPress webfront world
]
---
class: no-logo
### WordPress の 世界
- 豊富なプラグインとテーマによる高いカスタマイズ性が特徴

- 個人からビジネスまで幅広く使われている

- 言わずと知れた、世界でもっとも使われている .marker[CMS であり]、.marker[ウェブサイト でもある]

.img-wordpress[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/01.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/02.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/03.png)
]

---
class: no-logo
### WordPress の ウェブフロント = WordPress テーマ
- 豊富なテーマがテーマディレクトリにそろっている

- テーマによってブログサイトからコーポレートサイトまでとイメージがガラリと変わる

- もちろん、個人でも自由にテーマを開発することが可能！

.img-wordpress-theme[
  ![](../contents/2019-wordcamp-tokyo/images/02.png)
  ![](../contents/2019-wordcamp-tokyo/images/03.png)
  ![](../contents/2019-wordcamp-tokyo/images/04.png)
]
.small[
  テーマディレクトリ | WordPress.org - .url[https://ja.wordpress.org/themes/]  
  The Best WordPress Sites in the World | WordPress.org - .url[https://wordpress.org/showcase/]
]

---
class: no-logo
### WordPress テーマ 開発における考慮点
- 既存テーマのカスタマイズから入ると簡単 (e.g. 色変え、レイアウトの入れ替え...)
- 本格的にはテーマ･ファイル群を全部用意することで、まったく新しく作り出せる

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

HTML, CSS, JavaScript に加えて、PHP の 知識やスキルも必要となる  
もちろん WordPress 自体、たとえばディレクトリ構成や関数なども知る必要がある  
参考情報は多数あれど、テーマ ＝ ウェブフロント開発 は 意外と大変、打ち手はないか 🤔  

.img-wordpress[
  ![](../contents/2019-wordcamp-tokyo/images/06.png)
  ![](../contents/2019-wordcamp-tokyo/images/05.png)
  ![](../contents/2019-wordcamp-tokyo/images/07.png)
]

---
class: center, middle, no-logo
## ウェブフロント開発における潮流、JAMstack & SSG .english[
  Trends in webfront development, JAMstack and SSG .small[(Static Site Generator)]
]
---
class: no-logo
### JAMstack、そして SSG .small[(Static Site Generator)] とは
- JAMstack は "あらかじめ HTML 化された" ウェブサイトを配信する形式 の フロント開発技術

- 動的な要素(e.g. ユーザー投稿など) は Web API を利用し JavaScript で描画する

- "あらかじめ HTML 化された ウェブサイト" = 静的サイト を 作るために使うツールが SSG

.center[.img-jamstackconf[![](../contents/2019-javascript-matsuri/images/01.png)]]

---
class: no-logo
### JAMstack の 定義
定義: クライアントサイドJavaScript、再利用可能なAPI、構築済みのマークアップ が **ベース**
.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

- **クライアントサイド JavaScript**  
  HTTP リクエスト/レスポンスのようなダイナミックな処理は、  
  完全にクライアント上で実行されるようにする。（フレームワークやバニラなどは問わない）  

- **再利用可能な API**  
  全てのサーバサイド処理、DB処理は HTTPS で アクセスできる再利用可能な Web API にする。  
  カスタムメイドでも、サードパーティーでも問わない。

- .marker[**構築済みのマークアップ**]  
  テンプレート用のマークアップ = HTML は、サイトジェネレータ(= SSG) や ビルドツール で、  
  デプロイ時に事前ビルドし生成している 必要(should) がある。

---
class: no-logo
### JAMstack = SSG を使うことの メリット .small[(1/2)]
- **より良いパフォーマンス** ＆ **より安価で簡単なスケーリング**  
  HTML 生成の処理が不要で、すべて CDN へ 配置済みにできるため、CDN を フル活用できる

- **より高いセキュリティ**  
  HTML 生成処理 の オフライン化、  
  HTML のみの配信、CDN による  
  セキュリティの局所化と確保  

- **より良質な開発者エクスペリエンス**  
  データ と マークアップ の分離  
  開発ターゲットと責務の明確化  

.img-jamstack[![](../contents/2019-jaws-days/images/05.png)]

---
class: no-logo
### JAMstack = SSG を使うことの メリット .small[(2/2)]
- **より良いパフォーマンス** ＆ **より安価で簡単なスケーリング**  
  HTML 生成の処理が不要で、すべて CDN へ 配置済みにできるため、CDN を フル活用できる

- **より高いセキュリティ**  
  HTML 生成処理 の オフライン化、  
  HTML のみの配信、CDN による  
  セキュリティの局所化と確保  

.box[
- **より良質な開発者エクスペリエンス**  
  データ と マークアップ の分離  
  開発ターゲットと責務の明確化  
  
  .arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

  **WordPress テーマ開発の懸念点の**  
  **解決につながるのではないか！？**  
]

.img-jamstack[![](../contents/2019-jaws-days/images/05.png)]

---
class: no-logo
### 代表的な SSG
.ui.grid[
.nine.wide.column[.static-gen[
**サイト系**
- [Gatsby](https://www.gatsbyjs.org/)   - JavaScript, React, GraphQL

- [Gridsome](https://gridsome.org/) - JavaScript. Vue.js, GraphQL

**アプリ系**
- [Next.js](https://nextjs.org/)  - JavaScript, React

- [Nuxt.js](https://nuxtjs.org/)  - JavaScript, Vue.js
]]
.six.wide.column[
StaticGen - .url[.small[[https://www.staticgen.com](https://www.staticgen.com/)]]
.img-staitc-gen[![](../contents/2019-jaws-days/images/06.png)]
]]

.arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

**WordPress との 組み合わせ方は？**


---
class: center, middle, no-logo
## WordPress ＋ SSG が 織りなす新世界 .english[
  A further world woven by WordPress + SSG
]
---
class: no-logo
### WordPress と SSG の 組み合わせ方
- WordPress の REST API 経由で SSG と連携する

- GatsbyJS, Gridsome などは Plugin で 直接 WordPress へアクセス、完全に静的化

- Nuxt.js などは HTTP Client 経由で WordPress へ アクセス、動的な描画 (完全な静的化も可能)

.img-wordpress-ssg[
  ![](../contents/2019-wordcamp-tokyo/images/08.png)
  ![](../contents/2019-wordcamp-tokyo/images/09.png)
]

---
class: no-logo
### WordPress + GatsbyJS の 実装イメージ
.ui.grid[
.seven.wide.column[
#### `gatsby-config.js` .small[(一部抜粋)]
<pre class="prettyprint"><code class="javascript">module.exports = {
  plugins: [
    {
      resolve: 'gatsby-source-wordpress',
      options: {
        baseUrl: '[YOUR_WEBSITE_URL]',
        hostingWPCOM: false,
        protocol: 'https',
        useACF: false,
        auth: {},
        verboseOutput: false,
      }
    }
  ],
  ...
}
</code></pre>
]
.seven.wide.column[
#### gatsby-node.js .small[(一部抜粋)]
<pre class="prettyprint"><code class="html">exports.createPages = async ({ graphql, actions }) => {
  const { createPage } = actions
  const result = await graphql(`
    query {
      allWordpressPost {
        edges {
          node {
            id
            slug...
  `)
  const postTemplate = path.resolve(`./src/templates/post.js`)
  result.data.allWordpressPost.edges.forEach(edge => {
    createPage({
      path: edge.node.slug,
      component: slash(postTemplate),
      context: {
        id: edge.node.id,
        ...
}
</code></pre>
]]
.small[
  GatsbyCentral/gatsby-starter-wordpress -
  .url[https://github.com/GatsbyCentral/gatsby-starter-wordpress]
]

---
class: no-logo
### WordPress + Gridsome の 実装イメージ
.ui.grid[
.seven.wide.column[
#### `gridsome.config.js` .small[(一部抜粋)]
<pre class="prettyprint"><code class="javascript">module.exports = {
  plugins: [
    {
      use: '@gridsome/source-wordpress',
      options: {
        baseUrl: '[YOUR_WEBSITE_URL]',
        apiBase: 'wp-json',
        typeName: 'WordPress',
        perPage: 100,
        concurrent: 10
      }
    }
  ],
  templates: {
    WordPressPost: '/:year/:month/:day/:slug',
    WordPressTag: '/tag/:slug'
  },
  ...
}
</code></pre>
]
.seven.wide.column[
#### `Index.vue` .small[(一部抜粋)]
<pre class="prettyprint"><code class="html">&lt;template>
  &lt;Layout>
    &lt;ul class="post-list">
      &lt;li v-for="{ node } in $page.allWordPressPost.edges" :key="node.id">
        &lt;Post :post="node" />
      &lt;/li>
    &lt;/ul>
  &lt;/Layout>
&lt;/template>
&lt;page-query>
query Home ($page: Int) {
  allWordPressPost (page: $page, perPage: 10) @paginate {
    edges {
      node {
        id
        title
        path
        excerpt...
&lt;/page-query>
</code></pre>
]]
.small[
  gridsome/gridsome-starter-wordpress -
  .url[https://github.com/gridsome/gridsome-starter-wordpress]
]

---
class: no-logo
### WordPress ＋ SSG の メリット
- No.1 CMS である WordPress の エディター と コンテンツ管理 を そのままに活かせる

- ウェブフロント の JAMstack 化によるメリットを享受 .small[(パフォーマンス、スケーリング、セキュリティ)]

- ウェブフロント開発者 の "Better Developer Experience" .small[(データ と マークアップ の分離、責務の明確化)]

.center[
  .img-12[![](../contents/2019-wordcamp-tokyo/images/12.png)]
]

---
class: no-logo
### WordPress ＋ SSG がもたらすもの
- SSG は 比較的 技術習得がしやすく、新規の開発者が入りやすい

- JavaScript/Node.js 系 の フロントエンド技術者 が、そのままに参入できる

- WordPress と 密なテーマ開発 に加えて、SSG の ウェブフロント系が加わり すそ野が広がる

.img-11[
  ![](../contents/2019-wordcamp-tokyo/images/11.png)
]

.small[
  ※ SSG にも JAMstack Themes - .url[[https://JAMstackthemes.dev](https://JAMstackthemes.dev/)] のように多数のテーマが用意されている
]



---
class: center, middle, no-logo
## Headless WordPress CMS と その可能性 .english[
  Headless WordPress CMS and its possibilities
]
---
class: no-logo
### WordPress + SSG = "Better Developer Experience" 再考
.text-large-32[
  SSG により "Better Developer Experience" が もたらされたとして  
  技術スタックの観点から、それは "Better Developer Experience" か？  
]

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

- WordPress の環境構築は必要

- 運用の技術スタックも依然として必要

- むしろ、あまり必要としていなかった  
  Node.js が 追加  

結果的には技術スタックが増え、  
開発者の負担が増えているのではないか？  

.img-10[
  ![](../contents/2019-wordcamp-tokyo/images/10.png)
]

---
class: no-logo
### WordPress を Serverless .small[(Managed WordPress, WordPress SaaS)] にする
- WordPress の 実行基盤を Serverless、あるいは Managed や as a Service にする

- サービスとしての WordPress とし、所有ではなく利用することで構築や運用の負担をなくす

- コンテンツの作成と管理をサービスとしての WordPress 利用、ウェブフロントを SSG 構築にする

.center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

CMS として、コンテンツの作成と管理に特化したものは **Headless CMS** と呼ばれる  
WordPress を Headless CMS として扱い、ウェブフロントを SSG で JAMstack サイトにする  

技術スタックを増加させず、サービス利用によって構築･運用の負担を低減  
"Better Developer Experience" が 実現される、OK！  

**⇒ では、Serverless WordPress は Headless CMS と 成りうるのか**

---
class: no-logo
### 代表的な Headless CMS
.ui.grid[
.nine.wide.column[.static-gen[
- [Contentful](https://www.contentful.com/) - API Driven

- [GraphCMS](https://graphcms.com/) - API Driven, GraphQL

- [microCMS](https://microcms.io/) - API Driven, 日本製･日本語対応

.arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

最近注目を集め始めているが、まだまだ種類が少ない  
その注目も、まだエンジニアが中心と見える  
ユーザビリティにも、まだまだ課題がありそう  

**⇒ Serverless WordPress にも、勝機はありそうだ！**
]]
.six.wide.column[
headlessCMS - .url[.small[[https://headlesscms.org](https://headlesscms.org/)]]
.img-staitc-gen[![](../contents/2019-wordcamp-tokyo/images/01.png)]
]]

.footnote[※ ここでは Serverless(Managed, SaaS) の Headless CMS を対象としている]

---
class: no-logo
### Headless CMS としての WordPress の 可能性
**コンテンツを書くのは誰か？、誰が使うのか？**

- WordPress は 世界でもっとも使われている CMS

- 多くの情報が書籍やウェブサイトとして溢れる

- 使ったことがある人も多い

.arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

コンテンツの作成や管理において「WordPress に勝る CMS は、ない」と言っても過言ではない

Serverless な Headless CMS としての WordPress は、最高の CMS と言える  
それに加えて SSG で フロントを構築することで JAMstack サイトのメリットを享受でき  
また開発者フレンドリーな環境として、すべて良しの世界を描くことができる

---
class: no-logo
### Headless CMS としての WordPress 具体例: Shifter + SSG
**Shifter は Serverless な WordPress！**

- Shifter(= WordPress) が データソースの  
  　SSG プロジェクトを Netlify へ 配置する

- Shifter の ビルド時に、Netlify の Webhook 呼出し

- SSG で Shifter コンテンツをウェブサイト化

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

GatsbyJS や Gridsome などが WordPress を データソースにできるのを利用。  
Shifter が Webhooks と組み合わせてくれたことにより、SSG による サイト構築を実現。  

.img-webhooks[![](../contents/2019-shiftup-jp_getshifter-vol5/images/11.png)]

#### 参考
- [[Shifter Meetup] Shifterのユースケースと最新アップデート](https://speakerdeck.com/digitalcube/shifter-meetup-shifterfalseyusukesutozui-xin-atuhuteto)
- [Shifter Webhooksで Netlify上のGatsbyサイトにWordPressコンテンツをインポート](https://www.digitalcube.jp/shifter/4434/)


---
class: no-logo
### 新たな CMS、Headless WordPress SaaS + SSG の世界へ
- WordPress による、手軽なコンテンツ管理
- Shifter の WordPress SaaS によるセキュアな環境
- Shifter + SSG による "Better Developer Experience"

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-30[
  Shifter を WordPress の コンテンツの作成と管理 SaaS として使い、コスト削減

  ウェブ・フロントエンドの技術および技術者が、そのままに参入できる  
  次世代のサイト構築手法が生まれ SaaS 運用との相乗効果が期待される

  新たな CMS、.marker[Headless WordPress SaaS + SSG の 世界(= 市場)]が作られるだろう
]

**⇒ Shifter のような Serverless WordPress .small[(Managed WoradPress, WordPress as as Service)] の、更なる拡充も！**


---
class: center, middle, no-logo
## まとめ .english[
  Wrap-up
]
---
class: wrapup, no-logo
### まとめ .english[
  Wrap-up
]
- **JAMstack (= SSG 利用) な、サイトはメリットが大きい**  
  ⇒ パフォーマンス、スケーリング、セキュリティの向上が図れる  

- **WordPress を Headless CMS として使い、JAMstack のメリットを享受**  
  ⇒ ウェブ･フロントエンドの技術者も参入し WordPress の 世界が広がる  

- **.marker[Headless WordPress + JAMstack/SSG の 世界(= 市場) 創出へ]**  
  ⇒ WordPress SaaS による運用の負荷低減と  
  　 JAMstack/SSG によるモダン ウェブフロントの開発   



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
