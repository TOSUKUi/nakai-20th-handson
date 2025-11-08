


# 2025 中井研20周年イベント バイブコーディングプロダクト開発ハンズオン

このハンズオンは、実際に世間で騒がれている「バイブコーディング」について、より理解を深めるべく、AIツールを使って「動くプロダクト」を2時間程度で作ってみる実践型ワークショップ。

参加者のレベルに合わせて三つほどのルートを用意しているので、どれかを選んで始める。

## はじめに

このハンズオンでは、AIを活用して実際にアプリやWebページ、スライドなどの成果物を作ることがゴール。

初心者でも安心して参加できるよう、レベルに応じて3コースを用意している。

- コース1. 非プログラマ向け。「Canvas」を使いブラウザだけで完結するバイブコーディング。
- コース2. ターミナルやコードを少し触れる方向け。Gemini CLIを使った実践バイブコーディング。
- コース3. 上級者向け。特に制約はなく、時間内にプロダクトを何か作る。

> 💡 2時間で動くものを作ることをゴールに。完璧より「動く」ことを重視する！

## コース1.スマホ・非プログラマ向けブラウザだけで完結するコース

### Canvasとは？
Canvasは、近年のバイブコーディング・トレンドの中でも、特に「手軽さ」と「UI自動生成」に振り切ったツール。

「画像を変換する」や「要約するアプリを作って」というとGemini(ChatGPT)の画面内でアプリを自動で構築し、 インタラクティブに触れる状態で公開してくれる機能。

ブラウザだけでAIと対話しながらHTMLページやUIを自動生成可能。インストール不要で、スマホでもそのまま使える。

### Gemini Canvasでできること

> 実例


### AIツールも作成可能

APIを自動で使ってAIアプリケーションを構築できる。

「写真をとって加工して」みたいなアプリも作れる

https://g.co/gemini/share/4a26471c4e29


### Canvasを使う

1. ツールを選ぶ
   1. [Gemini Canvas](https://gemini.google.com/canvas) にアクセスして、Googleアカウントでログインします。

   2. [ChatGPT](https://chatgpt.com)のプレビュー機能でも可能。

2. 試しに以下のプロンプトを入力

   ```
   モバイル対応の自己紹介ページを作って。
   背景は淡い青で、中央にプロフィール画像を置き、
   名前・肩書き・SNSボタン（X・GitHub・メール）を配置してください。
   ```

3. 生成結果をプレビューし、修正指示を出してみよう。

   * 例：「ボタンを丸くして」「文字を中央寄せに」
   * 例：「背景色を白に」「フォントを太く」

4. 気に入ったらリンクを共有して完成！



> このコースの人はこの段階で作業を開始しても大丈夫ですし、次のGemini CLIコースの話を聞いても大丈夫です！

## コース2. Gemini CLIコース（プログラマ向け）
Canvasが「ブラウザ完結型」のバイブコーディングだとしたら、Gemini CLIは「開発環境統合型」のバイブコーディングである。

普段エンジニアが使うターミナル（CUI）上でAIと対話し、サーバーサイドのコード生成や環境構築を強力にサポートさせる。

より実践的な「AIとのペアプログラミング」を体験する。

### 実演

https://gemini.google.com/app

### 環境構築
#### Windowsの場合（Chocolateyで構築）

```powershell
# Chocolateyのインストール
powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

# Node.jsのインストール（LTS推奨）
choco install nodejs --version="24.11.0"

# バージョン確認
node -v  # → v24.11.0
npm -v   # → 11.6.1

```

#### macOS / Linuxの場合（nvm推奨）

既に入っていたり、インストール方法に哲学がある人は必ずしも従わなくてもよい
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts
nvm use --lts
node -v && npm -v
```

### Gemini CLIのセットアップ

```bash
npm install -g @google/gemini-cli
gemini  # 初回ログインでブラウザが開きます
```

### アプリを作ってみよう

gemini cliを開いた時に表示される入力欄に以下を入力

```bash
ポート3000で動作するExpressアプリを作成。
/ に "Hello from Gemini CLI" を返すようにしてください。
```

```bash
npm install
npm run start  # → http://localhost:3000
```

### (Webサーバーの場合)公開（ngrok）

```bash
# ngrokのインストール
# windowsの場合
choco install ngrok

# macの場合
brew install ngrok


# ngrokトークン登録
# https://dashboard.ngrok.com/login でトークンを取得して登録
ngrok config add-authtoken <YOUR_TOKEN>

ngrok http 3000 (ポートは自分のアプリのターミナル表示みる)
-> URLが表示される
```

表示されたURL（例：[https://xxxx.ngrok-free.app](https://xxxx.ngrok-free.app)を公開する


## 自由開発コース（上級者向け）

自分の好きな技術スタックでより高度なプロダクトを構築する。

触ったことがないようなものにトライしてみるのもよい！


## 作るアプリケーションのアイデア集
- 自己紹介サイト
- ランダムおみくじ／サイコロメーカー
- ブラウザで動くストップウォッチ＋ラップ計測
- タスク整理カンバン
- カメラ＋フィルターアプリ

