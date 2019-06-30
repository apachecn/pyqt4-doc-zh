# QQuaternion Class Reference

## [[QtGui](index.htm) module]

该QQuaternion类表示一个四元数组成的向量和标量的。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, float aScalar, float xpos, float ypos, float zpos)`
*   `__init__ (self, float aScalar, QVector3D aVector)`
*   `__init__ (self, QVector4D aVector)`
*   `__init__ (self, QQuaternion)`
*   `QQuaternion conjugate (self)`
*   `bool isIdentity (self)`
*   `bool isNull (self)`
*   `float length (self)`
*   `float lengthSquared (self)`
*   `normalize (self)`
*   `QQuaternion normalized (self)`
*   `QVector3D rotatedVector (self, QVector3D vector)`
*   `float scalar (self)`
*   `setScalar (self, float aScalar)`
*   `setVector (self, QVector3D aVector)`
*   `setVector (self, float aX, float aY, float aZ)`
*   `setX (self, float aX)`
*   `setY (self, float aY)`
*   `setZ (self, float aZ)`
*   `QVector4D toVector4D (self)`
*   `QVector3D vector (self)`
*   `float x (self)`
*   `float y (self)`
*   `float z (self)`

### Static Methods

*   `QQuaternion fromAxisAndAngle (QVector3D axis, float angle)`
*   `QQuaternion fromAxisAndAngle (float x, float y, float z, float angle)`
*   `QQuaternion nlerp (QQuaternion q1, QQuaternion q2, float t)`
*   `QQuaternion slerp (QQuaternion q1, QQuaternion q2, float t)`

### Special Methods

*   `QQuaternion __add__ (self, QQuaternion q2)`
*   `QQuaternion __div__ (self, float divisor)`
*   `bool __eq__ (self, QQuaternion q2)`
*   `QQuaternion __iadd__ (self, QQuaternion quaternion)`
*   `QQuaternion __idiv__ (self, float divisor)`
*   `QQuaternion __imul__ (self, float factor)`
*   `QQuaternion __imul__ (self, QQuaternion quaternion)`
*   `QQuaternion __isub__ (self, QQuaternion quaternion)`
*   `QQuaternion __mul__ (self, QQuaternion q2)`
*   `QQuaternion __mul__ (self, QQuaternion quaternion)`
*   `QQuaternion __mul__ (self, float factor)`
*   `bool __ne__ (self, QQuaternion q2)`
*   `QQuaternion __neg__ (self)`
*   `str __repr__ (self)`
*   `QQuaternion __sub__ (self, QQuaternion q2)`

* * *

## Detailed Description

这个类可以醃制。

该QQuaternion类表示一个四元数组成的向量和标量的。

四元被用来表示在三维空间中旋转，并包括由x ， y和z坐标，以及表示旋转角度的标量指定一个三维旋转轴线。

* * *

## Method Documentation

```
QQuaternion.__init__ (self)
```

构造一个单位四元数，即坐标为（ 1 ，0，0 ，0）。

```
QQuaternion.__init__ (self, float aScalar, float xpos, float ypos, float zpos)
```

构造一个四元数与向量（_xpos_，_ypos_，_zpos_）和_scalar_。

```
QQuaternion.__init__ (self, float aScalar, QVector3D aVector)
```

构造一个四元数向量从指定的_vector_和_scalar_。

**See also** [vector](qquaternion.html#vector)（）和[scalar](qquaternion.html#scalar)（ ） 。

```
QQuaternion.__init__ (self, QVector4D aVector)
```

构造一个从四元数的组成部分_vector_。

```
QQuaternion.__init__ (self, QQuaternion)
```

```
QQuaternion QQuaternion.conjugate (self)
```

[

返回该四元数的共轭物，它是（ -X ， -Y，- Z，标量） 。

](qquaternion.html)

```
QQuaternion QQuaternion.fromAxisAndAngle (QVector3D axis, float angle)
```

[

创建对应于通过旋转归一化的四元数_angle_有关指定三维度_axis_。

](qquaternion.html)

```
QQuaternion QQuaternion.fromAxisAndAngle (float x, float y, float z, float angle)
```

[

创建对应于通过旋转归一化的四元数_angle_关于3D轴（度_x_，_y_，_z_） 。

```
bool QQuaternion.isIdentity (self)
```

返回True如果这个四元数在x ，y和z分量都设置为0.0 ，而标量分量设置为1.0 ，否则返回False 。

```
bool QQuaternion.isNull (self)
```

返回True如果这个四元数在x，y ，z和标量分量都设置为0.0 ，否则返回False 。

```
float QQuaternion.length (self)
```

返回四元数的长度。这也被称为“规范” 。

](qquaternion.html)

[**See also**](qquaternion.html) [lengthSquared](qquaternion.html#lengthSquared)（）和[normalized](qquaternion.html#normalized)（ ） 。

```
float QQuaternion.lengthSquared (self)
```

返回四元数的平方长度。

**See also** [length](qquaternion.html#length)（ ） 。

```
QQuaternion QQuaternion.nlerp (QQuaternion q1, QQuaternion q2, float t)
```

[](qquaternion.html)

[沿着所述旋转位置之间的最短直线路径插值_q1_和_q2_。价值_t_应该介于0和1，表示的距离之间的旅行_q1_和_q2_。其结果将是](qquaternion.html)[normalized](qquaternion.html#normalized)（ ） 。

If _t_小于或等于0，则_q1_将被退回。如果_t_大于或等于1，则_q2_将被退回。

该nlerp （）函数是通常比快[slerp](qquaternion.html#slerp)（ ），将球形插，这对于某些应用足够好给近似的结果。

**See also** [slerp](qquaternion.html#slerp)（ ） 。

```
QQuaternion.normalize (self)
```

标准化到位确认当期的四元数。什么也没有发生，如果这是一个空四元或四元数的长度是非常接近1。

**See also** [length](qquaternion.html#length)（）和[normalized](qquaternion.html#normalized)（ ） 。

```
QQuaternion QQuaternion.normalized (self)
```

[

返回此四元数的归一化单元的形式。

如果这四元数为null，则空四元数返回。如果四元数的长度是非常接近于1 ，则该四元将被返回原样。否则，长度为1的四元数的归一化的形式将被退回。

](qquaternion.html)

[**See also**](qquaternion.html) [length](qquaternion.html#length)（）和[normalize](qquaternion.html#normalize)（ ） 。

```
QVector3D QQuaternion.rotatedVector (self, QVector3D vector)
```

[

旋转_vector_这个四元数来产生在三维空间的新载体。下面的代码：

```
 QVector3D result = q.rotatedVector(vector);

