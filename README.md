# Portfolio

hirotatsuuu のポートフォリオサイトです。
[https://hirotatsuuu.github.io/Portfolio/](https://hirotatsuuu.github.io/Portfolio/)

## 開発環境
* Framework: Astro
* Language: TypeScript
* Styling: Tailwind CSS
* Deployment: GitHub Pages (GitHub Actions)

## 使用ツールについて

### nvm（Node Version Manager）とは
Node.jsのバージョンを複数管理するためのツールです。プロジェクトごとに異なるNode.jsのバージョンを簡単に切り替えることができます。

### Corepackとは
Node.js（v16.13.0以降）に標準で含まれている、パッケージマネージャー（pnpmやYarn）を管理する仕組みです。これを利用することで、npm install -g を使わずに、安全かつプロジェクトに最適なバージョンのpnpmを自動で利用・管理できます。

### pnpmとは
Node.jsの高速で効率的なパッケージマネージャーです。従来のnpmと比較して、ディスク容量を大幅に節約し、インストール速度が非常に速いという特徴があります。

## プロジェクト構成
```text
my-portfolio/
├── src/
│   ├── components/       # UI部品（使い回すパーツ）
│   │   ├── Header.astro  # 共通ヘッダー
│   │   ├── Footer.astro  # 共通フッター
│   │   └── Profile.astro # 自己紹介カード
│   ├── layouts/          # ページ全体の骨組み
│   │   └── Layout.astro  # headや共通スタイルなど
│   ├── pages/            # ルーティング（URLになる）
│   │   ├── index.astro   # トップページ (/)
│   │   └── about.astro   # 自己紹介ページ (/about)
│   └── styles/           # グローバルCSS
│       └── global.css
├── astro.config.mjs      # デプロイ設定など
└── package.json          # pnpm管理
```

## 開発・実行方法

### 1. wingetによるnvmのインストールとNode.jsの準備

Windowsの管理者権限でPowerShellまたはコマンドプロンプトを開き、以下のコマンドを実行してnvm（nvm-windows）をインストールします。

```powershell
winget install CoreyButler.NVMforWindows
```

インストール完了後、環境変数を反映させるために**端末（PowerShellなど）を一度完全に閉じて、再度開き直してください。**

端末を開き直したら、以下のコマンドでNode.jsのLTS（推奨版）をインストールして有効化します。
```powershell
nvm install lts
nvm use lts
```

### 2. pnpmの有効化（Corepackの利用）
Node.js環境が用意できたら、標準搭載されているCorepackを有効化し、pnpmを使用可能な状態にします。
```powershell
corepack enable
corepack prepare pnpm@latest --activate
```

### 3. 依存関係のインストール
```powershell
pnpm install
```

### 4. ローカルサーバーの起動
```powershell
pnpm run dev
```
起動後、ブラウザで http://localhost:4321/Portfolio/ にアクセスしてください。

## ビルド
```powershell
pnpm run build
```

## ライセンス
MIT