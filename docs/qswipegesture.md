# QSwipeGesture Class Reference

## [[QtGui](index.htm) module]

该QSwipeGesture类描述了一个滑动手势用户所做的。[More...](#details)

继承[QGesture](qgesture.html)。

### Types

*   `enum SwipeDirection { NoDirection, Left, Right, Up, Down }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `SwipeDirection horizontalDirection (self)`
*   `setSwipeAngle (self, float value)`
*   `float swipeAngle (self)`
*   `SwipeDirection verticalDirection (self)`

* * *

## Detailed Description

该QSwipeGesture类描述了一个滑动手势用户所做的。

![](../img/swipegesture.png)

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

* * *

## Type Documentation

```
QSwipeGesture.SwipeDirection
```

该枚举描述了用于沿水平和垂直轴的姿态的运动的可能方向。

| Constant | Value | Description |
| --- | --- | --- |
| `QSwipeGesture.NoDirection` | `0` | 手势没有与它在一个特定的轴关联的运动。 |
| `QSwipeGesture.Left` | `1` | 该手势所涉及的水平方向运动到左边。 |
| `QSwipeGesture.Right` | `2` | 该手势所涉及的水平方向运动到右侧。 |
| `QSwipeGesture.Up` | `3` | 姿态参与垂直向上运动。 |
| `QSwipeGesture.Down` | `4` | 姿态参与垂直向下运动。 |

* * *

## Method Documentation

```
QSwipeGesture.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
SwipeDirection QSwipeGesture.horizontalDirection (self)
```

[

```
QSwipeGesture.setSwipeAngle (self, float value)
```

```
float QSwipeGesture.swipeAngle (self)
```

](qswipegesture.html#SwipeDirection-enum)

```
SwipeDirection QSwipeGesture.verticalDirection (self)
```

[](qswipegesture.html#SwipeDirection-enum)