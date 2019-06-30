# QGestureEvent Class Reference

## [[QtGui](index.htm) module]

该QGestureEvent类提供触发手势的说明。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, list-of-QGesture gestures)`
*   `__init__ (self, QGestureEvent)`
*   `accept (self)`
*   `accept (self, QGesture)`
*   `accept (self, Qt.GestureType)`
*   `list-of-QGesture activeGestures (self)`
*   `list-of-QGesture canceledGestures (self)`
*   `QGesture gesture (self, Qt.GestureType type)`
*   `list-of-QGesture gestures (self)`
*   `ignore (self)`
*   `ignore (self, QGesture)`
*   `ignore (self, Qt.GestureType)`
*   `bool isAccepted (self)`
*   `bool isAccepted (self, QGesture)`
*   `bool isAccepted (self, Qt.GestureType)`
*   `QPointF mapToGraphicsScene (self, QPointF gesturePoint)`
*   `setAccepted (self, bool accepted)`
*   `setAccepted (self, QGesture, bool)`
*   `setAccepted (self, Qt.GestureType, bool)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QGestureEvent类提供触发手势的说明。

该QGestureEvent类包含手势的列表，可以使用获得的[gestures](qgestureevent.html#gestures)（）函数。

手势可以是主动的或注销。可以用以下方式获得的那些当前正在执行的是列表的[activeGestures](qgestureevent.html#activeGestures)（）函数。可以使用访问那些以往不活跃，已被取消的名单[canceledGestures](qgestureevent.html#canceledGestures)（）函数。如果当前窗口失去焦点手势可能会被取消，例如，或因为超时，或者其他原因。

如果事件处理程序不通过调用泛型接受事件[QEvent.accept](qevent.html#accept)（ ）函数，所有的个体[QGesture](qgesture.html)那些没有接受，并在对象[Qt.GestureStarted](qt.html#GestureState-enum)状态将被传播到父控件链，直到一个小部件接受他们的个人，通过调用[QGestureEvent.accept](qgestureevent.html#accept)（ ）为他们每个人，或者一个事件过滤器所消耗的活动。

### Further Reading

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

* * *

## Method Documentation

```
QGestureEvent.__init__ (self, list-of-QGesture gestures)
```

创造了新的[QGestureEvent](qgestureevent.html)含的列表_gestures_。

```
QGestureEvent.__init__ (self, QGestureEvent)
```

```
QGestureEvent.accept (self)
```

接受事件，调用setAccepted相当于（真） 。

**See also** [QEvent.accept](qevent.html#accept)（ ） 。

```
QGestureEvent.accept (self, QGesture)
```

设置给定的接受标志_gesture_对象，调用相当于[setAccepted(gesture, true)](qgestureevent.html#setAccepted)。

设置接受标志表示该事件接收器想要的手势。不需要的手势可能会传播到父widget 。

**See also** [QGestureEvent.ignore](qgestureevent.html#ignore)（ ） 。

```
QGestureEvent.accept (self, Qt.GestureType)
```

设置给定的接受标志_gestureType_，调用相当于[setAccepted(gestureType, true)](qgestureevent.html#setAccepted)。

设置接受标志表示该事件接收器想要的手势。不需要的手势可能会传播到父widget 。

**See also** [QGestureEvent.ignore](qgestureevent.html#ignore)（ ） 。

```
list-of-QGesture QGestureEvent.activeGestures (self)
```

返回激活（未注销）手势的列表。

```
list-of-QGesture QGestureEvent.canceledGestures (self)
```

返回取消手势的列表。

```
QGesture QGestureEvent.gesture (self, Qt.GestureType type)
```

[

通过返回一个对象手势_type_。

```
list-of-QGesture QGestureEvent.gestures (self)
```

返回已交付的事件的所有手势。

```
QGestureEvent.ignore (self)
```

忽略该事件，调用setAccepted （假）的等价物。

](qgesture.html)

[**See also**](qgesture.html) [QEvent.ignore](qevent.html#ignore)（ ） 。

```
QGestureEvent.ignore (self, QGesture)
```

清除给定的接受标志参数_gesture_对象，调用相当于[setAccepted(gesture, false)](qgestureevent.html#setAccepted)。

清除接受标志表示该事件接收不想要的姿势。不需要的手势可能会传播到父widget 。

**See also** [QGestureEvent.accept](qgestureevent.html#accept)（ ） 。

```
QGestureEvent.ignore (self, Qt.GestureType)
```

清除给定的接受标志参数_gestureType_，调用相当于[setAccepted(gesture, false)](qgestureevent.html#setAccepted)。

清除接受标志表示该事件接收不想要的姿势。不需要的手势可能会propgated到父widget 。

**See also** [QGestureEvent.accept](qgestureevent.html#accept)（ ） 。

```
bool QGestureEvent.isAccepted (self)
```

返回True是事件已被接受，否则返回False 。

**See also** [QEvent.accepted](qevent.html#accepted-prop)。

```
bool QGestureEvent.isAccepted (self, QGesture)
```

返回True如果_gesture_被接受，否则返回False 。

```
bool QGestureEvent.isAccepted (self, Qt.GestureType)
```

返回True如果类型的手势_gestureType_被接受，否则返回False 。

```
QPointF QGestureEvent.mapToGraphicsScene (self, QPointF gesturePoint)
```

[

返回场景局部坐标如果_gesturePoint_是一个图形视图中。

](qpointf.html)

[当手势事件被传递到该功能可能是有用的](qpointf.html)[QGraphicsObject](qgraphicsobject.html)翻译点在屏幕坐标场景局部坐标。

**See also** [QPointF.isNull](qpointf.html#isNull)（）和[.](index.html)。

```
QGestureEvent.setAccepted (self, bool accepted)
```

设置或清除事件内部标志，确定它是否应该被传递到其他物体。

调用此函数的真正的价值_accepted_表示该呼叫者已接受该事件，并且它不应该被进一步传播。调用此函数与False值指示调用方忽略了的事件，它应该被传递到其他物体。

为方便起见，接受标志也可以与设置[accept](qgestureevent.html#accept)（ ） ，并与清除[ignore](qgestureevent.html#ignore)（ ） 。

**See also** [isAccepted](qgestureevent.html#isAccepted)（）和[QEvent.accepted](qevent.html#accepted-prop)。

```
QGestureEvent.setAccepted (self, QGesture, bool)
```

设置给定的接受标志_gesture_对象的指定的_value_。

设置接受标志表示该事件接收器想要的_gesture_。不需要的手势可能会传播到父widget 。

默认情况下，在手势类型的事件[QEvent.Gesture](qevent.html#Type-enum)被接受，并在手势[QEvent.GestureOverride](qevent.html#Type-enum)事件将被忽略。

为方便起见，接受标志也可以与设置[accept](qgestureevent.html#accept)（手势） ，并与清[ignore](qgestureevent.html#ignore)（手势） 。

```
QGestureEvent.setAccepted (self, Qt.GestureType, bool)
```

设置给定的接受标志_gestureType_对象的指定的_value_。

设置接受标志表示该事件接收器要接收指定类型的手势，_gestureType_。不需要的手势可能会传播到父widget 。

默认情况下，在手势类型的事件[QEvent.Gesture](qevent.html#Type-enum)被接受，并在手势[QEvent.GestureOverride](qevent.html#Type-enum)事件将被忽略。

为方便起见，接受标志也可以与设置[accept](qgestureevent.html#accept)（ gestureType ） ，并与清除[ignore](qgestureevent.html#ignore)（ gestureType ） 。

```
QWidget QGestureEvent.widget (self)
```

[

返回上发生事件的小部件。

](qwidget.html)