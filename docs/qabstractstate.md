# QAbstractState Class Reference

## [[QtCore](index.htm) module]

该QAbstractState类是一个国家的基类[QStateMachine](qstatemachine.html)。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QFinalState](qfinalstate.html)，[QHistoryState](qhistorystate.html)和[QState](qstate.html)。

### Methods

*   `__init__ (self, QState parent = None)`
*   `bool event (self, QEvent e)`
*   `QStateMachine machine (self)`
*   `onEntry (self, QEvent event)`
*   `onExit (self, QEvent event)`
*   `QState parentState (self)`

### Qt Signals

*   `void entered ()`
*   `void exited ()`

* * *

## Detailed Description

该QAbstractState类是一个国家的基类[QStateMachine](qstatemachine.html)。

该QAbstractState类是规定，是一部分的抽象基类[QStateMachine](qstatemachine.html)。它定义了所有的状态对象有共同的接口。 QAbstractState是一部分[The State Machine Framework](index.htm)。

该[entered](qabstractstate.html#entered)当该状态已被输入（）信号被发射。该[exited](qabstractstate.html#exited)当国家已经退出（ ）信号被发射。

该[parentState](qabstractstate.html#parentState)（ ）函数返回的状态的父状态。该[machine](qabstractstate.html#machine)（ ）函数返回的状态机的状态是一部分。

### Subclassing

该[onEntry](qabstractstate.html#onEntry)（ ）函数被调用时进入状态，重新实现这个功能，当进入状态执行自定义处理。

该[onExit](qabstractstate.html#onExit)（ ）函数被调用时，状态退出，重新实现这个函数来执行自定义处理时状态退出。

* * *

## Method Documentation

```
QAbstractState.__init__ (self, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的状态，用给定的_parent_状态。

```
bool QAbstractState.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QStateMachine QAbstractState.machine (self)
```

[

返回的状态机，这个状态是一部分，或者0，如果状态是不是一个国家机器的一部分。

```
QAbstractState.onEntry (self, QEvent event)
```

这种方法是抽象的，应在任何子类中重新实现。

当进入状态时调用此函数。给定_event_是什么原因导致要输入的状态。重新实现这个功能，当进入状态执行自定义处理。

```
QAbstractState.onExit (self, QEvent event)
```

这种方法是抽象的，应在任何子类中重新实现。

当状态退出时调用此函数。给定_event_是什么原因造成的状态退出。重新实现这个函数来执行自定义处理时状态退出。

](qstatemachine.html)

```
QState QAbstractState.parentState (self)
```

[

返回此状态的父状态，或者0，如果国家没有父状态。

* * *

## Qt Signal Documentation

```
void entered ()
```

这是该信号的默认超载。

](qstate.html)

[当国家已经进入（后这个信号被发射](qstate.html)[onEntry](qabstractstate.html#onEntry)（ ）被调用） 。

```
void exited ()
```

这是该信号的默认超载。

当国家已经退出（后这个信号被发射[onExit](qabstractstate.html#onExit)（ ）被调用） 。