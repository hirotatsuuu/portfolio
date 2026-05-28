# portfolio

おたつのポートフォリオサイト
[https://hirotatsuuu.github.io/portfolio/](https://hirotatsuuu.github.io/portfolio/)

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
src/
├── assets/      # 画像などの静的アセット
├── components/  # 再利用可能なUIコンポーネント
│   ├── About.astro
│   ├── Connect.astro
│   ├── Experience.astro
│   ├── Footer.astro
│   ├── Hero.astro
│   └── Youtube.astro
├── data/        # コンテンツのデータ管理
│   ├── ja.js    # 日本語コンテンツ
│   ├── en.js    # 英語コンテンツ
│   └── sns.js   # SNS・YouTubeリンクデータ
├── layouts/     # ページ全体のレイアウト
├── pages/       # 各ページ
└── styles/      # グローバルCSS
```

## カスタマイズ方法
1. コンテンツの編集
テキストやプロフィール情報を変更する場合は、src/data/ 以下のファイルを開いてください。

ja.js / en.js: サイト内のテキスト、タイトル、キャッチコピー

sns.js: SNSのリンク先やアイコン定義

2. 新しいセクションの追加
src/components/ に新しい .astro ファイルを作成し、src/pages/index.astro でインポート・呼び出しを行ってください。

3. YouTube動画の更新
最新動画を自動表示するために、src/components/Youtube.astro 内の iframe の src パラメータ（list=...）を、自身のプレイリストIDに合わせて書き換えてください。

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
起動後、ブラウザで http://localhost:4321/portfolio/ にアクセスしてください。

## ビルド
```powershell
pnpm run build
```

## ライセンス
MIT