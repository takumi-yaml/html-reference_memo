# 4. HTML syntax

## 1.  the doctype

- doctype（「DOCTYPE」として大文字にされることもある）は、ブラウザの処理モードと関連している従来の理由から、HTML構文のどの文書でも必須の部分です。
- 次の3つの形式のいずれかの特性と一致する必要があります。


それぞれの書式とルール
1. normal doctype 例:`<!DOCTYPE html>`
    - 1. 大文字と小文字を区別しない `<!DOCTYPE`
    - 2. 1つ以上の空白文字
    - 3. 大文字と小文字を区別しない `HTML`
    - 4. 必要に応じて1つ以上の空白文字
    - 5. `>`

2. deprecated doctype
    - 1. 大文字と小文字を区別しない `<!DOCTYPE`
    - 2. 1つ以上の空白文字
    - 3. 大文字と小文字を区別しない `HTML`
    - 4. 必要に応じて1つ以上の空白文字
    - 5. 大文字と小文字を区別しない `PUBLIC`
    - 6. 必要に応じて1つ以上の空白文字
    - 7. `"` か `'` のクォート
    - 8. パブリックID
    - 9. 7のクォートの閉じクォート
    - 10. permitted-public-ID-system-ID-combination の一部かどうかに応じて、以下のパーツ
        - 1. 必要に応じて1つ以上の空白文字
        - 2. `"` か `'` のクォート
        - 3. A permitted system ID
        - 4. 2のクォートの閉じクォート
    - 11. 必要に応じて1つ以上の空白文字
    - 12.  `>`
    - 例:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.0//EN">
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.0//EN" "http://www.w3.org/TR/REC-html40/strict.dtd">
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN">
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

3. legacy-tool-compatible doctype 例: `<!doctype HTML system "about:legacy-compat">`
    - 1. 大文字と小文字を区別しない `<!DOCTYPE`
    - 2. 1つ以上の空白文字
    - 3. 大文字と小文字を区別しない `HTML`
    - 4. 必要に応じて1つ以上の空白文字
    - 5. 大文字と小文字を区別しない `SYSTEM`
    - 6. 必要に応じて1つ以上の空白文字
    - 7. `"` か `'` のクォート
    - 8. 文字列 `about:legacy-compat`
    - 9. 7のクォートの閉じクォート
    - 10. 必要に応じて1つ以上の空白文字
    - 11. `>`


## 2. Character encoding declaration

- 文字エンコーディング宣言は、文書の保存または送信に使用される文字エンコーディングを指定するためのメカニズム
- 文字エンコード宣言には次の制限が適用されます
    - 指定された文字エンコーディング名は、ファイルをシリアライズするために使用される文字エンコーディングの名前でなければなりません。
    - 値は有効な文字エンコーディング名でなければなりません
        - IANA [文字セット]レジストリに「preferred MIME name」と表示された名前またはエイリアスフィールドがある文字セット名の大文字と小文字を区別しない一致でなければなりません。
            - エイリアスフィールドにそのようにラベルが付けられていない場合は、レジストリの[名前]フィールドで大文字と小文字を区別しない一致が検出されます。
    - 文字エンコーディング宣言は、文字参照やあらゆる種類の文字エスケープを使わずにシリアライズされなければなりません。
    - 文字エンコーディング宣言を含む要素は、文書の最初の512バイト以内にシリアライズされなければなりません。

- 文書がU + FEFF BYTE ORDER MARK（BOM）文字で始まらない場合、さらにそのエンコーディングがContent-Type HTTPヘッダによって明示的に与えられていない場合、使用される文字エンコーディングはASCII互換の文字エンコーディングでなければならず、さらに、そのエンコーディングがUS-ASCIIでない場合、エンコーディングは、charset属性を持つメタ要素またはエンコーディング宣言状態のメタ要素を使用して指定する必要があります。
- ドキュメントにcharset属性のメタ要素またはエンコード宣言状態のメタ要素が含まれている場合は、使用される文字エンコーディングはASCII互換の文字エンコーディングでなければなりません。
    - ASCII互換の文字エンコーディングは、US-ASCIIの上位集合（特にANSI_X3.4-1968）のバイト
        - 0x09
        - 0x0A
        - 0x0C
        - 0x0D
        - 0x20-0x22
        - 0x26
        - 0x27
        - 0x2C-0x3F
        - 0x41〜0x5A
        - 0x61〜0x7A。
- ドキュメントは以下の文字コードを使うべきではない
    - UTF-32
    - JIS_C6226-1983
    - JIS_X0212-1990
    - HZ-GB-2312
    - JOHAB (Windows code page 1361)
    - ISO-2022ベースのエンコーディング
    - EBCDICベースのエンコーディング
