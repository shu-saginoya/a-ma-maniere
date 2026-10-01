# A ma maniere Webサイト

洋服のお直し・お仕立てを行う「A ma maniere」の公式サイトです。

## 利用技術

静的サイトとして構築し、Cloudflare Pagesで配信。

- Astro
- TypeScript
- Tailwind CSS

## プロジェクト構成

```text
/
├── public/            静的アセット（favicon等）
├── src/
│   ├── layouts/       共通レイアウト
│   ├── pages/         ルーティング対象のページ
│   └── styles/        グローバルスタイル（Tailwind）
└── astro.config.mjs
```

## 開発コマンド

| コマンド            | 内容                               |
| ------------------- | ---------------------------------- |
| `pnpm install`      | 依存パッケージのインストール       |
| `pnpm dev`          | ローカル開発サーバーの起動         |
| `pnpm build`        | 本番用ビルド（`./dist/`に出力）    |
| `pnpm preview`      | ビルド結果のローカルプレビュー     |
| `pnpm format`       | Prettierによるコード整形           |
| `pnpm format:check` | フォーマット崩れのチェック（CI用） |

## デプロイ

GitHubリポジトリへのpushをトリガーに、Cloudflare Pagesが自動ビルド・デプロイを行う構成です。

- ビルドコマンド: `pnpm build`
- 出力ディレクトリ: `dist`
- 本番ドメイン: `a-ma-maniere.jp`
