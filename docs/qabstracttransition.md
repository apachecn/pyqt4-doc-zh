# QAbstractTransition Class Reference

## [[QtCore](index.htm) module]

该QAbstractTransition类是过渡之间的基类[QAbstractState](qabstractstate.html)对象。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QEventTransition](qeventtransition.html)和[QSignalTransition](qsignaltransition.html)。

### Methods

*   `__init__ (self, QState sourceState = None)`
*   `addAnimation (self, QAbstractAnimation animation)`
*   `list-of-QAbstractAnimation animations (self)`
*   `bool event (self, QEvent e)`
*   `bool eventTest (self, QEvent event)`
*   `QStateMachine machine (self)`
*   `onTransition (self, QEvent event)`
*   `removeAnimation (self, QAbstractAnimation animation)`
*   `setTargetState (self, QAbstractState target)`
*   `setTargetStates (self, list-of-QAbstractState targets)`
*   `QState sourceState (self)`
*   `QAbstractState targetState (self)`
*   `list-of-QAbstractState targetStates (self)`

### Qt Signals

*   `void triggered ()`

* * *

## Detailed Description

该QAbstractTransition类是过渡之间的基类[QAbstractState](qabstractstate.html)对象。

该QAbstractTransition类是过渡态之间的抽象基类（[QAbstractState](qabstractstate.html)的对象）[QStateMachine](qstatemachine.html)。 QAbstractTransition是一部分[The State Machine Framework](index.htm)。

该[sourceState](qabstracttransition.html#sourceState-prop)（ ）函数返回的过渡之源。该[targetStates](qabstracttransition.html#targetStates-prop)（ ）函数返回的过渡的目标。该[machine](qabstracttransition.html#machine)（ ）函数返回的状态机的过渡的一部分。

该[triggered](qabstracttransition.html#triggered)当过渡已被触发（）信号被发射。

转换可能会导致动画播放。使用[addAnimation](qabstracttransition.html#addAnimation)（）函数将动画添加到过渡。

### Subclassing

该[eventTest](qabstracttransition.html#eventTest)（ ）函数被调用的状态机来判断事件是否应触发的过渡。在你重新实现您通常检查事件类型和事件对象转换为正确的类型，并检查事件的一个或多个属性符合您的标准。

该[onTransition](qabstracttransition.html#onTransition)（ ）函数被调用时的过渡被触发，重新实现这个函数来执行自定义处理过渡。

* * *

## Method Documentation

```
QAbstractTransition.__init__ (self, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QAbstractTransition](qabstracttransition.html)与给定对象_sourceState_。

```
QAbstractTransition.addAnimation (self, QAbstractAnimation animation)
```

将给定_animation_到这种转变。过渡不走动画的所有权。

**See also** [removeAnimation](qabstracttransition.html#removeAnimation)（）和[animations](qabstracttransition.html#animations)（ ） 。

```
list-of-QAbstractAnimation QAbstractTransition.animations (self)
```

返回与此过渡，或一个空列表关联的，如果它没有动画的动画列表中。

**See also** [addAnimation](qabstracttransition.html#addAnimation)（ ） 。

```
bool QAbstractTransition.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QAbstractTransition.eventTest (self, QEvent event)
```

这种方法是抽象的，应在任何子类中重新实现。

这个函数被调用，以确定是否在给定_event_应引起这种转变来触发。重新实现这个函数，返回True，如果事件应触发的过渡，否则返回False 。

```
QStateMachine QAbstractTransition.machine (self)
```

[

返回该状态机，这是过渡的一部分，或者0，如果过渡不是一个状态机的一部分。

```
QAbstractTransition.onTransition (self, QEvent event)
```

这种方法是抽象的，应在任何子类中重新实现。

当转换触发此函数被调用。给定_event_是什么原因造成的过渡触发。重新实现这个函数来执行自定义处理时的过渡被触发。

```
QAbstractTransition.removeAnimation (self, QAbstractAnimation animation)
```

删除给定的_animation_从这种转变。

](qstatemachine.html)

[**See also**](qstatemachine.html) [addAnimation](qabstracttransition.html#addAnimation)（ ） 。

```
QAbstractTransition.setTargetState (self, QAbstractState target)
```

```
QAbstractTransition.setTargetStates (self, list-of-QAbstractState targets)
```

```
QState QAbstractTransition.sourceState (self)
```

[](qstate.html)

```
QAbstractState QAbstractTransition.targetState (self)
```

[

```
list-of-QAbstractState QAbstractTransition.targetStates (self)
```

* * *

## Qt Signal Documentation

```
void triggered ()
```

这是该信号的默认超载。

](qabstractstate.html)

[当过渡已被触发（在这信号被发射](qabstractstate.html)[onTransition](qabstracttransition.html#onTransition)（ ）被调用） 。