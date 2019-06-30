# QGraphicsSimpleTextItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSimpleTextItem类提供了可以添加到一个简单的文本路径项[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `__init__ (self, QString text, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `QRectF boundingRect (self)`
*   `bool contains (self, QPointF point)`
*   `QFont font (self)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPainterPath opaqueArea (self)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)`
*   `setFont (self, QFont font)`
*   `setText (self, QString text)`
*   `QPainterPath shape (self)`
*   `QString text (self)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsSimpleTextItem类提供了可以添加到一个简单的文本路径项[QGraphicsScene](qgraphicsscene.html)。

要设置项的文本，你可以通过一个[QString](qstring.html)到QGraphicsSimpleTextItem的构造函数，或调用[setText](qgraphicssimpletextitem.html#setText)（ ）以后更改的文本。设置文本填充颜色，调用[setBrush](qabstractgraphicsshapeitem.html#setBrush)（ ） 。

简单的文字项目可以同时拥有一个填充和轮廓;[setBrush](qabstractgraphicsshapeitem.html#setBrush)（ ）将设置文本的填充（即，文本颜色） ，和[setPen](qabstractgraphicsshapeitem.html#setPen)（ ）设置将用于绘制文本轮廓的画笔。 （后者可能会很慢，尤其是对于复杂的笔，并与长文本内容项目。 ）如果你想要的是绘制文本的简单的线条，你应该调用[setBrush](qabstractgraphicsshapeitem.html#setBrush)（ ）只，并保留笔未设置; QGraphicsSimpleTextItem的笔下是默认[Qt.NoPen](qt.html#PenStyle-enum)。

QGraphicsSimpleTextItem使用文本的格式大小和相关的字体提供合理的实施[boundingRect](qgraphicssimpletextitem.html#boundingRect)（ ）[shape](qgraphicssimpletextitem.html#shape)（）和[contains](qgraphicssimpletextitem.html#contains)（ ） 。你可以通过调用设置字体[setFont](qgraphicssimpletextitem.html#setFont)（ ） 。

QGraphicsSimpleText不显示丰富的文本，相反，你可以使用[QGraphicsTextItem](qgraphicstextitem.html)，它提供了全文的控制能力。

![](../img/graphicsview-simpletextitem.png)

* * *

## Method Documentation

```
QGraphicsSimpleTextItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsSimpleTextItem](qgraphicssimpletextitem.html)。

_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsSimpleTextItem.__init__ (self, QString text, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsSimpleTextItem](qgraphicssimpletextitem.html)，使用_text_作为默认的纯文本。

_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QRectF QGraphicsSimpleTextItem.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
bool QGraphicsSimpleTextItem.contains (self, QPointF point)
```

从重新实现[QGraphicsItem.contains](qgraphicsitem.html#contains)（ ） 。

```
QFont QGraphicsSimpleTextItem.font (self)
```

[

返回用于绘制该项目的文本的字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qgraphicssimpletextitem.html#setFont)（ ） 。

```
bool QGraphicsSimpleTextItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QGraphicsSimpleTextItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsSimpleTextItem.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QGraphicsSimpleTextItem.setFont (self, QFont font)
```

设置用于绘制项目的文本的字体_font_。

**See also** [font](qgraphicssimpletextitem.html#font)（ ） 。

```
QGraphicsSimpleTextItem.setText (self, QString text)
```

设置项的文本_text_。该文本将显示为纯文本。换行符（' \ n '） ，以及类型的字符[QChar.LineSeparator](qchar.html#SpecialCharacter-enum)会导致项目打破文本分成多行。

**See also** [text](qgraphicssimpletextitem.html#text)（ ） 。

```
QPainterPath QGraphicsSimpleTextItem.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
QString QGraphicsSimpleTextItem.text (self)
```

返回项的文本。

**See also** [setText](qgraphicssimpletextitem.html#setText)（ ） 。

```
int QGraphicsSimpleTextItem.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。