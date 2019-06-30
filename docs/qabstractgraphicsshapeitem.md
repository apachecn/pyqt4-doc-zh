# QAbstractGraphicsShapeItem Class Reference

## [[QtGui](index.htm) module]

该QAbstractGraphicsShapeItem类提供一个共同的基础，所有的路径项目。[More...](#details)

继承[QGraphicsItem](qgraphicsitem.html)。

通过继承[QGraphicsEllipseItem](qgraphicsellipseitem.html)，[QGraphicsPathItem](qgraphicspathitem.html)，[QGraphicsPolygonItem](qgraphicspolygonitem.html)，[QGraphicsRectItem](qgraphicsrectitem.html)和[QGraphicsSimpleTextItem](qgraphicssimpletextitem.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `QBrush brush (self)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPainterPath opaqueArea (self)`
*   `QPen pen (self)`
*   `setBrush (self, QBrush brush)`
*   `setPen (self, QPen pen)`

* * *

## Detailed Description

该QAbstractGraphicsShapeItem类提供一个共同的基础，所有的路径项目。

本身这个类没有完全实现的项目，特别是它没有实现[boundingRect](qgraphicsitem.html#boundingRect)（）和[paint](qgraphicsitem.html#paint)（），它是由遗传[QGraphicsItem](qgraphicsitem.html)。

你可以继承此文件提供一个简单的基实现访问，为项目的画笔和画刷。

* * *

## Method Documentation

```
QAbstractGraphicsShapeItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)。_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

```
QBrush QAbstractGraphicsShapeItem.brush (self)
```

[

返回该项目的画笔，或一个空刷，如果没有刷已定。

](qbrush.html)

[**See also**](qbrush.html) [setBrush](qabstractgraphicsshapeitem.html#setBrush)（ ） 。

```
bool QAbstractGraphicsShapeItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QAbstractGraphicsShapeItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QPen QAbstractGraphicsShapeItem.pen (self)
```

[

返回该项目的笔下。如果没有笔已定，这个函数返回QPen （ ） ，默认的黑色实线与笔宽0 。

](qpen.html)

[**See also**](qpen.html) [setPen](qabstractgraphicsshapeitem.html#setPen)（ ） 。

```
QAbstractGraphicsShapeItem.setBrush (self, QBrush brush)
```

设置项的刷_brush_。

该项目的刷来填充该项目。

如果使用毛刷带[QGradient](qgradient.html)的梯度是相对于项目的坐标系。

**See also** [brush](qabstractgraphicsshapeitem.html#brush)（ ） 。

```
QAbstractGraphicsShapeItem.setPen (self, QPen pen)
```

设置笔的资料，以_pen_。

画笔用于绘制项目的轮廓。

**See also** [pen](qabstractgraphicsshapeitem.html#pen)（ ） 。