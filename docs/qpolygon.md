# QPolygon Class Reference

## [[QtGui](index.htm) module]

该QPolygon类提供了使用精确到整数点的向量。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPolygon a)`
*   `__init__ (self, list-of-QPoint v)`
*   `__init__ (self, QRect rectangle, bool closed = False)`
*   `__init__ (self, int asize)`
*   `__init__ (self, list-of-int points)`
*   `__init__ (self, QVariant variant)`
*   `append (self, QPoint value)`
*   `QPoint at (self, int i)`
*   `QRect boundingRect (self)`
*   `clear (self)`
*   `bool contains (self, QPoint value)`
*   `bool containsPoint (self, QPoint pt, Qt.FillRule fillRule)`
*   `int count (self, QPoint value)`
*   `int count (self)`
*   `sip.voidptr data (self)`
*   `fill (self, QPoint value, int size = -1)`
*   `QPoint first (self)`
*   `int indexOf (self, QPoint value, int from = 0)`
*   `insert (self, int i, QPoint value)`
*   `QPolygon intersected (self, QPolygon r)`
*   `bool isEmpty (self)`
*   `QPoint last (self)`
*   `int lastIndexOf (self, QPoint value, int from = -1)`
*   `QPolygon mid (self, int pos, int length = -1)`
*   `QPoint point (self, int index)`
*   `prepend (self, QPoint value)`
*   `putPoints (self, int index, int firstx, int firsty, ...)`
*   `putPoints (self, int index, int nPoints, QPolygon fromPolygon, int from = 0)`
*   `remove (self, int i)`
*   `remove (self, int i, int count)`
*   `replace (self, int i, QPoint value)`
*   `setPoint (self, int index, QPoint pt)`
*   `setPoint (self, int index, int x, int y)`
*   `setPoints (self, list-of-int points)`
*   `setPoints (self, int firstx, int firsty, ...)`
*   `int size (self)`
*   `QPolygon subtracted (self, QPolygon r)`
*   `swap (self, QPolygon other)`
*   `translate (self, int dx, int dy)`
*   `translate (self, QPoint offset)`
*   `QPolygon translated (self, int dx, int dy)`
*   `QPolygon translated (self, QPoint offset)`
*   `QPolygon united (self, QPolygon r)`
*   `QPoint value (self, int i)`
*   `QPoint value (self, int i, QPoint defaultValue)`

### Special Methods

*   `QPolygon __add__ (self, QPolygon other)`
*   `int __contains__ (self, QPoint value)`
*   `__delitem__ (self, int i)`
*   `__delitem__ (self, slice slice)`
*   `bool __eq__ (self, QPolygon other)`
*   `QPoint __getitem__ (self, int i)`
*   `QPolygon __getitem__ (self, slice slice)`
*   `QPolygon __iadd__ (self, QPolygon other)`
*   `QPolygon __iadd__ (self, QPoint value)`
*   `__len__ (self)`
*   `object __lshift__ (self, QPoint value)`
*   `QPolygon __mul__ (self, QMatrix m)`
*   `QPolygon __mul__ (self, QTransform m)`
*   `bool __ne__ (self, QPolygon other)`
*   `__setitem__ (self, int i, QPoint value)`
*   `__setitem__ (self, slice slice, QPolygon list)`

* * *

## Detailed Description

这个类可以醃制。

该QPolygon类提供了使用精确到整数点的向量。

一个QPolygon对象是[QVector](index.htm)\u003c[QPoint](qpoint.html)\u003e 。把点添加到QPolygon最简单的方法是使用[QVector](index.htm)的流媒体运营商，如下图所示：

```
         QPolygon polygon;
         polygon << [QPoint](qpoint.html)(10, 20) << [QPoint](qpoint.html)(20, 30);

```

除了由所提供的功能[QVector](index.htm)， QPolygon提供了一些点的特定功能。

在一多边形的每个点可以通过将其索引的检索[point](qpolygon.html#point)（）函数。要填充多边形， QPolygon提供[setPoint](qpolygon.html#setPoint)（ ）函数来设置点给定的索引处，则[setPoints](qpolygon.html#setPoints)（）函数中的多边形组的所有点（它缩放到的点的给定数量），以及[putPoints](qpolygon.html#putPoints)（ ）函数拷贝了一些已知点成从指定的索引（如果需要调整大小的多边形）多边形。

QPolygon提供[boundingRect](qpolygon.html#boundingRect)（）和[translate](qpolygon.html#translate)（ ）用于几何函数的函数。使用[QMatrix.map](qmatrix.html#map)（）函数QPolygons的更一般的变换。

该QPolygon类是[implicitly shared](index.htm#implicit-data-sharing)。

* * *

## Method Documentation

```
QPolygon.__init__ (self)
```

构造一个多边形，没有分。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygon.__init__ (self, QPolygon a)
```

