# script – embedded script

- `script`要素は、動的なスクリプトと、ドキュメントに含まれたデータブロックを使用可能にします。

## 許可されたコンテンツ

- Non-replaceable character data

## 許可された属性

- グローバル属性 と type と language
- グローバル属性 と src と defer と async と type と charset と language

- グローバル属性
- `type`
    - MIMEタイプ
    - データのフォーマットかスクリプトの言語
    - 値: [RFC 2046](http://w3c.github.io/html-reference/references.html#refsRFC2046)で定義された有効なメディアタイプの文字列
- `language`
    - 廃止
    - スクリプト言語がJavaScriptであると特定する
- `src`
    - 空ではないURL
    - 使用する追加スクリプトのアドレス
- `defer`
    - `defer` または 空文字列 または 空
    - ドキュメントがパースされた後スクリプトが実行されるべきかを特定する
- `async`
    - `async` または 空文字列 または 空
    - スクリプトが使用可能になったら非同期で実行されるべきかを特定する
- `charset`
    - 文字エンコーディング名
    - 追加スクリプトの文字エンコーディング
    - 値:
        - [IANA 文字セットレジストリ](http://w3c.github.io/html-reference/references.html#refsCharacterSets)に「優先MIME名」というラベルの名前またはエイリアスフィールドがある文字セット名(ケースインセンシティブ)
        - エイリアスフィールドのいずれもそのようにラベル付けされていない場合、レジストリの名前フィールド(ケースインセンシティブ)。



## その他の制約や注意

- `script`要素はマッチする`-->`を持たない`<!--`を含めてはいけない。
- `src`属性を持つ`script`要素は以下の項目だけを含めることができます。
    - 改行だけで構成される行
        - 1つまたは複数のスペース（U+0020）文字またはタブ（U+0009）文字が前に付いていてもかまいません
    - `//`で始まる単一行のコメント
        - 1つまたは複数のスペース（U+0020）文字またはタブ（U+0009）文字が前に付いていてもかまいません
        - その後に改行ではない任意の数の文字が続き、改行で終わる
    - `/*`で始まる複数行のコメント
        - 1つまたは複数のスペース（U+0020）文字またはタブ（U+0009）文字が前に付いていてもかまいません
        - 最後は `*/`
- 値が "JavaScript"である`language`属性を持つ`script`要素は、値が "text/javascript"でない`type`属性を持つことはできません。
- `src`属性を指定されていない限り、`charset`属性を持つことはできません。
- `src`属性を指定されていない限り、`defer`属性を持つことはできません。
- `src`属性を指定されていない限り、`async`属性を持つことはできません。
- `language`属性は廃止済み
    - 代わりに`type`属性を使う

## タグの省略

- `script`要素開始タグと終了タグを持たなければならない。

## 許可された親要素

- メタデータ要素を含めることができる要素
- フレージング要素を含めることができる要素

## DOM interface

```c
interface HTMLScriptElement : HTMLElement {
           attribute DOMString src;
           attribute boolean async;
           attribute boolean defer;
           attribute DOMString type;
           attribute DOMString charset;
           attribute DOMString text;
};
```

## デフォルトdisplayプロパティ

```css
script {
display: none; }
```
