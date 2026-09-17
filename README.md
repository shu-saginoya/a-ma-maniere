# A ma maniere Webサイト

洋服のお直し・お仕立てを行う「A ma maniere」の公式サイトです。Astro + TypeScript + Tailwind CSS による静的サイトとして構築し、Cloudflare Pages で配信します。

詳細な仕様は [docs/SPEC.md](./docs/SPEC.md)、作業計画は [docs/PLAN.md](./docs/PLAN.md) を参照してください。

## プロジェクト構成

```text
/
├── public/            静的アセット（favicon等）
├── src/
│   ├── layouts/       共通レイアウト
│   ├── pages/         ルーティング対象のページ
│   └── styles/        グローバルスタイル（Tailwind）
├── docs/              仕様書・作業計画書
└── astro.config.mjs
```

## 開発コマンド

| コマンド               | 内容                               |
| ---------------------- | ---------------------------------- |
| `npm install`          | 依存パッケージのインストール       |
| `npm run dev`          | ローカル開発サーバーの起動         |
| `npm run build`        | 本番用ビルド（`./dist/`に出力）    |
| `npm run preview`      | ビルド結果のローカルプレビュー     |
| `npm run format`       | Prettierによるコード整形           |
| `npm run format:check` | フォーマット崩れのチェック（CI用） |

## デプロイ

GitHubリポジトリへのpushをトリガーに、Cloudflare Pagesが自動ビルド・デプロイを行う構成です。

- ビルドコマンド: `npm run build`
- 出力ディレクトリ: `dist`
- 本番ドメイン: `a-ma-maniere.jp`（DNS移行完了後に接続）
