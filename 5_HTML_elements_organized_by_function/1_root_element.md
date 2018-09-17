# 5-1. The root element

## html - root element

- html要素はドキュメントのルートを表現している

### 許可されたコンテンツ

- 1つの`head`要素とその後の1つの`body`要素


### 許可された属性

- グローバル属性
- マニフェスト
    - ドキュメントのアプリケーションキャッシュマニフェストのアドレス
        - オフラインでの使用時のキャッシュをコントロールする


## その他の制約や注意

- `version`属性は省いて良い


## タグの省略

- html要素内の最初にコメントがない場合、html要素の開始タグは省略することができます。
- html要素の直後にコメントがなく、その要素に空ではない、開始タグが省略されていないbody要素が含まれている場合終了タグは省略できます。

## DOM interface

```c
interface HTMLHtmlElement : HTMLElement {};
```

## デフォルトdisplayプロパティ

```css
html {
display: block; }
html:focus {
outline: none; }
```

