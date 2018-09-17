# meta http-equiv=refresh – "refresh" pragma directive

- 属性/値が`http-equiv=refresh`の`meta`要素は 現在のページをリロードするまでの秒数を指定するプラグマディレクティブ、または現在のページの代わりに別のページをロードするまでの秒数、と代替ページのURLを表現します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `http-equiv="refresh"`
    - meta要素は、現在のページをリロードするまでの秒数、または現在のページの代わりに別のページをロードするまでの秒数、および置換ページのURLを指定するプラグマディレクティブであることを示します
- `content`
    - 以下のいずれか
        - 現在のページをリロードするまでの秒数
        - 現在のページの代わりに別のページをロードするまでの秒数、および置換ページのURL
    - 値: 以下のいずれか
        - 正の整数
        - 次のパーツと順番からなる文字列
            - 1. 正の整数
            - 2. `;`
            - 3. 1つ以上の空白文字
            - 4. `url=`文字列 (ケースインセンシティブ)
            - 5. URL


## タグの省略

- `meta`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- メタデータ要素とnoscript要素を含めることができる要素

## DOM interface

```c
interface HTMLMetaElement : HTMLElement {
           attribute DOMString name;
           attribute DOMString httpEquiv;
           attribute DOMString content;
};
```
