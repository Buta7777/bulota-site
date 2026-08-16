# site/ — Bulota公式LP

静的HTML+CSSのみ。ビルド不要で、`site/index.html` をブラウザで開けばそのまま表示される。

```
site/
  index.html
  styles.css
  assets/
    wordmark_Bulota.svg   ← ヒーローのワードマーク(要配置)
    icon_B_tail.svg       ← favicon / プロフィール写真の代役 / フッター(要配置)
```

## 後で差し替える箇所

| 箇所 | 場所 | やること |
|---|---|---|
| デモ動画 | `index.html` の `<!-- 7. デモ動画 -->` | コメント内の iframe を有効化して `VIDEO_ID` を差し替え、`.video-placeholder` の div を削除する |
| 代表の写真 | `index.html` の `<!-- 6. 代表プロフィール -->` | `assets/icon_B_tail.svg` の img を `assets/ozaki.jpg` に差し替える(コメントに手順あり) |
| noteリンク | `index.html` のフッター `<!-- ▼ noteのURLが決まったら -->` | `href` を自分のnoteのURLに差し替える(いまはnoteのトップ) |
| OGP画像 | `<head>` | 画像を用意したら `og:image` を足す |

## ヘッダー / フッターのメモ

- ヘッダーは `position: sticky` で常時上部固定。スマホ幅ではロゴとCTAだけを出し、
  ナビリンクは760px以上で表示する(1ページ構成なのでハンバーガーメニューは持たない)
- アンカーのズレ補正は `[id] { scroll-margin-top: calc(var(--header-h) + 16px) }` で一括。
  ヘッダーの高さを変えるときは `--header-h` を直せば補正も追従する
- ヘッダーの「料金」は料金カード(`.plans#price`)に飛ぶ。サービスと同じセクション内
- フッターは `#453A3E` の反転配色。**ワードマークが濃色版で暗背景に沈む場合**は、
  `styles.css` の `.footer-wordmark { filter: brightness(0) invert(1); }` の
  コメントを外すと白単色になる

## 書いてある事実について

掲載しているのは実在する内容だけ。導入社数・満足度・お客様の声・顧問料/月額など、
事実として確認できない数字や声は載せていない。追記するときも同じ基準で。

## 色とフォント

- メイン `#F6AEBE` / アクセント `#C9536F` / 文字 `#453A3E` / 背景 `#FDF1F4`
  (CSS冒頭の `:root` に変数として定義)
- 見出し英字 Fredoka + 本文 Noto Sans JP を Google Fonts から読み込む。
  オフラインで開くとフォントだけ標準のゴシックに落ちるが、レイアウトは崩れない
