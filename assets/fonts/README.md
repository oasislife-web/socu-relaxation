# フォントについて

## inter-numerals.woff2

サイト内の**数字だけ**に使っているフォントです。

- 書体: **Inter**(制作: Rasmus Andersson)
- ライセンス: **SIL Open Font License 1.1** — 商用サイトでの利用・再配布ともに無料で可能です
- 公式: https://fonts.google.com/specimen/Inter
- ライセンス全文: https://openfontlicense.org/

### なぜこのファイルがあるのか

`0123456789` と `,` `.` `¥` の**12文字だけ**を切り出したファイルです。そのため **8KB** しかありません。

日本語と英文には使っていません(`styles.css` の `@font-face` にある `unicode-range` で、
上の12文字のときだけこのフォントを使う、と指定しています)。

### なぜ切り出しているのか

フォント全体を読み込むと数百KBになり、スマホの回線では表示が遅くなります。
数字しか使わないので、数字だけを切り出して軽くしています。

### 差し替えたいとき

Google Fonts で好きな書体を選び、以下のようにURLの末尾に `&text=` を付けると、
指定した文字だけのファイルを作ってくれます。

```
https://fonts.googleapis.com/css2?family=書体名&text=0123456789%C2%A5%2C.&display=swap
```

このURLをブラウザで開くと `.woff2` のリンクが出てくるので、それをダウンロードして
このフォルダに置き、`styles.css` の `@font-face` にあるファイル名を書き換えてください。
