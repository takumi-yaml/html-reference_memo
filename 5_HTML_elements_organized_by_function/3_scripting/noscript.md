# noscript – fallback content for script

- `noscript`要素はスクリプトをサポートしないユーザーエージェントに別のマークアップを、どのようにドキュメントがパースされたかに関わることで、表現するのに使われる

## 許可されたコンテンツ

- 0以上の以下
    - 1つ以上の`link`要素
    - 1つ以上の`meta http-equiv=default-style`要素
    - 1つ以上の`meta http-equiv=refresh`要素
    - 1つ以上の`style`要素
- トランスペアレント
    - フレージングコンテントか、フローコンテント

## 許可された属性

- グローバル属性


## その他の制約や注意

- `noscript`要素はxml構文では使用できない
- `noscript`要素は`noscript`要素をネストすることはできない

## タグの省略

- `noscript`要素開始タグと終了タグを持たなければならない。

## 許可された親要素

- メタデータ要素を含めることができる要素
- フレージング要素を含めることができる要素
- フロー要素を含めることができる要素

## DOM interface

- HTMLElementを使用する
