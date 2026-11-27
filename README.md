# site/ — bulota.jp

静的HTML+CSSのみ(JSなし)。ビルド不要で、各HTMLをブラウザで開けばそのまま表示される。

```
index.html    トップ(料金 #price / お問い合わせ #contact はこのページ内)
works.html    事例
about.html    事業者情報
privacy.html  プライバシーポリシー
styles.css    全ページ共通
assets/icon_clean.svg  favicon
```

ヘッダーとフッターは4ページに同じものを手で置いている。直すときは4ファイルとも直す。
フッターの「最終更新」も更新のたびに直す。

## 後で差し替える箇所(index.html 内にコメントあり)

| 箇所 | やること |
|---|---|
| 代表の顔写真 | `assets/ozaki.jpg` を置き、`#profile` のコメントを外す |
| 予約ページ | `#contact` のコメントを外してURLを入れる。冒頭のボタンの href も予約ページに替える |
| Googleフォーム | `#contact` のコメントを外して埋め込みコード(iframe)を入れる |
| ボタンの文言 | 予約URLが入ったら index.html 冒頭と works.html 末尾の「15分のヒアリングを相談する」を「予約する」に戻す |
| privacy.html | フォーム・予約を入れたら「外部サービスの利用」のコメントを外して表示する |

## デザイン

白地・濃い文字・差し色1色(`--accent`)。本文はスマホ17px / PC 18px。動き・写真・イラストは使わない。

## 書いてある事実について

掲載しているのは本人から受け取った内容だけ。数字・実績・お客様の声を足すときは、事実として確認できるものに限る。

変更前の旧LPは git タグ `backup-before-redesign-2026-11-27`(と `../site_backup_2026-11-27/`)に残してある。
