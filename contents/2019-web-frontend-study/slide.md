name: JAMstack/PWA アーキテクチャの紹介
count: false
class: cover, center, middle
# JAMstack/PWA アーキテクチャの紹介
.english[
  Introduction to JAMstack/PWA Architecture
]
.footer[@ウェブフロント勉強会 2019.11 [CLOSED] / 10 min<br /> .small[__\* A generalized material for publicizing based on slides at time of presentation__]]


---
### アーキテクチャ全体イメージ
.center[
  .img-arch[![](../contents/2019-web-frontend-study/images/01.png)]
]


---
### JAMstack
- ウェブサイトやアプリを構築するための新しいアーキテクチャ
- クライアントサイドJavaScript･再利用可能なAPI ･構築済みのマークアップで構成
- **J**avaScript, **A**PIs, prerendered-**M**arkup の Stack で JAMstack

SSG(Static Site Generator) と呼ばれるツールを使い UI 要素を可能な限り 静的 HTML 化、  
動的要素はブラウザ上から JavaScript で API 呼び出しし、クライアント上で描画。  
対してサーバー側でHTML生成は SSR(Server Side Rendering) と呼び JAMstack でない。  

CDN に 全てを配置、パフォーマンス や スケール、  
セキュリティのメリットを享受できる。  
またプログラマの役割分担が明確で開発性が良く  
近年注目されているアーキテクチャ  

.img-jamstack[![](../contents/2019-web-frontend-study/images/02.png)]


---
### PWA
- ウェブサイトをネイティブアプリのような UI/UX にする次世代規格
- Google が中心で策定し Microsoft も参画、Apple の対応が待たれる
- インストール、オフライン動作、プッシュ通知、Bluetooth、GPS などが使える

Web App Manifest により PWA を宣言しアプリ化  
Service Worker API で キャッシュやオフライン対応、  
HTML5 APIs で ネイティブの機能を利用して実現する。  

Outlook.com が  
PWA 対応し話題  

.img-pwa[
  ![](../contents/2019-web-frontend-study/images/03.png)
  ![](../contents/2019-web-frontend-study/images/04.png)  
  左はブラウザ、右は PWA 
]
.img-outlook[![](../contents/2019-web-frontend-study/images/05.png)]


---
### Nuxt.js
- Vue.js 系 の フレームワークで、以下の３タイプのサイトを生成できる
- Statically Generated、SPA.small[(Single Page Application)]、SSR.small[(Server Side Rendering)]
- HTML/CSS/JS を１ファイルにまとめるので開発しやすい

Vue.js は ウェブサイトやアプリを作るためのコア機能に絞られ  
柔軟で深い実装ができる反面、初期設定やコンポーネントの導入  
プラグインの設定と様々な準備が必要となり意外と敷居が高い。  

Nuxt.js は Vue.js 開発で必要となるであろう機能や設定を  
オールインワンで提供済みにしておいてくれるほか、  
`asyncData()` や `fetch()` などの非同期処理のための機能もある。  
PWA Plugin と SPA ビルドを使い JAMstack な PWA が作れる。  

.img-vue[![](../contents/2019-web-frontend-study/images/06.png)]


---
### Links
| Site name             | URL                                                               |
|:----------------------|:------------------------------------------------------------------|
| JAMstack              | https://jamstack.org                                              |
| StaticGen             | https://www.staticgen.com                                         |
|                       |                                                                   |
| Progressive Web Apps  | https://developers.google.com/web/progressive-web-apps            |
| Progressive web apps  | https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps |
| Web App Manifest      | https://developer.mozilla.org/docs/Web/Manifest                   |
| Service Worker API    | https://developer.mozilla.org/docs/Web/API/Service_Worker_API     |
| What Web Can Do Today | https://whatwebcando.today                                        |
|                       |                                                                   |
| Nuxt.js               | https://nuxtjs.or                                                 |
| Vue.js                | https://vuejs.org                                                 |
| Gridsome              | https://gridsome.org                                              |


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
