# base - base URL

- `base`要素は相対URLを解決するために文書全体のベースURLと、ハイパーリンクをたどるために文書全体のデフォルトブラウジングコンテキスト名を指定します。

## 許可されたコンテンツ

- 空 (void要素)

## 許可された属性

- グローバル属性
- `href`属性と`target`属性
    - `href`属性: ドキュメントのベースURL
- `target`属性
    - `target`属性: ブラウジングコンテキスト名か以下のリンク内のキーワード
        - [ブラウジングコンテキスト名](http://w3c.github.io/html-reference/datatypes.html#common.data.browsing-context-name)
        - 以下の文字列(ケースインセンシティブ)
            - `_blank`
            - `_self`
            - `_parent`
            - `_top`


## タグの省略

- `base`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- `head`

## DOM interface

```c
interface HTMLBaseElement : HTMLElement {
           attribute DOMString href;
           attribute DOMString target;
};
```
