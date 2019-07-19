name: Web-NFC の PWA で 簡単タイムレコーダー「ツカエタルヒの記録」
count: false
class: cover, center, middle
# Web-NFC の PWA で 簡単タイムレコーダー
# 「ツカエタルヒの記録」
.english[
  Web-NFC's PWA Simple Time Recorder "Tsukaetaruhi no kiroku"
]
.footer[[@勤怠を自動化する技術 LT Night](https://connpass.com/event/135463/) / 5 min]


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
## 😭私の現在の勤怠管理😱 .english[
  My current attendance management
]
---
### エクセルでサインして提出な！
- 指定フォーマットの Excel ファイルに手入力 😣

- 月末にサインして、上司のサインをもらう 😨

- 月初２営業日以内に PDF 化して事務へメール 🤯

- 事務が勤怠管理システムにデータを投入 😵

こんなことも  
　Excel を印刷、自分のサイン、PDF 化、上司へメール  
　上司が印刷、上司がサイン、PDF 化、私へメール  
　事務へ 上司のサイン付き PDF をメール...  
　これって、読めるのか！？  


---
### 当然、いろいろ と トラブる
- 毎日、手入力できない、忙しい、忘れる 😤

- 月初、上司が捕まらない、休めない 😰

- 今年の５月は 月初が ７日(火)！？　いつもより遅いので７日中に提出！😨

- 現在の有休残数がわからない、特に年度末は困る 😟 

- 有休残数を間違えられた！ 🤬


---
### 会社として、なんかないの？
- 社員証(IC カード) ＆ タッチ打刻機 ⇒ フロアに多数設置してるけどキミらは対象外な

- 社員証(IC カード) ＆ タッチ打刻機２ ⇒ フロアに１つ設置してるけどキミらは対象外な

- Web の 勤怠管理システム ⇒ タッチに連動してるし入力もできるけどキミはら見るだけな

- 社員証(IC カード) ＆ 入館ゲート ⇒ データ取ってるけどサビ残対策だけな

- あと、業務に関係ない機器の電源取得やネット接続は禁止な (ラズパイとか持ってくんなよ？)

※ 多くの社員は 社員証(IC カード) ＆ タッチ打刻機 です。  
　 たまたま私たちが特殊な勤怠管理が必要で Excel になっていること、ご了承ください。  


---
class: center, middle
## 「ツカエタルヒの記録」 <br /> Web-NFC の PWA で 簡単タイムレコーダー .english[
  Web-NFC's PWA Simple Time Recorder "Tsukaetaruhi no kiroku"
]

---
### せめても日々の時間記録は簡単に - 「ツカエタルヒの記録」
.center[
.resize-h320a[![](../contents/2019-attendance-tech-lt/images/01.png)]
.resize-h320a[![](../contents/2019-attendance-tech-lt/images/02.png)]
.resize-h320a[![](../contents/2019-attendance-tech-lt/images/03.png)]
.resize-h320a[![](../contents/2019-attendance-tech-lt/images/04.png)]
]
.footnote[
※ ログインボーナスは [るるてあ(@k_r_r_l_l_)](https://twitter.com/k_r_r_l_l_) さん の 肯定ペンギン を デモ用に使っています
]



---
class: center, middle
## “デモンストレーション” .english[
  Enjoying our short story
]



---
### 「ツカエタルヒの記録」機能概要
#### コンセプト： ユーザー側で手軽に勤務時間の管理が行える アプリ  
　  
**主な機能**
- NFC Tag のタッチで出勤時間と退勤時間を自動的に記録
- 毎日のログインボーナス！
- Web NFC に対応してない場合はタップでも記録可能

**今後の展望**
- リファクタリング ＆ 公開
- 記録データを Google スプレッドシート へ保存
- ログインボーナス/アワード の外部化による拡充  
※ [るるてあ(@k_r_r_l_l_)](https://twitter.com/k_r_r_l_l_) さん の 肯定ペンギン は デモ用のため公開時には変更されます


---
### 「ツカエタルヒの記録」システム概要
#### コンセプト： ユーザー側で手軽に勤務時間の管理が行える アプリ  
　  
**アーキテクチャ**
- **.marker[PWA (Progressive Web Apps)]** による 次世代アプリ仕様！！

**主な利用 技術/サービス**
- HTML/CSS/JavaScript

- Nuxt.js + TypeScript

- Web NFC API  
  ※ Suica などの FeliCa 系 カードは使えません  
  ※ 2019年7月現在、Android の Chrome のみで動作(要 Flag 設定)  

.resize-nfc[![](../contents/2019-attendance-tech-lt/images/05.png)]



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
