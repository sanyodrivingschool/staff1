# 三陽自動車学校 SNS流入LP（GitHub Pages）

## ファイル構成

```
index.html   … LP本体（CSS・JSも1ファイルに入っています）
images/      … 写真・OGP画像を入れるフォルダ（今は空）
.nojekyll    … GitHub PagesでJekyll処理をさせないための空ファイル
README.md    … このファイル
```

## 公開手順

1. GitHubで新しいリポジトリを作る（例：`sanyo-lp`、Public）
2. このフォルダの中身をすべてアップロードする（`.nojekyll` も忘れずに）
   - ブラウザなら「Add file → Upload files」にドラッグ＆ドロップ
   - コマンドなら：
     ```
     git init
     git add .
     git commit -m "first commit"
     git branch -M main
     git remote add origin https://github.com/<ユーザー名>/sanyo-lp.git
     git push -u origin main
     ```
3. リポジトリの **Settings → Pages** を開く
4. **Source：Deploy from a branch**、**Branch：main / (root)** を選んで Save
5. 1〜2分後に `https://<ユーザー名>.github.io/sanyo-lp/` で公開されます

## URLの使い分け

| 用途 | URL |
|---|---|
| 学生向けPR投稿 | `https://<ユーザー名>.github.io/sanyo-lp/` |
| 保護者向けPR投稿 | `https://<ユーザー名>.github.io/sanyo-lp/?t=parent` |

`?t=parent` を付けると、ファーストビューの見出しが保護者向けに切り替わります。
計測用に `&utm_source=instagram&utm_content=投稿ID&rep=営業ID` を足しても表示は変わりません。

## 公開前に差し替えるもの

`index.html` 内の【写真差し替え】と [ ] の部分です。

- 写真：ファーストビュー（720×960）、施設4枚、先輩の声、校舎2枚 → `images/` に入れて、`<div class="ph">…</div>` を `<img src="./images/xxx.webp" alt="…" width="…" height="…">` に置き換え
- OGP画像：`images/ogp.png`（1200×630）を用意
- 学生料金の総額、11月キャンペーンの内容と期限、送迎バスの運行エリア
- 先輩の声（掲載許諾を取ったもの）
- 「卒業生事故率の低さ 熊本市内No.1」の根拠（フッターの注記欄）
- FAQの友達紹介・グループ特典

## 計測（任意）

`<head>` 内のコメント位置に、既存のGoogle Tag Manager（GTM-P2TM5Z6）のタグを貼ると、
LINEボタン・電話タップなどをGTM側でイベント計測できます。
