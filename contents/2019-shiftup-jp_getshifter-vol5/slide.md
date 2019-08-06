name: Shifter ＋ SSG(Static Site Generator) が生み出す、新しい WordPress の世界
count: false
class: cover, center, middle
# Shifter＋SSG.small[(Static Site Generator)] が生み出す、
# 新しい WordPress の世界
.event-logo[[![](../assets/logo/shifter-jp.png)](https://eventregist.com/e/0if9nERXstQg)]
.english[
  New WordPress world created by Shifter + SSG
]
.footer[[@Shiftup! JP_Getshifter Vol5](https://eventregist.com/e/0if9nERXstQg) / 20 min]


---
count: false
class: preface, agenda
### Agenda
1. Shifter が もたらした、新世界 .english[
  New world brought by Shifter
]
2. Shifter ＋ SSG が 生み出す、さらなる新世界 .english[
  A further world created by Shifter + SSG
]
3. Shifter + SSG の 可能性 .english[
  Possibility of Shifter + SSG
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
class: center, middle
## Shifter が もたらした、新世界 .english[
  New world brought by Shifter
]
---
### WordPress の 世界
- 言わずと知れた、世界でもっとも使われている CMS

- 豊富なプラグインとテーマによる高いカスタマイズ性

- 個人からビジネスまで広く使われる柔軟さと拡張性

.img-wordpress[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/01.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/02.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/03.png)
]

---
### WordPress の 困りごと .small[(1/2)]
.hidden-wordpress2[
- セキュリティ対策 と 継続的なアップデート
- 監視 と パフォーマンスの最適化
- テーマのカスタマイズや作成には HTML, CSS, JavaScript に加え PHP を含めた技術力
]
.img-wordpress2[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/04.png)
]

---
### WordPress の 困りごと .small[(2/2)]
- セキュリティ対策 と 継続的なアップデート
- 監視 と パフォーマンスの最適化
- テーマのカスタマイズや作成には HTML, CSS, JavaScript に加え PHP を含めた技術力

.img-wordpress2[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/04.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/05.png)
  WordPress が リリースされた 2004~2005年頃は PHP の人気がとても高かった。
  (Java, C, C++ に次ぐ４位)

  近年は他言語の台頭により、JavaScript と同じ水準に。

  フロントエンド開発に PHP の技術者を求めることが難しくなってきているとも言える。
]


---
### Shifter、サービス利用としての WordPress
- WordPress を SaaS としてのサービス提供
- WordPress インスタンスを必要な時だけ利用する Serverless なアーキテクチャ
- WordPress サイト の 静的化 と CDN 配信による 高パフォーマンスなコンテンツ配信
.img-wordpress3[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/06.png)
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/07.png)  
  .small[.url[https://speakerdeck.com/digitalcube/shifter-kai-fa-falsewu-tai-li-san-zhong-falseshen-qi-bian]]
]

---
### Shifter が もたらした 新世界１、Serverless WordPress
- WordPress の インスタンスを必要な時だけ起動する

- 必要な時だけ使うことでセキュリティの向上が図れる

- フルマネージドによる継続的なアップデート

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

WordPress 運用の大きな困りごとであった  
"セキュリティ対策 と 継続的なアップデート" を  
Serverless = フルマネージド という形で解決！  

安心して安全に利用できる WordPress を提供

.img-wordpress3[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/08.png)  
  .small[.url[https://speakerdeck.com/digitalcube/shifter-kai-fa-falsewu-tai-li-san-zhong-falseshen-qi-bian]]
]


---
### Shifter が もたらした 新世界２、JAMStack WordPress .small[(1/2)]
WordPress サイト を 静的化し CDN から配信 = JAMStack  
⇒ 最近 話題になりつつある、ウェブサイト や アプリ を 構築するための新しいアーキテクチャ  
.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

- **より良いパフォーマンス**  
  HTML 事前生成 と CDN 活用による高速化

- **より安価で簡単なスケーリング**  
  CDN の スケーラビリティを享受

- **より高いセキュリティ**  
  WordPress 本体非公開による攻撃対象の局所化

- **より良質な開発者エクスペリエンス**  

.img-wordpress3[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/09.png)  
  .small[.url[https://cloudacademy.com/blog/wordpress-cloud-hosting-shifter/]]
]


---
### Shifter が もたらした 新世界２、JAMStack WordPress .small[(2/2)]
WordPress サイト を 静的化し CDN から配信 = JAMStack  
⇒ 最近 話題になりつつある、ウェブサイト や アプリ を 構築するための新しいアーキテクチャ  
.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

- **より良いパフォーマンス**  
  HTML 事前生成 と CDN 活用による高速化

- **より安価で簡単なスケーリング**  
  CDN の スケーラビリティを享受

- **より高いセキュリティ**  
  WordPress 本体非公開による攻撃対象の局所化

- .marker[**より良質な開発者エクスペリエンス**]  
  .face-wordpress3[🤔]

.img-wordpress3[
  ![](../contents/2019-shiftup-jp_getshifter-vol5/images/09.png)  
  .small[.url[https://cloudacademy.com/blog/wordpress-cloud-hosting-shifter/]]
]



---
class: center, middle
## Shifter ＋ SSG が 生み出す、さらなる新世界 .english[
  A further world created by Shifter + SSG
]
---
### JAMStack の 考え と Shifter の JAMStack WordPress について
#### JAMStack の 要件
- ダイナミックな処理は、完全にクライアント上で実行されるようにする
- 全てのサーバサイド処理、DB 処理は HTTPS で アクセスできる再利用可能な Web API にする
- HTML は サイトジェネレータ で 事前ビルドし生成している 必要(should) がある

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

#### Shifter, JAMStack WordPress
- WordPress を そのまま HTML 化する
- レイアウトについては WordPress Theme
- サーバーサイド処理が、DB 処理が  
  HTML 生成と分離できてないのではないか？


.img-wordpress4[
  ![](../contents/2019-jaws-days/images/05.png)  
  .small[.url[https://speakerdeck.com/biilmann/the-jam-stack] (一部修正)]
]

---
### WordPress Theme、それは "Better Developer Experience" ？
#### JAMStack の メリット "より良質な開発者エクスペリエンス" は 満たせているか？

- プログラムとデータとレイアウトが一体となっているため厳しい

- いわゆる HTML テンプレートの編集と同じになってしまう

- データ と レイアウト を 分離しない限り "より良質な開発者エクスペリエンス" は 満たせない

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-32[
  WordPress Theme 技術に加え、.marker[JAMStack 技術でも開発できるようにしたい]
  Vue.js(Gridsome, Nuxt.js)、React(GatsbyJS, Next.js) などを使いたい
]


---
### Shifter Webhooks ＋ SSG .small[(Static Site Generator)]
- Shifter を データソースとする  
  　SSG プロジェクトを Netlify へ 配置

- Shifter の ビルド時に、Netlify の Webhook 呼出し

- SSG で Shifter コンテンツをウェブサイト化

.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

SSG、具体的には Gridsome や GatsbyJS などは WordPress を データソースとして利用できます。  
それを Shifter が Webhooks と組み合わせてくれたことにより、SSG による サイト構築が実現！


.img-webhooks[![](../contents/2019-shiftup-jp_getshifter-vol5/images/11.png)]

.footnote[
#### 参考
- [[Shifter Meetup] Shifterのユースケースと最新アップデート](https://speakerdeck.com/digitalcube/shifter-meetup-shifterfalseyusukesutozui-xin-atuhuteto)
- [Shifter Webhooksで Netlify上のGatsbyサイトにWordPressコンテンツをインポート](https://www.digitalcube.jp/shifter/4434/)
]


---
class: center, middle
## Shifter + SSG の 可能性 .english[
  Possibility of Shifter + SSG
]
---
### WordPress の "Better Developer Experience"
#### WordPress で コンテンツ作成と管理
- No.1 CMS！ WordPress の コンテンツ作成と管理が素晴らしい
- ウェブや書籍など多くの情報があり使ったこともある人も多い

#### Shifter で WordPress を Headless CMS の SaaS として扱う
- Shifter の WordPress SaaS による安心安全を享受する
- Shifter による静的サイト生成はあるが、敢えて Headless CMS として使う ⇒ SSG 利用

#### SSG で WordPress の ウェブフロントを作る
- ウェブフロントには React や Vue.js を ベースとした JAMStack の良い開発技術がある
- データ と UI/UX の分離、JAMStack の "より良質な開発者エクスペリエンス" を 実現する

**⇒ JAMStack のコンテンツ管理を見ていると Headless CMS の潮流を感じるが、**  
**　 CMS として考えると結局のところ WordPress が優秀で、その SaaS、Shifter が望ましい**  

.img-headlesscms[![](../contents/2019-shiftup-jp_getshifter-vol5/images/10.png)]


---
### 新たな CMS、Headless WordPress SaaS + SSG の世界へ
- WordPress による、手軽なコンテンツ管理
- Shifter の WordPress SaaS によるセキュアな環境
- Shifter + SSG(Static Site Generator) による "Better Developer Experience"
.arrow-left-center[.text-arrow-large[.fa[.fa-angle-double-down[]]]]

.text-large-30[
  Shifter を WordPress の コンテンツの作成と管理 SaaS として使う  
  人材育成のハードルを下げ運用のコストや負荷を減らすことができる

  ウェブ・フロントエンドの技術および技術者が、そのままに参入できる  
  次世代のサイト構築手法が生まれ SaaS 運用との相乗効果が期待される

  新たな CMS、.marker[Headless WordPress SaaS + SSG の 世界(= 市場)]が作られるだろう
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
- **Shifter は WordPress SaaS として、WordPress の 困り事を解決**  
  ⇒ セキュリティ対策 と 継続的なアップデート  
  　 監視 と パフォーマンスの最適化

- **Shifter + SSG により WordPress Theme でない ウェブフロントを構築**  
  ⇒ ウェブ・フロントエンドの技術および技術者が、そのままに参入  

- **.marker[Headless WordPress SaaS + SSG/JAMStack の 世界(= 市場) 創出へ]**  
  ⇒ WordPress SaaS による運用の負荷低減と  
  　 SSG/JAMStack によるモダン ウェブフロントの開発   



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
- [Shiftup! JP_Getshifter Vol3！ 振り返り、Shifterのヘッドレス CMS 化に思いを馳せる](https://riotz.works/articles/lulzneko/2019/04/06/think-of-shifters-headlesscms-nize-on-shiftup-vol3/)
- [Shiftup! JP_Getshifter Vol3！ にて「JAMStack なサーバーレス・ウェブフロント」について発表](https://riotz.works/articles/lulzneko/2019/04/05/made-presentation-about-jamstack-at-shiftup-vol3/)
- [Shiftup! JP_Getshifter Vol3！ 参加レポート](https://riotz.works/articles/lulzneko/2019/04/03/take-seminar-on-shiftup-vol3/)

**テーマ関連記事**
- [JAMStack、それはハイパフォーマンスなウェブフロントを実現するアーキテクチャ](https://riotz.works/articles/2019/01/23/jamstack-an-architecture-to-realize-fine-web-front/)
- [Go_SaaS 三種の神器オンボーディングセミナー 1 〜東京〜 参加レポート](https://riotz.works/articles/lulzneko/2019/07/09/take-seminar-on-go-saas1-in-tokyo/)
- [Riots.works での JAMStack の利用](https://riotz.works/articles/2019/01/29/how-jamstack-is-used-in-riots.works/)



---
count: false
class: bottom, center, eof
## EOF
![](../assets/riotz.png)
