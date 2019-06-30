# QPolygonF Class Reference

## [[QtGui](index.htm) module]

该QPolygonF类提供了使用浮点精度点的矢量。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPolygonF a)`
*   `__init__ (self, list-of-QPointF v)`
*   `__init__ (self, QRectF r)`
*   `__init__ (self, QPolygon a)`
*   `__init__ (self, int asize)`
*   `append (self, QPointF value)`
*   `QPointF at (self, int i)`
*   `QRectF boundingRect (self)`
*   `clear (self)`
*   `bool contains (self, QPointF value)`
*   `bool containsPoint (self, QPointF pt, Qt.FillRule fillRule)`
*   `int count (self, QPointF value)`
*   `int count (self)`
*   `sip.voidptr data (self)`
*   `fill (self, QPointF value, int size = -1)`
*   `QPointF first (self)`
*   `int indexOf (self, QPointF value, int from = 0)`
*   `insert (self, int i, QPointF value)`
*   `QPolygonF intersected (self, QPolygonF r)`
*   `bool isClosed (self)`
*   `bool isEmpty (self)`
*   `QPointF last (self)`
*   `int lastIndexOf (self, QPointF value, int from = -1)`
*   `QPolygonF mid (self, int pos, int length = -1)`
*   `prepend (self, QPointF value)`
*   `remove (self, int i)`
*   `remove (self, int i, int count)`
*   `replace (self, int i, QPointF value)`
*   `int size (self)`
*   `QPolygonF subtracted (self, QPolygonF r)`
*   `swap (self, QPolygonF other)`
*   `QPolygon toPolygon (self)`
*   `translate (self, QPointF offset)`
*   `translate (self, float dx, float dy)`
*   `QPolygonF translated (self, QPointF offset)`
*   `QPolygonF translated (self, float dx, float dy)`
*   `QPolygonF united (self, QPolygonF r)`
*   `QPointF value (self, int i)`
*   `QPointF value (self, int i, QPointF defaultValue)`

### Special Methods

*   `QPolygonF __add__ (self, QPolygonF other)`
*   `int __contains__ (self, QPointF value)`
*   `__delitem__ (self, int i)`
*   `__delitem__ (self, slice slice)`
*   `bool __eq__ (self, QPolygonF other)`
*   `QPointF __getitem__ (self, int i)`
*   `QPolygonF __getitem__ (self, slice slice)`
*   `QPolygonF __iadd__ (self, QPolygonF other)`
*   `QPolygonF __iadd__ (self, QPointF value)`
*   `__len__ (self)`
*   `object __lshift__ (self, QPointF value)`
*   `QPolygonF __mul__ (self, QMatrix m)`
*   `QPolygonF __mul__ (self, QTransform m)`
*   `bool __ne__ (self, QPolygonF other)`
*   `__setitem__ (self, int i, QPointF value)`
*   `__setitem__ (self, slice slice, QPolygonF list)`

* * *

## Detailed Description

该QPolygonF类提供了使用浮点精度点的矢量。

一个QPolygonF是[QVector](index.htm)\u003c[QPointF](qpointf.html)\u003e 。把点添加到QPolygonF最简单的方法是使用它的流媒体运营商，如下图所示：

```
         QPolygonF polygon;
         polygon << [QPointF](qpointf.html)(10.4, 20.5) << [QPointF](qpointf.html)(20.2, 30.2);

```

除了由所提供的功能[QVector](index.htm)， QPolygonF提供[boundingRect](qpolygonf.html#boundingRect)（）和[translate](qpolygonf.html#translate)（ ）用于几何运算功能。使用[QMatrix.map](qmatrix.html#map)（）函数QPolygonFs的更一般的变换。

QPolygonF还提供了[isClosed](qpolygonf.html#isClosed)（）函数来确定一个多边形的起点和终点是否是相同的，并且[toPolygon](qpolygonf.html#toPolygon)（ ）函数返回此多边形的整数精度副本。

该QPolygonF类是[implicitly shared](index.htm#implicit-data-sharing)。

* * *

## Method Documentation

```
QPolygonF.__init__ (self)
```

构造一个多边形，没有分。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygonF.__init__ (self, QPolygonF a)
```

构造的给定的多边形_size_。创建空的多边形，如果_size_== 0 。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygonF.__init__ (self, list-of-QPointF v)
```

构造给定的一个副本_polygon_。

```
QPolygonF.__init__ (self, QRectF r)
```

构建了含有指定一个多边形_points_。

```
QPolygonF.__init__ (self, QPolygon a)
```

构造一个封闭的多边形从指定的_rectangle_。

多边形包含四个顶点按顺时针顺序矩形的开始，并与左上顶点结束。

**See also** [isClosed](qpolygonf.html#isClosed)（ ） 。

```
QPolygonF.__init__ (self, int asize)
```

构造从指定的整数根据一个基于浮动多边形_polygon_。

**See also** [toPolygon](qpolygonf.html#toPolygon)（ ） 。

```
QPolygonF.append (self, QPointF value)
```

```
QPointF QPolygonF.at (self, int i)
```

[](qpointf.html)

```
QRectF QPolygonF.boundingRect (self)
```

[](qrectf.html)

[返回多边形的边界矩形，或](qrectf.html)[QRectF](qrectf.html)（0,0,0,0） ，如果多边形是空的。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygonF.clear (self)
```

```
bool QPolygonF.contains (self, QPointF value)
```

```
bool QPolygonF.containsPoint (self, QPointF pt, Qt.FillRule fillRule)
```

返回True如果给定的_point_在多边形内根据指定的_fillRule_否则返回False 。

