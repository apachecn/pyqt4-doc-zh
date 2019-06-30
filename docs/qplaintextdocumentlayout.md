# QPlainTextDocumentLayout Class Reference

## [[QtGui](index.htm) module]

该QPlainTextDocumentLayout类实现一个纯文本布局[QTextDocument](qtextdocument.html) [More...](#details)

继承[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)。

### Methods

*   `__init__ (self, QTextDocument document)`
*   `QRectF blockBoundingRect (self, QTextBlock block)`
*   `int cursorWidth (self)`
*   `documentChanged (self, int from, int, int charsAdded)`
*   `QSizeF documentSize (self)`
*   `draw (self, QPainter, QAbstractTextDocumentLayout.PaintContext)`
*   `ensureBlockLayout (self, QTextBlock block)`
*   `QRectF frameBoundingRect (self, QTextFrame)`
*   `int hitTest (self, QPointF, Qt.HitTestAccuracy)`
*   `int pageCount (self)`
*   `requestUpdate (self)`
*   `setCursorWidth (self, int width)`

* * *

## Detailed Description

该QPlainTextDocumentLayout类实现一个纯文本布局[QTextDocument](qtextdocument.html)

一个QPlainTextDocumentLayout是必需的文本文档，可显示或编辑的[QPlainTextEdit](qplaintextedit.html)。看[QTextDocument.setDocumentLayout](qtextdocument.html#setDocumentLayout)（ ） 。

QPlainTextDocumentLayout使用[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)的API，[QTextDocument](qtextdocument.html)需要，但部分重新定义它，以更好地支持纯文本。为实例，并不对垂直像素进行操作，但在第（称为块）来代替。文档的高度是相同的它包含段落的数目。布局上也并不支持表或嵌套的框架，或者说超出了语法高亮段落的列表，任何形式的先进的文本布局。

* * *

## Method Documentation

```
QPlainTextDocumentLayout.__init__ (self, QTextDocument document)
```

构造一个纯文本文档布局的文本_document_。

```
QRectF QPlainTextDocumentLayout.blockBoundingRect (self, QTextBlock block)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QAbstractTextDocumentLayout.blockBoundingRect](qabstracttextdocumentlayout.html#blockBoundingRect)（ ） 。

```
int QPlainTextDocumentLayout.cursorWidth (self)
```

```
QPlainTextDocumentLayout.documentChanged (self, int from, int, int charsAdded)
```

从重新实现[QAbstractTextDocumentLayout.documentChanged](qabstracttextdocumentlayout.html#documentChanged)（ ） 。

```
QSizeF QPlainTextDocumentLayout.documentSize (self)
```

[](qsizef.html)

[从重新实现](qsizef.html)[QAbstractTextDocumentLayout.documentSize](qabstracttextdocumentlayout.html#documentSize)（ ） 。

```
QPlainTextDocumentLayout.draw (self, QPainter, QAbstractTextDocumentLayout.PaintContext)
```

从重新实现[QAbstractTextDocumentLayout.draw](qabstracttextdocumentlayout.html#draw)（ ） 。

```
QPlainTextDocumentLayout.ensureBlockLayout (self, QTextBlock block)
```

确保_block_具有有效的布局

```
QRectF QPlainTextDocumentLayout.frameBoundingRect (self, QTextFrame)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QAbstractTextDocumentLayout.frameBoundingRect](qabstracttextdocumentlayout.html#frameBoundingRect)（ ） 。

```
int QPlainTextDocumentLayout.hitTest (self, QPointF, Qt.HitTestAccuracy)
```

从重新实现[QAbstractTextDocumentLayout.hitTest](qabstracttextdocumentlayout.html#hitTest)（ ） 。

```
int QPlainTextDocumentLayout.pageCount (self)
```

从重新实现[QAbstractTextDocumentLayout.pageCount](qabstracttextdocumentlayout.html#pageCount)（ ） 。

```
QPlainTextDocumentLayout.requestUpdate (self)
```

请在所有视图一个完整的更新。

```
QPlainTextDocumentLayout.setCursorWidth (self, int width)
```