- ドキュメントは以下の文字コードを使ってはいけない
    - CESU-8
    - UTF-7
    - BOCU-1またはSCSU encodings.
- XML構文の文書では、[XML仕様](http://w3c.github.io/html-reference/references.html#refsXML)で定義されているXML宣言を使用して、必要に応じて文字エンコーディング情報を提供する必要があります。


## 3. Elements

- 要素のコンテンツモデルは要素の構造を定義します
    - 要素に含めることができるコンテンツ（存在する場合）と、その要素が持つことができる属性（存在する場合）
    - このリファレンスのHTML要素のセクションでは、HTML言語の一部であるすべての要素のコンテンツモデルについて説明します。
    - 要素には、コンテンツモデルの一部ではない内容または属性を含むことはできません。
- 要素の内容は、要素、文字データ、およびそれに含まれるコメントです。
    - 属性とその値は、要素の「内容」とはみなされません。
- 要素のテキストコンテンツは、[DOM4](http://w3c.github.io/html-reference/references.html#refsDOM)で定義されているように、要素のtextContent IDL属性の値です。
- void要素は、コンテンツモデルがいかなる状況下でもコンテンツを持つことを許さない要素です。
    -  void要素は属性を持つことができます。
- 以下はHTMLのvoid要素の完全なリストです
    - area
    - base
    - br
    - col
    - command
    - embed
    - hr
    - img
    - input
    - keygen
    - link
    - meta
    - param
    - source
    - track
    - wbr

- 以下のリストはHTML構文の構文ルール
    - タグは、マークアップの要素の開始と終了を区切るために使用されます。
        - 要素には開始位置を示す開始タグがあります。空でない要素には、終了位置を示す終了タグがあります。
    - タグ名は要素の開始タグと終了タグ内で使用され、要素の名前が与えられます。
        - HTML要素はすべて、0-9、a-z、およびA-Zの範囲の文字のみを使用する名前を持ちます。
    - 開始タグは以下のリストの、出現順にて構成されています
        - 1. `<`
        - 2. 要素のタグ名
        - 3. 必要に応じて、1つ以上の属性。
            - それぞれの前に1つ以上の空白文字を付ける必要があります。
        - 4. 必要に応じて、1つ以上の空白文字
        - 5. 要素がvoid要素のとき、必要に応じて、`/`
        - 6.  `>`
    - 開始タグは以下のリストの、出現順にて構成されています
        - 1. `<`
        - 2. `/`
        - 3. 要素のタグ名
        - 4. 必要に応じて、1つ以上の空白文字
        - 5.  `>`
    - void要素は開始タグだけを持ちます
        - 終了タグは指定してはいけません
    - 特定の要素の開始タグ、終了タグは省略できます。
        - このリファレンスのHTML要素セクションの各要素のサブセクションは、その特定の要素に対してどのタグ（もしあれば）を省略できるかに関する情報を提供します。
    - non-void要素は終了タグを持たなければいけない
        - このリファレンスのHTML要素セクション内のその要素のサブセクションが、その終了タグを省略できることを示している場合を除きます。
    - 要素の内容は、開始タグの直後（場合によっては暗黙の可能性もあります）と終了タグの直前（特定の場合に暗示される可能性があります）の間に配置する必要があります。


### 3.1 Misnested tags

- 要素に開始タグと終了タグの両方がある場合、その終了タグは開始タグが含まれる同じ要素の内容に含まれていなければなりません。
- 開始タグと同じ内容に含まれていない終了タグは、misnested tagであると言われます。
    - 次の例では、 `<i>`開始タグを含むb要素の内容に含まれていないため、`</i>`終了タグは誤ったタグです。

```html
<b>foo <i>bar</b> baz</i>
```

## 4.Attributes

- ある要素の属性は、その要素の開始タグ内で表現されます。属性には名前と値があります。
- 同じ開始タグには、相互に大文字小文字を区別しない同じ名前の2つ以上の属性が存在してはなりません。
- 次のリストは、HTML構文のドキュメント内の属性の構文ルールを示しています。
    - 属性名は、空白文字、`U+0000 NULL`、`"`、`'`、`>`、`/`、`=`以外の1つ以上の文字で構成されていなければなりません。 Unicodeによって定義されます。
    - XMLと互換性のある属性名は、XML仕様[XML](http://w3c.github.io/html-reference/references.html#refsXML)で定義されているNameプロダクションと一致し、 "："文字を含まず、最初の3文字は文字列 大文字と小文字を区別しない"xml"です。
    - 属性値には、引用符で囲まれていない属性値、シングルクォートの属性値、ダブルクォートの属性値のいずれであるかに応じて、追加の制限が加えられたテキストと文字参照が含まれます。
        - また、このリファレンスのHTML要素のセクションでは、特定の属性の許容値についてのさらなる制限が記述されており、属性にはこれらの制限に準拠する値が必要です。

- HTML構文では、4つの異なる方法で属性を指定できます。

- 1. empty attribute syntax
    - 特定の属性は、属性名だけを指定して値を指定することによって指定できます。
    - 次の例では、disabled属性は空の属性で指定されています

```html
<input disabled>

<!-- 空の属性構文は、次の例のように、空の文字列を属性の値として指定するのと全く同じです。-->
<input disabled="">
```

- 2. unquoted attribute-value syntax
    - 引用符で囲まれていない属性値は、次のリストを次の順序で指定することによって指定されます。
        1. 属性名
        2. 0以上の空白文字
        3. `=`
        4. 0以上の空白文字
        5. 属性値
    - 属性値の一般的な要件に加えて、引用符で囲まれていない属性値には次の制限があります。
        - 空白文字を含むことはできません
        - `"`, `'`,  `=`, `>`, `<`, \` を含むことはできません
        - 空の文字列であってはなりません
    - 引用符で囲まれていない属性構文を使用する属性の値の後に "/"文字が続く場合は、値の後ろに "/"文字の前に少なくとも1つの空白文字がなければなりません。
    - 次の例では、value属性は引用符で囲まれていない属性値の構文で与えられています。

```html
<input value=yes>
```


- 3. single-quoted attribute-value syntax
    - シングルクォートで囲まれた属性値は、次のリストを次の順序で指定することによって指定されます。
        1. 属性名
        2. 0以上の空白文字
        3. `=`
        4. 0以上の空白文字
        5. `'`
        6. 属性値
        7. `'`
    - 属性値の一般的な要件に加えて、シングルクォートで囲まれた属性値には次の制限があります。
        - `'` を含むことはできません
    - 次の例では、type属性はシングルクォートで囲まれた属性値構文で与えられます。

```html
<input type='checkbox'>
```

- 4. double-quoted attribute-value syntax
    - ダブルクォートで囲まれた属性値は、次のリストを次の順序で指定することによって指定されます。
        1. 属性名
        2. 0以上の空白文字
        3. `=`
        4. 0以上の空白文字
        5. `"`
        6. 属性値
        7. `"`
    - 属性値の一般的な要件に加えて、ダブルクォートで囲まれた属性値には次の制限があります。
        - `"` を含むことはできません
    - 次の例では、title属性はダブルクォートで囲まれた属性値構文で与えられます。

```html
<code title="U+003C LESS-THAN SIGN">&lt;</code>
```


## 5. Text and character data
- 要素内容（コメントを含む）および属性値のテキストは、Unicode文字で構成されていなければなりません。ただし、次の制限があります。
    - U+0000文字を含むことはできません
    - 定義されていないUnicode文字を永久に含むことはできません
    - 空白文字以外の制御文字を含むことはできません

- 文字データには、文字参照と特定の追加の制限によっては、テキストが含まれています
    - ドキュメントには、次の3種類の文字データがあります。

- 1. normal character data
    - 特定の要素にはnormal character dataが含まれています。normal character dataには、次のものが含まれます。
        - text
        - 文字参照
    - normal character dataには次の制限があります
        - `<` を含めることはできません

- 2. replaceable character data
    - HTML構文の文書では、title要素とtextarea要素にreplaceable character dataを含めることができます。replaceable character dataには、次のものが含まれます。
        - text 必要に応じて`<`を含む
        - 文字参照
    - replaceable character dataには次の制限があります
        - ambiguous ampersands(あいまいなアンパサンド)を含めることはできません
        - replaceable character dataを含む要素の、大文字小文字を区別しないタグ名が後ろに続く`</`文字列を含むことはできません
            - たとえば `</ title`または `</ textarea`
            - さらに`/`, `>`が続く
    - このリファレンスで説明されているように、replaceable character dataは、XML構文では使用できないHTML構文の機能です。
    - XML構文のドキュメントには、このリファレンスで説明されているようにreplaceable character dataを含むことはできません。
        - その代わりに、XML仕様[XML]に記述されているすべての構文制約に準拠しなければなりません。

- 3. non-replaceable character data
    - HTML構文の文書では、script要素とstyle要素には、non-replaceable character dataを含めることができます。non-replaceable character dataには、次のものが含まれます。
        - 文字参照を含めることはできません
        - non-replaceable character dataを含む要素の、大文字小文字を区別しないタグ名が後ろに続く`</`文字列を含むことはできません
            - たとえば `</script`または `</style`
            - さらに`/`, `>`が続く
    - このリファレンスで説明されているように、non-replaceable character dataは、XML構文では使用できないHTML構文の機能です。
    - XML構文のドキュメントには、このリファレンスで説明されているようにnon-replaceable character dataを含むことはできません。代わりに、XML仕様[XML](http://w3c.github.io/html-reference/references.html#refsXML)で定義されているすべての構文制約に準拠しなければなりません。


## 6. Character references

- 文字参照(実体参照)は、単一の個々の文字を表すためのマークアップの形式です
    - 文字参照には3つのタイプがあります。

- 1. named character references
    - named character references は以下の部分を正確に次の順序で構成します
        1. `&`
        2. ケースセンシティブな、HTML5仕様[HTML5]の「名前付き文字参照」セクションに記載されている名前の1つ。
        3. `;`
    - 以下は、文字 "†"（U + 2020 DAGGER）の名前付き文字参照の例です

```html
&dagger;
```

- 2. decimal numeric character references
    - decimal numeric character references は以下の部分を正確に次の順序で構成します
        1. `&`
        2. `#`
        3. ユニコードのコードポイントU+0000, U+000DではないU+0080〜U+009F, または0xD8000〜0xDFFF(サロゲート)に存在する0-9の1つ以上の数字
        3. `;`
    - 以下は、文字 "†"（U+2020 DAGGER）のdecimal numeric character referencesの例です。

```html
&#8224;
```

- 3. hexadecimal numeric character references
    - hexadecimal numeric character references は以下の部分を正確に次の順序で構成します
        1. `&`
        2. `#`
        3. `x` または `X`
        4. ユニコードのコードポイントU+0000, U+000DではないU+0080〜U+009F, または0xD8000〜0xDFFF(サロゲート)に存在する0-9, a-f, A-Fの1つ以上の数字
        5. `;`
    - 以下は、文字 "†"（U+2020 DAGGER）のhexadecimal numeric character referencesの例です。

```html
&#x2020;
```

- 文字参照はそれ自身テキストではなく、文字参照もテキストではありません。

- あいまいなアンパサンドは、0-9の範囲の1つ以上の文字の後に続く "&"文字です。
    - 範囲a-z、または範囲A-Z、続いて「;」 （セミコロン）文字
    - これらの文字は、HTML5仕様[HTML5]の「名前付き文字参照」セクションで指定された名前と一致しません。



## 7.  Comments

- コメントは、は以下の部分を正確に次の順序で構成します

1. コメント開始デリミタ `<!--`
2. テキスト
3. コメント終了デリミタ `-->`

- コメントには次の制限があります
    - `>`から始まる文字を含めることはできません
    - `->`から始まる文字を含めることはできません
    - `--`を含めることはできません
    - `-`で終わる文字を含めることはできません

例:

```html
<!-- main content starts here -->
```


## 8. SVG and MathML elements in HTML documents

- SVGおよびMathML要素は、SVGおよびMathML名前空間の要素です。
- MathML名前空間からのmath要素とSVG名前空間からのsvg要素は、フレーズコンテンツが許可されている文書であればどこでも許可されます。
- SVGおよびMathML要素は、HTML構文の文書とXML構文の文書の両方で使用できます。
- XML構文の文書におけるSVGおよびMathML要素の構文規則は、XML仕様[XML](http://w3c.github.io/html-reference/references.html#refsXML)で定義されています。
- 次のリストは、HTML構文のドキュメント内のSVGおよびMathML要素に特に適用される追加の構文ルールを示しています。
    - 終了タグが単一の`/`を持つSVGおよびMathML要素は、`>`(閉じカッコ)の前にself-closingとしてマークされていると言われています。
    - SVGおよびMathML要素には、開始タグと終了タグを持つか、self-closingとしてマークされた開始タグが含まれていなければなりません。
        - self-closingの場合、終了タグは必要ありません。
    - self-closingとしてマークされたSVGとMathML要素は、コンテンツを持つことができません。
    - self-closingタグではないSVG,MathML要素のコンテンツは、文字データ、コメント、およびCDATAセクションに含まれるすべての文字データが通常の文字データでなければならないという制約があります。


## 9. CDATA sections in SVG and MathML contents

- HTML構文の文書内のSVGおよびMathMLコンテンツのCDATAセクションは、以下の部分を正確に次の順序で構成します
    - 1. CDATA 開始デリミタ `<![CDATA[`
    - 2. テキスト
        - 文字列 `]]>`を含めることはできません
    - 3. CDATA 終了デリミタ `]]>`

例：

```html
<annotation encoding="text/latex">
<![CDATA[\documentclass{article}
\usepackage{amsmath}
\begin{document}
The absolute value of $x$:
\[
\left|x\right|= \begin{cases}-x& \text{if $x<0$}\\
                              x& \text{otherwise}\end{cases}
\]
\end{document}]]>
</annotation>
```
