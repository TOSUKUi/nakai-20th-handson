
---

# AIプロダクト開発ハンズオン – Canvas / Gemini CLI / 自由開発

スマホユーザーからエンジニアまで、AIツールを使って「動くプロダクト」を2時間で作る実践型ワークショップです。3つのアプローチから自分に合う方法を選んで進めましょう。

---

## はじめに

このハンズオンでは、AIを活用して実際にアプリやWebページ、スライドなどの成果物を作ります。初心者でも安心して参加できるよう、レベルに応じて3コースを用意しています。

* **[Canvasコース](#canvasコーススマホ非プログラマ向け)：** スマホ・非プログラマ向け。ブラウザだけで完結。
* **[Gemini CLIコース](#gemini-cliコースプログラマ向け)：** コード少し触れる方向け。ローカル環境構築＋ngrok公開。
* **[自由開発コース](#自由開発コース上級者向け)：** 上級者向け。Gemini API・n8n・LangChainなどを利用。

> 💡 2時間で動くものを作ることをゴールにしよう。完璧より「動く」ことを重視！

---

## Canvasコース（スマホ・非プログラマ向け）

ブラウザだけでAIと対話しながらHTMLページやUIを自動生成できます。インストール不要で、スマホでもそのまま使えます。

1. [Gemini Canvas](https://gemini.google.com/canvas) にアクセスして、Googleアカウントでログインします。

    [ChatGPT](https://chatgpt.com)で生成してもらってプレビュー機能でも可能。

2. 試しに以下のプロンプトを入力してみましょう：

   ```
   モバイル対応の自己紹介ページを作って。
   背景は淡い青で、中央にプロフィール画像を置き、
   名前・肩書き・SNSボタン（X・GitHub・メール）を配置してください。
   ```

3. 生成結果をプレビューし、修正指示を出してみよう。

   * 例：「ボタンを丸くして」「文字を中央寄せに」
   * 例：「背景色を白に」「フォントを太く」

4. 気に入ったらリンクを共有して完成！




### Gemini Canvasでできること

「画像を変換する」や「要約するアプリを作って」というとgeminiのAPIを自動で使ってAIアプリケーションを構築できる。

「写真をとって加工して」みたいなアプリも作れる

https://g.co/gemini/share/4a26471c4e29


---

## Gemini CLIコース（プログラマ向け）

Gemini CLIを使えば、AIが生成したコードをローカルで実行し、ngrokで公開できます。

### Windowsの場合（Chocolateyで構築）

```powershell
# Chocolateyのインストール
powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

# Node.jsのインストール（LTS推奨）
choco install nodejs --version="24.11.0"

# バージョン確認
node -v  # → v24.11.0
npm -v   # → 11.6.1

# ngrokのインストール
choco install ngrok

# ngrokトークン登録
# https://dashboard.ngrok.com/login でトークンを取得して登録
ngrok config add-authtoken <YOUR_TOKEN>
```

### macOS / Linuxの場合（nvm推奨）

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

```bash
ポート3000で動作するExpressアプリを作成。
/ に "Hello from Gemini CLI" を返すようにしてください。
```

```bash
npm install
npm run start  # → http://localhost:3000
```

### 公開（ngrok）

```bash
ngrok http 3000
```

表示されたURL（例：[https://xxxx.ngrok-free.app）を共有して公開完了です。](https://xxxx.ngrok-free.app）を共有して公開完了です。)

---

## 自由開発コース（上級者向け）

自分の好きな技術スタックでより高度なプロダクトを構築しましょう。

---

## 作るアプリケーションのアイデア集
- 自己紹介サイト
- ランダムおみくじ／サイコロメーカー
- ブラウザで動くストップウォッチ＋ラップ計測
- タスク整理カンバン
- カメラ＋フィルターアプリ

---

## まとめと次のステップ

このハンズオンでは「AIと一緒に作る」体験を重視しました。重要なのは、まず試してみること。動くものを作る過程でAIの特性が自然に理解できます。

* Canvas → 直感的に成果物を出す
* CLI → 環境構築とコード生成を学ぶ
* 自由開発 → 実務応用・外部連携

---
