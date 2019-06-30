# QPoint Class Reference

## [[QtCore](index.htm) module]

该QPoint类定义使用整数精度在平面上的一个点。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int xpos, int ypos)`
*   `__init__ (self, QPoint)`
*   `bool isNull (self)`
*   `int manhattanLength (self)`
*   `setX (self, int xpos)`
*   `setY (self, int ypos)`
*   `int x (self)`
*   `int y (self)`

### Special Methods

*   `QPoint __mul__ (self, QMatrix m)`
*   `QPoint __mul__ (self, QMatrix4x4 matrix)`
*   `QPoint __mul__ (self, QTransform m)`
*   `QPoint __add__ (self, QPoint p2)`
*   `int __bool__ (self)`
*   `QPoint __div__ (self, float c)`
*   `bool __eq__ (self, QPoint p2)`
*   `QPoint __iadd__ (self, QPoint p)`
*   `QPoint __idiv__ (self, float c)`
*   `QPoint __imul__ (self, int c)`
*   `QPoint __imul__ (self, float c)`
*   `QPoint __isub__ (self, QPoint p)`
*   `QPoint __mul__ (self, int c)`
*   `QPoint __mul__ (self, QPoint p)`
*   `QPoint __mul__ (self, float c)`
*   `QPoint __mul__ (self, QPoint p)`
*   `bool __ne__ (self, QPoint p2)`
*   `QPoint __neg__ (self)`
*   `str __repr__ (self)`
*   `QPoint __sub__ (self, QPoint p2)`

* * *

## Detailed Description

这个类可以醃制。

该QPoint类定义使用整数精度在平面上的一个点。

被指定的点由斧头协调和使用y坐标可接的[x](qpoint.html#x)（）和[y](qpoint.html#y)（）函数。该[isNull](qpoint.html#isNull)如果x和y都设置为0 （）函数返回真。坐标可以使用设置（或改变）的[setX](qpoint.html#setX)（）和[setY](qpoint.html#setY)（）函数，或者在[rx](qpoint.html#rx)（）和[ry](qpoint.html#ry)（ ），它返回引用到坐标（允许直接操作）等功能。

给定一个点_p_，下面的语句是等价的：

```
 QPoint p;

 p.setX(p.x() + 1);
 p += QPoint(1, 0);
 p.rx()++;

```

甲QPoint对象也可以被用作载体：加法和减法的定义为矢量（每个组分单独加入） 。一个QPoint对象也可以通过分频或倍频`int`或`qreal`。

此外， QPoint类提供[manhattanLength](qpoint.html#manhattanLength)（）函数，它给出了QPoint物体的长度的一种廉价的近似解释为一个向量。最后，相比QPoint对象可以被串流播放，以及。

* * *

## Method Documentation

```
QPoint.__init__ (self)
```

构造一个零点，即坐标为（ 0，0）

**See also** [isNull](qpoint.html#isNull)（ ） 。

```
QPoint.__init__ (self, int xpos, int ypos)
```

构造一个点与给定的坐标（_x_，_y_） 。

**See also** [setX](qpoint.html#setX)（）和[setY](qpoint.html#setY)（ ） 。

```
QPoint.__init__ (self, QPoint)
```

```
bool QPoint.isNull (self)
```

返回True如果x和y坐标都设置为0 ，否则返回False 。

```
int QPoint.manhattanLength (self)
```

返回的绝对值之和[x](qpoint.html#x)（）和[y](qpoint.html#y)（ ） ，传统上被称为“曼哈顿长度”从原点的向量的点。例如：

```
 [QPoint](qpoint.html) oldPosition;

 MyWidget.mouseMoveEvent([QMouseEvent](qmouseevent.html) *event)
 {
     [QPoint](qpoint.html) point = event->pos() - oldPosition;
     if (point.manhattanLength() > 3)
         // the mouse has moved more than 3 pixels since the oldPosition
 }

```

这是一个有用的，快速的计算，近似真实的长度：

```
 double trueLength = sqrt(pow(x(), 2) + pow(y(), 2));

```

“曼哈顿长度”的传统产生，是因为这样的距离适用于旅客谁只能行驶在矩形网格，就像曼哈顿的大街上。

```
QPoint.setX (self, int xpos)
```

设置该点的x坐标，以给定的_x_协调。

**See also** [x](qpoint.html#x)（）和[setY](qpoint.html#setY)（ ） 。

```
QPoint.setY (self, int ypos)
```

设置该点的y坐标为给定的_y_协调。

**See also** [y](qpoint.html#y)（）和[setX](qpoint.html#setX)（ ） 。

```
int QPoint.x (self)
```

返回该点的x坐标。

**See also** [setX](qpoint.html#setX)（）和[rx](qpoint.html#rx)（ ） 。

```
int QPoint.y (self)
```

返回此点的y坐标。

**See also** [setY](qpoint.html#setY)（）和[ry](qpoint.html#ry)（ ） 。

```
QPoint __mul__ (self, QMatrix m)
```

[

如果QtGui模块导入此方法仅适用。

](qpoint.html)

```
QPoint __mul__ (self, QMatrix4x4 matrix)
```

[

如果QtGui模块导入此方法仅适用。

](qpoint.html)

```
QPoint __mul__ (self, QTransform m)
```

[

如果QtGui模块导入此方法仅适用。

](qpoint.html)

```
QPoint QPoint.__add__ (self, QPoint p2)
```

[

```
int QPoint.__bool__ (self)
```

](qpoint.html)

```
QPoint QPoint.__div__ (self, float c)
```

[

```
bool QPoint.__eq__ (self, QPoint p2)
```

](qpoint.html)

```
QPoint QPoint.__iadd__ (self, QPoint p)
```

[](qpoint.html)

```
QPoint QPoint.__idiv__ (self, float c)
```

[](qpoint.html)

```
QPoint QPoint.__imul__ (self, int c)
```

[](qpoint.html)

```
QPoint QPoint.__imul__ (self, float c)
```

[](qpoint.html)

```
QPoint QPoint.__isub__ (self, QPoint p)
```

[](qpoint.html)

```
QPoint QPoint.__mul__ (self, int c)
```

[](qpoint.html)

```
QPoint QPoint.__mul__ (self, QPoint p)
```

[](qpoint.html)

```
QPoint QPoint.__mul__ (self, float c)
```

[](qpoint.html)

```
QPoint QPoint.__mul__ (self, QPoint p)
```

[

```
bool QPoint.__ne__ (self, QPoint p2)
```

](qpoint.html)

```
QPoint QPoint.__neg__ (self)
```

[

```
str QPoint.__repr__ (self)
```

](qpoint.html)

```
QPoint QPoint.__sub__ (self, QPoint p2)
```

[](qpoint.html)