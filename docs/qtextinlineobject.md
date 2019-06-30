# QTextInlineObject Class Reference

## [[QtGui](index.htm) module]

该QTextInlineObject类表示一个嵌入对象[QTextLayout](qtextlayout.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextInlineObject)`
*   `float ascent (self)`
*   `float descent (self)`
*   `QTextFormat format (self)`
*   `int formatIndex (self)`
*   `float height (self)`
*   `bool isValid (self)`
*   `QRectF rect (self)`
*   `setAscent (self, float a)`
*   `setDescent (self, float d)`
*   `setWidth (self, float w)`
*   `Qt.LayoutDirection textDirection (self)`
*   `int textPosition (self)`
*   `float width (self)`

* * *

## Detailed Description

该QTextInlineObject类表示一个嵌入对象[QTextLayout](qtextlayout.html)。

如果文本布局是用来铺陈的部分该类仅用于[QTextDocument](qtextdocument.html)。

嵌入对象具有使用，可以设置各种属性，例如[setWidth](qtextinlineobject.html#setWidth)（ ）[setAscent](qtextinlineobject.html#setAscent)（）和[setDescent](qtextinlineobject.html#setDescent)（ ） 。它佔据矩形由下式给出[rect](qtextinlineobject.html#rect)（） ，并通过isRightToLeft其方向（） 。它在文本布局位置（由下式给出） ，其格式由下式给出[format](qtextinlineobject.html#format)（ ） 。

* * *

## Method Documentation

```
QTextInlineObject.__init__ (self)
```

创建用于在位置的项目一个新的嵌入对象_i_在文本引擎_e_。

```
QTextInlineObject.__init__ (self, QTextInlineObject)
```

```
float QTextInlineObject.ascent (self)
```

返回内嵌对象的上升。

**See also** [setAscent](qtextinlineobject.html#setAscent)（ ）[descent](qtextinlineobject.html#descent)（ ）[width](qtextinlineobject.html#width)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
float QTextInlineObject.descent (self)
```

返回内嵌对象的血统。

**See also** [setDescent](qtextinlineobject.html#setDescent)（ ）[ascent](qtextinlineobject.html#ascent)（ ）[width](qtextinlineobject.html#width)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
QTextFormat QTextInlineObject.format (self)
```

[

返回中的文本布局内联对象的格式。

```
int QTextInlineObject.formatIndex (self)
```

返回描述中的文本布局内联对象的格式为整数。

```
float QTextInlineObject.height (self)
```

](qtextformat.html)

[返回内嵌对象的总高度。这等于](qtextformat.html)[ascent](qtextinlineobject.html#ascent)（）+[descent](qtextinlineobject.html#descent)（）+ 1 。

**See also** [ascent](qtextinlineobject.html#ascent)（ ）[descent](qtextinlineobject.html#descent)（ ）[width](qtextinlineobject.html#width)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
bool QTextInlineObject.isValid (self)
```

返回True如果嵌入对象是有效的，否则返回False 。

```
QRectF QTextInlineObject.rect (self)
```

[

返回内嵌对象的矩形。

](qrectf.html)

[**See also**](qrectf.html) [ascent](qtextinlineobject.html#ascent)（ ）[descent](qtextinlineobject.html#descent)（）和[width](qtextinlineobject.html#width)（ ） 。

```
QTextInlineObject.setAscent (self, float a)
```

设置内嵌对象的登顶_a_。

**See also** [ascent](qtextinlineobject.html#ascent)（ ）[setDescent](qtextinlineobject.html#setDescent)（ ）[width](qtextinlineobject.html#width)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
QTextInlineObject.setDescent (self, float d)
```

设置内嵌对象的体面_d_。

**See also** [descent](qtextinlineobject.html#descent)（ ）[setAscent](qtextinlineobject.html#setAscent)（ ）[width](qtextinlineobject.html#width)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
QTextInlineObject.setWidth (self, float w)
```

设置内嵌对象的宽度_w_。

**See also** [width](qtextinlineobject.html#width)（ ）[ascent](qtextinlineobject.html#ascent)（ ）[descent](qtextinlineobject.html#descent)（）和[rect](qtextinlineobject.html#rect)（ ） 。

```
Qt.LayoutDirection QTextInlineObject.textDirection (self)
```

[

如果对象应订出从右到左或向右。

```
int QTextInlineObject.textPosition (self)
```

内联对象内的文本布局位置。

```
float QTextInlineObject.width (self)
```

返回内嵌对象的宽度。

](qt.html#LayoutDirection-enum)

[**See also**](qt.html#LayoutDirection-enum) [setWidth](qtextinlineobject.html#setWidth)（ ）[ascent](qtextinlineobject.html#ascent)（ ）[descent](qtextinlineobject.html#descent)（）和[rect](qtextinlineobject.html#rect)（ ） 。