构造的给定的多边形_size_。创建空的多边形，如果_size_== 0 。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygon.__init__ (self, list-of-QPoint v)
```

构造给定的一个副本_polygon_。

**See also** [setPoints](qpolygon.html#setPoints)（ ） 。

```
QPolygon.__init__ (self, QRect rectangle, bool closed = False)
```

构建了含有指定一个多边形_points_。

**See also** [setPoints](qpolygon.html#setPoints)（ ） 。

```
QPolygon.__init__ (self, int asize)
```

构造一个多边形从给定的_rectangle_。如果_closed_是假的，多边形只包含四点顺时针矩形下令，否则多边形的第五点设置为_rectangle_，左上（ ） 。

需要注意的是该矩形的右下角位于（ rectangle.x （）+ rectangle.width （） ， rectangle.y （）+ rectangle.height （））。

**See also** [setPoints](qpolygon.html#setPoints)（ ） 。

```
QPolygon.__init__ (self, list-of-int points)
```

```
QPolygon.__init__ (self, QVariant variant)
```

```
QPolygon.append (self, QPoint value)
```

```
QPoint QPolygon.at (self, int i)
```

[](qpoint.html)

```
QRect QPolygon.boundingRect (self)
```

[](qrect.html)

[返回多边形的边界矩形，或](qrect.html)[QRect](qrect.html)（ 0，0， 0，0） ，如果多边形是空的。

**See also** [QVector.isEmpty](index.htm#isEmpty)（ ） 。

```
QPolygon.clear (self)
```

```
bool QPolygon.contains (self, QPoint value)
```

```
bool QPolygon.containsPoint (self, QPoint pt, Qt.FillRule fillRule)
```

返回True如果给定的_point_在多边形内根据指定的_fillRule_否则返回False 。

此功能被引入Qt的4.3 。

```
int QPolygon.count (self, QPoint value)
```

```
int QPolygon.count (self)
```

```
sip.voidptr QPolygon.data (self)
```

```
QPolygon.fill (self, QPoint value, int size = -1)
```

```
QPoint QPolygon.first (self)
```

[

```
int QPolygon.indexOf (self, QPoint value, int from = 0)
```

```
QPolygon.insert (self, int i, QPoint value)
```

](qpoint.html)

```
QPolygon QPolygon.intersected (self, QPolygon r)
```

[

返回一个多边形是这个多边形的交点_r_。

对多边形集合运算将视作为多边形区域。非封闭的多边形将被隐式关闭处理。

此功能被引入Qt的4.3 。

```
bool QPolygon.isEmpty (self)
```

](qpolygon.html)

```
QPoint QPolygon.last (self)
```

[

```
int QPolygon.lastIndexOf (self, QPoint value, int from = -1)
```

](qpoint.html)

```
QPolygon QPolygon.mid (self, int pos, int length = -1)
```

[](qpolygon.html)

```
QPoint QPolygon.point (self, int index)
```

[

提取的点的坐标在给定的_index_到*_x_和*_y_（如果它们是有效的指针）。

](qpoint.html)

[**See also**](qpoint.html) [setPoint](qpolygon.html#setPoint)（ ） 。

```
QPolygon.prepend (self, QPoint value)
```

```
QPolygon.putPoints (self, int index, int firstx, int firsty, ...)
```

Copies _nPoints_从变量参数列表指出这个多边形从给定的_index_。

该点被给定为一个整数序列，从_firstx_然后_firsty_，等等。多边形调整大小，如果`index+nPoints`超过其目前的规模。

示例代码用三个点（4,5） ， （6,7 ）创建了一个多边形和（8,9） ，由1至3个点扩大多边形：

```
         [QPolygon](qpolygon.html) polygon(1);
         polygon[0] = [QPoint](qpoint.html)(4, 5);
         polygon.putPoints(1, 2, 6,7, 8,9);

```

下面的代码有相同的结果，但这里的putPoints （ ）函数复盖，而不是延伸：

```
         [QPolygon](qpolygon.html) polygon(3);
         polygon.putPoints(0, 3, 4,5, 0,0, 8,9);
         polygon.putPoints(1, 1, 6,7);

