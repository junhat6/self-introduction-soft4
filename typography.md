# タイポグラフィ定義

デジタル庁デザインシステム タイポグラフィページをもとに選定。
参照：https://design.digital.go.jp/dads/foundations/typography/

---

## フォントファミリー

| 用途 | フォント | CSSトークン |
|---|---|---|
| 本文・見出し（サンセリフ） | Noto Sans JP | `--font-family-sans` |
| コード（等幅） | Noto Sans Mono | `--font-family-mono` |

デジタル庁公式の CSS 記述例：

```css
body { font-family: 'Noto Sans JP', -apple-system, BlinkMacSystemFont, sans-serif; }
code { font-family: 'Noto Sans Mono', monospace; }
```

### 読み込み方法（Google Fonts CDN）

`index.html` の `<head>` に以下を追加する：

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;700&family=Noto+Sans+Mono:wght@400;700&display=swap" rel="stylesheet">
```

`wght@400;700` は N（Normal）と B（Bold）の2ウェイトだけ読み込む指定。
不要なウェイトを読み込むとページが重くなるので必要最小限にする。

---

## 書体の太さ（font-weight）

デジタル庁は2段階のみ使用。

| 識別子 | font-weight | 用途 |
|---|---|---|
| N | `400`（normal） | 本文・補足 |
| B | `700`（bold） | 見出し・強調 |

---

## フォントサイズ（font-size）

| サイズ（px） | 用途 |
|---|---|
| 48〜64 | Display：視覚的インパクト重視の大見出し |
| 16〜45 | Standard：見出し・本文の主要サイズ |
| 14 | 最小サイズ。フッターなど制約がある箇所のみ。**14px未満は原則禁止** |

---

## 行高（line-height）

| line-height | 用途 |
|---|---|
| 1.0（100%） | ボタンなど1行UIコンポーネント |
| 1.4（140%） | 大きめ見出し |
| 1.5（150%） | 見出し・本文の最低ライン |
| 1.6（160%） | 一般的な本文 |
| 1.7（170%） | 読みやすさ・心理的負荷軽減を重視した本文 |
| 1.75（175%） | 170%と用途同じ。グリッド幅・フォントサイズに応じて使い分け |

> **注意**：CSSでは `%` ではなく単位なし数値（`1.7` など）で指定する。

---

## 文字間隔（letter-spacing）

フォントサイズに応じて変わる。

| フォントサイズ | letter-spacing |
|---|---|
| 45px 以上 | `0` |
| 36px | `0.01em` |
| 26px 以下（本文・UI系） | `0.02em` |

---

## このページで使うスタイルの対応表

デジタル庁のテキストスタイル名（`Std-16N-170` のような形式）から、
このページの各要素に適用するスタイルを選定した。

| 要素 | スタイル名 | size | weight | line-height | letter-spacing |
|---|---|---|---|---|---|
| 名前（Hero大見出し） | `Std-32B-150` | 32px | 700 | 1.5 | 0.01em |
| セクション見出し（h2） | `Std-20B-150` | 20px | 700 | 1.5 | 0.02em |
| サブ見出し（h3） | `Std-17B-170` | 17px | 700 | 1.7 | 0.02em |
| 本文（p） | `Std-16N-170` | 16px | 400 | 1.7 | 0.02em |
| ナビリンク | `Oln-16B-100` | 16px | 700 | 1.0 | 0.02em |
| ラベル・補足 | `Std-14N-130` | 14px | 400 | 1.3 | 0 |
| コードスニペット | `Mono-16N-150` | 16px | 400 | 1.5 | 0 |

---

## CSS変数への対応（style.cssに書く形）

```css
:root {
  --font-sans: 'Noto Sans JP', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'Noto Sans Mono', monospace;
}
```

---

## 参考：デジタル庁ページ

- タイポグラフィ概要：https://design.digital.go.jp/dads/foundations/typography/
- テキストスタイル一覧：https://design.digital.go.jp/dads/foundations/typography/text-style/
