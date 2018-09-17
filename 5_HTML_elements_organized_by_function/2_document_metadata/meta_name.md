# meta name – name-value metadata

- `name`属性のある`meta`要素は name/valueの形でドキュメントのメタデータを表現します。

## 許可されたコンテンツ

- 空(void要素)

## 許可された属性

- グローバル属性
- `name`
    - 文字列
    - name/valueペアのnameの部分を特定する
    - [指定された名前は、HTML5仕様で定義されている標準メタデータ名か、定義済みのメタデータ名セットの登録済み拡張子]のいずれかでなければなりません。](http://w3c.github.io/html-reference/references.html#refsHTML5)
- `content`
    - 文字列
    - name/valueペアのvalueの部分を特定する


## その他の制約や注意

- `name`属性は定義済みメタデータ名か、登録済みメタデータ名でなければならない。
    - 定義済みメタデータは以下のいずれか
        - application-name
            - name属性が "application-name"に設定されている場合、content属性の値は、ページが表す(ページを表示している)Webアプリケーションの名前を表す文字列でなければなりません
        - author
            - name属性が "author"に設定されている場合、content属性の値は、ドキュメントの作者の名前を示す文字列でなければなりません。
        - description
            - name属性が "description"に設定されている場合、content属性の値はページを説明する文字列でなければなりません。
        - generator
            - name属性が "generator"に設定されている場合、content属性の値は、ドキュメントを生成するために使用されるソフトウェアを識別する文字列でなければなりません。
        - keywords
            - name属性が "keywords"に設定されている場合、content属性の値はカンマで区切られた文字列のセットでなければなりません。それぞれの文字列はドキュメントに関連するキーワードです。


## タグの省略

- `meta`要素はvoid要素。
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

## デフォルトdisplayプロパティ

```css
link {
display: none; }
```
