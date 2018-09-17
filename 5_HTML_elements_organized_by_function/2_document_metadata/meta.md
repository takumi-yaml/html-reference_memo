# meta - metadata

- `meta`要素はメタデータを表現する上で複数の目的がある要素です。

- メタ要素のディテール
    - [meta name](http://w3c.github.io/html-reference/meta.name.html#meta.name)
    - [meta http-equiv=refresh](http://w3c.github.io/html-reference/meta.http-equiv.refresh.html#meta.http-equiv.refresh)
    - [meta http-equiv=default-style](http://w3c.github.io/html-reference/meta.http-equiv.default-style.html#meta.http-equiv.default-style)
    - [meta charset](http://w3c.github.io/html-reference/meta.charset.html#meta.charset)
    - [meta http-equiv=content-type](http://w3c.github.io/html-reference/meta.http-equiv.content-type.html#meta.http-equiv.content-type)


## その他の制約や注意

- meta要素のscheme属性は廃止されています。フィールドごとに1つのスキームのみを使用するか、スキーム宣言を値の一部にします。
- meta要素を使用してドキュメント全体のデフォルト言語を指定するのは廃止されました。代わりにルート要素に言語を指定することを検討してください。


## HTML5での変更

- HTMLの以前のバージョンでは、meta要素のhttp-equiv属性に任意の数の値を含めることができましたが、http-equiv属性はこの参照で説明されている特定の値のみに制限されるようになりました。
- また、新しいcharset属性も使用できるようになりました。
