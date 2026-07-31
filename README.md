# GADGET LOG

ガジェットアフィリエイトブログの土台。ビルド不要の素のHTML/CSSなので、`index.html` や `articles/*.html` を直接編集するだけで更新できます。

## 構成

```
index.html          トップページ（記事一覧）
style.css            共通スタイル
disclosure.html       PR表記・運営者情報
privacy.html          プライバシーポリシー
articles/             個別記事
```

## 記事を追加する手順

1. `articles/` 内の既存ファイル（例: `mobile-battery-comparison.html`）をコピーして新しいファイル名にする
2. タイトル・スペック表・良かった点/気になった点・本文を書き換える
3. `<a class="cta-button" href="#" ...>` の `href="#"` を実際のアフィリエイトリンクに差し替える
4. `index.html` の `.article-grid` 内に新しい `<article class="article-card">` を追加してリンクする

## アフィリエイトリンクの貼り方

- Amazonアソシエイトの審査に通ったら、商品ページで発行される紹介リンク（`https://www.amazon.co.jp/dp/XXXXXXX?tag=あなたのタグ-22` の形式）を `cta-button` の `href` に貼る
- リンクには必ず `rel="nofollow sponsored noopener"` を付けたままにする（付与済みテンプレートになっています）
- 記事冒頭の `.disclosure-banner`（PRを含む旨の表示）は削除しないこと（景品表示法のステルスマーケティング規制対応）

## 公開前にやること

- [ ] `disclosure.html` と `privacy.html` の `<!-- TODO -->` 箇所に連絡先メールアドレスを記載
- [ ] 各記事の商品名・スペック・レビュー内容を実際に使用したものに差し替え
- [ ] Amazonアソシエイト / 楽天アフィリエイト等のASPに登録し、審査に申請
- [ ] 審査に通ったら `href="#"` を実際のアフィリエイトリンクに置き換え

## GitHub Pagesへの公開手順

既存のプロフィールサイト（`kaitoinoue0921-sudo.github.io`）とは別の、新しいリポジトリとして公開します。

1. GitHubで新しいリポジトリを作成（例: `gadget-log`）。Public、READMEなし で作成
2. このディレクトリで以下を実行:
   ```
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/kaitoinoue0921-sudo/gadget-log.git
   git push -u origin main
   ```
3. GitHubのリポジトリ → Settings → Pages で、Branch を `main` / `/(root)` に設定
4. 数分後に `https://kaitoinoue0921-sudo.github.io/gadget-log/` で公開される
