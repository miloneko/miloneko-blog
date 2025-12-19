# miloneko-blog

Hugo + Void テーマを使用したブログサイト

## 📝 コンテンツ追加方法

### 1. 新しい投稿を作成する

#### 方法1: 手動でファイルを作成

1. `content/posts/` ディレクトリに新しいMarkdownファイルを作成
2. ファイル名は `投稿タイトル.md` または `投稿タイトル-日付.md` 形式（例: `aws-learning-2025-12-20.md`）

#### 方法2: Hugoコマンドを使用（推奨）

```bash
hugo new posts/投稿タイトル.md
```

### 2. 投稿ファイルの構造

投稿ファイルは以下の形式で記述します：

```markdown
+++
title = '投稿タイトル'
date = 2025-12-20T10:00:00+09:00
draft = false
tags = ['タグ1', 'タグ2']
+++

ここから本文を記述します。

## 見出し2

本文の内容...

### 見出し3

さらに詳細な内容...
```

#### フロントマター（ファイル上部の設定）

- **title**: 投稿のタイトル（必須）
- **date**: 投稿日時（必須、形式: `YYYY-MM-DDTHH:MM:SS+09:00`）
- **draft**: 下書きかどうか（`true` = 非公開、`false` = 公開）
- **tags**: タグの配列（例: `['Daily', 'Learning', 'AWS']`）

### 3. よく使うタグ

- `Daily` - 日常の記録
- `Learning` - 学習記録
- `AWS` - AWS関連
- `Go` - Go言語関連
- `Infrastructure` - インフラ関連

必要に応じて新しいタグを追加できます。

### 4. Markdown記法

#### 見出し

```markdown
# 見出し1（通常は使わない）
## 見出し2
### 見出し3
#### 見出し4
```

#### リスト

```markdown
- 箇条書き1
- 箇条書き2
  - ネストした項目

1. 番号付きリスト1
2. 番号付きリスト2
```

#### コードブロック

````markdown
```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```
````

#### リンク

```markdown
[リンクテキスト](https://example.com)
```

#### 画像

```markdown
![画像の説明](/images/画像ファイル名.jpg)
```

画像は `static/images/` ディレクトリに配置してください。

#### 強調

```markdown
**太字**
*斜体*
`コード`
```

### 5. Aboutページの更新

`content/about/index.md` を編集して自己紹介を更新できます。

### 6. ビルドとプレビュー

#### 開発サーバーでプレビュー

```bash
hugo server -D
```

ブラウザで `http://localhost:1313` にアクセス

- `-D` オプション: 下書き（`draft: true`）の投稿も表示

#### 本番用ビルド

```bash
hugo
```

`public/` ディレクトリに静的ファイルが生成されます。

### 7. ディレクトリ構造

```
miloneko-blog/
├── content/
│   ├── posts/          # 投稿ファイル
│   │   ├── daily-test.md
│   │   └── learning-test.md
│   └── about/
│       └── index.md    # Aboutページ
├── static/
│   └── images/         # 画像ファイル
│       └── avatar.jpg
├── hugo.toml           # 設定ファイル
└── public/             # ビルド出力（自動生成）
```

### 8. メニュー構成

現在のメニュー構成：
- **Home** - トップページ
- **Posts** - 投稿一覧
- **Tags** - タグ一覧
- **About** - 自己紹介ページ

メニューの変更は `hugo.toml` の `[[menus.main]]` セクションで設定できます。

### 9. よくある質問

**Q: 投稿を非公開にしたい**
A: フロントマターの `draft = true` に設定

**Q: 投稿の日付を変更したい**
A: フロントマターの `date` を編集

**Q: タグを追加・変更したい**
A: フロントマターの `tags = ['タグ1', 'タグ2']` を編集

**Q: 画像を追加したい**
A: `static/images/` に画像を配置し、Markdownで `![説明](/images/ファイル名.jpg)` と記述

### 10. 参考リンク

- [Hugo公式ドキュメント](https://gohugo.io/documentation/)
- [Markdown記法ガイド](https://www.markdownguide.org/)
- [Voidテーマ](https://github.com/Daucloud/hugo-theme-void)