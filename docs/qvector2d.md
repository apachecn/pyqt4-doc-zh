# QVector2D Class Reference

## [[QtGui](index.htm) module]

该QVector2D类表示二维空间中的向量或顶点。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, float xpos, float ypos)`
*   `__init__ (self, QPoint point)`
*   `__init__ (self, QPointF point)`
*   `__init__ (self, QVector3D vector)`
*   `__init__ (self, QVector4D vector)`
*   `__init__ (self, QVector2D)`
*   `bool isNull (self)`
*   `float length (self)`
*   `float lengthSquared (self)`
*   `normalize (self)`
*   `QVector2D normalized (self)`
*   `setX (self, float aX)`
*   `setY (self, float aY)`
*   `QPoint toPoint (self)`
*   `QPointF toPointF (self)`
*   `QVector3D toVector3D (self)`
*   `QVector4D toVector4D (self)`
*   `float x (self)`
*   `float y (self)`

### Static Methods

*   `float dotProduct (QVector2D v1, QVector2D v2)`

### Special Methods

*   `QVector2D __add__ (self, QVector2D v2)`
*   `QVector2D __div__ (self, float divisor)`
*   `bool __eq__ (self, QVector2D v2)`
*   `QVector2D __iadd__ (self, QVector2D vector)`
*   `QVector2D __idiv__ (self, float divisor)`
*   `QVector2D __imul__ (self, float factor)`
*   `QVector2D __imul__ (self, QVector2D vector)`
*   `QVector2D __isub__ (self, QVector2D vector)`
*   `QVector2D __mul__ (self, QVector2D vector)`
*   `QVector2D __mul__ (self, float factor)`
*   `QVector2D __mul__ (self, QVector2D v2)`
*   `bool __ne__ (self, QVector2D v2)`
*   `QVector2D __neg__ (self)`
*   `str __repr__ (self)`
*   `QVector2D __sub__ (self, QVector2D v2)`

* * *

## Detailed Description

这个类可以醃制。

该QVector2D类表示二维空间中的向量或顶点。

该QVector2D类也可以用来表示在二维空间的顶点。因此，我们并不需要提供一个独立的顶点类。

**Note:**通过在QVector2D实例设计值存储`float`。这意味着，在平台上，其中`qreal`参数QVector2D函数表示为`double`值，有可能丢失精度。

* * *

## Method Documentation

```
QVector2D.__init__ (self)
```

构造一个空向量，即坐标为（ 0 ， 0 ， 0 ） 。

```
QVector2D.__init__ (self, float xpos, float ypos)
```

构造一个具有坐标向量（_xpos_，_ypos_） 。

```
QVector2D.__init__ (self, QPoint point)
```

构造一个向量x和y坐标从2D_point_。

```
QVector2D.__init__ (self, QPointF point)
```

构造一个向量x和y坐标从2D_point_。

```
QVector2D.__init__ (self, QVector3D vector)
```

构造一个向量x和y坐标由三维_vector_。的Z坐标_vector_被丢弃。

**See also** [toVector3D](qvector2d.html#toVector3D)（ ） 。

```
QVector2D.__init__ (self, QVector4D vector)
```

构造一个向量x和y坐标由三维_vector_。该z和w的坐标_vector_被丢弃。

**See also** [toVector4D](qvector2d.html#toVector4D)（ ） 。

```
QVector2D.__init__ (self, QVector2D)
```

```
float QVector2D.dotProduct (QVector2D v1, QVector2D v2)
```

返回的点积_v1_和_v2_。

```
bool QVector2D.isNull (self)
```

返回True如果x和y坐标都设置为0.0 ，否则返回False 。

```
float QVector2D.length (self)
```

返回向量的距离原点的长度。

**See also** [lengthSquared](qvector2d.html#lengthSquared)（）和[normalized](qvector2d.html#normalized)（ ） 。

```
float QVector2D.lengthSquared (self)
```

返回向量的距离原点的平方长度。这等同于用本身的矢量的点积。

**See also** [length](qvector2d.html#length)（）和[dotProduct](qvector2d.html#dotProduct)（ ） 。

```
QVector2D.normalize (self)
```

标准化到位确认当期的载体。如果该矢量是零矢量或矢量的长度非常接近1没有反应。

**See also** [length](qvector2d.html#length)（）和[normalized](qvector2d.html#normalized)（ ） 。

```
QVector2D QVector2D.normalized (self)
```

[

返回此向量的归一化的单位向量形式。

如果这个向量为null，则一个空向量被返回。如果该矢量的长度非常接近1，则向量将被返回原样。否则，长度为1的向量的归一化形式将被退回。

](qvector2d.html)

[**See also**](qvector2d.html) [length](qvector2d.html#length)（）和[normalize](qvector2d.html#normalize)（ ） 。

```
QVector2D.setX (self, float aX)
```

设置该点的x坐标，以给定的_x_协调。

**See also** [x](qvector2d.html#x)（）和[setY](qvector2d.html#setY)（ ） 。

```
QVector2D.setY (self, float aY)
```

设置该点的y坐标为给定的_y_协调。

**See also** [y](qvector2d.html#y)（）和[setX](qvector2d.html#setX)（ ） 。

```
QPoint QVector2D.toPoint (self)
```

[](qpoint.html)

[返回](qpoint.html)[QPoint](qpoint.html)这个形式二维向量的。

**See also** [toPointF](qvector2d.html#toPointF)（）和[toVector3D](qvector2d.html#toVector3D)（ ） 。

```
QPointF QVector2D.toPointF (self)
```

[](qpointf.html)

[返回](qpointf.html)[QPointF](qpointf.html)这个形式二维向量的。

**See also** [toPoint](qvector2d.html#toPoint)（）和[toVector3D](qvector2d.html#toVector3D)（ ） 。

```
QVector3D QVector2D.toVector3D (self)
```

[

返回三维形式这个二维矢量的，与z坐标设为零。

](qvector3d.html)

[**See also**](qvector3d.html) [toVector4D](qvector2d.html#toVector4D)（）和[toPoint](qvector2d.html#toPoint)（ ） 。

```
QVector4D QVector2D.toVector4D (self)
```

[

返回4D形式这个二维矢量的，与z和w的坐标设置为零。

](qvector4d.html)

[**See also**](qvector4d.html) [toVector3D](qvector2d.html#toVector3D)（）和[toPoint](qvector2d.html#toPoint)（ ） 。

```
float QVector2D.x (self)
```

返回该点的x坐标。

**See also** [setX](qvector2d.html#setX)（）和[y](qvector2d.html#y)（ ） 。

```
float QVector2D.y (self)
```

返回此点的y坐标。

**See also** [setY](qvector2d.html#setY)（）和[x](qvector2d.html#x)（ ） 。

```
QVector2D QVector2D.__add__ (self, QVector2D v2)
```

[](qvector2d.html)

```
QVector2D QVector2D.__div__ (self, float divisor)
```

[

```
bool QVector2D.__eq__ (self, QVector2D v2)
```

](qvector2d.html)

```
QVector2D QVector2D.__iadd__ (self, QVector2D vector)
```

[](qvector2d.html)

```
QVector2D QVector2D.__idiv__ (self, float divisor)
```

[](qvector2d.html)

```
QVector2D QVector2D.__imul__ (self, float factor)
```

[](qvector2d.html)

```
QVector2D QVector2D.__imul__ (self, QVector2D vector)
```

[](qvector2d.html)

```
QVector2D QVector2D.__isub__ (self, QVector2D vector)
```

[](qvector2d.html)

```
QVector2D QVector2D.__mul__ (self, QVector2D vector)
```

[](qvector2d.html)

```
QVector2D QVector2D.__mul__ (self, float factor)
```

[](qvector2d.html)

```
QVector2D QVector2D.__mul__ (self, QVector2D v2)
```

[

```
bool QVector2D.__ne__ (self, QVector2D v2)
```

](qvector2d.html)

```
QVector2D QVector2D.__neg__ (self)
```

[

```
str QVector2D.__repr__ (self)
```

](qvector2d.html)

```
QVector2D QVector2D.__sub__ (self, QVector2D v2)
```

[](qvector2d.html)