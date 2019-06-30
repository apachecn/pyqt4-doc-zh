# QRadialGradient Class Reference

## [[QtGui](index.htm) module]

该QRadialGradient类是用来与组合[QBrush](qbrush.html)指定一个径向渐变画笔。[More...](#details)

继承[QGradient](qgradient.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPointF center, float radius, QPointF focalPoint)`
*   `__init__ (self, QPointF center, float centerRadius, QPointF focalPoint, float focalRadius)`
*   `__init__ (self, QPointF center, float radius)`
*   `__init__ (self, float cx, float cy, float radius, float fx, float fy)`
*   `__init__ (self, float cx, float cy, float centerRadius, float fx, float fy, float focalRadius)`
*   `__init__ (self, float cx, float cy, float radius)`
*   `__init__ (self, QRadialGradient)`
*   `QPointF center (self)`
*   `float centerRadius (self)`
*   `QPointF focalPoint (self)`
*   `float focalRadius (self)`
*   `float radius (self)`
*   `setCenter (self, QPointF center)`
*   `setCenter (self, float x, float y)`
*   `setCenterRadius (self, float radius)`
*   `setFocalPoint (self, QPointF focalPoint)`
*   `setFocalPoint (self, float x, float y)`
*   `setFocalRadius (self, float radius)`
*   `setRadius (self, float radius)`

* * *

## Detailed Description

该QRadialGradient类是用来与组合[QBrush](qbrush.html)指定一个径向渐变画笔。

Qt支持简单的和扩展的径向渐变。

简单的径向渐变在它周围一个圆圈一个联络点和结束点之间进行插值的色彩。扩展的径向渐变的焦点圆和圆心之间进行插值的色彩。点由两个圆限定的锥形外面将是透明的。对于简单的径向渐变的焦点调整到趴在中心圆内，而焦点可以在一个扩展的径向渐变的任何位置。

外底点的梯度可以是填充，反射或重复这取决于当前设置的[spread](qgradient.html#Spread-enum)方法：

| ![](../img/qradialgradient-pad.png) | ![](../img/qradialgradient-reflect.png) | ![](../img/qradialgradient-repeat.png) |
| [PadSpread](qgradient.html#Spread-enum) (default) | [ReflectSpread](qgradient.html#Spread-enum) | [RepeatSpread](qgradient.html#Spread-enum) |

在渐变中的颜色使用的停止点定义[QGradientStop](qgradient.html#QGradientStop-typedef)输入时，即位置和颜色。使用[QGradient.setColorAt](qgradient.html#setColorAt)（）或[QGradient.setStops](qgradient.html#setStops)（）函数定义的停止点。它是渐变的一整套停止点，描述如何渐变区域应填补。如果已指定没有停止点，黑色在0到白在1梯度使用。

除了从继承的功能[QGradient](qgradient.html)，该QRadialGradient类提供了[center](qradialgradient.html#center)（ ）[focalPoint](qradialgradient.html#focalPoint)（）和[radius](qradialgradient.html#radius)（ ）函数分别返回渐变的中心，焦点和半径。

* * *

## Method Documentation

```
QRadialGradient.__init__ (self)
```

构造一个简单的径向渐变的中心和焦点在（ 0 ， 0 ）为1的半径。

```
QRadialGradient.__init__ (self, QPointF center, float radius, QPointF focalPoint)
```

构造一个简单的径向渐变与给定_center_，_radius_和_focalPoint_。

**Note:**如果给定的焦点是由确定的圆形外_center_点_radius_，它会被重新调整到趴在圆上的一个点，它与线相交的_center_至_focalPoint_。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QRadialGradient.__init__ (self, QPointF center, float centerRadius, QPointF focalPoint, float focalRadius)
```

构造具有给定中心的一个简单的径向渐变（_cx_，_cy_） ，_radius_和焦点（_fx_，_fy_） 。

**Note:**如果给定的焦点是由该中心确定的圆（外_cx_，_cy_）和_radius_它会被重新调整到线从中心到焦点和圆之间的交点。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QRadialGradient.__init__ (self, QPointF center, float radius)
```

构造一个简单的径向渐变与给定_center_，_radius_而在圆心的焦点。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QRadialGradient.__init__ (self, float cx, float cy, float radius, float fx, float fy)
```

构建与中心简单的径向渐变在（_cx_，_cy_性）和指定_radius_。的聚焦点位于该圆的中心。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QRadialGradient.__init__ (self, float cx, float cy, float centerRadius, float fx, float fy, float focalRadius)
```

构造一个扩展的径向渐变与给定_center_，_centerRadius_，_focalPoint_和_focalRadius_。

此功能被引入Qt的4.8 。

```
QRadialGradient.__init__ (self, float cx, float cy, float radius)
```

构造一个扩展的径向渐变与给定中心（_cx_，_cy_） ，中心半径，_centerRadius_，焦点， （_fx_，_fy_） ，和焦半径_focalRadius_。

此功能被引入Qt的4.8 。

```
QRadialGradient.__init__ (self, QRadialGradient)
```

```
QPointF QRadialGradient.center (self)
```

[

返回此径向渐变的逻辑坐标的中心。

](qpointf.html)

[**See also**](qpointf.html) [setCenter](qradialgradient.html#setCenter)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
float QRadialGradient.centerRadius (self)
```

返回逻辑坐标此径向渐变的中心半径。

此功能被引入Qt的4.8 。

**See also** [setCenterRadius](qradialgradient.html#setCenterRadius)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
QPointF QRadialGradient.focalPoint (self)
```

[

返回逻辑坐标此径向渐变的焦点。

](qpointf.html)

[**See also**](qpointf.html) [setFocalPoint](qradialgradient.html#setFocalPoint)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
float QRadialGradient.focalRadius (self)
```

返回逻辑坐标此径向渐变的焦点半径。

此功能被引入Qt的4.8 。

**See also** [setFocalRadius](qradialgradient.html#setFocalRadius)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
float QRadialGradient.radius (self)
```

返回逻辑坐标此径向渐变的半径。

相当于[centerRadius](qradialgradient.html#centerRadius)（ ）

**See also** [setRadius](qradialgradient.html#setRadius)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
QRadialGradient.setCenter (self, QPointF center)
```

这个设置径向渐变的逻辑坐标的中心，_center_。

这个函数中引入了Qt 4.2中。

**See also** [center](qradialgradient.html#center)（ ） 。

```
QRadialGradient.setCenter (self, float x, float y)
```

这是一个重载函数。

这个设置径向渐变的逻辑坐标的中心（_x_，_y_） 。

这个函数中引入了Qt 4.2中。

**See also** [center](qradialgradient.html#center)（ ） 。

```
QRadialGradient.setCenterRadius (self, float radius)
```

设置在逻辑坐标此径向渐变的中心半径_radius_

此功能被引入Qt的4.8 。

**See also** [centerRadius](qradialgradient.html#centerRadius)（ ） 。

```
QRadialGradient.setFocalPoint (self, QPointF focalPoint)
```

设置在逻辑坐标此径向渐变的焦点，以_focalPoint_。

这个函数中引入了Qt 4.2中。

**See also** [focalPoint](qradialgradient.html#focalPoint)（ ） 。

```
QRadialGradient.setFocalPoint (self, float x, float y)
```

这是一个重载函数。

设置在逻辑坐标此径向渐变的焦点为（_x_，_y_） 。

这个函数中引入了Qt 4.2中。

**See also** [focalPoint](qradialgradient.html#focalPoint)（ ） 。

```
QRadialGradient.setFocalRadius (self, float radius)
```

设置在逻辑坐标此径向渐变的焦点半径_radius_

此功能被引入Qt的4.8 。

**See also** [focalRadius](qradialgradient.html#focalRadius)（ ） 。

```
QRadialGradient.setRadius (self, float radius)
```

设置在逻辑坐标此径向渐变的半径_radius_

相当于[setCenterRadius](qradialgradient.html#setCenterRadius)（ ）

这个函数中引入了Qt 4.2中。

**See also** [radius](qradialgradient.html#radius)（ ） 。