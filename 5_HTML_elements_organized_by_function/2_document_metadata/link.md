# link - inter-document relationship metadata

- `link`要素は、文書間の関係を表すメタデータを表します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `href`
    - 必要に応じてスペースで囲まれた空文字列ではないURL
    - リンク先を指定するURL
- `rel`
    - 必要に応じてスペースで囲まれた絶対URL
    - リンクを含むドキュメントとリンク先との間の関係を指定するトークンのセット。
    - 各トークンは、HTML5仕様で定義されたリンクタイプか、リンクタイプ[HTML5](http://dev.w3.org/html5/spec/links.html#linkTypes)の事前定義されたセットへの登録拡張でなければなりません。
- `hreflang`
    - [BCP 47](http://w3c.github.io/html-reference/references.html#refsBCP47)にて定義された言語タグ
    - リンク先の言語
- `media`
    - リンク先が基づいて設計されたメディア
    - [メディアクエリの有効なリスト](http://w3c.github.io/html-reference/references.html#refsMediaQueries)
- `type`
    - リンク先のMIMEタイプ
    - [RFC 2046](http://w3c.github.io/html-reference/references.html#refsRFC2046)で定義された有効なMIMEタイプの文字列定義
- `sizes`
    - ビジュアルメディアのためのアイコンのサイズ
    - 各トークンは、次のいずれかでなければなりません。
        - 文字列 `any`
        - 0から始まらない、各値を`x`で区切られた2つの正の整数


## その他の制約や注意

- `link`要素の`target`属性は省いても問題ない。
- `link`要素の`urn`属性は古い。
    - 代わりにhref属性を使用して優先永続識別子(preferrd persistent identifier)を指定してください。
- `charset`属性は古い。
    - 代わりにリンクされたリソースにHTTP Content-Typeヘッダーを使用します。
- `methods`属性は古い。
    - 代わりにHTTPオプション機能を使用してください。
- `rev`属性は古い。
    - 代わりにrel属性を使用し、逆の意味を持つ用語を使用します。

## タグの省略

- `link`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- メタデータ要素、noscript要素を含めることができる要素

## DOM interface

```c
nterface HTMLLIElement : HTMLElement {
           attribute long value;
};
```

## デフォルトdisplayプロパティ

```css
link {
display: none; }
```
