# meta charset – document character-encoding declaration

- `charset`属性を持つ`meta`要素は、文字コード宣言を表現します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `charset`
    - 文字コード名
    - 文字コードを特定する
        - XML構文の文書の場合、charset属性の値は、文字列 "UTF-8"(ケースセンシティブ)でなければなりません。
    - 値
        - [IANA 文字セットレジストリ](http://w3c.github.io/html-reference/references.html#refsCharacterSets)に「優先MIME名」というラベルの名前またはエイリアスフィールドがある文字セット名(ケースインセンシティブ)
        - エイリアスフィールドのいずれもそのようにラベル付けされていない場合、レジストリの名前フィールド(ケースインセンシティブ)。


## タグの省略

- `link`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- メタデータ要素を含めることができる要素

## DOM interface

```c
interface HTMLMetaElement : HTMLElement {
           attribute DOMString name;
           attribute DOMString httpEquiv;
           attribute DOMString content;
};
```
