# Astro プロフィール

日本語のシンプルな1ページプロフィールサイトです。Astroと通常のCSSのみを使用し、外部UIライブラリ・外部フォント・ブラウザー用JavaScriptは不要です。スマートフォンとPCに対応しています。

## ローカル起動

Node.js **22.12.0以上の偶数バージョン**（推奨: Node.js 24 LTS）とnpm 9.6.5以上を用意してください。

ZIPを解凍し、プロジェクトフォルダーで実行します。

```bash
cd astro-profile
npm install
npm run dev
```

ターミナルに表示されるURL（通常は http://localhost:4321 ）を開きます。通常の停止は `Ctrl+C` です。バックグラウンド起動になった場合は `npm exec astro dev stop` で停止できます。

```bash
npm run build    # dist/ に静的サイトを生成
npm run preview  # ビルド結果をローカルで確認
```

## プロフィールの変更

- `src/pages/index.astro` 冒頭の `profile`、`skills`、`links` を編集します。名前・文章・スキル・リンクはダミーです。
- 画像は `public/` に置き、`profile.avatar` をファイル名（例: `avatar.jpg`）に変更します。画像を変更したら `img` の `alt` も本人を説明する文章に変更してください。
- ロゴの `TY` と `public/favicon.svg` も自分のイニシャルに合わせて変更できます。
- 見た目は同じファイル末尾の `<style>` で変更できます。
- フッターの年はビルド時の年になります。

## GitHubへのpush

GitHubで**空のリポジトリ**を作成してください（README・.gitignore・Licenseは追加しません）。GitのインストールとGitHubへの認証を済ませ、プロジェクトフォルダーで実行します。

```bash
git init
git add .
git commit -m "Create Astro profile page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

`YOUR_USERNAME` と `YOUR_REPOSITORY` を自分の値に置き換えてください。`package-lock.json` はコミットし、`node_modules/`・`dist/`・`.astro/` は `.gitignore` で除外します。

GitHubへのpushはソースコードの保存です。Web公開には別途ホスティングの設定が必要です。GitHub Pagesで公開する場合は `astro.config.mjs` の `site` と（リポジトリ配下の公開なら）`base` の設定、およびデプロイ用ワークフローを追加してください。

## 構成

```text
astro-profile/
├── public/
│   ├── avatar.svg
│   └── favicon.svg
├── src/pages/index.astro
├── .gitignore
├── astro.config.mjs
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md
```

Astroのセットアップ要件: [公式ドキュメント](https://docs.astro.build/en/install-and-setup/)
