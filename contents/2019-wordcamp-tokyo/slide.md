name: WordPress と SSG(Static Site Generator) が織りなす、WordPress ウェブフロントの新世界
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

2. ウェブフロント開発における潮流、SSG .small[(Static Site Generator)] .english[
  Trends in webfront development, SSG
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
class: center, middle, no-logo
## WordPress ウェブフロント の 世界 .english[
  WordPress webfront world
]
---
class: no-logo
### WordPress の 世界
- 言わずと知れた、世界でもっとも使われている CMS であり ウェブサイト でもある

- 豊富なプラグインとテーマによる高いカスタマイズ性が特徴

- 個人からビジネスまで幅広く使われている

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

.img-wordpress[
  ![](http://www.gifpng.com/300x200?text=テーマディレクトリ\nキャプチャ)
  ![](http://www.gifpng.com/300x200?text=ブログサイト例\nキャプチャ)
  ![](http://www.gifpng.com/300x200?text=企業サイト例\nキャプチャ)
]

.footnote[テーマディレクトリ | WordPress.org - .url[https://ja.wordpress.org/themes/]]

---
class: no-logo
### WordPress テーマ 開発における考慮点
- 既存テーマのカスタマイズから入ると簡単 (e.g. 色変え、レイアウトの入れ替え...)
- 本格的にはテーマ･ファイル群を全部用意することで、まったく新しく作り出せる

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

HTML, CSS, JavaScript に加えて、PHP の 知識やスキルも必要となる  
もちろん WordPress 自体、たとえばディレクトリ構成や関数なども  
参考情報は多数あれど、テーマ ＝ ウェブフロント開発 は 意外と大変、打ち手はないか 🤔  

.img-wordpress[
  ![](http://www.gifpng.com/300x180?text=ディレクトリ構成)
  ![](http://www.gifpng.com/300x180?text=テーマコード例)
  ![](http://www.gifpng.com/300x180?text=技術スタック)
]

---
class: center, middle, no-logo
## ウェブフロント開発における潮流、SSG .english[
  Trends in webfront development, SSG .small[(Static Site Generator)]
]
---
class: no-logo
### SSG(Static Site Generator) とは
- ウェブサイトを "あらかじめ HTML 化して" 配信する形式 の ウェブフロント開発技術

- 動的な要素(e.g. ユーザー投稿など) は Web API から JSON で受け取り JavaScript で描画

- SSG で作られるサイトは JAMstack と呼ばれ、ウェブフロントで話題になっているキーワード

.img-wordpress[
  ![](http://www.gifpng.com/400x400?text=SSGの実行イメージ)
]
.img-jamstackconf[![](../contents/2019-javascript-matsuri/images/01.png)]


---
class: no-logo
### SSG による ウェブフロント開発 = JAMstack のメリット
- **より良いパフォーマンス** ＆ **より安価で簡単なスケーリング**  
  HTML 生成の処理が不要で CDN へ 配置済みにできるため、CDN を フル活用できる

- **より高いセキュリティ**  
  HTML 生成処理 の オフライン化  
  HTML のみの配信、CDN による  
  セキュリティの局所化と確保  

- **より良質な開発者エクスペリエンス**  
  データ と マークアップ の分離  
  開発ターゲットと責務の明確化  
  
  .arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

  **WordPress テーマ開発の懸念点の**  
  **解決につながるのではないか！？**  

.img-jamstack[![](../contents/2019-jaws-days/images/05.png)]

---
class: no-logo
### 代表的な SSG
.ui.grid[
.nine.wide.column[.static-gen[
**サイト系**
- [Gatsby](https://www.gatsbyjs.org/)   - JavaScript, React, GraphQL

- [Gridsome](https://gridsome.org/) - JavaScript. Vue.js, GraphQL

- [Hexo](https://hexo.io/)     - JavaScript, EJS, Pug, Haml, Swig...

- [VuePress](https://vuepress.vuejs.org/) - JavaScript, Vue.js, Vue.js-OFFICIAL

**アプリ系**
- [Next.js](https://nextjs.org/)  - JavaScript, React

- [Nuxt.js](https://nuxtjs.org/)  - JavaScript, Vue.js
]]
.six.wide.column[
StaticGen - .url[.small[[https://www.staticgen.com](https://www.staticgen.com/)]]
.img-staitc-gen[![](../contents/2019-jaws-days/images/06.png)]
]]

.arrow-left-150[.text-arrow-medium[.fa[.fa-angle-double-down[]]]]

**WordPress との 組み合わせは？ 相性は？**


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

- Nuxt.js などは HTTP Client 経由で WordPress へ アクセス、動的な描画 と 静的化 の 両方が可能

.img-wordpress[
  ![](http://www.gifpng.com/300x280?text=完全静的化のイメージ)
  ![](http://www.gifpng.com/300x280?text=動的描画のイメージ)
]

---
class: no-logo
### WordPress ＋ SSG の メリット
- No.1 CMS である WordPress の エディター と コンテンツ管理 を そのままに活かせる

- ウェブフロント の JAMstack 化によるメリットを享受 .small[(パフォーマンス、スケーリング、セキュリティ)]

- ウェブフロント開発者 の "Better Developer Experience"

.img-wordpress[
  ![](http://www.gifpng.com/300x280?text=WordPress の Headless CMS 図)
  ![](http://www.gifpng.com/300x280?text=Better Developer Experience)
]

---
class: no-logo
### "Better Developer Experience" がもたらすもの
- SSG は 比較的 技術習得がしやすく、新規の開発者が入りやすい

- JavaScript/Node.js 系 の フロントエンド技術者 が、そのままに参入できる

- WordPress と 密なテーマ開発 に加えて、SSG の ウェブフロント系が加わり すそ野が広がる

.img-wordpress[
  ![](http://www.gifpng.com/300x280?text=PHP WP Theme PG)
  ![](http://www.gifpng.com/300x280?text=WordPress)
  ![](http://www.gifpng.com/300x280?text=JS SSG PG)
]

---
class: no-logo
### 具体例: WordPress + GatsbyJS
[アーキ図とコード]
---
class: no-logo
### 具体例: WordPress + Gridsome
[アーキ図とコード]



---
class: center, middle, no-logo
## Headless WordPress CMS と その可能性 .english[
  Headless WordPress CMS and its possibilities
]
---
class: no-logo
### WordPress + SSG = Headless CMS の 世界
---
class: no-logo
### 代表的な Headless CMS
---
class: no-logo
### Headless CMS としての WordPress は？
---
class: no-logo
### Headless CMS = WordPress + SSG での考慮点
---
class: no-logo
### Serverless WordPress(Managed WordPress) という考え方
---
class: no-logo
### 具体例: Shifter + SSG
---
class: no-logo
### Serverless WordPress + SSG がもたらす CMS の 新世界



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