此功能被引入Qt的4.3 。

```
int QPolygonF.count (self, QPointF value)
```

```
int QPolygonF.count (self)
```

```
sip.voidptr QPolygonF.data (self)
```

```
QPolygonF.fill (self, QPointF value, int size = -1)
```

```
QPointF QPolygonF.first (self)
```

[

```
int QPolygonF.indexOf (self, QPointF value, int from = 0)
```

```
QPolygonF.insert (self, int i, QPointF value)
```

](qpointf.html)

```
QPolygonF QPolygonF.intersected (self, QPolygonF r)
```

[

返回一个多边形是这个多边形的交点_r_。

对多边形集合运算将视作为多边形区域。非封闭的多边形将被隐式关闭处理。

此功能被引入Qt的4.3 。

```
bool QPolygonF.isClosed (self)
```

返回True如果多边形是封闭的，否则返回False 。

多边形被认为是封闭的，如果起点和终点都是平等的。

](qpolygonf.html)

[**See also**](qpolygonf.html) [QVector.first](index.htm#first)（）和[QVector.last](index.htm#last)（ ） 。

```
bool QPolygonF.isEmpty (self)
```

```
QPointF QPolygonF.last (self)
```

[

```
int QPolygonF.lastIndexOf (self, QPointF value, int from = -1)
```

](qpointf.html)

```
QPolygonF QPolygonF.mid (self, int pos, int length = -1)
```

[

```
QPolygonF.prepend (self, QPointF value)
```

```
QPolygonF.remove (self, int i)
```

```
QPolygonF.remove (self, int i, int count)
```

```
QPolygonF.replace (self, int i, QPointF value)
```

```
int QPolygonF.size (self)
```

](qpolygonf.html)

```
QPolygonF QPolygonF.subtracted (self, QPolygonF r)
```

[

返回一个多边形是_r_减去这个多边形。

对多边形集合运算将视作为多边形区域。非封闭的多边形将被隐式关闭处理。

此功能被引入Qt的4.3 。

```
QPolygonF.swap (self, QPolygonF other)
```

掉期多边形_other_与此多边形。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

](qpolygonf.html)

```
QPolygon QPolygonF.toPolygon (self)
```

[](qpolygon.html)

[创建并返回一个](qpolygon.html)[QPolygon](qpolygon.html)把每个[QPointF](qpointf.html)到[QPoint](qpoint.html)。

**See also** [QPointF.toPoint](qpointf.html#toPoint)（ ） 。

```
QPolygonF.translate (self, QPointF offset)
```

翻译所有点在多边形由给定的_offset_。

**See also** [translated](qpolygonf.html#translated)（ ） 。

```
QPolygonF.translate (self, float dx, float dy)
```

这是一个重载函数。

由（将所有的点在多边形_dx_，_dy_） 。

**See also** [translated](qpolygonf.html#translated)（ ） 。

```
QPolygonF QPolygonF.translated (self, QPointF offset)
```

[

返回该多边形的一个副本，是由给定的翻译_offset_。

此功能被引入Qt的4.6 。

](qpolygonf.html)

[**See also**](qpolygonf.html) [translate](qpolygonf.html#translate)（ ） 。

```
QPolygonF QPolygonF.translated (self, float dx, float dy)
```

[

这是一个重载函数。

返回由（翻译多边形的副本_dx_，_dy_） 。

此功能被引入Qt的4.6 。

](qpolygonf.html)

[**See also**](qpolygonf.html) [translate](qpolygonf.html#translate)（ ） 。

```
QPolygonF QPolygonF.united (self, QPolygonF r)
```

[

返回一个多边形是这个多边形和工会_r_。

对多边形集合运算将视作为多边形区域。非封闭的多边形将被隐式关闭处理。

此功能被引入Qt的4.3 。

](qpolygonf.html)

[**See also**](qpolygonf.html) [intersected](qpolygonf.html#intersected)（）和[subtracted](qpolygonf.html#subtracted)（ ） 。

```
QPointF QPolygonF.value (self, int i)
```

[](qpointf.html)

```
QPointF QPolygonF.value (self, int i, QPointF defaultValue)
```

[](qpointf.html)

```
QPolygonF QPolygonF.__add__ (self, QPolygonF other)
```

[

```
int QPolygonF.__contains__ (self, QPointF value)
```

```
QPolygonF.__delitem__ (self, int i)
```

```
QPolygonF.__delitem__ (self, slice slice)
```

```
bool QPolygonF.__eq__ (self, QPolygonF other)
```

](qpolygonf.html)

```
QPointF QPolygonF.__getitem__ (self, int i)
```

[](qpointf.html)

```
QPolygonF QPolygonF.__getitem__ (self, slice slice)
```

[](qpolygonf.html)

```
QPolygonF QPolygonF.__iadd__ (self, QPolygonF other)
```

[](qpolygonf.html)

```
QPolygonF QPolygonF.__iadd__ (self, QPointF value)
```

[

```
 QPolygonF.__len__ (self)
```

```
object QPolygonF.__lshift__ (self, QPointF value)
```

](qpolygonf.html)

```
QPolygonF QPolygonF.__mul__ (self, QMatrix m)
```

[](qpolygonf.html)

```
QPolygonF QPolygonF.__mul__ (self, QTransform m)
```

[

```
bool QPolygonF.__ne__ (self, QPolygonF other)
```

```
QPolygonF.__setitem__ (self, int i, QPointF value)
```

```
QPolygonF.__setitem__ (self, slice slice, QPolygonF list)
```

](qpolygonf.html)