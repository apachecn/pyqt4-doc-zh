# QAbstractTextDocumentLayout Class Reference

## [[QtGui](index.htm) module]

该QAbstractTextDocumentLayout类是用于实现自定义布局QTextDocuments的抽象基类。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QPlainTextDocumentLayout](qplaintextdocumentlayout.html)。

### Types

*   `class **[PaintContext](index.htm)**`
*   `class **[Selection](index.htm)**`

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `QString anchorAt (self, QPointF pos)`
*   `QRectF blockBoundingRect (self, QTextBlock block)`
*   `QTextDocument document (self)`
*   `documentChanged (self, int from, int charsRemoved, int charsAdded)`
*   `QSizeF documentSize (self)`
*   `draw (self, QPainter painter, PaintContext context)`
*   `drawInlineObject (self, QPainter painter, QRectF rect, QTextInlineObject object, int posInDocument, QTextFormat format)`
*   `QTextCharFormat format (self, int pos)`
*   `QRectF frameBoundingRect (self, QTextFrame frame)`
*   `QTextObjectInterface handlerForObject (self, int objectType)`
*   `int hitTest (self, QPointF point, Qt.HitTestAccuracy accuracy)`
*   `int pageCount (self)`
*   `QPaintDevice paintDevice (self)`
*   `positionInlineObject (self, QTextInlineObject item, int posInDocument, QTextFormat format)`
*   `registerHandler (self, int objectType, QObject component)`
*   `resizeInlineObject (self, QTextInlineObject item, int posInDocument, QTextFormat format)`
*   `setPaintDevice (self, QPaintDevice device)`

### Qt Signals

*   `void documentSizeChanged (const QSizeF&)`
*   `void pageCountChanged (int)`
*   `void update (const QRectF& = QRectF(0,0,1e+09,1e+09))`
*   `void updateBlock (const QTextBlock&)`

* * *

## Detailed Description

该QAbstractTextDocumentLayout类是用于实现自定义布局QTextDocuments的抽象基类。

Qt提供了标准布局可以处理简单的文字处理，包括内嵌图片，列表和表格。

有些应用程序，如文字处理器或DTP应用程序可能需要比Qt的布局引擎提供的，那些更多的功能，在这种情况下，你可以继承QAbstractTextDocumentLayout为您的文本文档提供自定义布局行为。

