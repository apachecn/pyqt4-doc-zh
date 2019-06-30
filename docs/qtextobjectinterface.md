# QTextObjectInterface Class Reference

## [[QtGui](index.htm) module]

该QTextObjectInterface类允许自定义文本对象的图形中[QTextDocument](qtextdocument.html)秒。[More...](#details)

通过继承[QPyTextObject](qpytextobject.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextObjectInterface)`
*   `drawObject (self, QPainter painter, QRectF rect, QTextDocument doc, int posInDocument, QTextFormat format)`
*   `QSizeF intrinsicSize (self, QTextDocument doc, int posInDocument, QTextFormat format)`

* * *

## Detailed Description

该QTextObjectInterface类允许自定义文本对象的图形中[QTextDocument](qtextdocument.html)秒。

文本对象描述的文本文档中的一个或多个元素的结构，例如，从HTML导入的图像是使用文本对象来实现。文本对象知道如何布局并绘制它的元素当一个文档被渲染。

Qt的可自定义文本对象通过注册一个自定义的被插入到文档中[object type](qtextformat.html#objectType)同[QTextCharFormat](qtextcharformat.html)。一个QTextObjectInterface也必须对这种类型实施，并[registered](qabstracttextdocumentlayout.html#registerHandler)与[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)文档。当对象类型，而渲染遇到[QTextDocument](qtextdocument.html)时，[intrinsicSize](qtextobjectinterface.html#intrinsicSize)（）和[drawObject](qtextobjectinterface.html#drawObject)（）的接口的函数被调用。

下面的列表说明插入一个自定义的文本对象插入到文档中所需的步骤：

*   Choose an _objectType_. The _objectType_ is an integer with a value greater or equal to [QTextFormat.UserObject](qtextformat.html#ObjectTypes-enum).
*   Create a [QTextCharFormat](qtextcharformat.html) object and set the object type to the chosen type using the setObjectType() function.
*   Implement the QTextObjectInterface class.
*   Call [QAbstractTextDocumentLayout.registerHandler](qabstracttextdocumentlayout.html#registerHandler)() with an instance of your QTextObjectInterface subclass to register your object type.
*   Insert [QChar.ObjectReplacementCharacter](qchar.html#SpecialCharacter-enum) with the aforementioned [QTextCharFormat](qtextcharformat.html) of the chosen object type into the document. As mentioned, the functions of QTextObjectInterface [intrinsicSize()](qtextobjectinterface.html#intrinsicSize) and [drawObject()](qtextobjectinterface.html#drawObject) will then be called with the [QTextFormat](qtextformat.html) as parameter whenever the replacement character is encountered.

一个类实现一个文本对象需要同时继承[QObject](qobject.html)和QTextObjectInterface 。[QObject](qobject.html)必须是继承了一流的。例如：

```
 class SvgTextObject : public [QObject](qobject.html), public QTextObjectInterface
 {
     Q_OBJECT
     Q_INTERFACES(QTextObjectInterface)

```

文本对象的数据通常存储在[QTextCharFormat](qtextcharformat.html) using [QTextCharFormat.setProperty](qtextformat.html#setProperty)（） ，然后用检索[QTextCharFormat.property](qtextformat.html#property)（ ） 。

**Warning:**复制和粘贴操作忽略自定义的文本对象。

* * *

## Method Documentation

```
QTextObjectInterface.__init__ (self)
```

```
QTextObjectInterface.__init__ (self, QTextObjectInterface)
```

```
QTextObjectInterface.drawObject (self, QPainter painter, QRectF rect, QTextDocument doc, int posInDocument, QTextFormat format)
```

这种方法是抽象的，应在任何子类中重新实现。

使用指定绘制这个文本对象_painter_。

该矩形的大小，_rect_，画中是先前计算的大小[intrinsicSize](qtextobjectinterface.html#intrinsicSize)（ ） 。矩形的位置是相对于_painter_。

您还可以得到该文件（_doc_）和位置（_posInDocument_的）的_format_该文件中。

**See also** [intrinsicSize](qtextobjectinterface.html#intrinsicSize)（ ） 。

```
QSizeF QTextObjectInterface.intrinsicSize (self, QTextDocument doc, int posInDocument, QTextFormat format)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该intrinsicSize （ ）函数返回所代表的文本对象的大小_format_给定的文件中（_doc_）在给定位置（_posInDocument_） 。

](qsizef.html)

[计算出的大小将用于后续调用](qsizef.html)[drawObject](qtextobjectinterface.html#drawObject)（ ）就本_format_。

**See also** [drawObject](qtextobjectinterface.html#drawObject)（ ） 。