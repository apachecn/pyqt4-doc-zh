# QGraphicsRectItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsRectItem类提供了一个长方形项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `__init__ (self, QRectF rect, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `__init__ (self, float x, float y, float w, float h, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `QRectF boundingRect (self)`
*   `bool contains (self, QPointF point)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPainterPath opaqueArea (self)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `QRectF rect (self)`
*   `setRect (self, QRectF rect)`
*   `setRect (self, float ax, float ay, float w, float h)`
*   `QPainterPath shape (self)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsRectItem类提供了一个长方形项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。

要设置项目的矩形，通过一个[QRectF](qrectf.html)到QGraphicsRectItem的构造函数，或致电[setRect](qgraphicsrectitem.html#setRect)（）函数。该[rect](qgraphicsrectitem.html#rect)（ ）函数返回当前矩形。

![](../img/graphicsview-rectitem.png)

QGraphicsRectItem使用矩形和钢笔的宽度，以提供合理的实施[boundingRect](qgraphicsrectitem.html#boundingRect)（ ）[shape](qgraphicsrectitem.html#shape)（）和[contains](qgraphicsrectitem.html#contains)（ ） 。该[paint](qgraphicsrectitem.html#paint)（ ）函数绘制使用该项目的相关笔触的矩形，它可以通过调用设置[setPen](qabstractgraphicsshapeitem.html#setPen)（）和[setBrush](qabstractgraphicsshapeitem.html#setBrush)（）函数。

**Note:**无效矩形的绘制，如那些具有负宽度或高度，是不确定的。如果你不能确定你使用的是有效的矩形（例如，如果您正在使用的数据来自不可靠的源创建矩形），那么你应该使用[QRectF.normalized](qrectf.html#normalized)（）来创建正规化矩形，并使用这些来代替。

* * *

## Method Documentation

```
QGraphicsRectItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsRectItem](qgraphicsrectitem.html)。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsRectItem.__init__ (self, QRectF rect, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsRectItem](qgraphicsrectitem.html)，使用_rect_作为默认的矩形。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsRectItem.__init__ (self, float x, float y, float w, float h, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsRectItem](qgraphicsrectitem.html)由（定义了默认的矩形_x_，_y_）和给定的_width_和_height_。

_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QRectF QGraphicsRectItem.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
bool QGraphicsRectItem.contains (self, QPointF point)
```

从重新实现[QGraphicsItem.contains](qgraphicsitem.html#contains)（ ） 。

```
bool QGraphicsRectItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QGraphicsRectItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsRectItem.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QRectF QGraphicsRectItem.rect (self)
```

[

返回该项目的矩形。

](qrectf.html)

[**See also**](qrectf.html) [setRect](qgraphicsrectitem.html#setRect)（ ） 。

```
QGraphicsRectItem.setRect (self, QRectF rect)
```

设置项的矩形也可以在给定_rectangle_。

**See also** [rect](qgraphicsrectitem.html#rect)（ ） 。

```
QGraphicsRectItem.setRect (self, float ax, float ay, float w, float h)
```

设置项的矩形，由（定义的矩形_x_，_y_）和给定的_width_和_height_。

这个方便的功能等同于调用`setRect(QRectF(x, y, width, height))`

**See also** [rect](qgraphicsrectitem.html#rect)（ ） 。

```
QPainterPath QGraphicsRectItem.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
int QGraphicsRectItem.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。