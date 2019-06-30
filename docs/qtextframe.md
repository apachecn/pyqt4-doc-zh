# QTextFrame Class Reference

## [[QtGui](index.htm) module]

该QTextFrame类表示一帧[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextObject](qtextobject.html)。

通过继承[QTextTable](qtexttable.html)。

### Types

*   `class **[iterator](index.htm)**`

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `iterator begin (self)`
*   `list-of-QTextFrame childFrames (self)`
*   `iterator end (self)`
*   `QTextCursor firstCursorPosition (self)`
*   `int firstPosition (self)`
*   `QTextFrameFormat frameFormat (self)`
*   `QTextCursor lastCursorPosition (self)`
*   `int lastPosition (self)`
*   `QTextFrame parentFrame (self)`
*   `setFrameFormat (self, QTextFrameFormat aformat)`

* * *

## Detailed Description

该QTextFrame类表示一帧[QTextDocument](qtextdocument.html)。

文本框的文档中的文本提供结构。它们被用作通用的容器，其他的文档元素。帧通常是通过使用建立的[QTextCursor.insertFrame](qtextcursor.html#insertFrame)（ ） 。

框架可以用来创建分层结构的富文本文档。每个文档都有一个根框架（[QTextDocument.rootFrame](qtextdocument.html#rootFrame)（ ） ） ，根框架下的每一帧都有一个父框架和子框架的一个（可能为空）列表。父框架可以被发现[parentFrame](qtextframe.html#parentFrame)（ ）和[childFrames](qtextframe.html#childFrames)（）函数提供子框架的列表。

每个帧包含至少一个文本块，使文字游标中插入新的文档元素。其结果是，在[QTextFrame.iterator](index.htm)类是用来给定的框架内穿越两个块和子框架。在该帧中的第一个和最后一个子元素可以与发现[begin](qtextframe.html#begin)（）和[end](qtextframe.html#end)（ ） 。

帧也有使用的格式（指定[QTextFrameFormat](qtextframeformat.html)），它可与设置[setFormat](qtextobject.html#setFormat)（）和read与[format](qtextobject.html#format)（ ） 。

文字游标可以得到该点到框架内的第一个和最后一个有效的光标位置;使用[firstCursorPosition](qtextframe.html#firstCursorPosition)（）和[lastCursorPosition](qtextframe.html#lastCursorPosition)（ ）这个函数。在文档中的帧的幅度可以与发现[firstPosition](qtextframe.html#firstPosition)（）和[lastPosition](qtextframe.html#lastPosition)（ ） 。

您可以使用在一帧中的内容重复的[QTextFrame.iterator](index.htm)类：这提供了其内部文本块和子帧的列表只读访问。

* * *

## Method Documentation

```
QTextFrame.__init__ (self, QTextDocument doc)
```

创建文本一个新的空框架_document_。

```
iterator QTextFrame.begin (self)
```

[](index.htm)

[返回一个迭代器指向框架内的第一个文档元素。请参阅文档](index.htm)[STL-style-Iterators](index.htm#stl-style-iterators)了解更多信息。

**See also** [end](qtextframe.html#end)（ ） 。

```
list-of-QTextFrame QTextFrame.childFrames (self)
```

返回框架的子框架的一个（可能为空）列表。

**See also** [parentFrame](qtextframe.html#parentFrame)（ ） 。

```
iterator QTextFrame.end (self)
```

[](index.htm)

[返回一个迭代器，指向过去的框架内的最后一个文档元素的位置。请参阅文档](index.htm)[STL-Style Iterators](index.htm#stl-style-iterators)了解更多信息。

**See also** [begin](qtextframe.html#begin)（ ） 。

```
QTextCursor QTextFrame.firstCursorPosition (self)
```

[

返回框架内的第一个光标位置。

](qtextcursor.html)

[**See also**](qtextcursor.html) [lastCursorPosition](qtextframe.html#lastCursorPosition)（ ）[firstPosition](qtextframe.html#firstPosition)（）和[lastPosition](qtextframe.html#lastPosition)（ ） 。

```
int QTextFrame.firstPosition (self)
```

返回框架内的第一个文件的位置。

**See also** [lastPosition](qtextframe.html#lastPosition)（ ）[firstCursorPosition](qtextframe.html#firstCursorPosition)（）和[lastCursorPosition](qtextframe.html#lastCursorPosition)（ ） 。

```
QTextFrameFormat QTextFrame.frameFormat (self)
```

[

返回帧的格式。

](qtextframeformat.html)

[**See also**](qtextframeformat.html) [setFrameFormat](qtextframe.html#setFrameFormat)（ ） 。

```
QTextCursor QTextFrame.lastCursorPosition (self)
```

[

返回框架内的一个光标位置。

](qtextcursor.html)

[**See also**](qtextcursor.html) [firstCursorPosition](qtextframe.html#firstCursorPosition)（ ）[firstPosition](qtextframe.html#firstPosition)（）和[lastPosition](qtextframe.html#lastPosition)（ ） 。

```
int QTextFrame.lastPosition (self)
```

返回框架内的最后一份文件的位置。

**See also** [firstPosition](qtextframe.html#firstPosition)（ ）[firstCursorPosition](qtextframe.html#firstCursorPosition)（）和[lastCursorPosition](qtextframe.html#lastCursorPosition)（ ） 。

```
QTextFrame QTextFrame.parentFrame (self)
```

[

返回框架的父框架。如果该帧是一个文件的根帧，这将返回0。

](qtextframe.html)

[**See also**](qtextframe.html) [childFrames](qtextframe.html#childFrames)（）和[QTextDocument.rootFrame](qtextdocument.html#rootFrame)（ ） 。

```
QTextFrame.setFrameFormat (self, QTextFrameFormat aformat)
```

设置帧的_format_。

**See also** [frameFormat](qtextframe.html#frameFormat)（ ） 。