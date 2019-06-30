# QTextDocumentFragment Class Reference

## [[QtGui](index.htm) module]

该QTextDocumentFragment类表示了一块格式化文本从一个[QTextDocument](qtextdocument.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextDocument document)`
*   `__init__ (self, QTextCursor range)`
*   `__init__ (self, QTextDocumentFragment rhs)`
*   `bool isEmpty (self)`
*   `QString toHtml (self)`
*   `QString toHtml (self, QByteArray encoding)`
*   `QString toPlainText (self)`

### Static Methods

*   `QTextDocumentFragment fromHtml (QString html)`
*   `QTextDocumentFragment fromHtml (QString html, QTextDocument resourceProvider)`
*   `QTextDocumentFragment fromPlainText (QString plainText)`

* * *

## Detailed Description

该QTextDocumentFragment类表示了一块格式化文本从一个[QTextDocument](qtextdocument.html)。

一个QTextDocumentFragment是富文本的一个片段，可以插入到[QTextDocument](qtextdocument.html)。文档片段可以从被创建[QTextDocument](qtextdocument.html)，从[QTextCursor](qtextcursor.html)的选择，或从另一个文件片段。文件的片段，也可以通过静态函数创建的，[fromPlainText](qtextdocumentfragment.html#fromPlainText)（）和[fromHtml](qtextdocumentfragment.html#fromHtml)（ ） 。

文档片段的内容可以通过使用获得以纯文本的[toPlainText](qtextdocumentfragment.html#toPlainText)（）函数，或者它可以得到的HTML[toHtml](qtextdocumentfragment.html#toHtml)（ ） 。

* * *

## Method Documentation

```
QTextDocumentFragment.__init__ (self)
```

构造一个空[QTextDocumentFragment](qtextdocumentfragment.html)。

**See also** [isEmpty](qtextdocumentfragment.html#isEmpty)（ ） 。

```
QTextDocumentFragment.__init__ (self, QTextDocument document)
```

转换给定的_document_成[QTextDocumentFragment](qtextdocumentfragment.html)。注意，这个[QTextDocumentFragment](qtextdocumentfragment.html)只存储文件内容，而不是像文档的标题的元信息。

```
QTextDocumentFragment.__init__ (self, QTextCursor range)
```

创建[QTextDocumentFragment](qtextdocumentfragment.html)从_cursor_的选择。如果光标没有选择，创建​​片段是空的。

**See also** [isEmpty](qtextdocumentfragment.html#isEmpty)（）和[QTextCursor.selection](qtextcursor.html#selection)（ ） 。

```
QTextDocumentFragment.__init__ (self, QTextDocumentFragment rhs)
```

拷贝构造函数。创建的副本_other_片段。

```
QTextDocumentFragment QTextDocumentFragment.fromHtml (QString html)
```

[](qtextdocumentfragment.html)

[返回](qtextdocumentfragment.html)[QTextDocumentFragment](qtextdocumentfragment.html)根据任意一块的HTML中的给定_text_。该格式被保留尽可能多的，例如， “ \u003cb\u003e粗体\u003c / B\u003e ”将成为一个文档片段与文本“大胆”的一个大胆的字符格式。

```
QTextDocumentFragment QTextDocumentFragment.fromHtml (QString html, QTextDocument resourceProvider)
```

[](qtextdocumentfragment.html)

[返回](qtextdocumentfragment.html)[QTextDocumentFragment](qtextdocumentfragment.html)根据任意一块的HTML中的给定_text_。该格式被保留尽可能多的，例如， “ \u003cb\u003e粗体\u003c / B\u003e ”将成为一个文档片段与文本“大胆”的一个大胆的字符格式。

如果所提供的HTML包含引用外部资源，如导入的样式表，那么他们将通过加载_resourceProvider_。

这个函数中引入了Qt 4.2中。

```
QTextDocumentFragment QTextDocumentFragment.fromPlainText (QString plainText)
```

[

返回包含给定一个文档片段_plainText_。

](qtextdocumentfragment.html)

[当插入这样一个片段成](qtextdocumentfragment.html)[QTextDocument](qtextdocument.html)的当前字符格式[QTextCursor](qtextcursor.html)用于插入被用作文本格式。

```
bool QTextDocumentFragment.isEmpty (self)
```

返回True如果该片段为空，否则返回False 。

```
QString QTextDocumentFragment.toHtml (self)
```

返回文档片段的内容作为HTML，使用指定的_encoding_（例如， “UTF- 8”，“ ISO 8859 ” ） 。

这个函数中引入了Qt 4.2中。

**See also** [toPlainText](qtextdocumentfragment.html#toPlainText)（ ）[QTextDocument.toHtml](qtextdocument.html#toHtml)（）和[QTextCodec](qtextcodec.html)。

```
QString QTextDocumentFragment.toHtml (self, QByteArray encoding)
```

这是一个重载函数。

```
QString QTextDocumentFragment.toPlainText (self)
```

返回文档片段的文字为纯文本（即不带格式信息） 。

**See also** [toHtml](qtextdocumentfragment.html#toHtml)（ ） 。