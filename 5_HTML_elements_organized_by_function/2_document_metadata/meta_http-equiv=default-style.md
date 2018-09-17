# meta http-equiv=default-style - “preferred stylesheet” pragma directive

- `http-equiv`属性に`default-style`値を持つ`meta`要素は、ドキュメントの優先スタイルシートを指定するプラグマディレクティブを表現します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `http-equive="default-style"`
    - メタ要素はドキュメントの優先スタイルシートを特定するプラグマディレクティブであることを示す
    - リンク先を指定するURL
- `content`
    - default-style の名前
    - ドキュメントの優先スタイルシートの名前を特定する。
    - 名前は、次の制約条件のいずれかを満たす必要があります。
        - 同じドキュメント内のlink要素のtitle属性の値と一致していなければならず、そのlink要素にはCSSスタイルシートの場所を参照するhref属性が必要です。
        - 同じ文書内のstyle要素のtitle属性の値と一致しなければならず、その要素の内容はCSSスタイルシートでなければなりません。


## タグの省略

- `link`要素はvoid要素。
    - 開始タグは必須, 終了タグ含めることはできません。

## 許可された親要素

- メタデータ要素、noscript要素を含めることができる要素

## DOM interface

```c
interface HTMLMetaElement : HTMLElement {
           attribute DOMString name;
           attribute DOMString httpEquiv;
           attribute DOMString content;
};
```
