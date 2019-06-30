# QVector3D Class Reference

## [[QtGui](index.htm) module]

该QVector3D类表示在三维空间中的矢量或顶点。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, float xpos, float ypos, float zpos)`
*   `__init__ (self, QPoint point)`
*   `__init__ (self, QPointF point)`
*   `__init__ (self, QVector2D vector)`
*   `__init__ (self, QVector2D vector, float zpos)`
*   `__init__ (self, QVector4D vector)`
*   `__init__ (self, QVector3D)`
*   `float distanceToLine (self, QVector3D point, QVector3D direction)`
*   `float distanceToPlane (self, QVector3D plane, QVector3D normal)`
*   `float distanceToPlane (self, QVector3D plane1, QVector3D plane2, QVector3D plane3)`
*   `bool isNull (self)`
*   `float length (self)`
*   `float lengthSquared (self)`
*   `normalize (self)`
*   `QVector3D normalized (self)`
*   `setX (self, float aX)`
*   `setY (self, float aY)`
*   `setZ (self, float aZ)`
*   `QPoint toPoint (self)`
*   `QPointF toPointF (self)`
*   `QVector2D toVector2D (self)`
*   `QVector4D toVector4D (self)`
*   `float x (self)`
*   `float y (self)`
*   `float z (self)`

### Static Methods

*   `QVector3D crossProduct (QVector3D v1, QVector3D v2)`
*   `float dotProduct (QVector3D v1, QVector3D v2)`
*   `QVector3D normal (QVector3D v1, QVector3D v2)`
*   `QVector3D normal (QVector3D v1, QVector3D v2, QVector3D v3)`

### Special Methods

*   `QVector3D __add__ (self, QVector3D v2)`
*   `QVector3D __div__ (self, float divisor)`
*   `bool __eq__ (self, QVector3D v2)`
*   `QVector3D __iadd__ (self, QVector3D vector)`
*   `QVector3D __idiv__ (self, float divisor)`
*   `QVector3D __imul__ (self, float factor)`
*   `QVector3D __imul__ (self, QVector3D vector)`
*   `QVector3D __isub__ (self, QVector3D vector)`
*   `QVector3D __mul__ (self, QMatrix4x4 matrix)`
*   `QVector3D __mul__ (self, QVector3D vector)`
*   `QVector3D __mul__ (self, float factor)`
*   `QVector3D __mul__ (self, QVector3D v2)`
*   `bool __ne__ (self, QVector3D v2)`
*   `QVector3D __neg__ (self)`
*   `str __repr__ (self)`
*   `QVector3D __sub__ (self, QVector3D v2)`

* * *

## Detailed Description

这个类可以醃制。

该QVector3D类表示在三维空间中的矢量或顶点。

载体是三维表示和绘画的主要基石之一。它们由三个坐标，传统上被称为的x，y和z 。

该QVector3D类也可以用来表示在三维空间的顶点。因此，我们并不需要提供一个独立的顶点类。

**Note:**通过在QVector3D实例设计值存储`float`。这意味着，在平台上，其中`qreal`参数QVector3D函数表示为`double`值，有可能丢失精度。

* * *

## Method Documentation

```
QVector3D.__init__ (self)
```

构造一个空向量，即坐标为（ 0 ， 0 ， 0 ） 。

```
QVector3D.__init__ (self, float xpos, float ypos, float zpos)
```

构造一个具有坐标向量（_xpos_，_ypos_，_zpos_） 。

```
QVector3D.__init__ (self, QPoint point)
```

构造一个向量x和y坐标从2D_point_，和一个Z座标为0 。

```
QVector3D.__init__ (self, QPointF point)
```

构造一个向量x和y坐标从2D_point_，和一个Z座标为0 。

```
QVector3D.__init__ (self, QVector2D vector)
```

构造一个三维向量从指定的2D_vector_。的z坐标设为零。

**See also** [toVector2D](qvector3d.html#toVector2D)（ ） 。

```
QVector3D.__init__ (self, QVector2D vector, float zpos)
```

构造一个三维向量从指定的2D_vector_。 Z坐标设置为_zpos_。

**See also** [toVector2D](qvector3d.html#toVector2D)（ ） 。

```
QVector3D.__init__ (self, QVector4D vector)
```

构造一个三维向量从指定4D_vector_。在W坐标将被丢弃。

**See also** [toVector4D](qvector3d.html#toVector4D)（ ） 。

```
QVector3D.__init__ (self, QVector3D)
```

```
QVector3D QVector3D.crossProduct (QVector3D v1, QVector3D v2)
```

[

返回向量的叉积_v1_和_v2_，对应于由所确定的平面的法线矢量_v1_和_v2_。

](qvector3d.html)

[**See also**](qvector3d.html) [normal](qvector3d.html#normal)（ ） 。

```
float QVector3D.distanceToLine (self, QVector3D point, QVector3D direction)
```

返回由定义的直线的距离，这个顶点是_point_和单位矢量_direction_。

If _direction_是一个空向量，那么它没有定义线。在这种情况下，从距离_point_这个顶点将被返回。

**See also** [distanceToPlane](qvector3d.html#distanceToPlane)（ ） 。

```
float QVector3D.distanceToPlane (self, QVector3D plane, QVector3D normal)
```

返回的距离从该顶点由顶点限定的平面_plane_和_normal_单位向量。该_normal_参数被假定已经被标准化为单位向量。

返回值将是负面的，如果顶点是平面的下方，​​或零，如果它是在飞机上。

**See also** [normal](qvector3d.html#normal)（）和[distanceToLine](qvector3d.html#distanceToLine)（ ） 。

```
float QVector3D.distanceToPlane (self, QVector3D plane1, QVector3D plane2, QVector3D plane3)
```

这是一个重载函数。

返回从该顶点的距离的顶点所限定的平面_plane1_，_plane2_和_plane3_。

返回值将是负面的，如果顶点是平面的下方，​​或零，如果它是在飞机上。

两个向量的定义平面的_plane2_ - _plane1_和_plane3_ - _plane1_。

**See also** [normal](qvector3d.html#normal)（）和[distanceToLine](qvector3d.html#distanceToLine)（ ） 。

```
float QVector3D.dotProduct (QVector3D v1, QVector3D v2)
```

返回的点积_v1_和_v2_。

```
bool QVector3D.isNull (self)
```

返回True如果在x，y ，z坐标都设置为0.0 ，否则返回False 。

```
float QVector3D.length (self)
```

返回向量的距离原点的长度。

**See also** [lengthSquared](qvector3d.html#lengthSquared)（）和[normalized](qvector3d.html#normalized)（ ） 。

```
float QVector3D.lengthSquared (self)
```

返回向量的距离原点的平方长度。这等同于用本身的矢量的点积。

**See also** [length](qvector3d.html#length)（）和[dotProduct](qvector3d.html#dotProduct)（ ） 。

```
QVector3D QVector3D.normal (QVector3D v1, QVector3D v2)
```

[

返回一个平面上的由矢量定义的法线向量_v1_和_v2_，归一化是一个单位矢量。

](qvector3d.html)

[使用](qvector3d.html)[crossProduct](qvector3d.html#crossProduct)（）来计算的交叉乘积_v1_和_v2_如果你不需要将结果进行标准化为单位矢量。

**See also** [crossProduct](qvector3d.html#crossProduct)（）和[distanceToPlane](qvector3d.html#distanceToPlane)（ ） 。

```
QVector3D QVector3D.normal (QVector3D v1, QVector3D v2, QVector3D v3)
```

[

这是一个重载函数。

返回一个平面上的由矢量定义的法线向量_v2_ - _v1_和_v3_ - _v1_，归一化是一个单位矢量。

](qvector3d.html)

[使用](qvector3d.html)[crossProduct](qvector3d.html#crossProduct)（）来计算的交叉乘积_v2_ - _v1_和_v3_ - _v1_如果你不需要将结果进行标准化为单位矢量。

**See also** [crossProduct](qvector3d.html#crossProduct)（）和[distanceToPlane](qvector3d.html#distanceToPlane)（ ） 。

```
QVector3D.normalize (self)
```

标准化到位确认当期的载体。如果该矢量是零矢量或矢量的长度非常接近1没有反应。

**See also** [length](qvector3d.html#length)（）和[normalized](qvector3d.html#normalized)（ ） 。

```
QVector3D QVector3D.normalized (self)
```

[

返回此向量的归一化的单位向量形式。

如果这个向量为null，则一个空向量被返回。如果该矢量的长度非常接近1，则向量将被返回原样。否则，长度为1的向量的归一化形式将被退回。

](qvector3d.html)

[**See also**](qvector3d.html) [length](qvector3d.html#length)（）和[normalize](qvector3d.html#normalize)（ ） 。

```
QVector3D.setX (self, float aX)
```

设置该点的x坐标，以给定的_x_协调。

**See also** [x](qvector3d.html#x)（ ）[setY](qvector3d.html#setY)（）和[setZ](qvector3d.html#setZ)（ ） 。

```
QVector3D.setY (self, float aY)
```

设置该点的y坐标为给定的_y_协调。

**See also** [y](qvector3d.html#y)（ ）[setX](qvector3d.html#setX)（）和[setZ](qvector3d.html#setZ)（ ） 。

```
QVector3D.setZ (self, float aZ)
```

设置该点的z坐标，以给定的_z_协调。

**See also** [z](qvector3d.html#z)（ ）[setX](qvector3d.html#setX)（）和[setY](qvector3d.html#setY)（ ） 。

```
QPoint QVector3D.toPoint (self)
```

[](qpoint.html)

[返回](qpoint.html)[QPoint](qpoint.html)本表格3D向量。 Z坐标将被丢弃。

**See also** [toPointF](qvector3d.html#toPointF)（）和[toVector2D](qvector3d.html#toVector2D)（ ） 。

```
QPointF QVector3D.toPointF (self)
```

[](qpointf.html)

[返回](qpointf.html)[QPointF](qpointf.html)本表格3D向量。 Z坐标将被丢弃。

**See also** [toPoint](qvector3d.html#toPoint)（）和[toVector2D](qvector3d.html#toVector2D)（ ） 。

```
QVector2D QVector3D.toVector2D (self)
```

[

返回此三维矢量的2D向量形式，去掉了z坐标。

](qvector2d.html)

[**See also**](qvector2d.html) [toVector4D](qvector3d.html#toVector4D)（）和[toPoint](qvector3d.html#toPoint)（ ） 。

```
QVector4D QVector3D.toVector4D (self)
```

[

返回4D形式这个三维矢量，用坐标设置为零瓦特。

](qvector4d.html)

[**See also**](qvector4d.html) [toVector2D](qvector3d.html#toVector2D)（）和[toPoint](qvector3d.html#toPoint)（ ） 。

```
float QVector3D.x (self)
```

返回该点的x坐标。

**See also** [setX](qvector3d.html#setX)（ ）[y](qvector3d.html#y)（）和[z](qvector3d.html#z)（ ） 。

```
float QVector3D.y (self)
```

返回此点的y坐标。

**See also** [setY](qvector3d.html#setY)（ ）[x](qvector3d.html#x)（）和[z](qvector3d.html#z)（ ） 。

```
float QVector3D.z (self)
```

返回此点的z坐标。

**See also** [setZ](qvector3d.html#setZ)（ ）[x](qvector3d.html#x)（）和[y](qvector3d.html#y)（ ） 。

```
QVector3D QVector3D.__add__ (self, QVector3D v2)
```

[](qvector3d.html)

```
QVector3D QVector3D.__div__ (self, float divisor)
```

[

```
bool QVector3D.__eq__ (self, QVector3D v2)
```

](qvector3d.html)

```
QVector3D QVector3D.__iadd__ (self, QVector3D vector)
```

[](qvector3d.html)

```
QVector3D QVector3D.__idiv__ (self, float divisor)
```

[](qvector3d.html)

```
QVector3D QVector3D.__imul__ (self, float factor)
```

[](qvector3d.html)

```
QVector3D QVector3D.__imul__ (self, QVector3D vector)
```

[](qvector3d.html)

```
QVector3D QVector3D.__isub__ (self, QVector3D vector)
```

[](qvector3d.html)

```
QVector3D QVector3D.__mul__ (self, QMatrix4x4 matrix)
```

[](qvector3d.html)

```
QVector3D QVector3D.__mul__ (self, QVector3D vector)
```

[](qvector3d.html)

```
QVector3D QVector3D.__mul__ (self, float factor)
```

[](qvector3d.html)

```
QVector3D QVector3D.__mul__ (self, QVector3D v2)
```

[

```
bool QVector3D.__ne__ (self, QVector3D v2)
```

](qvector3d.html)

```
QVector3D QVector3D.__neg__ (self)
```

[

```
str QVector3D.__repr__ (self)
```

](qvector3d.html)

```
QVector3D QVector3D.__sub__ (self, QVector3D v2)
```

[](qvector3d.html)