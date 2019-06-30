# QGraphicsEllipseItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsEllipseItem类提供了一个椭圆形项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

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
*   `setSpanAngle (self, int angle)`
*   `setStartAngle (self, int angle)`
*   `QPainterPath shape (self)`
*   `int spanAngle (self)`
*   `int startAngle (self)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsEllipseItem类提供了一个椭圆形项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。

QGraphicsEllipseItem respresents用填充和轮廓的椭圆形，而且你还可以使用它的椭圆段（见[startAngle](qgraphicsellipseitem.html#startAngle)（ ）[spanAngle](qgraphicsellipseitem.html#spanAngle)（））。

| ![](../img/graphicsview-ellipseitem.png) | ![](../img/graphicsview-ellipseitem-pie.png) |

要设置项目的椭圆形，传递[QRectF](qrectf.html)到QGraphicsEllipseItem的构造函数，或调用[setRect](qgraphicsellipseitem.html#setRect)（ ） 。该[rect](qgraphicsellipseitem.html#rect)（ ）函数返回当前的椭圆形状。

QGraphicsEllipseItem使用矩形和钢笔的宽度，以提供合理的实施[boundingRect](qgraphicsellipseitem.html#boundingRect)（ ）[shape](qgraphicsellipseitem.html#shape)（）和[contains](qgraphicsellipseitem.html#contains)（ ） 。该[paint](qgraphicsellipseitem.html#paint)（ ）函数绘制使用该项目的相关的画笔和画刷的椭圆，它可以通过调用设置[setPen](qabstractgraphicsshapeitem.html#setPen)（）和[setBrush](qabstractgraphicsshapeitem.html#setBrush)（ ） 。

* * *

## Method Documentation

```
QGraphicsEllipseItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsEllipseItem](qgraphicsellipseitem.html)。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsEllipseItem.__init__ (self, QRectF rect, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsEllipseItem](qgraphicsellipseitem.html) using _rect_作为默认的矩形。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsEllipseItem.__init__ (self, float x, float y, float w, float h, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsEllipseItem](qgraphicsellipseitem.html)使用由（定义的矩形_x_，_y_）和给定的_width_和_height_，作为默认的矩形。_parent_被传递给[QAbstractGraphicsShapeItem](qabstractgraphicsshapeitem.html)的构造。

此功能被引入Qt的4.3 。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QRectF QGraphicsEllipseItem.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
bool QGraphicsEllipseItem.contains (self, QPointF point)
```

从重新实现[QGraphicsItem.contains](qgraphicsitem.html#contains)（ ） 。

```
bool QGraphicsEllipseItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QGraphicsEllipseItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsEllipseItem.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QRectF QGraphicsEllipseItem.rect (self)
```

[](qrectf.html)

[返回该项目的椭圆几何体作为一个](qrectf.html)[QRectF](qrectf.html)。

**See also** [setRect](qgraphicsellipseitem.html#setRect)（）和[QPainter.drawEllipse](qpainter.html#drawEllipse)（ ） 。

```
QGraphicsEllipseItem.setRect (self, QRectF rect)
```

设置项的椭圆几何_rect_。矩形的左边缘定义椭圆的左边缘，并且矩形的顶边描述了椭圆形的顶部。矩形的高度和宽度描述椭圆的高度和宽度。

**See also** [rect](qgraphicsellipseitem.html#rect)（）和[QPainter.drawEllipse](qpainter.html#drawEllipse)（ ） 。

```
QGraphicsEllipseItem.setRect (self, float ax, float ay, float w, float h)
```

设置项的矩形，由（定义的矩形_x_，_y_）和给定的_width_和_height_。

这个方便的功能等同于调用`setRect(QRectF(x, y, width, height))`

**See also** [rect](qgraphicsellipseitem.html#rect)（ ） 。

```
QGraphicsEllipseItem.setSpanAngle (self, int angle)
```

设置为椭圆段的跨度角_angle_，这在一定程度的16份。这个角度被一起使用[startAngle](qgraphicsellipseitem.html#startAngle)（）表示一个椭圆形段（馅饼） 。默认情况下，跨度角为5760 （ 360 * 16 ，一个完整的椭圆） 。

**See also** [spanAngle](qgraphicsellipseitem.html#spanAngle)（ ）[setStartAngle](qgraphicsellipseitem.html#setStartAngle)（）和[QPainter.drawPie](qpainter.html#drawPie)（ ） 。

```
QGraphicsEllipseItem.setStartAngle (self, int angle)
```

设置为椭圆段的起始角度_angle_，这在一定程度的16份。这个角度被一起使用[spanAngle](qgraphicsellipseitem.html#spanAngle)（ ）来表示椭圆段（饼图） 。默认情况下，起始角度为0 。

**See also** [startAngle](qgraphicsellipseitem.html#startAngle)（ ）[setSpanAngle](qgraphicsellipseitem.html#setSpanAngle)（）和[QPainter.drawPie](qpainter.html#drawPie)（ ） 。

```
QPainterPath QGraphicsEllipseItem.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
int QGraphicsEllipseItem.spanAngle (self)
```

返回一定程度的16份椭圆段的跨度角度。这个角度被一起使用[startAngle](qgraphicsellipseitem.html#startAngle)（ ）来表示椭圆段（饼图） 。默认情况下，这个函数返回5760 （ 360 * 16 ，一个完整的椭圆） 。

**See also** [setSpanAngle](qgraphicsellipseitem.html#setSpanAngle)（）和[startAngle](qgraphicsellipseitem.html#startAngle)（ ） 。

```
int QGraphicsEllipseItem.startAngle (self)
```

返回一定程度的16份为椭圆段的起始角度。这个角度被一起使用[spanAngle](qgraphicsellipseitem.html#spanAngle)（ ）来表示椭圆段（饼图） 。默认情况下，起始角度为0 。

**See also** [setStartAngle](qgraphicsellipseitem.html#setStartAngle)（）和[spanAngle](qgraphicsellipseitem.html#spanAngle)（ ） 。

```
int QGraphicsEllipseItem.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。