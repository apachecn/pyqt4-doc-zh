# QGraphicsScale Class Reference

## [[QtGui](index.htm) module]

该QGraphicsScale类提供了一个尺度变换。[More...](#details)

继承[QGraphicsTransform](qgraphicstransform.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `applyTo (self, QMatrix4x4 matrix)`
*   `QVector3D origin (self)`
*   `setOrigin (self, QVector3D point)`
*   `setXScale (self, float)`
*   `setYScale (self, float)`
*   `setZScale (self, float)`
*   `float xScale (self)`
*   `float yScale (self)`
*   `float zScale (self)`

### Qt Signals

*   `void originChanged ()`
*   `void scaleChanged ()`
*   `void xScaleChanged ()`
*   `void yScaleChanged ()`
*   `void zScaleChanged ()`

* * *

## Detailed Description

该QGraphicsScale类提供了一个尺度变换。

[QGraphicsScene](qgraphicsscene.html)提供某些参数，以帮助控制规模应适用。

原产地是，该项目是由（即，它保持相对固定的母公司作为该项目的其馀部分的增长）缩放点。默认情况下，原点是[QPointF](qpointf.html)（0 ，0）。

参数[xScale](qgraphicsscale.html#xScale-prop)，[yScale](qgraphicsscale.html#yScale-prop)和[zScale](qgraphicsscale.html#zScale-prop)描述比例因子在水平，垂直和深度方向上适用。它们可以取任何值，包括0（对产品折叠到一个点）或负值。负[xScale](qgraphicsscale.html#xScale-prop)值水平反映的项目。负[yScale](qgraphicsscale.html#yScale-prop)值将垂直翻转的项目。负[zScale](qgraphicsscale.html#zScale-prop)将翻转的项目年底结束。

* * *

## Method Documentation

```
QGraphicsScale.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QGraphicsScale](qgraphicsscale.html)与给定对象_parent_。

```
QGraphicsScale.applyTo (self, QMatrix4x4 matrix)
```

从重新实现[QGraphicsTransform.applyTo](qgraphicstransform.html#applyTo)（ ） 。

```
QVector3D QGraphicsScale.origin (self)
```

[

```
QGraphicsScale.setOrigin (self, QVector3D point)
```

```
QGraphicsScale.setXScale (self, float)
```

```
QGraphicsScale.setYScale (self, float)
```

```
QGraphicsScale.setZScale (self, float)
```

```
float QGraphicsScale.xScale (self)
```

```
float QGraphicsScale.yScale (self)
```

```
float QGraphicsScale.zScale (self)
```

* * *

## Qt Signal Documentation

```
void originChanged ()
```

这是该信号的默认超载。

](qvector3d.html)

[](qvector3d.html)[QGraphicsScale](qgraphicsscale.html)发出这个信号时，其原产地的变化。

**See also** [QGraphicsScale.origin](qgraphicsscale.html#origin-prop)。

```
void scaleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的[xScale](qgraphicsscale.html#xScale-prop)，[yScale](qgraphicsscale.html#yScale-prop)或[zScale](qgraphicsscale.html#zScale-prop)对象的变化。

**See also** [QGraphicsScale.xScale](qgraphicsscale.html#xScale-prop)，[QGraphicsScale.yScale](qgraphicsscale.html#yScale-prop)和[QGraphicsScale.zScale](qgraphicsscale.html#zScale-prop)。

```
void xScaleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的[xScale](qgraphicsscale.html#xScale-prop)属性更改。

此功能被引入Qt的4.7 。

```
void yScaleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的[yScale](qgraphicsscale.html#yScale-prop)属性更改。

此功能被引入Qt的4.7 。

```
void zScaleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的[zScale](qgraphicsscale.html#zScale-prop)属性更改。

此功能被引入Qt的4.7 。