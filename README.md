# Drop動画リンク集

ソフトバレーチーム「Drop」の練習・大会の動画(YouTube)と写真(Google Photos)のリンク集ページです。

GitHub Pages で公開しています(チーム内共有用。検索エンジンには載らないよう `noindex` を指定しています)。

## ファイル構成

| パス | 内容 |
|---|---|
| `index.html` | ページ本体。データ・デザイン・年別フィルタがすべてこの1ファイルに入っています |
| `assets/drop-icon.jpg` | ヘッダーのDropアイコン(サムネイル未設定の項目の代替画像も兼用) |
| `thumbs/*.jpg` | 各YouTubeプレイリストのサムネイル画像 |

## 項目を追加するには

`index.html` の中の `const events = [ ... ]` に、**日付の新しい順**で1行追加します。

```js
{ date: "2026/09/01", title: "○○区ソフトバレー大会", video: "https://youtube.com/playlist?list=XXXX", photo: "https://photos.app.goo.gl/XXXX", thumb: "thumbs/ev-e-14.jpg" },
```

- `date` … `YYYY/MM/DD` 形式。ここから年別フィルタのボタンが自動で作られます
- `title` … 表示名
- `video` … YouTubeプレイリストのURL(無ければ省略可)
- `photo` … Google PhotosアルバムのURL(無ければ省略可)
- `thumb` … `thumbs/` に置いたサムネイル画像のパス(省略するとDropアイコンが表示されます)

年をまたぐ常設のコレクションは `const evergreen = [ ... ]` の方に追加します(こちらは日付なし)。

追加したら、ページ下部の「最終更新」の日付(`index.html` 末尾付近)も書き換えてください。

## 反映方法

```
git add .
git commit -m "○○大会を追加"
git push origin main
```

push から1分ほどでページに反映されます。
