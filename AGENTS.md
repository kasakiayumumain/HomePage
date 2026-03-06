# Repository Guidelines

## プロジェクト構成とモジュール配置
このリポジトリはビルド不要の静的サイトです（HTML/CSS/Vanilla JS）。

- ルートHTML: `index.html`, `services.html`, `works.html`, `flow.html`, `faq.html`, `company.html`, `contact.html`, `privacy.html`
- スタイル: `assets/css/style.css`
- スクリプト: `assets/js/main.js`
- 画像: `assets/img/`（施工事例画像は `assets/img/works/`）

共通デザインは `style.css`、共通動作は `main.js` に集約してください。

## 開発・確認コマンド
コンパイル工程はありません。ローカルサーバーで確認します。

- `python3 -m http.server 8080` : リポジトリ直下でローカル配信
- `http://localhost:8080/index.html` を開く : 動作確認
- `npx --yes prettier@3 --check "**/*.{html,css,js,md}"` : 任意の整形チェック

VS Code を使う場合は Live Server でも問題ありません。

## コーディング規約と命名
- インデントは 2 スペース（HTML/CSS/JS）
- ファイル名は小文字を基本（必要に応じて kebab-case）
- セマンティックHTMLを優先し、`aria-*`、`alt`、見出し階層を適切に保つ
- 再利用可能なクラス設計を優先し、過度なインラインスタイルは避ける
- JavaScript はフレームワークを使わず、既存実装方針に合わせる

## テスト方針
自動テストは未導入です。PR前に手動確認を実施してください。

- 全ページがエラーなく表示される
- ナビゲーションとアクティブ表示がPC/スマホで正しい
- FAQアコーディオンが開閉する
- 問い合わせフォームの必須入力と完了表示（`?submitted=1#thanks`）が機能する
- CTA（問い合わせ、LINE、電話リンク）が動作する

## コミット・PRルール
この作業環境では Git 履歴を参照できないため、以下を推奨します。

- コミット形式: `type(scope): summary`
  - 例: `feat(contact): improve mobile cta visibility`
- 1コミット1目的を意識して小さく分ける
- PRには目的、変更ファイル、確認結果、PC/スマホのスクリーンショットを添付
- プレースホルダー変更（LINE ID、Formspree ID、地図URL、住所）を明記

## セキュリティと設定注意
機密情報や個人情報はコミットしないでください。以下はプレースホルダーのまま管理します。

- `@YOUR_LINE_ID`
- `https://formspree.io/f/YOUR_ID`
- `YOUR_MAP_EMBED_URL`

公開前チェックで実値に差し替えてください。
