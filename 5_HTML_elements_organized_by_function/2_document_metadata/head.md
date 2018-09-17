# head - document metadata container

- `head`要素はドキュメントのメタデータを収集します。

## 許可された属性

- グローバル属性


## その他の制約や注意

- `head`要素の`profile`属性は古い。
- どのメタ要素の用語がドキュメントで使用されているかを宣言するには、名前をメタ拡張として登録します。
- 特定のUAのビヘイビアをトリガするには、代わりにlink要素を使用します。


## タグの省略

- head要素内の最初の要素が要素の場合は、head要素の開始タグを省略することができます。
- head要素の終了タグは、head要素の直後にスペース文字やコメントがない場合は省略することができます。

## 許可された親要素

- `html`

## DOM interface

```c
interface HTMLHeadElement : HTMLElement {};
```

## デフォルトdisplayプロパティ

```css
head {
display: none; }
```

