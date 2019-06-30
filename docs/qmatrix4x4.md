# QMatrix4x4 Class Reference

## [[QtGui](index.htm) module]

该QMatrix4x4类表示在三维空间中的4×4变换矩阵。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, sequence-of-float values)`
*   `__init__ (self, float m11, float m12, float m13, float m14, float m21, float m22, float m23, float m24, float m31, float m32, float m33, float m34, float m41, float m42, float m43, float m44)`
*   `__init__ (self, QTransform transform)`
*   `__init__ (self, QMatrix matrix)`
*   `__init__ (self, QMatrix4x4)`
*   `QVector4D column (self, int index)`
*   `list-of-float copyDataTo (self)`
*   `list-of-float data (self)`
*   `float determinant (self)`
*   `fill (self, float value)`
*   `flipCoordinates (self)`
*   `frustum (self, float left, float right, float bottom, float top, float nearPlane, float farPlane)`
*   `(QMatrix4x4, bool invertible) inverted (self)`
*   `bool isIdentity (self)`
*   `lookAt (self, QVector3D eye, QVector3D center, QVector3D up)`
*   `QPoint map (self, QPoint point)`
*   `QPointF map (self, QPointF point)`
*   `QVector3D map (self, QVector3D point)`
*   `QVector4D map (self, QVector4D point)`
*   `QRect mapRect (self, QRect rect)`
*   `QRectF mapRect (self, QRectF rect)`
*   `QVector3D mapVector (self, QVector3D vector)`
*   `QMatrix3x3 normalMatrix (self)`
*   `optimize (self)`
*   `ortho (self, QRect rect)`
*   `ortho (self, QRectF rect)`
*   `ortho (self, float left, float right, float bottom, float top, float nearPlane, float farPlane)`
*   `perspective (self, float angle, float aspect, float nearPlane, float farPlane)`
*   `rotate (self, float angle, QVector3D vector)`
*   `rotate (self, float angle, float x, float y, float z = 0)`
*   `rotate (self, QQuaternion quaternion)`
*   `QVector4D row (self, int index)`
*   `scale (self, QVector3D vector)`
*   `scale (self, float x, float y)`
*   `scale (self, float x, float y, float z)`
*   `scale (self, float factor)`
*   `setColumn (self, int index, QVector4D value)`
*   `setRow (self, int index, QVector4D value)`
*   `setToIdentity (self)`
*   `QMatrix toAffine (self)`
*   `QTransform toTransform (self)`
*   `QTransform toTransform (self, float distanceToPlane)`
*   `translate (self, QVector3D vector)`
*   `translate (self, float x, float y)`
*   `translate (self, float x, float y, float z)`
*   `QMatrix4x4 transposed (self)`

### Special Methods

*   `QMatrix4x4 __add__ (self, QMatrix4x4 m2)`
*   `QMatrix4x4 __div__ (self, float divisor)`
*   `bool __eq__ (self, QMatrix4x4 other)`
*   `object __getitem__ (self, object)`
*   `QMatrix4x4 __iadd__ (self, QMatrix4x4 other)`
*   `QMatrix4x4 __idiv__ (self, float divisor)`
*   `QMatrix4x4 __imul__ (self, QMatrix4x4 other)`
*   `QMatrix4x4 __imul__ (self, float factor)`
*   `QMatrix4x4 __isub__ (self, QMatrix4x4 other)`
*   `QMatrix4x4 __mul__ (self, QMatrix4x4 m2)`
*   `QVector3D __mul__ (self, QVector3D vector)`
*   `QVector4D __mul__ (self, QVector4D vector)`
*   `QPoint __mul__ (self, QPoint point)`
*   `QPointF __mul__ (self, QPointF point)`
*   `QMatrix4x4 __mul__ (self, QMatrix4x4 matrix)`
*   `QMatrix4x4 __mul__ (self, float factor)`
*   `bool __ne__ (self, QMatrix4x4 other)`
*   `QMatrix4x4 __neg__ (self)`
*   `str __repr__ (self)`
*   `__setitem__ (self, object, float)`
*   `QMatrix4x4 __sub__ (self, QMatrix4x4 m2)`

* * *

## Detailed Description

这个类可以醃制。

该QMatrix4x4类表示在三维空间中的4×4变换矩阵。

* * *

## Method Documentation

```
QMatrix4x4.__init__ (self)
```

构造一个单位矩阵。

```
QMatrix4x4.__init__ (self, sequence-of-float values)
```

构造一个矩阵从给定的16浮点_values_。该数组的内容_values_被认为是行优先的顺序。

如果矩阵有一种特殊类型（身份证，平移，缩放等） ，程序员应该遵循这个构造函数调用[optimize](qmatrix4x4.html#optimize)（ ）如果他们想[QMatrix4x4](qmatrix4x4.html)优化还呼吁[translate](qmatrix4x4.html#translate)（ ）[scale](qmatrix4x4.html#scale)（）等

**See also** [copyDataTo](qmatrix4x4.html#copyDataTo)（）和[optimize](qmatrix4x4.html#optimize)（ ） 。

```
QMatrix4x4.__init__ (self, float m11, float m12, float m13, float m14, float m21, float m22, float m23, float m24, float m31, float m32, float m33, float m34, float m41, float m42, float m43, float m44)
```

构造一个矩阵由16个元素_m11_，_m12_，_m13_，_m14_，_m21_，_m22_，_m23_，_m24_，_m31_，_m32_，_m33_，_m34_，_m41_，_m42_，_m43_和_m44_。该元素按行优先的顺序指定。

如果矩阵有一种特殊类型（身份证，平移，缩放等） ，程序员应该遵循这个构造函数调用[optimize](qmatrix4x4.html#optimize)（ ）如果他们想[QMatrix4x4](qmatrix4x4.html)优化还呼吁[translate](qmatrix4x4.html#translate)（ ）[scale](qmatrix4x4.html#scale)（）等

**See also** [optimize](qmatrix4x4.html#optimize)（ ） 。

```
QMatrix4x4.__init__ (self, QTransform transform)
```

构造一个4x4矩阵从最左边的4列和最上面的4行的_matrix_。如果_matrix_具有小于4的列或行，其馀的元素都充满了从单位矩阵的元素。

**See also** [toGenericMatrix](qmatrix4x4.html#toGenericMatrix)（ ） 。

```
QMatrix4x4.__init__ (self, QMatrix matrix)
```

```
QMatrix4x4.__init__ (self, QMatrix4x4)
```

构造一个4x4矩阵与传统的Qt 2D变换矩阵_transform_。

If _transform_有一种特殊类型（身份证，平移，缩放等） ，程序员应该遵循这个构造函数调用[optimize](qmatrix4x4.html#optimize)（ ）如果他们想[QMatrix4x4](qmatrix4x4.html)优化还呼吁[translate](qmatrix4x4.html#translate)（ ）[scale](qmatrix4x4.html#scale)（）等

**See also** [toTransform](qmatrix4x4.html#toTransform)（）和[optimize](qmatrix4x4.html#optimize)（ ） 。

```
QVector4D QMatrix4x4.column (self, int index)
```

[

返回列的元素_index_为4D向量。

](qvector4d.html)

[**See also**](qvector4d.html) [setColumn](qmatrix4x4.html#setColumn)（）和[row](qmatrix4x4.html#row)（ ） 。

```
list-of-float QMatrix4x4.copyDataTo (self)
```

获取可在此矩阵中的16个项目，并将它们复制到_values_以行优先的顺序。

```
list-of-float QMatrix4x4.data (self)
```

返回一个指针，该矩阵的原始数据。

**See also** [constData](qmatrix4x4.html#constData)（）和[optimize](qmatrix4x4.html#optimize)（ ） 。

```
float QMatrix4x4.determinant (self)
```

返回该矩阵的行列式。

```
QMatrix4x4.fill (self, float value)
```

填补这一MATRX的所有元素_value_。

```
QMatrix4x4.flipCoordinates (self)
```

之间翻转右手和左手被乘以-1的y和z坐标的坐标系。这是通常用来创建一个左手正投影视图，而无需缩放视口[ortho](qmatrix4x4.html#ortho)（ ）一样。

**See also** [ortho](qmatrix4x4.html#ortho)（ ） 。

```
QMatrix4x4.frustum (self, float left, float right, float bottom, float top, float nearPlane, float farPlane)
```

乘以这个矩阵由另一个应用的透视投影圆台的窗口左下角（_left_，_bottom_） ，右上角（_right_，_top_） ，并且指定_nearPlane_和_farPlane_剪切平面。

**See also** [ortho](qmatrix4x4.html#ortho)（）和[perspective](qmatrix4x4.html#perspective)（ ） 。

```
(QMatrix4x4, bool invertible) QMatrix4x4.inverted (self)
```

返回该矩阵的逆矩阵。返回的身份，如果这个矩阵不能倒置，即[determinant](qmatrix4x4.html#determinant)（ ）是零。如果_invertible_否则为False ;不为空，那么真正的将被写入该位置，如果该矩阵可以反转。

如果矩阵是公认的身份或一个正交矩阵，则该函数将迅速颠倒使用优化例程的矩阵。

**See also** [determinant](qmatrix4x4.html#determinant)（）和[normalMatrix](qmatrix4x4.html#normalMatrix)（ ） 。

```
bool QMatrix4x4.isIdentity (self)
```

返回True如果这个矩阵是单位，否则为False 。

**See also** [setToIdentity](qmatrix4x4.html#setToIdentity)（ ） 。

```
QMatrix4x4.lookAt (self, QVector3D eye, QVector3D center, QVector3D up)
```

乘以这个矩阵由另一个适用的_eye_位置的转变。该_center_值指示该视图的中心，该_eye_在看。该_up_值指示哪个方向，应考虑向上相对于所述_eye_。

```
QPoint QMatrix4x4.map (self, QPoint point)
```

[

地图_point_由这个矩阵乘以_point_。

](qpoint.html)

[**See also**](qpoint.html) [mapRect](qmatrix4x4.html#mapRect)（ ） 。

```
QPointF QMatrix4x4.map (self, QPointF point)
```

[

地图_point_由这个矩阵乘以_point_。

](qpointf.html)

[**See also**](qpointf.html) [mapRect](qmatrix4x4.html#mapRect)（ ） 。

```
QVector3D QMatrix4x4.map (self, QVector3D point)
```

[

地图_point_由这个矩阵乘以_point_。

](qvector3d.html)

[**See also**](qvector3d.html) [mapRect](qmatrix4x4.html#mapRect)（）和[mapVector](qmatrix4x4.html#mapVector)（ ） 。

```
QVector4D QMatrix4x4.map (self, QVector4D point)
```

[

地图_point_由这个矩阵乘以_point_。

](qvector4d.html)

[**See also**](qvector4d.html) [mapRect](qmatrix4x4.html#mapRect)（ ） 。

```
QRect QMatrix4x4.mapRect (self, QRect rect)
```

[

地图_rect_由该矩阵通过的角倍增_rect_然后形成从结果一个新的矩形。返回的矩形将与边平行于水平轴和垂直轴以普通二维矩形。

](qrect.html)

[**See also**](qrect.html) [map](qmatrix4x4.html#map)（ ） 。

```
QRectF QMatrix4x4.mapRect (self, QRectF rect)
```

[

地图_rect_由该矩阵通过的角倍增_rect_然后形成从结果一个新的矩形。返回的矩形将与边平行于水平轴和垂直轴以普通二维矩形。

](qrectf.html)

[**See also**](qrectf.html) [map](qmatrix4x4.html#map)（ ） 。

```
QVector3D QMatrix4x4.mapVector (self, QVector3D vector)
```

[

地图_vector_通过这个矩阵的顶3X3部分乘以_vector_。这个矩阵的转换和投影组件将被忽略。

](qvector3d.html)

[**See also**](qvector3d.html) [map](qmatrix4x4.html#map)（ ） 。

```
QMatrix3x3 QMatrix4x4.normalMatrix (self)
```

[

返回对应于该4×4变换法矩阵。正常的矩阵是这样的4x4矩阵的左上角的3×3部分的逆的转置。如果3×3子矩阵是不可逆的，则该函数返回的标识。

](qmatrix3x3.html)

[**See also**](qmatrix3x3.html) [inverted](qmatrix4x4.html#inverted)（ ） 。

```
QMatrix4x4.optimize (self)
```

从它的当前元素优化这个矩阵的使用。

一些操作，如[translate](qmatrix4x4.html#translate)（ ）[scale](qmatrix4x4.html#scale)（）和[rotate](qmatrix4x4.html#rotate)（）可以进行更有效，如果正在修改的矩阵是已经已知的身份，前[translate](qmatrix4x4.html#translate)（） ，前[scale](qmatrix4x4.html#scale)（）等

通常情况下，[QMatrix4x4](qmatrix4x4.html)类跟踪这种特殊类型的内部作为被执行的操作。然而，如果基质是与操作者直接修改（）（）或[data](qmatrix4x4.html#data)（），然后[QMatrix4x4](qmatrix4x4.html)将失去轨道的特殊类型，将恢复为最安全的，但至少有效率的运作之后。

通过直接修改矩阵后调用优化（ ） ，程序员可以强制[QMatrix4x4](qmatrix4x4.html)收回特殊类型，如果元素出现，以符合公知的优化类型之一。

**See also** [operator](qmatrix4x4.html#operator-28-29)（ ） （ ） ，[data](qmatrix4x4.html#data)（）和[translate](qmatrix4x4.html#translate)（ ） 。

```
QMatrix4x4.ortho (self, QRect rect)
```

乘以这个矩阵由另一个应用正交投影的窗口左下角（_left_，_bottom_） ，右上角（_right_，_top_） ，并且指定_nearPlane_和_farPlane_剪切平面。

**See also** [frustum](qmatrix4x4.html#frustum)（）和[perspective](qmatrix4x4.html#perspective)（ ） 。

```
QMatrix4x4.ortho (self, QRectF rect)
```

这是一个重载函数。

乘以这个矩阵由另一个应用正交投影为一个窗口，由指定的边界_rect_。分别为近，远裁剪平面将是-1到1 。

**See also** [frustum](qmatrix4x4.html#frustum)（）和[perspective](qmatrix4x4.html#perspective)（ ） 。

```
QMatrix4x4.ortho (self, float left, float right, float bottom, float top, float nearPlane, float farPlane)
```

这是一个重载函数。

乘以这个矩阵由另一个应用正交投影为一个窗口，由指定的边界_rect_。分别为近，远裁剪平面将是-1到1 。

**See also** [frustum](qmatrix4x4.html#frustum)（）和[perspective](qmatrix4x4.html#perspective)（ ） 。

```
QMatrix4x4.perspective (self, float angle, float aspect, float nearPlane, float farPlane)
```

乘以这个矩阵由其他适用的透视投影。视场会_angle_具有给定范围内的一个窗口度_aspect_比。凸起将具有指定的_nearPlane_和_farPlane_剪切平面。

**See also** [ortho](qmatrix4x4.html#ortho)（）和[frustum](qmatrix4x4.html#frustum)（ ） 。

```
QMatrix4x4.rotate (self, float angle, QVector3D vector)
```

另一个通过旋转坐标的倍数这个矩阵_angle_关于度_vector_。

**See also** [scale](qmatrix4x4.html#scale)（）和[translate](qmatrix4x4.html#translate)（ ） 。

```
QMatrix4x4.rotate (self, float angle, float x, float y, float z = 0)
```

倍数这个矩阵由另一个根据指定旋转坐标_quaternion_。该_quaternion_假定已经被标准化。

**See also** [scale](qmatrix4x4.html#scale)（ ）[translate](qmatrix4x4.html#translate)（）和[QQuaternion](qquaternion.html)。

```
QMatrix4x4.rotate (self, QQuaternion quaternion)
```

这是一个重载函数。

另一个通过旋转坐标相乘这个矩阵_angle_关于向量（度_x_，_y_，_z_） 。

**See also** [scale](qmatrix4x4.html#scale)（）和[translate](qmatrix4x4.html#translate)（ ） 。

```
QVector4D QMatrix4x4.row (self, int index)
```

[

返回行的元素_index_为4D向量。

](qvector4d.html)

[**See also**](qvector4d.html) [setRow](qmatrix4x4.html#setRow)（）和[column](qmatrix4x4.html#column)（ ） 。

```
QMatrix4x4.scale (self, QVector3D vector)
```

通过另一种由组分鳞坐标乘以该矩阵_vector_。

**See also** [translate](qmatrix4x4.html#translate)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.scale (self, float x, float y)
```