该QAbstractTextDocumentLayout子类的实例可以在安装[QTextDocument](qtextdocument.html)与对象[setDocumentLayout()](qtextdocument.html#setDocumentLayout)功能。

您可以将自定义对象成[QTextDocument](qtextdocument.html)，见[QTextObjectInterface](qtextobjectinterface.html)类描述的细节。

* * *

## Method Documentation

```
QAbstractTextDocumentLayout.__init__ (self, QTextDocument doc)
```

创建用于指定一个新的文本文档布局_document_。

```
QString QAbstractTextDocumentLayout.anchorAt (self, QPointF pos)
```

返回锚的参考给定的_position_，或者如果没有锚存在于该点一个空字符串。

```
QRectF QAbstractTextDocumentLayout.blockBoundingRect (self, QTextBlock block)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的边框_block_。

](qrectf.html)

```
QTextDocument QAbstractTextDocumentLayout.document (self)
```

[

返回此布局工作于文本文档。

```
QAbstractTextDocumentLayout.documentChanged (self, int from, int charsRemoved, int charsAdded)
```

这种方法是抽象的，应在任何子类中重新实现。

此功能被称为文档变化时的内容。当文本被插入，删除时，会发生变化，或这两种的组合。这种变化是通过指定_position_，_charsRemoved_和_charsAdded_对应于该变化的开始字符的位置，从文档中删除的字符数，和字符的数量加入。

例如，进入一个空文档中插入文本“Hello ”时，_charsRemoved_将0和_charsAdded_将5（该字符串的长度）。

替换文本是删除和插入的组合。例如，如果文本“Hello ”被替换为“Hi” ，_charsRemoved_将是5和_charsAdded_将2 。

](qtextdocument.html)

[对于子类](qtextdocument.html)[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)，这是中央函数所在的工作的很大一部分来布置和位置文件的内容已经完成。

例如，在一个子类，只安排文本块，这个功能的实现就必须做到以下几点：

*   Determine the list of changed [QTextBlock](qtextblock.html)(s) using the parameters provided.
*   Each [QTextBlock](qtextblock.html) object's corresponding [QTextLayout](qtextlayout.html) object needs to be processed. You can access the [QTextBlock](qtextblock.html)'s layout using the [QTextBlock.layout](qtextblock.html#layout)() function. This processing should take the document's page size into consideration.
*   If the total number of pages changed, the [pageCountChanged](qabstracttextdocumentlayout.html#pageCountChanged)() signal should be emitted.
*   If the total size changed, the [documentSizeChanged](qabstracttextdocumentlayout.html#documentSizeChanged)() signal should be emitted.
*   The [update](qabstracttextdocumentlayout.html#update)() signal should be emitted to schedule a repaint of areas in the layout that require repainting.

**See also** [QTextLayout](qtextlayout.html)。

```
QSizeF QAbstractTextDocumentLayout.documentSize (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回文档的布局的总大小。

这些信息可用于显示部件来正确地更新自己的滚动条。

](qsizef.html)

[**See also**](qsizef.html) [documentSizeChanged](qabstracttextdocumentlayout.html#documentSizeChanged)（）和[QTextDocument.pageSize](qtextdocument.html#pageSize-prop)。

```
QAbstractTextDocumentLayout.draw (self, QPainter painter, PaintContext context)
```

这种方法是抽象的，应在任何子类中重新实现。

绘制布局与给定的_painter_使用给定的_context_。

```
QAbstractTextDocumentLayout.drawInlineObject (self, QPainter painter, QRectF rect, QTextInlineObject object, int posInDocument, QTextFormat format)
```

调用此函数绘制内嵌的对象，_object_用给定的_painter_由指定的矩形内_rect_使用指定的文本_format_。

_posInDocument_指定文件内的对象的位置。

默认实现调用drawObject （ ）上的对象处理程序。这个函数被调用只在Qt的。子类可以重新实现此功能自定义内联对象的绘制。

**See also** [draw](qabstracttextdocumentlayout.html#draw)（ ） 。

```
QTextCharFormat QAbstractTextDocumentLayout.format (self, int pos)
```

[

返回字符格式，适用于给定的_position_。

](qtextcharformat.html)

```
QRectF QAbstractTextDocumentLayout.frameBoundingRect (self, QTextFrame frame)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的边框_frame_。

](qrectf.html)

```
QTextObjectInterface QAbstractTextDocumentLayout.handlerForObject (self, int objectType)
```

[

返回一个处理程序的特定对象_objectType_。

```
int QAbstractTextDocumentLayout.hitTest (self, QPointF point, Qt.HitTestAccuracy accuracy)
```

这种方法是抽象的，应在任何子类中重新实现。

返回光标当前位置为给定的_point_用指定的_accuracy_。返回-1，如果没有有效的光标位置被发现。

```
int QAbstractTextDocumentLayout.pageCount (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回中所包含的布局的页面数。

](qtextobjectinterface.html)

[**See also**](qtextobjectinterface.html) [pageCountChanged](qabstracttextdocumentlayout.html#pageCountChanged)（ ） 。

```
QPaintDevice QAbstractTextDocumentLayout.paintDevice (self)
```

[

返回用于呈现文档的布局绘制设备。

](qpaintdevice.html)

[**See also**](qpaintdevice.html) [setPaintDevice](qabstracttextdocumentlayout.html#setPaintDevice)（ ） 。

```
QAbstractTextDocumentLayout.positionInlineObject (self, QTextInlineObject item, int posInDocument, QTextFormat format)
```

勾画出嵌入对象_item_使用给定的文本_format_。

_posInDocument_指定文件内的对象的位置。

默认实现不执行任何操作。这个函数被调用只在Qt的。子类可以重新实现此功能自定义内联对象的位置。

**See also** [drawInlineObject](qabstracttextdocumentlayout.html#drawInlineObject)（ ） 。

```
QAbstractTextDocumentLayout.registerHandler (self, int objectType, QObject component)
```

注册给定的_component_作为一个处理程序的特定项目_objectType_。

**Note:**registerHandler （ ）为每个对象类型被调用一次。这意味着，只有一个对相同的对象类型的多个字符替换处理程序。

```
QAbstractTextDocumentLayout.resizeInlineObject (self, QTextInlineObject item, int posInDocument, QTextFormat format)
```

设置内嵌对象的大小_item_对应于文本_format_。

_posInDocument_指定文件内的对象的位置。

默认实现调整大小的_item_由对象处理程序的intrinsicSize （ ）函数返回的大小。这个函数被调用只在Qt的。子类可以重新实现此功能自定义内联对象的大小调整。

```
QAbstractTextDocumentLayout.setPaintDevice (self, QPaintDevice device)
```

获取用于渲染文档的布局，以给定的涂料设备_device_。

**See also** [paintDevice](qabstracttextdocumentlayout.html#paintDevice)（ ） 。

* * *

## Qt Signal Documentation

```
void documentSizeChanged (const QSizeF&)
```

这是该信号的默认超载。

当文档布局的大小变更为这个信号被发射_newSize_。

的子类[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)应该发出这个信号，当文档的整个版面大小的变化。这个信号是显示文本文件，因为它使他们能够正确地更新自己的滚动条小工具非常有用。

**See also** [documentSize](qabstracttextdocumentlayout.html#documentSize)（ ） 。

```
void pageCountChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的布局变化的页数;_newPages_是更新页面计数。

的子类[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)应该发出这个信号时的布局中的页面的数量发生了变化。被改变的页面数通过改变布局或文件内容本身引起的。

**See also** [pageCount](qabstracttextdocumentlayout.html#pageCount)（ ） 。

```
void update (const QRectF& = QRectF (0,0,1e+09,1e+09))
```

这是该信号的默认超载。

这个信号被发射时，矩形_rect_已被更新。

的子类[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)应该发出这个信号，当内容的布局改变，以重新绘制。

```
void updateBlock (const QTextBlock&)
```

这是该信号的默认超载。

指定时，这个信号被发射_block_已被更新。

的子类[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)应该发出这个信号时的布局_block_为了重新绘制了变化。

此功能被引入Qt的4.4 。