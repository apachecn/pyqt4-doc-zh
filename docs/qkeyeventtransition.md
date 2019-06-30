# QKeyEventTransition Class Reference

## [[QtGui](index.htm) module]

该QKeyEventTransition类提供了关键事件的转变。[More...](#details)

继承[QEventTransition](qeventtransition.html)。

### Methods

*   `__init__ (self, QState sourceState = None)`
*   `__init__ (self, QObject object, QEvent.Type type, int key, QState sourceState = None)`
*   `bool eventTest (self, QEvent event)`
*   `int key (self)`
*   `Qt.KeyboardModifiers modifierMask (self)`
*   `onTransition (self, QEvent event)`
*   `setKey (self, int key)`
*   `setModifierMask (self, Qt.KeyboardModifiers modifiers)`

* * *

## Detailed Description

该QKeyEventTransition类提供了关键事件的转变。

QKeyEventTransition是一部分[The State Machine Framework](index.htm)。

* * *

## Method Documentation

```
QKeyEventTransition.__init__ (self, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造具有给定一个新的关键事件转变_sourceState_。

```
QKeyEventTransition.__init__ (self, QObject object, QEvent.Type type, int key, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造对给定事件的一个新的关键事件转变_type_对于给定的_object_用给定的_key_和_sourceState_。

```
bool QKeyEventTransition.eventTest (self, QEvent event)
```

从重新实现[QAbstractTransition.eventTest](qabstracttransition.html#eventTest)（ ） 。

```
int QKeyEventTransition.key (self)
```

```
Qt.KeyboardModifiers QKeyEventTransition.modifierMask (self)
```

[

```
QKeyEventTransition.onTransition (self, QEvent event)
```

](index.htm)

[从重新实现](index.htm)[QAbstractTransition.onTransition](qabstracttransition.html#onTransition)（ ） 。

```
QKeyEventTransition.setKey (self, int key)
```

```
QKeyEventTransition.setModifierMask (self, Qt.KeyboardModifiers modifiers)
```