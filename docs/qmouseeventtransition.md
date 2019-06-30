# QMouseEventTransition Class Reference

## [[QtGui](index.htm) module]

该QMouseEventTransition类提供了鼠标事件的转变。[More...](#details)

继承[QEventTransition](qeventtransition.html)。

### Methods

*   `__init__ (self, QState sourceState = None)`
*   `__init__ (self, QObject object, QEvent.Type type, Qt.MouseButton button, QState sourceState = None)`
*   `Qt.MouseButton button (self)`
*   `bool eventTest (self, QEvent event)`
*   `QPainterPath hitTestPath (self)`
*   `Qt.KeyboardModifiers modifierMask (self)`
*   `onTransition (self, QEvent event)`
*   `setButton (self, Qt.MouseButton button)`
*   `setHitTestPath (self, QPainterPath path)`
*   `setModifierMask (self, Qt.KeyboardModifiers modifiers)`

* * *

## Detailed Description

该QMouseEventTransition类提供了鼠标事件的转变。

QMouseEventTransition是一部分[The State Machine Framework](index.htm)。

* * *

## Method Documentation

```
QMouseEventTransition.__init__ (self, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造具有给定一个新的鼠标事件转变_sourceState_。

```
QMouseEventTransition.__init__ (self, QObject object, QEvent.Type type, Qt.MouseButton button, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造对给定事件的一个新的鼠标事件转变_type_对于给定的_object_用给定的_button_和_sourceState_。

```
Qt.MouseButton QMouseEventTransition.button (self)
```

[

```
bool QMouseEventTransition.eventTest (self, QEvent event)
```

](qt.html#MouseButton-enum)

[从重新实现](qt.html#MouseButton-enum)[QAbstractTransition.eventTest](qabstracttransition.html#eventTest)（ ） 。

```
QPainterPath QMouseEventTransition.hitTestPath (self)
```

[

返回此鼠标事件过渡点击测试路径。

](qpainterpath.html)

[**See also**](qpainterpath.html) [setHitTestPath](qmouseeventtransition.html#setHitTestPath)（ ） 。

```
Qt.KeyboardModifiers QMouseEventTransition.modifierMask (self)
```

[

```
QMouseEventTransition.onTransition (self, QEvent event)
```

](index.htm)

[从重新实现](index.htm)[QAbstractTransition.onTransition](qabstracttransition.html#onTransition)（ ） 。

```
QMouseEventTransition.setButton (self, Qt.MouseButton button)
```

```
QMouseEventTransition.setHitTestPath (self, QPainterPath path)
```

设置命中测试路径为这个鼠标事件过渡到_path_。如果一个有效的路径已被设定，过渡只会触发如果鼠标事件位置（[QMouseEvent.pos](qmouseevent.html#pos)（））是在路径内。

**See also** [hitTestPath](qmouseeventtransition.html#hitTestPath)（）和[QPainterPath.contains](qpainterpath.html#contains)（ ） 。

```
QMouseEventTransition.setModifierMask (self, Qt.KeyboardModifiers modifiers)
```