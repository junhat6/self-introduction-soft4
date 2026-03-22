# カラーテーマ定義

デジタル庁デザインシステム（`@digital-go-jp/design-tokens v1.1.9`）のトークンをベースに選定。

## 方針

- ニュートラル（グレー・白・黒）を主軸に、シンプルで読みやすい構成
- アクセントカラーはブルー1色のみ。デジタル庁らしい清潔感を出す
- 装飾的な色は使わない

---

## 採用カラー一覧

### テキスト

デジタル庁が定義するニュートラルの4段階に準拠。

| 役割 | トークン | HEX | 使う場所 |
|---|---|---|---|
| プライマリー | `--color-neutral-solid-gray-900` | `#1a1a1a` | 見出し、本文 |
| セカンダリー | `--color-neutral-solid-gray-536` | `#767676` | 補足説明、ラベル |
| ターシャリ | `--color-neutral-solid-gray-420` | `#949494` | 注記、プレースホルダー |
| リンク（通常） | `--color-primitive-blue-1000` | `#00118f` | aタグ（global.css 実測値） |
| リンク（ホバー） | `--color-primitive-blue-900` | `#0017c1` | a:hover（ボタンと逆方向） |

### 背景

デジタル庁サイトと同様に白をメインベースとし、gray-50 は一部セクションのアクセントのみに使用。

| 用途 | トークン | HEX | 使う場所 |
|---|---|---|---|
| メイン背景 | `--color-neutral-white` | `#ffffff` | body・ほとんどのセクション |
| サブ背景 | `--color-neutral-solid-gray-50` | `#f2f2f2` | 一部セクション（視覚的リズムのため交互に使う） |

### ボーダー・区切り線

divider.css（GitHub 実装）より。デジタル庁はグレーの文字色と同じトークンを区切り線にも使用している。

| 用途 | トークン | HEX | 使う場所 |
|---|---|---|---|
| 区切り線（標準） | `--color-neutral-solid-gray-420` | `#949494` | セクション間の hr、カード枠 |
| 区切り線（強め） | `--color-neutral-solid-gray-536` | `#767676` | ナビ下線など目立たせたい境界 |

### アクセント（ブルー）

デジタル庁の button.css 実装（GitHub）より取得。ボタン通常色は blue-900。

| 用途 | トークン | HEX | 使う場所 |
|---|---|---|---|
| アクセント（通常） | `--color-primitive-blue-900` | `#0017c1` | セクション左ボーダー、強調、ボタン通常色 |
| アクセント（ホバー） | `--color-primitive-blue-1000` | `#00118f` | ホバー時 |
| アクセント（薄め） | `--color-primitive-blue-50` | `#e8f1fe` | スキルチップの背景など |

---

## CSS変数への対応（style.cssに書く形）

```css
:root {
  /* テキスト（デジタル庁ニュートラル4段階準拠） */
  --text-main:    #1a1a1a;  /* gray-900  プライマリー          */
  --text-sub:     #767676;  /* gray-536  セカンダリー          */
  --text-muted:   #949494;  /* gray-420  ターシャリ            */

  /* 背景 */
  --bg-page:      #ffffff;  /* white     メイン背景            */
  --bg-alt:       #f2f2f2;  /* gray-50   サブ背景（交互）      */

  /* ボーダー（divider.css 実装より） */
  --border:       #949494;  /* gray-420  区切り線・カード枠     */
  --border-strong:#767676;  /* gray-536  ナビ下線など強め       */

  /* アクセント（button.css より: blue-900 が通常色） */
  --accent:       #0017c1;  /* blue-900  装飾・左ボーダー・ボタン */
  --accent-hover: #00118f;  /* blue-1000 ホバー時（ボタン）      */
  --accent-light: #e8f1fe;  /* blue-50   チップ背景など薄め      */

  /* リンク（global.css より: 通常は blue-1000、ホバーで blue-900） */
  --link:         #00118f;  /* blue-1000 リンク通常              */
  --link-hover:   #0017c1;  /* blue-900  リンクホバー            */
}
```

---

## 参考：デジタル庁トークンソース

- パッケージ: `@digital-go-jp/design-tokens@1.1.9`
- ファイル: `dist/tokens-simple.css`
- URL: https://unpkg.com/@digital-go-jp/design-tokens@1.1.9/dist/tokens-simple.css
