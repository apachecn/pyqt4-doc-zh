# QPointF Class Reference

## [[QtCore](index.htm) module]

该QPointF类定义使用浮点精度在平面上的点。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPainterPath.Element)`
*   `__init__ (self, float xpos, float ypos)`
*   `__init__ (self, QPoint p)`
*   `__init__ (self, QPointF)`
*   `bool isNull (self)`
*   `float manhattanLength (self)`
*   `setX (self, float xpos)`
*   `setY (self, float ypos)`
*   `QPoint toPoint (self)`
*   `float x (self)`
*   `float y (self)`

### Special Methods

*   `QPointF __mul__ (self, QMatrix m)`
*   `QPointF __mul__ (self, QMatrix4x4 matrix)`
*   `QPointF __mul__ (self, QTransform m)`
*   `QPointF __add__ (self, QPointF p2)`
*   `int __bool__ (self)`
*   `QPointF __div__ (self, float c)`
*   `bool __eq__ (self, QPointF p2)`
*   `QPointF __iadd__ (self, QPointF p)`
*   `QPointF __idiv__ (self, float c)`
*   `QPointF __imul__ (self, float c)`
*   `QPointF __isub__ (self, QPointF p)`
*   `QPointF __mul__ (self, float c)`
*   `QPointF __mul__ (self, QPointF p)`
*   `bool __ne__ (self, QPointF p2)`
*   `QPointF __neg__ (self)`
*   `str __repr__ (self)`
*   `QPointF __sub__ (self, QPointF p2)`

* * *

## Detailed Description

这个类可以醃制。

该QPointF类定义使用浮点精度在平面上的点。

被指定的点由斧头协调和使用y坐标可接的[x](qpointf.html#x)（）和[y](qpointf.html#y)（）函数。使用浮点数精度进行所指定的点的坐标。该[isNull](qpointf.html#isNull)如果x和y都设置为0.0 （ ）函数返回True。坐标可以使用设置（或改变）的[setX](qpointf.html#setX)（）和[setY](qpointf.html#setY)（）函数，或者在[rx](qpointf.html#rx)（）和[ry](qpointf.html#ry)（ ），它返回引用到坐标（允许直接操作）等功能。

给定一个点_p_，下面的语句是等价的：

```
 QPointF p;

 p.setX(p.x() + 1.0);
 p += QPointF(1.0, 0.0);
 p.rx()++;

```

甲QPointF对象也可以被用作载体：加法和减法的定义为矢量（每个组分单独加入） 。一个QPointF对象也可以通过分频或倍频`int`或`qreal`。

此外， QPointF类提供一个构造函数将一[QPoint](qpoint.html)反对成QPointF对象，以及相应的[toPoint](qpointf.html#toPoint)（ ）函数返回一个[QPoint](qpoint.html)副本_this_点。最后，相比QPointF对象可以被串流播放，以及。

* * *

## Method Documentation

```
QPointF.__init__ (self)
```

构造一个空点，即坐标为（ 0.0 ， 0.0 ）

**See also** [isNull](qpointf.html#isNull)（ ） 。

```
QPointF.__init__ (self, QPainterPath.Element)
```

如果QtGui模块导入此方法仅适用。

构造一个空点，即坐标为（ 0.0 ， 0.0 ）

**See also** [isNull](qpointf.html#isNull)（ ） 。

```
QPointF.__init__ (self, float xpos, float ypos)
```

构造给定的一个副本_point_。

**See also** [toPoint](qpointf.html#toPoint)（ ） 。

```
QPointF.__init__ (self, QPoint p)
```

构造一个点与给定的坐标（_x_，_y_） 。

**See also** [setX](qpointf.html#setX)（）和[setY](qpointf.html#setY)（ ） 。

```
QPointF.__init__ (self, QPointF)
```

```
bool QPointF.isNull (self)
```

返回True如果x和y坐标都设置为0.0 ，否则返回False 。

**Note:**由于此函数将+0.0和-0.0不同，分有其中一个或两个值有一个负号不是定义为零点零值坐标。

```
float QPointF.manhattanLength (self)
```

返回的绝对值之和[x](qpointf.html#x)（）和[y](qpointf.html#y)（ ） ，传统上被称为“曼哈顿长度”从原点的向量的点。

此功能被引入Qt的4.6 。

**See also** [QPoint.manhattanLength](qpoint.html#manhattanLength)（ ） 。

```
QPointF.setX (self, float xpos)
```

设置该点的x坐标，以给定的_x_协调。

**See also** [x](qpointf.html#x)（）和[setY](qpointf.html#setY)（ ） 。

```
QPointF.setY (self, float ypos)
```

设置该点的y坐标为给定的_y_协调。

**See also** [y](qpointf.html#y)（）和[setX](qpointf.html#setX)（ ） 。

```
QPoint QPointF.toPoint (self)
```

[](qpoint.html)

[舍入此点的坐标为最接近的整数，并返回一个](qpoint.html)[QPoint](qpoint.html)对象与圆的坐标。

**See also** [QPointF](qpointf.html#QPointF)（ ） 。

```
float QPointF.x (self)
```

返回该点的x坐标。

**See also** [setX](qpointf.html#setX)（）和[rx](qpointf.html#rx)（ ） 。

```
float QPointF.y (self)
```

返回此点的y坐标。

**See also** [setY](qpointf.html#setY)（）和[ry](qpointf.html#ry)（ ） 。

```
QPointF __mul__ (self, QMatrix m)
```

[

如果QtGui模块导入此方法仅适用。

](qpointf.html)

```
QPointF __mul__ (self, QMatrix4x4 matrix)
```

[

如果QtGui模块导入此方法仅适用。

](qpointf.html)

```
QPointF __mul__ (self, QTransform m)
```

[

如果QtGui模块导入此方法仅适用。

](qpointf.html)

```
QPointF QPointF.__add__ (self, QPointF p2)
```

[

```
int QPointF.__bool__ (self)
```

](qpointf.html)

```
QPointF QPointF.__div__ (self, float c)
```

[

```
bool QPointF.__eq__ (self, QPointF p2)
```

](qpointf.html)

```
QPointF QPointF.__iadd__ (self, QPointF p)
```

[](qpointf.html)

```
QPointF QPointF.__idiv__ (self, float c)
```

[](qpointf.html)

```
QPointF QPointF.__imul__ (self, float c)
```

[](qpointf.html)

```
QPointF QPointF.__isub__ (self, QPointF p)
```

[](qpointf.html)

```
QPointF QPointF.__mul__ (self, float c)
```

[](qpointf.html)

```
QPointF QPointF.__mul__ (self, QPointF p)
```

[

```
bool QPointF.__ne__ (self, QPointF p2)
```

](qpointf.html)

```
QPointF QPointF.__neg__ (self)
```

[

```
str QPointF.__repr__ (self)
```

](qpointf.html)

```
QPointF QPointF.__sub__ (self, QPointF p2)
```

[](qpointf.html)