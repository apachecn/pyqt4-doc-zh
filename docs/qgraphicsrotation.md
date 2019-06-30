# QGraphicsRotation Class Reference

## [[QtGui](index.htm) module]

该QGraphicsRotation类提供围绕给定轴的旋转变换。[More...](#details)

继承[QGraphicsTransform](qgraphicstransform.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `float angle (self)`
*   `applyTo (self, QMatrix4x4 matrix)`
*   `QVector3D axis (self)`
*   `QVector3D origin (self)`
*   `setAngle (self, float)`
*   `setAxis (self, QVector3D axis)`
*   `setAxis (self, Qt.Axis axis)`
*   `setOrigin (self, QVector3D point)`

### Qt Signals

*   `void angleChanged ()`
*   `void axisChanged ()`
*   `void originChanged ()`

* * *

## Detailed Description

该QGraphicsRotation类提供围绕给定轴的旋转变换。

您可以通过分配提供所需的轴[QVector3D](qvector3d.html)该轴属性或者通过一个成员，如果[Qt.Axis](qt.html#Axis-enum)到setAxis方便的功能。默认情况下，该轴为（0 ，0，1 ），即，围绕Z轴旋转。

角特性，这是由QGraphicsRotation提供，现在描述了围绕该轴旋转的度数。

QGraphicsRotation提供某些参数，以帮助控制如何旋转应该被应用。

原点是该项目围绕其旋转（即，它保持固定的相对于父作为产品的其馀部分被转动）的位置。默认情况下，原点是[QPointF](qpointf.html)（0 ，0）。

角属性提供的度数为围绕原点的项目按顺时针方向旋转。该值也可以是负的，表示逆时针旋转。对于动画的目的，也可能是有用的，以提供旋转角度超过（ -360 ， 360 ）度，例如以动画如何项目旋转几次。

注意：最后一次旋转是在三维空间中的旋转后投影回2D的综合效应。如果几个旋转是连续进行的，他们不会像预期的那样，除非他们都绕Z轴。

* * *

## Method Documentation

```
QGraphicsRotation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGraphicsRotation](qgraphicsrotation.html)用给定的_parent_。

```
float QGraphicsRotation.angle (self)
```

```
QGraphicsRotation.applyTo (self, QMatrix4x4 matrix)
```

从重新实现[QGraphicsTransform.applyTo](qgraphicstransform.html#applyTo)（ ） 。

```
QVector3D QGraphicsRotation.axis (self)
```

[](qvector3d.html)

```
QVector3D QGraphicsRotation.origin (self)
```

[

```
QGraphicsRotation.setAngle (self, float)
```

```
QGraphicsRotation.setAxis (self, QVector3D axis)
```

```
QGraphicsRotation.setAxis (self, Qt.Axis axis)
```

```
QGraphicsRotation.setOrigin (self, QVector3D point)
```

* * *

## Qt Signal Documentation

```
void angleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的角度发生了变化。

](qvector3d.html)

[**See also**](qvector3d.html) [QGraphicsRotation.angle](qgraphicsrotation.html#angle-prop)。

```
void axisChanged ()
```

这是该信号的默认超载。

这个信号被发射时的对象更改轴。

**See also** [QGraphicsRotation.axis](qgraphicsrotation.html#axis-prop)。

```
void originChanged ()
```

这是该信号的默认超载。

这个信号被发射时的原点已经改变。

**See also** [QGraphicsRotation.origin](qgraphicsrotation.html#origin-prop)。