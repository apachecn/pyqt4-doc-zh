# QGraphicsPathItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsPathItem类提供了可以添加到一个路径项[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `__init__ (self, QPainterPath path, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `QRectF boundingRect (self)`
*   `bool contains (self, QPointF point)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPainterPath opaqueArea (self)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `QPainterPath path (self)`
*   `setPath (self, QPainterPath path)`
*   `QPainterPath shape (self)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsPathItem类提供了可以添加到一个路径项[QGraphicsScene](qgraphicsscene.html)。

要设置项目的路径，通过一个[QPainterPath](qpainterpath.html)到QGraphicsPathItem的构造函数，或致电[setPath](qgraphicspathitem.html#setPath)（）函数。该[path](qgraphicspathitem.html#pathx)（ ）函数返回当前路径。

![](../img/graphicsview-pathitem.png)

QGraphicsPathItem使用的路径，以提供合理的实施[boundingRect](qgraphicspathitem.html#boundingRect)（ ）[shape](qgraphicspathitem.html#shape)（）和[contains](qgraphicspathitem.html#contains)（ ） 。该[paint](qgraphicspathitem.html#paint)使用该项目的相关画笔和画刷（ ）函数绘制的路径，你可以通过调用设置[setPen](qabstractgraphicsshapeitem.html#setPen)（）和[setBrush](qabstractgraphicsshapeitem.html#setBrush)（）函数。

* * *

## Method Documentation

```
QGraphicsPathItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个QGraphicsPath 。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsPathItem.__init__ (self, QPainterPath path, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造使用QGraphicsPath项目_path_作为默认的路径。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QRectF QGraphicsPathItem.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
bool QGraphicsPathItem.contains (self, QPointF point)
```

从重新实现[QGraphicsItem.contains](qgraphicsitem.html#contains)（ ） 。

```
bool QGraphicsPathItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QGraphicsPathItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsPathItem.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QPainterPath QGraphicsPathItem.path (self)
```

[

```
QGraphicsPathItem.setPath (self, QPainterPath path)
```

设置项的路径，以在给定_path_。

](qpainterpath.html)

[**See also**](qpainterpath.html) [path](qgraphicspathitem.html#pathx)（ ） 。

```
QPainterPath QGraphicsPathItem.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
int QGraphicsPathItem.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。