```

等效于以下内容：

](qvector3d.html)

```
 QVector3D result = (q *QQuaternion(0, vector) * q.conjugate()).vector();

```

```
float QQuaternion.scalar (self)
```

返回此四元数的标量分量。

**See also** [setScalar](qquaternion.html#setScalar)（ ）[x](qquaternion.html#x)（ ）[y](qquaternion.html#y)（）和[z](qquaternion.html#z)（ ） 。

```
QQuaternion.setScalar (self, float aScalar)
```

设置此四元数的标量分量_scalar_。

**See also** [scalar](qquaternion.html#scalar)（ ）[setX](qquaternion.html#setX)（ ）[setY](qquaternion.html#setY)（）和[setZ](qquaternion.html#setZ)（ ） 。

```
QQuaternion.setVector (self, QVector3D aVector)
```

设置此四元数的向量组件_vector_。

**See also** [vector](qquaternion.html#vector)（）和[setScalar](qquaternion.html#setScalar)（ ） 。

```
QQuaternion.setVector (self, float aX, float aY, float aZ)
```

设置此四元数的向量分量（_x_，_y_，_z_） 。

**See also** [vector](qquaternion.html#vector)（）和[setScalar](qquaternion.html#setScalar)（ ） 。

```
QQuaternion.setX (self, float aX)
```

设置此四元数的向量的x坐标给定的_x_协调。

**See also** [x](qquaternion.html#x)（ ）[setY](qquaternion.html#setY)（ ）[setZ](qquaternion.html#setZ)（）和[setScalar](qquaternion.html#setScalar)（ ） 。

```
QQuaternion.setY (self, float aY)
```

设置此四元数的向量的y坐标给定的_y_协调。

**See also** [y](qquaternion.html#y)（ ）[setX](qquaternion.html#setX)（ ）[setZ](qquaternion.html#setZ)（）和[setScalar](qquaternion.html#setScalar)（ ） 。

```
QQuaternion.setZ (self, float aZ)
```

设置此四元数的向量的z坐标给定的_z_协调。

**See also** [z](qquaternion.html#z)（ ）[setX](qquaternion.html#setX)（ ）[setY](qquaternion.html#setY)（）和[setScalar](qquaternion.html#setScalar)（ ） 。

```
QQuaternion QQuaternion.slerp (QQuaternion q1, QQuaternion q2, float t)
```

[

沿着所述旋转位置之间的最短路径球形插_q1_和_q2_。价值_t_应该介于0和1，表示球面距离之间旅行_q1_和_q2_。

If _t_小于或等于0，则_q1_将被退回。如果_t_大于或等于1，则_q2_将被退回。

](qquaternion.html)

[**See also**](qquaternion.html) [nlerp](qquaternion.html#nlerp)（ ） 。

```
QVector4D QQuaternion.toVector4D (self)
```

[

返回此四元数为4D向量。

](qvector4d.html)

```
QVector3D QQuaternion.vector (self)
```

[

返回此四元数的矢量分量。

](qvector3d.html)

[**See also**](qvector3d.html) [setVector](qquaternion.html#setVector)（）和[scalar](qquaternion.html#scalar)（ ） 。

```
float QQuaternion.x (self)
```

返回此四元数的向量的x坐标。

**See also** [setX](qquaternion.html#setX)（ ）[y](qquaternion.html#y)（ ）[z](qquaternion.html#z)（）和[scalar](qquaternion.html#scalar)（ ） 。

```
float QQuaternion.y (self)
```

返回此四元数的向量的y坐标。

**See also** [setY](qquaternion.html#setY)（ ）[x](qquaternion.html#x)（ ）[z](qquaternion.html#z)（）和[scalar](qquaternion.html#scalar)（ ） 。

```
float QQuaternion.z (self)
```

返回此四元数的向量的z坐标。

**See also** [setZ](qquaternion.html#setZ)（ ）[x](qquaternion.html#x)（ ）[y](qquaternion.html#y)（）和[scalar](qquaternion.html#scalar)（ ） 。

```
QQuaternion QQuaternion.__add__ (self, QQuaternion q2)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__div__ (self, float divisor)
```

[

```
bool QQuaternion.__eq__ (self, QQuaternion q2)
```

](qquaternion.html)

```
QQuaternion QQuaternion.__iadd__ (self, QQuaternion quaternion)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__idiv__ (self, float divisor)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__imul__ (self, float factor)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__imul__ (self, QQuaternion quaternion)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__isub__ (self, QQuaternion quaternion)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__mul__ (self, QQuaternion q2)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__mul__ (self, QQuaternion quaternion)
```

[](qquaternion.html)

```
QQuaternion QQuaternion.__mul__ (self, float factor)
```

[

```
bool QQuaternion.__ne__ (self, QQuaternion q2)
```

](qquaternion.html)

```
QQuaternion QQuaternion.__neg__ (self)
```

[

```
str QQuaternion.__repr__ (self)
```

](qquaternion.html)

```
QQuaternion QQuaternion.__sub__ (self, QQuaternion q2)
```

[](qquaternion.html)