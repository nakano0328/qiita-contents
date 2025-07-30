# qiita-contents

Qiita の記事を管理するリポジトリ

## 概要

このリポジトリは[Qiita CLI](https://github.com/increments/qiita-cli)を使用して Qiita の記事を管理しています。記事の執筆、プレビュー、公開を効率的に行うことができます。

## セットアップ

### 1. リポジトリのクローン

```bash
git clone https://github.com/your-username/qiita-contents.git
cd qiita-contents
```

### 2. Qiita CLI のインストール

```bash
npm install -g @qiita/qiita-cli
```

### 3. Qiita アクセストークンの設定

1. [Qiita の設定ページ](https://qiita.com/settings/applications)でアクセストークンを発行
2. GitHub リポジトリの Secrets に`QIITA_TOKEN`として登録

## 使用方法

### 新しい記事の作成

```bash
npx qiita new article-title
```

### プレビューの起動

```bash
npx qiita preview
```

プレビューは http://localhost:8888 で確認できます。

### 記事の公開

記事を`public/`ディレクトリに配置して main ブランチに push すると、GitHub Actions が自動的に Qiita に公開します。

## 設定ファイル

### qiita.config.json

- `includePrivate: false` - 非公開記事は含めない
- `host: "localhost"` - プレビューサーバーのホスト
- `port: 8888` - プレビューサーバーのポート

## 自動公開

[`.github/workflows/publish.yml`](.github/workflows/publish.yml)により、main ブランチへの push 時に自動的に Qiita に記事が公開されます。

## 記事一覧

- [RAG（検索拡張生成）とは？仕組みからメリット、活用例までやさしく解説](public/rag-overview.md)

## 開発者向け情報

### 記事の管理

- 記事は`public/`ディレクトリに配置
- ファイル名は記事のタイトルに対応
- Front matter でメタデータを管理

### GitHub Actions

記事の自動公開には以下の権限が必要です：

- `contents: write`
- `QIITA_TOKEN`シークレット

## ライセンス

MIT License
