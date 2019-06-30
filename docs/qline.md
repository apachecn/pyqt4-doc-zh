# QLine Class Reference

## [[QtCore](index.htm) module]

该QLine类提供了使用整数精度的二维矢量。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPoint pt1_, QPoint pt2_)`
*   `__init__ (self, int x1pos, int y1pos, int x2pos, int y2pos)`
*   `__init__ (self, QLine)`
*   `int dx (self)`
*   `int dy (self)`
*   `bool isNull (self)`
*   `QPoint p1 (self)`
*   `QPoint p2 (self)`
*   `setLine (self, int aX1, int aY1, int aX2, int aY2)`
*   `setP1 (self, QPoint aP1)`
*   `setP2 (self, QPoint aP2)`
*   `setPoints (self, QPoint aP1, QPoint aP2)`
*   `translate (self, QPoint point)`
*   `translate (self, int adx, int ady)`
*   `QLine translated (self, QPoint p)`
*   `QLine translated (self, int adx, int ady)`
*   `int x1 (self)`
*   `int x2 (self)`
*   `int y1 (self)`
*   `int y2 (self)`

### Special Methods

*   `QLine __mul__ (self, QMatrix m)`
*   `QLine __mul__ (self, QTransform m)`
*   `int __bool__ (self)`
*   `bool __eq__ (self, QLine d)`
*   `bool __ne__ (self, QLine d)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

该QLine类提供了使用整数精度的二维矢量。

甲QLine描述了一个二维表面上的有限长度线（或线段） 。利用整数点精度为坐标指定该行的起点和终点。使用[QLineF](qlinef.html)构造函数来检索一个浮点副本。

| ![](../img/qline-point.png) | ![](../img/qline-coordinates.png) |

可使用检索到的线的开始点和结束点的位置的[p1](qline.html#p1)（ ）[x1](qline.html#x1)（ ）[y1](qline.html#y1)（ ）[p2](qline.html#p2)（ ）[x2](qline.html#x2)（）和[y2](qline.html#y2)（）函数。该[dx](qline.html#dx)（）和[dy](qline.html#dy)（）函数返回该行的水平和垂直分量。使用[isNull](qline.html#isNull)（ ）来确定QLine是否代表有效的线或空行。

最后，该线可以被转换的给定使用偏移[translate](qline.html#translate)（）函数。

* * *

## Method Documentation

```
QLine.__init__ (self)
```

构造一个空行。

```
QLine.__init__ (self, QPoint pt1_, QPoint pt2_)
```

构造一个线对象，它代表之间的界线_p1_和_p2_。

```
QLine.__init__ (self, int x1pos, int y1pos, int x2pos, int y2pos)
```

构造一个线对象，它代表之间（线_x1_，_y1_）和（_x2_，_y2_） 。

```
QLine.__init__ (self, QLine)
```

```
int QLine.dx (self)
```

返回该行的矢量的水平分量。

**See also** [dy](qline.html#dy)（ ） 。

```
int QLine.dy (self)
```

返回该行的矢量的垂直分量。

**See also** [dx](qline.html#dx)（ ） 。

```
bool QLine.isNull (self)
```

返回True如果该行没有设置与有效的起始和结束点，否则返回False 。

```
QPoint QLine.p1 (self)
```

[

返回该行的起点。

](qpoint.html)

[**See also**](qpoint.html) [setP1](qline.html#setP1)（ ）[x1](qline.html#x1)（ ）[y1](qline.html#y1)（）和[p2](qline.html#p2)（ ） 。

```
QPoint QLine.p2 (self)
```

[

返回该行的终点。

](qpoint.html)

[**See also**](qpoint.html) [setP2](qline.html#setP2)（ ）[x2](qline.html#x2)（ ）[y2](qline.html#y2)（）和[p1](qline.html#p1)（ ） 。

```
QLine.setLine (self, int aX1, int aY1, int aX2, int aY2)
```

设置此行到开始_x1_，_y1_并在结束_x2_，_y2_。

此功能被引入Qt的4.4 。

**See also** [setP1](qline.html#setP1)（ ）[setP2](qline.html#setP2)（ ）[p1](qline.html#p1)（）和[p2](qline.html#p2)（ ） 。

```
QLine.setP1 (self, QPoint aP1)
```

设置此行的起点，以_p1_。

此功能被引入Qt的4.4 。

**See also** [setP2](qline.html#setP2)（）和[p1](qline.html#p1)（ ） 。

```
QLine.setP2 (self, QPoint aP2)
```

设置此行的终点_p2_。

此功能被引入Qt的4.4 。

**See also** [setP1](qline.html#setP1)（）和[p2](qline.html#p2)（ ） 。

```
QLine.setPoints (self, QPoint aP1, QPoint aP2)
```

设置此行的起点_p1_并且这条线的终点_p2_。

此功能被引入Qt的4.4 。

**See also** [setP1](qline.html#setP1)（ ）[setP2](qline.html#setP2)（ ）[p1](qline.html#p1)（）和[p2](qline.html#p2)（ ） 。

```
QLine.translate (self, QPoint point)
```

由给定的转换这一行_offset_。

```
QLine.translate (self, int adx, int ady)
```

这是一个重载函数。

翻译这行指定的距离_dx_和_dy_。

```
QLine QLine.translated (self, QPoint p)
```

[

返回此行翻译由给定_offset_。

此功能被引入Qt的4.4 。

](qline.html)

```
QLine QLine.translated (self, int adx, int ady)
```

[

这是一个重载函数。

返回此行翻译指定的距离_dx_和_dy_。

此功能被引入Qt的4.4 。

```
int QLine.x1 (self)
```

返回该行的起始点的X坐标。

](qline.html)

[**See also**](qline.html) [p1](qline.html#p1)（ ） 。

```
int QLine.x2 (self)
```

返回该行的结束点的x坐标。

**See also** [p2](qline.html#p2)（ ） 。

```
int QLine.y1 (self)
```

返回该行的起点的y坐标。

**See also** [p1](qline.html#p1)（ ） 。

```
int QLine.y2 (self)
```

返回该行的结束点的Y坐标。

**See also** [p2](qline.html#p2)（ ） 。

```
QLine __mul__ (self, QMatrix m)
```

[

如果QtGui模块导入此方法仅适用。

](qline.html)

```
QLine __mul__ (self, QTransform m)
```

[

如果QtGui模块导入此方法仅适用。

```
int QLine.__bool__ (self)
```

```
bool QLine.__eq__ (self, QLine d)
```

```
bool QLine.__ne__ (self, QLine d)
```

```
str QLine.__repr__ (self)
```

](qline.html)