这是一个重载函数。

另一个是由该组件缩放坐标乘以这个矩阵_x_和_y_。

**See also** [translate](qmatrix4x4.html#translate)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.scale (self, float x, float y, float z)
```

这是一个重载函数。

另一个是由该组件缩放坐标乘以这个矩阵_x_，_y_和_z_。

**See also** [translate](qmatrix4x4.html#translate)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.scale (self, float factor)
```

这是一个重载函数。

通过另一种由给定的缩放坐标乘以该矩阵_factor_。

**See also** [translate](qmatrix4x4.html#translate)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.setColumn (self, int index, QVector4D value)
```

设置列的元素_index_向的分量_value_。

**See also** [column](qmatrix4x4.html#column)（）和[setRow](qmatrix4x4.html#setRow)（ ） 。

```
QMatrix4x4.setRow (self, int index, QVector4D value)
```

设置行的元素_index_向的分量_value_。

**See also** [row](qmatrix4x4.html#row)（）和[setColumn](qmatrix4x4.html#setColumn)（ ） 。

```
QMatrix4x4.setToIdentity (self)
```

设置此矩阵的身份。

**See also** [isIdentity](qmatrix4x4.html#isIdentity)（ ） 。

```
QMatrix QMatrix4x4.toAffine (self)
```

[

返回对应于该矩阵的传统Qt的2D仿射变换矩阵。据推测，此矩阵只包含2D仿射变换的元素。

](qmatrix.html)

[**See also**](qmatrix.html) [toTransform](qmatrix4x4.html#toTransform)（ ） 。

```
QTransform QMatrix4x4.toTransform (self)
```

[

返回对应于该矩阵的传统Qt的2D变换矩阵。

](qtransform.html)

[返回](qtransform.html)[QTransform](qtransform.html)是通过简单地去掉了第三行和第三列中形成[QMatrix4x4](qmatrix4x4.html)。这是适合于实施正投影其中的Z坐标应该被丢弃，而不是预测。

**See also** [toAffine](qmatrix4x4.html#toAffine)（ ） 。

```
QTransform QMatrix4x4.toTransform (self, float distanceToPlane)
```

[

返回对应于该矩阵的传统Qt的2D变换矩阵。

](qtransform.html)

[If _distanceToPlane_为非零，则表示投影因子使用调整为在z坐标。 1024的值对应于所使用的投影系数](qtransform.html)[QTransform.rotate](qtransform.html#rotate)（）的x和y轴。

If _distanceToPlane_是零，则返回[QTransform](qtransform.html)是通过简单地去掉了第三行和第三列中形成[QMatrix4x4](qmatrix4x4.html)。这是适合于实施正投影其中的Z坐标应该被丢弃，而不是预测。

**See also** [toAffine](qmatrix4x4.html#toAffine)（ ） 。

```
QMatrix4x4.translate (self, QVector3D vector)
```

通过另一种由组分转化坐标乘以该矩阵_vector_。

**See also** [scale](qmatrix4x4.html#scale)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.translate (self, float x, float y)
```

这是一个重载函数。

另一个是由该组件转换坐标乘以这个矩阵_x_和_y_。

**See also** [scale](qmatrix4x4.html#scale)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4.translate (self, float x, float y, float z)
```

这是一个重载函数。

另一个是由该组件转换坐标乘以这个矩阵_x_，_y_和_z_。

**See also** [scale](qmatrix4x4.html#scale)（）和[rotate](qmatrix4x4.html#rotate)（ ） 。

```
QMatrix4x4 QMatrix4x4.transposed (self)
```

[

返回此矩阵，换位关于它的对角线。

](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__add__ (self, QMatrix4x4 m2)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__div__ (self, float divisor)
```

[

```
bool QMatrix4x4.__eq__ (self, QMatrix4x4 other)
```

```
object QMatrix4x4.__getitem__ (self, object)
```

](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__iadd__ (self, QMatrix4x4 other)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__idiv__ (self, float divisor)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__imul__ (self, QMatrix4x4 other)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__imul__ (self, float factor)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__isub__ (self, QMatrix4x4 other)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__mul__ (self, QMatrix4x4 m2)
```

[](qmatrix4x4.html)

```
QVector3D QMatrix4x4.__mul__ (self, QVector3D vector)
```

[](qvector3d.html)

```
QVector4D QMatrix4x4.__mul__ (self, QVector4D vector)
```

[](qvector4d.html)

```
QPoint QMatrix4x4.__mul__ (self, QPoint point)
```

[](qpoint.html)

```
QPointF QMatrix4x4.__mul__ (self, QPointF point)
```

[](qpointf.html)

```
QMatrix4x4 QMatrix4x4.__mul__ (self, QMatrix4x4 matrix)
```

[](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__mul__ (self, float factor)
```

[

```
bool QMatrix4x4.__ne__ (self, QMatrix4x4 other)
```

](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__neg__ (self)
```

[

```
str QMatrix4x4.__repr__ (self)
```

```
QMatrix4x4.__setitem__ (self, object, float)
```

](qmatrix4x4.html)

```
QMatrix4x4 QMatrix4x4.__sub__ (self, QMatrix4x4 m2)
```

[](qmatrix4x4.html)