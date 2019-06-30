# QGraphicsPixmapItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsPixmapItem类提供了一个图片项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QGraphicsItem](qgraphicsitem.html)。

### Types

*   `enum ShapeMode { MaskShape, BoundingRectShape, HeuristicMaskShape }`

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `__init__ (self, QPixmap pixmap, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `QRectF boundingRect (self)`
*   `bool contains (self, QPointF point)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPointF offset (self)`
*   `QPainterPath opaqueArea (self)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)`
*   `QPixmap pixmap (self)`
*   `setOffset (self, QPointF offset)`
*   `setOffset (self, float ax, float ay)`
*   `setPixmap (self, QPixmap pixmap)`
*   `setShapeMode (self, ShapeMode mode)`
*   `setTransformationMode (self, Qt.TransformationMode mode)`
*   `QPainterPath shape (self)`
*   `ShapeMode shapeMode (self)`
*   `Qt.TransformationMode transformationMode (self)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsPixmapItem类提供了一个图片项目，你可以添加到[QGraphicsScene](qgraphicsscene.html)。

要设置项目的像素图，通过一个[QPixmap](qpixmap.html)到QGraphicsPixmapItem的构造函数，或致电[setPixmap](qgraphicspixmapitem.html#setPixmap)（）函数。该[pixmap](qgraphicspixmapitem.html#pixmap)（ ）函数返回当前像素图。

QGraphicsPixmapItem使用像素图的可选的alpha掩码来提供合理的实施[boundingRect](qgraphicspixmapitem.html#boundingRect)（ ）[shape](qgraphicspixmapitem.html#shape)（）和[contains](qgraphicspixmapitem.html#contains)（ ） 。

![](../img/graphicsview-pixmapitem.png)

像素图被绘制在该项目的（0 ，0）坐标，所返回的[offset](qgraphicspixmapitem.html#offset)（ ） 。你可以通过调用更改绘图偏移[setOffset](qgraphicspixmapitem.html#setOffset)（ ） 。

你可以通过调用设定的像素图的转型模式[setTransformationMode](qgraphicspixmapitem.html#setTransformationMode)（ ） 。默认情况下，[Qt.FastTransformation](qt.html#TransformationMode-enum)使用时，可提供快速，非平滑缩放。[Qt.SmoothTransformation](qt.html#TransformationMode-enum) enables [QPainter.SmoothPixmapTransform](qpainter.html#RenderHint-enum)在画家和质量取决于平台和视口上。结果通常是不如叫QPixmap.scale （ ）直接。通话[transformationMode](qgraphicspixmapitem.html#transformationMode)（ ）来获得该项目目前的转型模式。

* * *

## Type Documentation

```
QGraphicsPixmapItem.ShapeMode
```

这个枚举说明如何[QGraphicsPixmapItem](qgraphicspixmapitem.html)计算其形状​​和不透明的区域。

默认值是MaskShape 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsPixmapItem.MaskShape` | `0` | 该形状是通过调用确定[QPixmap.mask](qpixmap.html#mask)（ ） 。这种形状仅包括不透明像素的像素图的。由于形状比较复杂，但是，它可以比其它模式更慢，并且使用更多的存储器。 |
| `QGraphicsPixmapItem.BoundingRectShape` | `1` | 该形状是由跟踪像素映像的轮廓来确定。这是最快的形状模式，但它并没有考虑到的像素图的任何透明区域。 |
| `QGraphicsPixmapItem.HeuristicMaskShape` | `2` | 该形状是通过调用确定[QPixmap.createHeuristicMask](qpixmap.html#createHeuristicMask)（ ） 。性能和内存消耗是类似MaskShape 。 |

* * *

## Method Documentation

```
QGraphicsPixmapItem.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsPixmapItem](qgraphicspixmapitem.html)。_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsPixmapItem.__init__ (self, QPixmap pixmap, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsPixmapItem](qgraphicspixmapitem.html)，使用_pixmap_作为默认的pixmap 。_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QRectF QGraphicsPixmapItem.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
bool QGraphicsPixmapItem.contains (self, QPointF point)
```

从重新实现[QGraphicsItem.contains](qgraphicsitem.html#contains)（ ） 。

```
bool QGraphicsPixmapItem.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPointF QGraphicsPixmapItem.offset (self)
```

[

返回图片项目的_offset_，它定义了像素图的左上角，在局部坐标的点。

](qpointf.html)

[**See also**](qpointf.html) [setOffset](qgraphicspixmapitem.html#setOffset)（ ） 。

```
QPainterPath QGraphicsPixmapItem.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsPixmapItem.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QPixmap QGraphicsPixmapItem.pixmap (self)
```

[](qpixmap.html)

[返回该项目的像素图，或无效](qpixmap.html)[QPixmap](qpixmap.html)如果没有像素图已定。

**See also** [setPixmap](qgraphicspixmapitem.html#setPixmap)（ ） 。

```
QGraphicsPixmapItem.setOffset (self, QPointF offset)
```

设置图片项目的偏移量_offset_。[QGraphicsPixmapItem](qgraphicspixmapitem.html)将使用绘制其像素图_offset_其左上角。

**See also** [offset](qgraphicspixmapitem.html#offset)（ ） 。

```
QGraphicsPixmapItem.setOffset (self, float ax, float ay)
```

这个方便的功能等同于调用setOffset （[QPointF](qpointf.html)（_x_，_y_））。

此功能被引入Qt的4.3 。

```
QGraphicsPixmapItem.setPixmap (self, QPixmap pixmap)
```

设置项的像素图来_pixmap_。

**See also** [pixmap](qgraphicspixmapitem.html#pixmap)（ ） 。

```
QGraphicsPixmapItem.setShapeMode (self, ShapeMode mode)
```

设置项的形状模式_mode_。形模式描述了如何[QGraphicsPixmapItem](qgraphicspixmapitem.html)计算出其形状。默认模式是[MaskShape](qgraphicspixmapitem.html#ShapeMode-enum)。

**See also** [shapeMode](qgraphicspixmapitem.html#shapeMode)（）和[ShapeMode](qgraphicspixmapitem.html#ShapeMode-enum)。

```
QGraphicsPixmapItem.setTransformationMode (self, Qt.TransformationMode mode)
```

设置图片项目的改造模式_mode_，并切换该项目的更新。默认模式是[Qt.FastTransformation](qt.html#TransformationMode-enum)，它提供了无平滑快速转型。

[Qt.SmoothTransformation](qt.html#TransformationMode-enum) enables [QPainter.SmoothPixmapTransform](qpainter.html#RenderHint-enum)在画家和质量取决于平台和视口上。结果通常是不如叫QPixmap.scale （ ）直接。

**See also** [transformationMode](qgraphicspixmapitem.html#transformationMode)（ ） 。

```
QPainterPath QGraphicsPixmapItem.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
ShapeMode QGraphicsPixmapItem.shapeMode (self)
```

[](qgraphicspixmapitem.html#ShapeMode-enum)

[返回该项目的形状模式。形模式描述了如何](qgraphicspixmapitem.html#ShapeMode-enum)[QGraphicsPixmapItem](qgraphicspixmapitem.html)计算出其形状。默认模式是[MaskShape](qgraphicspixmapitem.html#ShapeMode-enum)。

**See also** [setShapeMode](qgraphicspixmapitem.html#setShapeMode)（）和[ShapeMode](qgraphicspixmapitem.html#ShapeMode-enum)。

```
Qt.TransformationMode QGraphicsPixmapItem.transformationMode (self)
```

[](qt.html#TransformationMode-enum)

[返回像素图的改造模式。默认模式是](qt.html#TransformationMode-enum)[Qt.FastTransformation](qt.html#TransformationMode-enum)，它提供了无平滑快速转型。

**See also** [setTransformationMode](qgraphicspixmapitem.html#setTransformationMode)（ ） 。

```
int QGraphicsPixmapItem.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。