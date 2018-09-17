# style – style (presentation) information

- `style`要素はドキュメントに埋め込まれたcssの情報を支給します

## 許可されたコンテンツ

- Non-replaceable character data / 非置換文字データ

## 許可された属性

- グローバル属性 と type と media
- グローバル属性 と type と media と scoped

- `type`
    - MIMEタイプ
    - スタイルを決める言語を指示した有効なMIMEタイプ
- `media`
    - スタイルが適用されるメディアを指定する
        - [メディアクエリ](http://w3c.github.io/html-reference/references.html#refsMediaQueries)
- `scoped`
    - `scoped` または 空文字列 または 空
    - `style`要素の親要素と子要素だけにスタイルが適応されることを意味するスタイル情報であることを指している。
    - またはドキュメント全体に適応されることを指している


## その他の制約や注意
- `style`要素は対応する`-->`文字列がない`<!--`文字列を含めることはできません。


## タグの省略

- `style`は開始タグ、終了タグを持たなければなりません。

## 許可された親要素

- メタデータ要素, div, noscript, section, article, asideを含めることができる要素


## DOM interface

```c
interface HTMLStyleElement : HTMLElement {
           attribute boolean disabled;
           attribute DOMString media;
           attribute DOMString type;
           attribute boolean scoped;
};
HTMLStyleElement implements LinkStyle;
```


## デフォルトdisplayプロパティ

```css
style {
display: none; }
```
