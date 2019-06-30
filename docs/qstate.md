# QState Class Reference

## [[QtCore](index.htm) module]

该QState类提供了一个通用的状态[QStateMachine](qstatemachine.html)。[More...](#details)

继承[QAbstractState](qabstractstate.html)。

通过继承[QStateMachine](qstatemachine.html)。

### Types

*   `enum ChildMode { ExclusiveStates, ParallelStates }`

### Methods

*   `__init__ (self, QState parent = None)`
*   `__init__ (self, ChildMode childMode, QState parent = None)`
*   `addTransition (self, QAbstractTransition transition)`
*   `QSignalTransition addTransition (self, QObject sender, SIGNAL() signal, QAbstractState target)`
*   `QSignalTransition addTransition (self, signal signal, QAbstractState target)`
*   `QAbstractTransition addTransition (self, QAbstractState target)`
*   `assignProperty (self, QObject object, str name, QVariant value)`
*   `ChildMode childMode (self)`
*   `QAbstractState errorState (self)`
*   `bool event (self, QEvent e)`
*   `QAbstractState initialState (self)`
*   `onEntry (self, QEvent event)`
*   `onExit (self, QEvent event)`
*   `removeTransition (self, QAbstractTransition transition)`
*   `setChildMode (self, ChildMode mode)`
*   `setErrorState (self, QAbstractState state)`
*   `setInitialState (self, QAbstractState state)`
*   `list-of-QAbstractTransition transitions (self)`

### Qt Signals

*   `void finished ()`
*   `void propertiesAssigned ()`

* * *

## Detailed Description

该QState类提供了一个通用的状态[QStateMachine](qstatemachine.html)。

QState对象可以有子状态，可以有过渡到其他国家。 QState是一部分[The State Machine Framework](index.htm)。

该[addTransition](qstate.html#addTransition)（ ）函数添加一个过渡。该[removeTransition](qstate.html#removeTransition)（ ）函数删除一个过渡。该[transitions](qstate.html#transitions)（ ）函数返回的状态的向外的转移。

该[assignProperty](qstate.html#assignProperty)（ ）函数用于定义当进入一种状态，应该进行财产分配。

顶级状态，必须通过一个[QStateMachine](qstatemachine.html)对象作为它们的父状态，或者使用加入到一个状态机[QStateMachine.addState](qstatemachine.html#addState)（ ） 。

### States with Child States

该[childMode](qstate.html#childMode-prop)属性决定了孩子的状态对待。对于非平行状态群体，[setInitialState](qstate.html#initialState-prop)（ ）函数必须被调用来设置初始状态。孩子的状态是相互排斥的状态，状态机需要知道进入哪个孩子的状态时，父状态是一个过渡的目标。

国家发出的[QState.finished](qstate.html#finished)（ ）信号，当最后一个孩子的状态（[QFinalState](qfinalstate.html)）进入。

该[setErrorState](qstate.html#errorState-prop)（）设置状态的错误状态。错误状态是状态机将过渡，如果当试图进入状态（例如，因为没有初始状态已经设置）检测到一个错误的状态。

* * *

## Type Documentation

```
QState.ChildMode
```

此枚举指定如何一个国家的孩子状态处理。

| Constant | Value | Description |
| --- | --- | --- |
| `QState.ExclusiveStates` | `0` | 孩子的状态是互斥的，初始状态必须通过调用设置[QState.setInitialState](qstate.html#initialState-prop)（ ） 。 |
| `QState.ParallelStates` | `1` | 孩子的状态是平行的。当进入母体的状态，它的所有子状态进入并行。 |

* * *

## Method Documentation

```
QState.__init__ (self, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的状态，用给定的_parent_状态。

```
QState.__init__ (self, ChildMode childMode, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的状态，用给定的_childMode_和给定的_parent_状态。

```
QState.addTransition (self, QAbstractTransition transition)
```

该_transition_说法有它的所有权转移给Qt的。

将给定_transition_。过渡拥有此状态为源。这个状态需要过渡的所有权。

```
QSignalTransition QState.addTransition (self, QObject sender, SIGNAL() signal, QAbstractState target)
```

[](qsignaltransition.html)

[增加了与给定关联的过渡_signal_的给定_sender_对象，并返回新](qsignaltransition.html)[QSignalTransition](qsignaltransition.html)对象。过渡拥有此状态为源，和给定_target_作为目标的状态。

```
QSignalTransition QState.addTransition (self, signal signal, QAbstractState target)
```

[

增加了一个无条件的过渡从这种状态给定的_target_状态，然后返回新的转换对象。

](qsignaltransition.html)

```
QAbstractTransition QState.addTransition (self, QAbstractState target)
```

[

该_target_说法有它的所有权转移给Qt的。

```
QState.assignProperty (self, QObject object, str name, QVariant value)
```

指示这种状态的属性与给定的设置_name_的给定_object_为给定的_value_当进入状态。

](qabstracttransition.html)

[**See also**](qabstracttransition.html) [propertiesAssigned](qstate.html#propertiesAssigned)（ ） 。

```
ChildMode QState.childMode (self)
```

[](qstate.html#ChildMode-enum)

```
QAbstractState QState.errorState (self)
```

[

```
bool QState.event (self, QEvent e)
```

](qabstractstate.html)

[从重新实现](qabstractstate.html)[QObject.event](qobject.html#event)（ ） 。

```
QAbstractState QState.initialState (self)
```

[

```
QState.onEntry (self, QEvent event)
```

](qabstractstate.html)

[从重新实现](qabstractstate.html)[QAbstractState.onEntry](qabstractstate.html#onEntry)（ ） 。

```
QState.onExit (self, QEvent event)
```

从重新实现[QAbstractState.onExit](qabstractstate.html#onExit)（ ） 。

```
QState.removeTransition (self, QAbstractTransition transition)
```

该_transition_争论

删除给定的_transition_从这种状态。过渡状态释放所有权。

**See also** [addTransition](qstate.html#addTransition)（ ） 。

```
QState.setChildMode (self, ChildMode mode)
```

```
QState.setErrorState (self, QAbstractState state)
```

```
QState.setInitialState (self, QAbstractState state)
```

```
list-of-QAbstractTransition QState.transitions (self)
```

返回此状态的外向转移（即过渡的地方这种状态是[source state](qabstracttransition.html#sourceState-prop)） ，或一个空列表，如果这个国家没有向外的转移。

此功能被引入Qt的4.7 。

**See also** [addTransition](qstate.html#addTransition)（ ） 。

* * *

## Qt Signal Documentation

```
void finished ()
```

这是该信号的默认超载。

当进入最后孩子的这个状态状态这个信号被发射。

**See also** [QFinalState](qfinalstate.html)。

```
void propertiesAssigned ()
```

这是该信号的默认超载。

当所有的属性都被分配了他们的最终值这个信号被发射。如果国家分配一个值，来完成一个动画存在一个或多个属性（或者设置在过渡或作为默认的动画状态机） ，那么信号将不发射，直到所有这样的动画已经播放完毕。

如果没有相关的动画，或为国家中没有定义属性赋值，那么信号将被立即发射的进入状态之前。

**See also** [QState.assignProperty](qstate.html#assignProperty)（）和[QAbstractTransition.addAnimation](qabstracttransition.html#addAnimation)（ ） 。