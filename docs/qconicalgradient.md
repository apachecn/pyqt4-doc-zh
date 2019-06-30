# QConicalGradient Class Reference

## [[QtGui](index.htm) module]

该QConicalGradient类是用来与组合[QBrush](qbrush.html)指定一个锥形渐变画笔。[More...](#details)

继承[QGradient](qgradient.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPointF center, float startAngle)`
*   `__init__ (self, float cx, float cy, float startAngle)`
*   `__init__ (self, QConicalGradient)`
*   `float angle (self)`
*   `QPointF center (self)`
*   `setAngle (self, float angle)`
*   `setCenter (self, QPointF center)`
*   `setCenter (self, float x, float y)`

* * *

## Detailed Description

该QConicalGradient类是用来与组合[QBrush](qbrush.html)指定一个锥形渐变画笔。

锥形渐变插值围绕中心点插值颜色逆时针旋转。

![](../img/qconicalgradient.png)

在渐变中的颜色使用的停止点定义[QGradientStop](qgradient.html#QGradientStop-typedef)输入时，即位置和颜色。使用[QGradient.setColorAt](qgradient.html#setColorAt)（）或[QGradient.setStops](qgradient.html#setStops)（）函数定义的停止点。它是渐变的一整套停止点，描述如何渐变区域应填补。如果已指定没有停止点，黑色在0到白在1梯度使用。

除了从继承的功能[QGradient](qgradient.html)，该QConicalGradient类提供了[angle](qconicalgradient.html#angle)（）和[center](qconicalgradient.html#center)（ ）函数返回渐变的起始角度和中心。

注意，这个[setSpread](qgradient.html#setSpread)（）函数具有锥形梯度没有影响。其原因是，在锥形梯度通过定义封闭的，即圆锥渐变填充从0整个圆 - 360度，而径向或线性梯度的边界可以通过它的半径或最终停止点，分别被指定。

* * *

## Method Documentation

```
QConicalGradient.__init__ (self)
```

构造一个带有圆锥形中心（ 0 ， 0 ）开始的插补角度0 。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（ ）[setCenter](qconicalgradient.html#setCenter)（）和[setAngle](qconicalgradient.html#setAngle)（ ） 。

```
QConicalGradient.__init__ (self, QPointF center, float startAngle)
```

构造一个锥形渐变与给定_center_，在开始内插在给定的_angle_。该_angle_必须以度为0和360之间进行指定。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QConicalGradient.__init__ (self, float cx, float cy, float startAngle)
```

构造一个锥形渐变与给定中心（_cx_，_cy_），从内插在给定的_angle_。角度必须以度为0和360之间进行指定。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QConicalGradient.__init__ (self, QConicalGradient)
```

```
float QConicalGradient.angle (self)
```

返回锥形梯度逻辑坐标的起始角度。

**See also** [setAngle](qconicalgradient.html#setAngle)（）和[stops](qgradient.html#stops)（ ） 。

```
QPointF QConicalGradient.center (self)
```

[

返回锥形渐变的逻辑坐标的中心。

](qpointf.html)

[**See also**](qpointf.html) [setCenter](qconicalgradient.html#setCenter)（）和[stops](qgradient.html#stops)（ ） 。

```
QConicalGradient.setAngle (self, float angle)
```

Sets _angle_作此锥形梯度逻辑坐标的起始角度。

这个函数中引入了Qt 4.2中。

**See also** [angle](qconicalgradient.html#angle)（ ） 。

```
QConicalGradient.setCenter (self, QPointF center)
```

设置此锥形渐变的逻辑坐标的中心，_center_。

**See also** [center](qconicalgradient.html#center)（ ） 。

```
QConicalGradient.setCenter (self, float x, float y)
```

这是一个重载函数。

设置此锥形渐变的逻辑坐标的中心（_x_，_y_） 。

**See also** [center](qconicalgradient.html#center)（ ） 。