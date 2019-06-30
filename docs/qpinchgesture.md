# QPinchGesture Class Reference

## [[QtGui](index.htm) module]

该QPinchGesture类描述的捏合姿态由用户进行。[More...](#details)

继承[QGesture](qgesture.html)。

### Types

*   `enum ChangeFlag { ScaleFactorChanged, RotationAngleChanged, CenterPointChanged }`
*   `class **[ChangeFlags](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QPointF centerPoint (self)`
*   `ChangeFlags changeFlags (self)`
*   `QPointF lastCenterPoint (self)`
*   `float lastRotationAngle (self)`
*   `float lastScaleFactor (self)`
*   `float rotationAngle (self)`
*   `float scaleFactor (self)`
*   `setCenterPoint (self, QPointF value)`
*   `setChangeFlags (self, ChangeFlags value)`
*   `setLastCenterPoint (self, QPointF value)`
*   `setLastRotationAngle (self, float value)`
*   `setLastScaleFactor (self, float value)`
*   `setRotationAngle (self, float value)`
*   `setScaleFactor (self, float value)`
*   `setStartCenterPoint (self, QPointF value)`
*   `setTotalChangeFlags (self, ChangeFlags value)`
*   `setTotalRotationAngle (self, float value)`
*   `setTotalScaleFactor (self, float value)`
*   `QPointF startCenterPoint (self)`
*   `ChangeFlags totalChangeFlags (self)`
*   `float totalRotationAngle (self)`
*   `float totalScaleFactor (self)`

* * *

## Detailed Description

该QPinchGesture类描述的捏合姿态由用户进行。

甲捏合姿态是触摸的用户输入的形式，其中用户通常触摸两个点用拇指和手指的输入装置上，移动它们靠近在一起或进一步分开来改变缩放因子，缩放或细节的水平前用户界面。

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

![](../img/pinchgesture.png)

而不是反复应用相同的捏手势，用户可以继续触摸输入装置在一处，并应用第二触摸到一个新的点，持续手势。当这种情况发生时，手势事件将继续被传递到目标对象，包含在QPinchGesture的一个实例[Qt.GestureUpdated](qt.html#GestureState-enum)状态。

* * *

## Type Documentation

```
QPinchGesture.ChangeFlag
```

这个枚举说明可能发生的手势对象的属性的更改。

| Constant | Value | Description |
| --- | --- | --- |
| `QPinchGesture.ScaleFactorChanged` | `0x1` | 持有的比例因子[scaleFactor](qpinchgesture.html#scaleFactor-prop)改变。 |
| `QPinchGesture.RotationAngleChanged` | `0x2` | 持有的旋转角度[rotationAngle](qpinchgesture.html#rotationAngle-prop)改变。 |
| `QPinchGesture.CenterPointChanged` | `0x4` | 持有的中心点[centerPoint](qpinchgesture.html#centerPoint-prop)改变。 |

该ChangeFlags类型是一个typedef为[QFlags](index.htm)\u003cChangeFlag\u003e 。它存储ChangeFlag值的或组合。

**See also** [changeFlags](qpinchgesture.html#changeFlags-prop)和[totalChangeFlags](qpinchgesture.html#totalChangeFlags-prop)。

* * *

## Method Documentation

```
QPinchGesture.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QPointF QPinchGesture.centerPoint (self)
```

[](qpointf.html)

```
ChangeFlags QPinchGesture.changeFlags (self)
```

[](index.htm)

```
QPointF QPinchGesture.lastCenterPoint (self)
```

[

```
float QPinchGesture.lastRotationAngle (self)
```

```
float QPinchGesture.lastScaleFactor (self)
```

```
float QPinchGesture.rotationAngle (self)
```

```
float QPinchGesture.scaleFactor (self)
```

```
QPinchGesture.setCenterPoint (self, QPointF value)
```

```
QPinchGesture.setChangeFlags (self, ChangeFlags value)
```

```
QPinchGesture.setLastCenterPoint (self, QPointF value)
```

```
QPinchGesture.setLastRotationAngle (self, float value)
```

```
QPinchGesture.setLastScaleFactor (self, float value)
```

```
QPinchGesture.setRotationAngle (self, float value)
```

```
QPinchGesture.setScaleFactor (self, float value)
```

```
QPinchGesture.setStartCenterPoint (self, QPointF value)
```

```
QPinchGesture.setTotalChangeFlags (self, ChangeFlags value)
```

```
QPinchGesture.setTotalRotationAngle (self, float value)
```

```
QPinchGesture.setTotalScaleFactor (self, float value)
```

](qpointf.html)

```
QPointF QPinchGesture.startCenterPoint (self)
```

[](qpointf.html)

```
ChangeFlags QPinchGesture.totalChangeFlags (self)
```

[

```
float QPinchGesture.totalRotationAngle (self)
```

```
float QPinchGesture.totalScaleFactor (self)
```

](index.htm)