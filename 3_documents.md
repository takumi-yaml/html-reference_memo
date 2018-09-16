# 3. documents

## 1. The HTML language and HTML and XML syntaxes

- HTML languageはアプリケーションがいくつかの方法でメモリに表現できる抽象的な言語で、いくつかの方法で具体的な構文を使用して送信することができます。
- HTMLの2つの具体的なシンタックスを説明する
    - 1. HTML構文としてこの参考文献を通して言及され
    - 2. XML構文としてこの参考文献を通して参照される別の構文である。
- ブラウザは2つの別々なパーサーを実装されている
    - HTMLパーサーはHTMLシンタックスのHTMLを処理する際に使われる
        - [HTMLシンタックス](http://w3c.github.io/html-reference/syntax.html)
    - XMLパーサーはXMLシンタックスのXMLを処理する際に使われる
        - [XMLシンタックス](http://w3c.github.io/html-reference/references.html#refsXML)
        - [XMLの仕様](http://w3c.github.io/html-reference/references.html#refsXML)
        - [xmlの説明](http://w3c.github.io/html-reference/documents.html#syntax-document-xml)


## 2. The HTML namespace and MIME types

- HTML名前空間は[ここで](http://www.w3.org/1999/xhtml.)で定義されている
- HTML名前空間はHTML/XMLシンタックスのための名前空間
- text / html MIMEタイプで提供されるドキュメントは、HTML構文のドキュメントの特性について、このリファレンスの記述と一致している必要があります。
- HTML名前空間宣言を持ち、text / xml、application / xml、application / xhtml + xmlなどのXML MIMEタイプで処理される文書は、XML構文の文書の特性について、このリファレンスの記述と一致している必要があります。


## 3-1. Conformant documents in the HTML syntax

- HTML構文の適合文書は、以下の順番で構成されている必要があります。

1. 必要に応じて、単一のU+FEFF BOM
2. いくつかのコメントと空白文字
3. doctype
4. いくつかのコメントと空白文字
5. html要素と属性とそのコンテンツ
    - html要素の開始タグと終了タグ、および場合によってはhtml要素の特定の子孫要素の開始タグと終了タグを省略することができます。
        - この場合、開始タグと終了タグは暗黙的に指定されます。
6. いくつかのコメントと空白文字

- htmlシンタックスを持ったドキュメントはこのリファレンスのhtmlシンタックスで説明されているシンタックスとマッチしている必要がある


### 3-1-1 Implied start tags and end tags

- htmlシンタックスのドキュメントでは、html要素とhtml要素の特定の子孫要素の開始/終了タグは省略できる。
- 特定の要素でタグの省略があっった場合でも、概念的には、文書は要素を含むと考えることができる
- その開始タグと終了タグが暗黙に含まれていると見なすことができます。
- 以下の例ではhtml, head, bodyタグが暗黙的に含まれている
    - それにもかかわらず、完全で有効な文書であることに注意してください。
```html
<!DOCTYPE html>
<title>A relatively minimal HTML document</title>
<p>Hello World!</p>
```

- user agentから見ると、この例のDOMツリーは以下のように構成されている
    - DOMツリーには、開始タグと終了タグが文書に暗示されているhtml、head、およびbody要素が含まれています。


### 3-2 Conformant documents in the XML syntax

- XML構文の適合文書は、[Namespaces in XML]仕様で定義されているように、名前空間で整形式のXML文書でなければならず、そのルート要素はhtml要素でなければなりません。
    - XML構文の文書は、XML形式の制約に従わないHTML構文の機能を使用してはならない（例えば、XML構文の文書は引用されていない属性値構文を使用してはならず、タグを省略してはならない）。


## 4. Case insensitivity in tag names and attribute names

- HTML構文のドキュメントでは、
    - HTML要素のタグ名は、この文書のHTML要素のセクションで与えられた要素の名前の大文字と小文字を区別しない大文字と小文字の組み合わせで記述することができます。つまり、タグ名では大文字と小文字が区別されません。
    - HTML要素の属性名は、この文書のHTML要素のセクションで与えられた属性の名前の大文字と小文字を区別しない大文字と小文字の組み合わせで記述することができます。つまり、属性名は大文字と小文字を区別しません。

- XML構文のドキュメントでは、
    - HTML要素のタグ名は、この文書のHTML要素の節で与えられた要素の名前と完全に一致していなければなりません。つまり、タグ名では大文字と小文字が区別されます。
    - HTML要素の属性名は、この文書のHTML要素の節で与えられた属性の名前と完全に一致していなければなりません。つまり、属性名では大文字と小文字が区別されます。