```

**See also** [setPoints](qpolygon.html#setPoints)（ ） 。

```
QPolygon.putPoints (self, int index, int nPoints, QPolygon fromPolygon, int from = 0)
```

```
QPolygon.remove (self, int i)
```

```
QPolygon.remove (self, int i, int count)
```

```
QPolygon.replace (self, int i, QPoint value)
```

```
QPolygon.setPoint (self, int index, QPoint pt)
```

设定点在给定的_index_到由指定的点（_x_，_y_） 。

**See also** [point](qpolygon.html#point)（ ）[putPoints](qpolygon.html#putPoints)（）和[setPoints](qpolygon.html#setPoints)（ ） 。

```
QPolygon.setPoint (self, int index, int x, int y)
```

这是一个重载函数。

设定点在给定的_index_为给定的_point_。

```
QPolygon.setPoints (self, list-of-int points)
```

调整大小的多边形_nPoints_并用给定的填充它_points_。

示例代码创建了两个点（ 10 ， 20 ）和（ 30 ， 40 ）多边形：

```
         static const int points[] = { 10, 20, 30, 40 };
         [QPolygon](qpolygon.html) polygon;
         polygon.setPoints(2, points);

```

**See also** [setPoint](qpolygon.html#setPoint)（）和[putPoints](qpolygon.html#putPoints)（ ） 。

```
QPolygon.setPoints (self, int firstx, int firsty, ...)
```

这是一个重载函数。

调整大小的多边形_nPoints_并用可变参数列表中指定的点进行填充。该点被给定为一个整数序列，从_firstx_然后_firsty_，等等。

示例代码创建了两个点（ 10 ， 20 ）和（ 30 ， 40 ）多边形：

```
         [QPolygon](qpolygon.html) polygon;
         polygon.setPoints(2, 10, 20, 30, 40);

```

```
int QPolygon.size (self)
```

```
QPolygon QPolygon.subtracted (self, QPolygon r)
```

[

返回一个多边形是_r_减去这个多边形。

对多边形集合运算将视作为多边形区域。非封闭的多边形将被隐式关闭处理。

此功能被引入Qt的4.3 。

```
QPolygon.swap (self, QPolygon other)
```

掉期多边形_other_与此多边形。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QPolygon.translate (self, int dx, int dy)
```

由（将所有的点在多边形_dx_，_dy_） 。

](qpolygon.html)

[**See also**](qpolygon.html) [translated](qpolygon.html#translated)（ ） 。

```
QPolygon.translate (self, QPoint offset)
```

这是一个重载函数。

由给定的转换的所有点在多边形_offset_。

**See also** [translated](qpolygon.html#translated)（ ） 。

```
QPolygon QPolygon.translated (self, int dx, int dy)
```

[

返回由（翻译多边形的副本_dx_，_dy_） 。

此功能被引入Qt的4.6 。

](qpolygon.html)

[**See also**](qpolygon.html) [translate](qpolygon.html#translate)（ ） 。

```
QPolygon QPolygon.translated (self, QPoint offset)
```

[

这是一个重载函数。

返回该多边形的一个副本，是由给定的翻译_offset_。

此功能被引入Qt的4.6 。

](qpolygon.html)

[**See also**](qpolygon.html) [translate](qpolygon.html#translate)（ ） 。

```
QPolygon QPolygon.united (self, QPolygon r)
```

[

返回一个多边形是这个多边形和工会_r_。

对多边形集合运算，将视作为多边形区域，并含蓄地闭合多边形。

此功能被引入Qt的4.3 。

](qpolygon.html)

[**See also**](qpolygon.html) [intersected](qpolygon.html#intersected)（）和[subtracted](qpolygon.html#subtracted)（ ） 。

```
QPoint QPolygon.value (self, int i)
```

[](qpoint.html)

```
QPoint QPolygon.value (self, int i, QPoint defaultValue)
```

[](qpoint.html)

```
QPolygon QPolygon.__add__ (self, QPolygon other)
```

[

```
int QPolygon.__contains__ (self, QPoint value)
```

```
QPolygon.__delitem__ (self, int i)
```

```
QPolygon.__delitem__ (self, slice slice)
```

```
bool QPolygon.__eq__ (self, QPolygon other)
```

](qpolygon.html)

```
QPoint QPolygon.__getitem__ (self, int i)
```

[](qpoint.html)

```
QPolygon QPolygon.__getitem__ (self, slice slice)
```

[](qpolygon.html)

```
QPolygon QPolygon.__iadd__ (self, QPolygon other)
```

[](qpolygon.html)

```
QPolygon QPolygon.__iadd__ (self, QPoint value)
```

[

```
 QPolygon.__len__ (self)
```

```
object QPolygon.__lshift__ (self, QPoint value)
```

](qpolygon.html)

```
QPolygon QPolygon.__mul__ (self, QMatrix m)
```

[](qpolygon.html)

```
QPolygon QPolygon.__mul__ (self, QTransform m)
```

[

```
bool QPolygon.__ne__ (self, QPolygon other)
```

```
QPolygon.__setitem__ (self, int i, QPoint value)
```

```
QPolygon.__setitem__ (self, slice slice, QPolygon list)
```

](qpolygon.html)