# QVector4D Class Reference

## [[QtGui](index.htm) module]

该QVector4D类表示四维空间中的向量或顶点。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, float xpos, float ypos, float zpos, float wpos)`
*   `__init__ (self, QPoint point)`
*   `__init__ (self, QPointF point)`
*   `__init__ (self, QVector2D vector)`
*   `__init__ (self, QVector2D vector, float zpos, float wpos)`
*   `__init__ (self, QVector3D vector)`
*   `__init__ (self, QVector3D vector, float wpos)`
*   `__init__ (self, QVector4D)`
*   `bool isNull (self)`
*   `float length (self)`
*   `float lengthSquared (self)`
*   `normalize (self)`
*   `QVector4D normalized (self)`
*   `setW (self, float aW)`
*   `setX (self, float aX)`
*   `setY (self, float aY)`
*   `setZ (self, float aZ)`
*   `QPoint toPoint (self)`
*   `QPointF toPointF (self)`
*   `QVector2D toVector2D (self)`
*   `QVector2D toVector2DAffine (self)`
*   `QVector3D toVector3D (self)`
*   `QVector3D toVector3DAffine (self)`
*   `float w (self)`
*   `float x (self)`
*   `float y (self)`
*   `float z (self)`

### Static Methods

*   `float dotProduct (QVector4D v1, QVector4D v2)`

### Special Methods

*   `QVector4D __add__ (self, QVector4D v2)`
*   `QVector4D __div__ (self, float divisor)`
*   `bool __eq__ (self, QVector4D v2)`
*   `QVector4D __iadd__ (self, QVector4D vector)`
*   `QVector4D __idiv__ (self, float divisor)`
*   `QVector4D __imul__ (self, float factor)`
*   `QVector4D __imul__ (self, QVector4D vector)`
*   `QVector4D __isub__ (self, QVector4D vector)`
*   `QVector4D __mul__ (self, QMatrix4x4 matrix)`
*   `QVector4D __mul__ (self, QVector4D vector)`
*   `QVector4D __mul__ (self, float factor)`
*   `QVector4D __mul__ (self, QVector4D v2)`
*   `bool __ne__ (self, QVector4D v2)`
*   `QVector4D __neg__ (self)`
*   `str __repr__ (self)`
*   `QVector4D __sub__ (self, QVector4D v2)`

* * *

## Detailed Description

这个类可以醃制。

该QVector4D类表示四维空间中的向量或顶点。

该QVector4D类也可以用来表示在四维空间的顶点。因此，我们并不需要提供一个独立的顶点类。

**Note:**通过在QVector4D实例设计值存储`float`。这意味着，在平台上，其中`qreal`参数QVector4D函数表示为`double`值，有可能丢失精度。

* * *

## Method Documentation

```
QVector4D.__init__ (self)
```

构造一个空向量，即坐标为（ 0 ， 0 ， 0 ， 0 ） 。

```
QVector4D.__init__ (self, float xpos, float ypos, float zpos, float wpos)
```

构造一个具有坐标向量（_xpos_，_ypos_，_zpos_，_wpos_） 。

```
QVector4D.__init__ (self, QPoint point)
```

构造一个向量x和y坐标从2D_point_和z为0瓦特坐标。

```
QVector4D.__init__ (self, QPointF point)
```

构造一个向量x和y坐标从2D_point_和z为0瓦特坐标。

```
QVector4D.__init__ (self, QVector2D vector)
```

构造一个4D向量从指定的2D_vector_。在z和w坐标被设置为零。

**See also** [toVector2D](qvector4d.html#toVector2D)（ ） 。

```
QVector4D.__init__ (self, QVector2D vector, float zpos, float wpos)
```

构造一个4D向量从指定的2D_vector_。在z和w的坐标被设置为_zpos_和_wpos_分别。

**See also** [toVector2D](qvector4d.html#toVector2D)（ ） 。

```
QVector4D.__init__ (self, QVector3D vector)
```

构造一个4D向量从指定的3D_vector_。的瓦特坐标被设置为零。

**See also** [toVector3D](qvector4d.html#toVector3D)（ ） 。

```
QVector4D.__init__ (self, QVector3D vector, float wpos)
```

构造一个4D向量从指定的3D_vector_。在W的坐标设置为_wpos_。

**See also** [toVector3D](qvector4d.html#toVector3D)（ ） 。

```
QVector4D.__init__ (self, QVector4D)
```

```
float QVector4D.dotProduct (QVector4D v1, QVector4D v2)
```

返回的点积_v1_和_v2_。

```
bool QVector4D.isNull (self)
```

返回True如果在x，y ， z和w坐标都设置为0.0 ，否则返回False 。

```
float QVector4D.length (self)
```

返回向量的距离原点的长度。

**See also** [lengthSquared](qvector4d.html#lengthSquared)（）和[normalized](qvector4d.html#normalized)（ ） 。

```
float QVector4D.lengthSquared (self)
```

返回向量的距离原点的平方长度。这等同于用本身的矢量的点积。

**See also** [length](qvector4d.html#length)（）和[dotProduct](qvector4d.html#dotProduct)（ ） 。

```
QVector4D.normalize (self)
```

标准化到位确认当期的载体。如果该矢量是零矢量或矢量的长度非常接近1没有反应。

**See also** [length](qvector4d.html#length)（）和[normalized](qvector4d.html#normalized)（ ） 。

```
QVector4D QVector4D.normalized (self)
```

[

返回此向量的归一化的单位向量形式。

如果这个向量为null，则一个空向量被返回。如果该矢量的长度非常接近1，则向量将被返回原样。否则，长度为1的向量的归一化形式将被退回。

](qvector4d.html)

[**See also**](qvector4d.html) [length](qvector4d.html#length)（）和[normalize](qvector4d.html#normalize)（ ） 。

```
QVector4D.setW (self, float aW)
```

设置该点的坐标瓦特为给定的_w_协调。

**See also** [w](qvector4d.html#w)（ ）[setX](qvector4d.html#setX)（ ）[setY](qvector4d.html#setY)（）和[setZ](qvector4d.html#setZ)（ ） 。

```
QVector4D.setX (self, float aX)
```

设置该点的x坐标，以给定的_x_协调。

**See also** [x](qvector4d.html#x)（ ）[setY](qvector4d.html#setY)（ ）[setZ](qvector4d.html#setZ)（）和[setW](qvector4d.html#setW)（ ） 。

```
QVector4D.setY (self, float aY)
```

设置该点的y坐标为给定的_y_协调。

**See also** [y](qvector4d.html#y)（ ）[setX](qvector4d.html#setX)（ ）[setZ](qvector4d.html#setZ)（）和[setW](qvector4d.html#setW)（ ） 。

```
QVector4D.setZ (self, float aZ)
```

设置该点的z坐标，以给定的_z_协调。

**See also** [z](qvector4d.html#z)（ ）[setX](qvector4d.html#setX)（ ）[setY](qvector4d.html#setY)（）和[setW](qvector4d.html#setW)（ ） 。

```
QPoint QVector4D.toPoint (self)
```

[](qpoint.html)

[返回](qpoint.html)[QPoint](qpoint.html)构成本4D向量。在Z和W坐标将被丢弃。

**See also** [toPointF](qvector4d.html#toPointF)（）和[toVector2D](qvector4d.html#toVector2D)（ ） 。

```
QPointF QVector4D.toPointF (self)
```

[](qpointf.html)

[返回](qpointf.html)[QPointF](qpointf.html)构成本4D向量。在Z和W坐标将被丢弃。

**See also** [toPoint](qvector4d.html#toPoint)（）和[toVector2D](qvector4d.html#toVector2D)（ ） 。

```
QVector2D QVector4D.toVector2D (self)
```

[

返回此4D向量的二维矢量形式，滴在z和w的坐标。

](qvector2d.html)

[**See also**](qvector2d.html) [toVector2DAffine](qvector4d.html#toVector2DAffine)（ ）[toVector3D](qvector4d.html#toVector3D)（）和[toPoint](qvector4d.html#toPoint)（ ） 。

```
QVector2D QVector4D.toVector2DAffine (self)
```

[

返回此4D向量的二维矢量的形式，将所述x和y坐标由瓦特坐标和滴的z坐标。返回一个空向量，如果w是零。

](qvector2d.html)

[**See also**](qvector2d.html) [toVector2D](qvector4d.html#toVector2D)（ ）[toVector3DAffine](qvector4d.html#toVector3DAffine)（）和[toPoint](qvector4d.html#toPoint)（ ） 。

```
QVector3D QVector4D.toVector3D (self)
```

[

返回此4D向量的三维矢量形式，下降的W坐标。

](qvector3d.html)

[**See also**](qvector3d.html) [toVector3DAffine](qvector4d.html#toVector3DAffine)（ ）[toVector2D](qvector4d.html#toVector2D)（）和[toPoint](qvector4d.html#toPoint)（ ） 。

```
QVector3D QVector4D.toVector3DAffine (self)
```

[

返回此4D向量的三维矢量的形式，将所述的x， y和z的瓦特坐标的坐标。返回一个空向量，如果w是零。

](qvector3d.html)

[**See also**](qvector3d.html) [toVector3D](qvector4d.html#toVector3D)（ ）[toVector2DAffine](qvector4d.html#toVector2DAffine)（）和[toPoint](qvector4d.html#toPoint)（ ） 。

```
float QVector4D.w (self)
```

返回此点的W坐标。

**See also** [setW](qvector4d.html#setW)（ ）[x](qvector4d.html#x)（ ）[y](qvector4d.html#y)（）和[z](qvector4d.html#z)（ ） 。

```
float QVector4D.x (self)
```

返回该点的x坐标。

**See also** [setX](qvector4d.html#setX)（ ）[y](qvector4d.html#y)（ ）[z](qvector4d.html#z)（）和[w](qvector4d.html#w)（ ） 。

```
float QVector4D.y (self)
```

返回此点的y坐标。

**See also** [setY](qvector4d.html#setY)（ ）[x](qvector4d.html#x)（ ）[z](qvector4d.html#z)（）和[w](qvector4d.html#w)（ ） 。

```
float QVector4D.z (self)
```

返回此点的z坐标。

**See also** [setZ](qvector4d.html#setZ)（ ）[x](qvector4d.html#x)（ ）[y](qvector4d.html#y)（）和[w](qvector4d.html#w)（ ） 。

```
QVector4D QVector4D.__add__ (self, QVector4D v2)
```

[](qvector4d.html)

```
QVector4D QVector4D.__div__ (self, float divisor)
```

[

```
bool QVector4D.__eq__ (self, QVector4D v2)
```

](qvector4d.html)

```
QVector4D QVector4D.__iadd__ (self, QVector4D vector)
```

[](qvector4d.html)

```
QVector4D QVector4D.__idiv__ (self, float divisor)
```

[](qvector4d.html)

```
QVector4D QVector4D.__imul__ (self, float factor)
```

[](qvector4d.html)

```
QVector4D QVector4D.__imul__ (self, QVector4D vector)
```

[](qvector4d.html)

```
QVector4D QVector4D.__isub__ (self, QVector4D vector)
```

[](qvector4d.html)

```
QVector4D QVector4D.__mul__ (self, QMatrix4x4 matrix)
```

[](qvector4d.html)

```
QVector4D QVector4D.__mul__ (self, QVector4D vector)
```

[](qvector4d.html)

```
QVector4D QVector4D.__mul__ (self, float factor)
```

[](qvector4d.html)

```
QVector4D QVector4D.__mul__ (self, QVector4D v2)
```

[

```
bool QVector4D.__ne__ (self, QVector4D v2)
```

](qvector4d.html)

```
QVector4D QVector4D.__neg__ (self)
```

[

```
str QVector4D.__repr__ (self)
```

](qvector4d.html)

```
QVector4D QVector4D.__sub__ (self, QVector4D v2)
```

[](qvector4d.html)