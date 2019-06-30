# QGesture Class Reference

## [[QtGui](index.htm) module]

该QGesture类表示一种姿态，包含描述相应的用户输入的属性。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QPanGesture](qpangesture.html)，[QPinchGesture](qpinchgesture.html)，[QSwipeGesture](qswipegesture.html)，[QTapAndHoldGesture](qtapandholdgesture.html)和[QTapGesture](qtapgesture.html)。

### Types

*   `enum GestureCancelPolicy { CancelNone, CancelAllInContext }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `GestureCancelPolicy gestureCancelPolicy (self)`
*   `Qt.GestureType gestureType (self)`
*   `bool hasHotSpot (self)`
*   `QPointF hotSpot (self)`
*   `setGestureCancelPolicy (self, GestureCancelPolicy policy)`
*   `setHotSpot (self, QPointF value)`
*   `Qt.GestureState state (self)`
*   `unsetHotSpot (self)`

* * *

## Detailed Description

该QGesture类表示一种姿态，包含描述相应的用户输入的属性。

不直接由开发商建造的手势对象。它们被创建[QGestureRecognizer](qgesturerecognizer.html)对象已注册的应用程序，请参阅[QGestureRecognizer.registerRecognizer](qgesturerecognizer.html#registerRecognizer)（ ） 。

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

### Gesture Properties

类具有可以由用户进行查询，以获得一些手势的特定参数的属性的列表。例如，该捏合姿态具有被公开为一个属性的缩放因子。

自定义手势识别器开发人员可以以提供关于手势的附加信息添加额外的属性。这可以通过添加新的动态属性，以一个QGesture对象，或者通过继承QGesture类（或它的子类）来完成。

### Lifecycle of a Gesture Object

需要的，是通过Qt的拥有当A QGesture实例隐式创建。开发商不应该摧毁它们或将它们存储供以后使用的Qt的可能摧毁他们的特定实例，并创建新的来替换它们。

注册手势识别通过监视目标对象的输入事件的[recognize()](qgesturerecognizer.html#recognize)功能，根据需要更新所述手势的对象的属性。

所述手势的对象可以在被递送到目标对象[QGestureEvent](qgestureevent.html)如果相应的姿态是主动还是刚被取消。被输送的每个事件包含手势的对象的列表中，由于可被使能用于目标对象为多个姿态的支持。由于事件在Qt的处理方式，手势事件可以被其他对象进行过滤。

* * *

## Type Documentation

```
QGesture.GestureCancelPolicy
```

这个枚举说明如何接受一个手势可以自动取消其他手势。

| Constant | Value | Description |
| --- | --- | --- |
| `QGesture.CancelNone` | `0` | 在接受这个手势没有其他的手势将受到影响。 |
| `QGesture.CancelAllInContext` | `1` | 在接受这个手势是活跃在上下文中的所有手势（尊重[Qt.GestureFlag](qt.html#GestureFlag-enum)这是指定的，当订阅的手势）将被取消。 |

* * *

## Method Documentation

```
QGesture.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的手势对象与给定_parent_。

[QGesture](qgesture.html)目的是通过手势识别在所创建的[QGestureRecognizer.create](qgesturerecognizer.html#create)（）函数。

```
GestureCancelPolicy QGesture.gestureCancelPolicy (self)
```

[](qgesture.html#GestureCancelPolicy-enum)

```
Qt.GestureType QGesture.gestureType (self)
```

[

```
bool QGesture.hasHotSpot (self)
```

](qt.html#GestureType-enum)

```
QPointF QGesture.hotSpot (self)
```

[

```
QGesture.setGestureCancelPolicy (self, GestureCancelPolicy policy)
```

```
QGesture.setHotSpot (self, QPointF value)
```

](qpointf.html)

```
Qt.GestureState QGesture.state (self)
```

[

```
QGesture.unsetHotSpot (self)
```

](qt.html#GestureState-enum)