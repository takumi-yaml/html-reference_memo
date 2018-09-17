# body – document body

- `body`要素は、ドキュメントのメタデータとは対照的に、ドキュメントの本体を表現します。

## 許可されたコンテンツ

- フローコンテント
    - フロー要素と通常の文字データで構成される

## 許可された属性

- グローバル属性
- onafaterprint属性
- onbeforeprint属性
- onbeforeunload属性
- onblur属性
- onerror属性
- onfocus属性
- onhashchange属性
- onload属性
- onmessage属性
- onoffline属性
- ononline属性
- onpagehide属性
- onpageshow属性
- onpopstate属性
- onresize属性
- onstorage属性
- onunload属性

- グローバル属性
- `onafterprint`属性
    - ユーザーがドキュメントを印刷後
- `onbeforeprint`属性
    - ユーザーがドキュメントを印刷リクエスト後
- `onbeforeunload`属性
    - ドキュメントがアンロードされる瞬間
- `onblur`属性
    - ドキュメントへのフォーカスがなくなったあと
- `onerror`属性
    - ドキュメントが正しくロードされなかったとき
- `onhashchange`属性
    - 現在のドキュメントのアドレスのフラグメント識別子が変更されたとき
- `onload`属性
    - ドキュメントロード後
- `onmessage`属性
    - ドキュメントがメッセージを受け取った後
- `onoffline`属性
    - ネットワーク接続が解除されたあと
- `ononline`属性
    - ネットワーク接続が復活したあと
- `onpagehide`属性
    - ネットワーク接続が復活したあと
- `onpageshow`属性
    - ネットワーク接続が復活したあと
- `onpopstate`属性
    - セッションヒストリーからユーザーがナビゲートした後
- `onresize`属性
- `onstorage`属性
    - ストレージ領域が変更後
- `onunload`属性
    - ドキュメントが消えるとき


## その他の制約や注意

- `alink`属性は廃止済み
    - 代わりにCSSを使う
- `background`属性は廃止済み
    - 代わりにCSSを使う
- `bgcolor`属性は廃止済み
    - 代わりにCSSを使う
- `link`属性は廃止済み
    - 代わりにCSSを使う
- `marginbottom`属性は廃止済み
    - 代わりにCSSを使う
- `marginheight`属性は廃止済み
    - 代わりにCSSを使う
- `marginleft`属性は廃止済み
    - 代わりにCSSを使う
- `marginright`属性は廃止済み
    - 代わりにCSSを使う
- `margintop`属性は廃止済み
    - 代わりにCSSを使う
- `marginwidth`属性は廃止済み
    - 代わりにCSSを使う
- `text`属性は廃止済み
    - 代わりにCSSを使う
- `vlink`属性は廃止済み
    - 代わりにCSSを使う

## タグの省略

- `body`要素内の最初のものが`script`要素または`style`要素である場合を除き、`body`要素の最初にコメントか空白文字がなければ、開始タグを省略できる。
- `body`要素の終了タグは、`body`要素の直後にコメントがなく、要素が空でないか、開始タグが省略されていない場合は省略できます。

## 許可された親要素

- html

## DOM interface

```c
interface HTMLBodyElement : HTMLElement {
           attribute EventHandler onafterprint;
           attribute EventHandler onbeforeprint;
           attribute EventHandler onbeforeunload;
           attribute EventHandler onblur;
           attribute OnErrorEventHandler onerror;
           attribute EventHandler onfocus;
           attribute EventHandler onhashchange;
           attribute EventHandler onload;
           attribute EventHandler onmessage;
           attribute EventHandler onoffline;
           attribute EventHandler ononline;
           attribute EventHandler onpopstate;
           attribute EventHandler onpagehide;
           attribute EventHandler onpageshow;
           attribute EventHandler onresize;
           attribute EventHandler onscroll;
           attribute EventHandler onstorage;
           attribute EventHandler onunload;
};
```

## デフォルトdisplayプロパティ

```css
body {
display: block;
margin: 8px; }
body:focus {
outline: none; }
```
