# QTextLine Class Reference

## [[QtGui](index.htm) module]

在QTextLine类表示一个文本行内[QTextLayout](qtextlayout.html)。[More...](#details)

### Types

*   `enum CursorPosition { CursorBetweenCharacters, CursorOnCharacter }`
*   `enum Edge { Leading, Trailing }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextLine)`
*   `float ascent (self)`
*   `(float, int cursorPos) cursorToX (self, int cursorPos, Edge edge = QTextLine.Leading)`
*   `float descent (self)`
*   `draw (self, QPainter painter, QPointF position, QTextLayout.FormatRange selection = None)`
*   `float height (self)`
*   `float horizontalAdvance (self)`
*   `bool isValid (self)`
*   `float leading (self)`
*   `bool leadingIncluded (self)`
*   `int lineNumber (self)`
*   `QRectF naturalTextRect (self)`
*   `float naturalTextWidth (self)`
*   `QPointF position (self)`
*   `QRectF rect (self)`
*   `setLeadingIncluded (self, bool included)`
*   `setLineWidth (self, float width)`
*   `setNumColumns (self, int columns)`
*   `setNumColumns (self, int columns, float alignmentWidth)`
*   `setPosition (self, QPointF pos)`
*   `int textLength (self)`
*   `int textStart (self)`
*   `float width (self)`
*   `float x (self)`
*   `int xToCursor (self, float x, CursorPosition edge = QTextLine.CursorBetweenCharacters)`
*   `float y (self)`

* * *

## Detailed Description

在QTextLine类表示一个文本行内[QTextLayout](qtextlayout.html)。

一个文本行通常是由创建[QTextLayout.createLine](qtextlayout.html#createLine)（ ） 。

创建后，该行可使用的填充[setLineWidth](qtextline.html#setLineWidth)（）或[setNumColumns](qtextline.html#setNumColumns)（）函数。 A线都有一些属性，包括其佔用的矩形，[rect](qtextline.html#rect)（） ，其坐标，[x](qtextline.html#x)（）和[y](qtextline.html#y)（） ，其[textLength](qtextline.html#textLength)（ ）[width](qtextline.html#width)（）和[naturalTextWidth](qtextline.html#naturalTextWidth)（） ，和其[ascent](qtextline.html#ascent)（ ）和体面（）相对于文本。光标在该行的条款的位置是可从[cursorToX](qtextline.html#cursorToX)（）和从它的逆[xToCursor](qtextline.html#xToCursor)（ ） 。 A线可以与移动[setPosition](qtextline.html#setPosition)（ ） 。

* * *

## Type Documentation

```
QTextLine.CursorPosition
```

| Constant | Value |
| --- | --- |
| `QTextLine.CursorBetweenCharacters` | `0` |
| `QTextLine.CursorOnCharacter` | `1` |

```
QTextLine.Edge
```

| Constant | Value |
| --- | --- |
| `QTextLine.Leading` | `0` |
| `QTextLine.Trailing` | `1` |

* * *

## Method Documentation

```
QTextLine.__init__ (self)
```

创建一个无效的行。

```
QTextLine.__init__ (self, QTextLine)
```

```
float QTextLine.ascent (self)
```

返回该行的崛起。

**See also** [descent](qtextline.html#descent)（）和[height](qtextline.html#height)（ ） 。

```
(float, int cursorPos) QTextLine.cursorToX (self, int cursorPos, Edge edge = QTextLine.Leading)
```

光标位置转换_cursorPos_到的对应的行内x位置，同时考虑_edge_。

If _cursorPos_是不是一个有效的光标位置，最接近的有效光标位置将被替代使用，并CPOS将被修改为指向这个有效的光标位置。

**See also** [xToCursor](qtextline.html#xToCursor)（ ） 。

```
float QTextLine.descent (self)
```

返回该行的后裔。

**See also** [ascent](qtextline.html#ascent)（）和[height](qtextline.html#height)（ ） 。

```
QTextLine.draw (self, QPainter painter, QPointF position, QTextLayout.FormatRange selection = None)
```

绘制行中给定的_painter_在指定的_position_。该_selection_供内部使用保留的。

```
float QTextLine.height (self)
```

返回该行的高度。这等于[ascent](qtextline.html#ascent)（）+[descent](qtextline.html#descent)（ ） + 1 ，如果是不包括在内的领先。如果领导包括在内，这等于[ascent](qtextline.html#ascent)（）+[descent](qtextline.html#descent)（）+[leading](qtextline.html#leading)（）+ 1 。

**See also** [ascent](qtextline.html#ascent)（ ）[descent](qtextline.html#descent)（ ）[leading](qtextline.html#leading)（）和[setLeadingIncluded](qtextline.html#setLeadingIncluded)（ ） 。

```
float QTextLine.horizontalAdvance (self)
```

返回文本的水平前进。文本的进步是从它的位置到下一个位置，在该文本自然会得出的距离。

通过将前进到文本行的位置，并使用这个作为第二文本行的位置，你就可以无需在两者之间的间隙来定位两行并排侧。

此功能被引入Qt的4.7 。

```
bool QTextLine.isValid (self)
```

返回True如果该文本行是有效的，否则返回False 。

```
float QTextLine.leading (self)
```

返回该行的领导。

此功能被引入Qt的4.6 。

**See also** [ascent](qtextline.html#ascent)（ ）[descent](qtextline.html#descent)（）和[height](qtextline.html#height)（ ） 。

```
bool QTextLine.leadingIncluded (self)
```

返回True如果积极主导，计入该行的高度，否则返回False 。

默认情况下，是不包括在内的领先。

此功能被引入Qt的4.6 。

**See also** [setLeadingIncluded](qtextline.html#setLeadingIncluded)（ ） 。

```
int QTextLine.lineNumber (self)
```

返回文本引擎的线的位置。

```
QRectF QTextLine.naturalTextRect (self)
```

[

返回复盖的线的矩形。

```
float QTextLine.naturalTextWidth (self)
```

](qrectf.html)

[返回由文本所佔据的线的宽度。这始终是\u003c =到](qrectf.html)[width](qtextline.html#width)（ ） ，并且是可以在不改变换行位置使用的布局（ ）的最小宽度。

```
QPointF QTextLine.position (self)
```

[

返回该行的位置相对于文本布局的地位。

](qpointf.html)

[**See also**](qpointf.html) [setPosition](qtextline.html#setPosition)（ ） 。

```
QRectF QTextLine.rect (self)
```

[

返回该行的边界矩形。

](qrectf.html)

[**See also**](qrectf.html) [x](qtextline.html#x)（ ）[y](qtextline.html#y)（ ）[textLength](qtextline.html#textLength)（）和[width](qtextline.html#width)（ ） 。

```
QTextLine.setLeadingIncluded (self, bool included)
```

包括积极主导入行的高度，如果_included_为True，否则不包括领先。

默认情况下，是不包括在内的领先。

需要注意的是负领先被忽略，它必须在代码中使用的文本行通过让线重叠处理。

此功能被引入Qt的4.6 。

**See also** [leadingIncluded](qtextline.html#leadingIncluded)（ ） 。

```
QTextLine.setLineWidth (self, float width)
```

勾画出具有给定的线_width_。该生产线是从起始位置充满了尽可能多的字符将适合入行。在壳体的文本不能被分割在该行的末尾，将被填充有附加字符到下一个空白字符或文本的末尾。

```
QTextLine.setNumColumns (self, int columns)
```

勾画出的线条。该生产线是从它的起始位置充满了尽可能多的字符被指定_numColumns_。若文本不能被分割，直到_numColumns_字符，该行就会充满尽可能多的字符到下一个空格或文字的结尾。

```
QTextLine.setNumColumns (self, int columns, float alignmentWidth)
```

勾画出的线条。该生产线是从它的起始位置充满了尽可能多的字符被指定_numColumns_。若文本不能被分割，直到_numColumns_字符，该行就会充满尽可能多的字符到下一个空格或文字的结尾。提供_alignmentWidth_被用作基准宽度对齐。

```
QTextLine.setPosition (self, QPointF pos)
```

移动线位置_pos_。

**See also** [position](qtextline.html#position)（ ） 。

```
int QTextLine.textLength (self)
```

返回该行的文本的长度。

**See also** [naturalTextWidth](qtextline.html#naturalTextWidth)（ ） 。

```
int QTextLine.textStart (self)
```

返回该行的开始从传递到该字符串的开头[QTextLayout](qtextlayout.html)。

```
float QTextLine.width (self)
```

返回所指定的布局（ ）函数线的宽度。

**See also** [naturalTextWidth](qtextline.html#naturalTextWidth)（ ）[x](qtextline.html#x)（ ）[y](qtextline.html#y)（ ）[textLength](qtextline.html#textLength)（）和[rect](qtextline.html#rect)（ ） 。

```
float QTextLine.x (self)
```

返回该行的x位置。

**See also** [rect](qtextline.html#rect)（ ）[y](qtextline.html#y)（ ）[textLength](qtextline.html#textLength)（）和[width](qtextline.html#width)（ ） 。

```
int QTextLine.xToCursor (self, float x, CursorPosition edge = QTextLine.CursorBetweenCharacters)
```

转换的x坐标_x_到最近匹配的光标位置，根据光标位置类型，_cpos_。

**See also** [cursorToX](qtextline.html#cursorToX)（ ） 。

```
float QTextLine.y (self)
```

返回该行的y位置。

**See also** [x](qtextline.html#x)（ ）[rect](qtextline.html#rect)（ ）[textLength](qtextline.html#textLength)（）和[width](qtextline.html#width)（ ） 。