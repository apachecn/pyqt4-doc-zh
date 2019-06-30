# QLinearGradient Class Reference

## [[QtGui](index.htm) module]

该QLinearGradient类是用来与组合[QBrush](qbrush.html)指定一个线性渐变画笔。[More...](#details)

继承[QGradient](qgradient.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPointF start, QPointF finalStop)`
*   `__init__ (self, float xStart, float yStart, float xFinalStop, float yFinalStop)`
*   `__init__ (self, QLinearGradient)`
*   `QPointF finalStop (self)`
*   `setFinalStop (self, QPointF stop)`
*   `setFinalStop (self, float x, float y)`
*   `setStart (self, QPointF start)`
*   `setStart (self, float x, float y)`
*   `QPointF start (self)`

* * *

## Detailed Description

该QLinearGradient类是用来与组合[QBrush](qbrush.html)指定一个线性渐变画笔。

线性渐变起始点和结束点之间进行插值的色彩。外面这些点的梯度可以是填充，反射或重复这取决于当前设置的[spread](qgradient.html#Spread-enum)方法：

| ![](../img/qlineargradient-pad.png) | ![](../img/qlineargradient-reflect.png) | ![](../img/qlineargradient-repeat.png) |
| [PadSpread](qgradient.html#Spread-enum) (default) | [ReflectSpread](qgradient.html#Spread-enum) | [RepeatSpread](qgradient.html#Spread-enum) |

在渐变中的颜色使用的停止点定义[QGradientStop](qgradient.html#QGradientStop-typedef)输入时，即位置和颜色。使用[QGradient.setColorAt](qgradient.html#setColorAt)（）或[QGradient.setStops](qgradient.html#setStops)（）函数定义的停止点。它是渐变的一整套停止点，描述如何渐变区域应填补。如果已指定没有停止点，黑色在0到白在1梯度使用。

除了从继承的功能[QGradient](qgradient.html)，该QLinearGradient类提供了[finalStop](qlineargradient.html#finalStop)（ ）函数返回渐变的最后一站一点，和[start](qlineargradient.html#start)（ ）函数返回渐变的起点。

* * *

## Method Documentation

```
QLinearGradient.__init__ (self)
```

构造之间具有内插区域的默认线性梯度（0，0 ）和（1 ，1）。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（ ）[setStart](qlineargradient.html#setStart)（）和[setFinalStop](qlineargradient.html#setFinalStop)（ ） 。

```
QLinearGradient.__init__ (self, QPointF start, QPointF finalStop)
```

构造给定之间的插值区域的线性渐变_start_点_finalStop_。

**Note:**预期的参数值以像素为单位。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QLinearGradient.__init__ (self, float xStart, float yStart, float xFinalStop, float yFinalStop)
```

构造之间的插值区域的线性渐变（_x1_，_y1_）和（_x2_，_y2_） 。

**Note:**预期的参数值以像素为单位。

**See also** [QGradient.setColorAt](qgradient.html#setColorAt)（）和[QGradient.setStops](qgradient.html#setStops)（ ） 。

```
QLinearGradient.__init__ (self, QLinearGradient)
```

```
QPointF QLinearGradient.finalStop (self)
```

[

返回此逻辑坐标线性渐变的最后一站一点。

](qpointf.html)

[**See also**](qpointf.html) [setFinalStop](qlineargradient.html#setFinalStop)（）和[QGradient.stops](qgradient.html#stops)（ ） 。

```
QLinearGradient.setFinalStop (self, QPointF stop)
```

设置此逻辑坐标线性渐变的最后一站，以点_stop_。

这个函数中引入了Qt 4.2中。

**See also** [finalStop](qlineargradient.html#finalStop)（ ） 。

```
QLinearGradient.setFinalStop (self, float x, float y)
```

这是一个重载函数。

设置此逻辑坐标线性渐变的最后一站，以点_x_，_y_。

这个函数中引入了Qt 4.2中。

**See also** [start](qlineargradient.html#start)（ ） 。

```
QLinearGradient.setStart (self, QPointF start)
```

设置此逻辑坐标线性渐变的起点_start_。

这个函数中引入了Qt 4.2中。

**See also** [start](qlineargradient.html#start)（ ） 。

```
QLinearGradient.setStart (self, float x, float y)
```

这是一个重载函数。

设置此逻辑坐标线性渐变的起点_x_，_y_。

这个函数中引入了Qt 4.2中。

**See also** [start](qlineargradient.html#start)（ ） 。

```
QPointF QLinearGradient.start (self)
```

[

返回此逻辑坐标的线性渐变的起点。

](qpointf.html)

[**See also**](qpointf.html) [setStart](qlineargradient.html#setStart)（）和[QGradient.stops](qgradient.html#stops)（ ） 。