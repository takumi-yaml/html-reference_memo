# meta http-equiv=content-type – document character-encoding declaration

- `content-type`値を持つ`charset`属性があり、値を持つ`content`属性がある`meta`要素は、文字エンコーディング宣言を表現します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `http-equiv="content-type"`
    - エンコーディング宣言ステートにメタ要素があり、文字エンコーディング宣言を表現していることを指している
- `content`
    - 文字エンコーディング名を提供する特別な文字列
    - 値： 以下のパーツの、出現順で構成されている
        - 1. `text/html`
        - 2. 必要に応じて1つ以上の空白
        - 3. `charset=`
        - 4. 以下のいずれか
            - HTML構文では文字エンコーディング名
            - XML構文では'UTF-8'(ケースインセンシティブ)


## タグの省略

- `meta`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- メタデータ要素を含めることができる要素


## 詳細

- 値が`content-type`の`http-equiv`属性を持ち、さらに`content`属性と値をもつ`meta`要素はエンコーディング宣言ステートにあると言われます


## DOM interface

```c
interface HTMLMetaElement : HTMLElement {
           attribute DOMString name;
           attribute DOMString httpEquiv;
           attribute DOMString content;
};
```
