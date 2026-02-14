# AGENTS.md

## ギャラリー追加エージェント

X（Twitter）の投稿 URL が共有された場合、以下のワークフローを自動で実行する。

### トリガー

ユーザーが X の投稿 URL（`x.com` または `twitter.com` のステータス URL）を共有し、ギャラリーへの追加を依頼したとき。

### ワークフロー

1. `/embed-tweet <URL>` コマンドを実行する
2. oEmbed API (`https://publish.twitter.com/oembed?url=<URL>&dnt=true&lang=ja`) から埋め込み HTML を取得する
3. `index.html` の `<!-- /gallery-grid -->` コメント直前に gallery-item を追加する
4. 投稿内容に基づいてタグ（item-tag）と説明（item-label）を適切に設定する
5. 変更内容をユーザーに報告し、コミット・プッシュの指示を待つ

### gallery-item テンプレート

```html
<div class="gallery-item">
  <div class="embed-wrapper">
    <!-- oEmbed API から取得した blockquote -->
  </div>
  <div class="item-label">
    <span class="item-tag">タグ名</span>
    作品の簡単な説明
  </div>
</div>
```

### タグの付け方

投稿内容から判断して適切なタグを付ける:

- `Fan Art` - ファンアート作品
- `Animation` - 動画・アニメーション
- `Illustration` - イラスト作品
- `ComfyUI` - ComfyUI のワークフロー・技術紹介
- `WIP` - 制作途中の共有

### 注意事項

- `twitter widgets.js` の script タグが既に存在するか確認し、重複させない
- ユーザーが埋め込みコード（blockquote）を直接貼った場合は oEmbed API を使わずそのまま使用する
