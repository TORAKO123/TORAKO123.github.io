X(Twitter)の投稿URLを受け取り、oEmbed APIで埋め込みコードを取得して、index.htmlのギャラリーセクションに追加するスキルです。

## 手順

1. 引数として渡された X の URL を確認する: $ARGUMENTS
2. oEmbed API を使って埋め込みコードを取得する:
   - URL: `https://publish.twitter.com/oembed?url=<投稿URL>&dnt=true&lang=ja`
   - WebFetch で取得し、`html` フィールドから blockquote 部分を抽出する
3. index.html の `gallery-grid` 内に新しい `gallery-item` を追加する:
   - 既存のアイテムの後、`</div><!-- gallery-grid -->` の前に追加
   - 以下のテンプレートを使用:

```html
<div class="gallery-item">
  <div class="embed-wrapper">
    <!-- ここに取得した blockquote を挿入 -->
  </div>
  <div class="item-label">
    <span class="item-tag">タグ</span>
    作品の説明
  </div>
</div>
```

4. タグと説明は、埋め込みコード内のテキストやハッシュタグから適切に判断して設定する
5. twitter widgets.js の script タグが既にあるか確認し、なければ追加する
6. 変更を保存し、ユーザーに結果を報告する（コミット・プッシュはユーザーの指示を待つ）
