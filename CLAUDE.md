# TORAKO Portfolio - CLAUDE.md

## プロジェクト概要

TORAKO（AI時代のかわいいクリエイター）のポートフォリオサイト。
GitHub Pages でホスティング。`main` ブランチへの push で自動デプロイ。

- サイトURL: https://TORAKO123.github.io/
- X: https://x.com/toratorako123
- YouTube: https://youtube.com/@TORAKO-123

## 技術スタック

- 単一ファイル構成（`index.html`）
- HTML + CSS + vanilla JS のみ（外部ライブラリなし）
- Google Fonts: Zen Maru Gothic, Quicksand
- GitHub Actions でデプロイ（`.github/workflows/static.yml`）

## デザインルール

- カラーテーマ: パステルピンク × ラベンダー × クリーム
- フォント: 日本語は Zen Maru Gothic、英語は Quicksand
- アニメーション: fade-in（IntersectionObserver）、CSS animations
- レスポンシブ対応必須

## ギャラリー運用

- X の投稿 URL をギャラリーに追加する場合は `/embed-tweet` コマンドを使うこと
- 埋め込みは oEmbed API で取得する
- 挿入位置: `<!-- /gallery-grid -->` コメントの直前

## コミットルール

- コミットメッセージは日本語で書く
- push 前に必ずユーザーの確認を取る
