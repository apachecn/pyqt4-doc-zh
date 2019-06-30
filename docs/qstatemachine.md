# QStateMachine Class Reference

## [[QtCore](index.htm) module]

该QStateMachine类提供了一个分层有限状态机。[More...](#details)

继承[QState](qstate.html)。

### Types

*   `enum Error { NoError, NoInitialStateError, NoDefaultStateInHistoryStateError, NoCommonAncestorForTransitionError }`
*   `enum EventPriority { NormalPriority, HighPriority }`
*   `enum RestorePolicy { DontRestoreProperties, RestoreProperties }`
*   `class **[SignalEvent](index.htm)**`
*   `class **[WrappedEvent](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addDefaultAnimation (self, QAbstractAnimation animation)`
*   `addState (self, QAbstractState state)`
*   `bool cancelDelayedEvent (self, int id)`
*   `clearError (self)`
*   `list-of-QAbstractState configuration (self)`
*   `list-of-QAbstractAnimation defaultAnimations (self)`
*   `Error error (self)`
*   `QString errorString (self)`
*   `bool event (self, QEvent e)`
*   `bool eventFilter (self, QObject watched, QEvent event)`
*   `RestorePolicy globalRestorePolicy (self)`
*   `bool isAnimated (self)`
*   `bool isRunning (self)`
*   `onEntry (self, QEvent event)`
*   `onExit (self, QEvent event)`
*   `int postDelayedEvent (self, QEvent event, int delay)`
*   `postEvent (self, QEvent event, EventPriority priority = QStateMachine.NormalPriority)`
*   `removeDefaultAnimation (self, QAbstractAnimation animation)`
*   `removeState (self, QAbstractState state)`
*   `setAnimated (self, bool enabled)`
*   `setGlobalRestorePolicy (self, RestorePolicy restorePolicy)`
*   `start (self)`
*   `stop (self)`

### Qt Signals

*   `void started ()`
*   `void stopped ()`

* * *

## Detailed Description

该QStateMachine类提供了一个分层有限状态机。

QStateMachine是基于概念和符号 [Statecharts](http://www.wisdom.weizmann.ac.il/~dharel/SCANNED.PAPERS/Statecharts.pdf)。 QStateMachine是一部分[The State Machine Framework](index.htm)。

状态机管理一组状态（即从继承的类[QAbstractState](qabstractstate.html)）和转换（后裔[QAbstractTransition](qabstracttransition.html)）之间的状态，这些状态和转换定义一个状态图。一旦一个状态图已经建成，状态机可以执行它。 QStateMachine的执行算法是基于[State Chart XML (SCXML)](http://www.w3.org/TR/scxml/)算法。该框架的[overview](index.htm)给出了几种状态图，并建立它们的代码。

使用[addState](qstatemachine.html#addState)（ ）函数的顶级状态添加到状态机。国与删除[removeState](qstatemachine.html#removeState)（）函数。机器运行时拆卸状态是气馁。

之前可以对机器进行启动，[initial state](qstate.html#initialState-prop)必须设置。初始状态是状态启动时，机器进入。然后，您可以[start](qstatemachine.html#start)（ ）状态机。该[started](qstatemachine.html#started)当进入初始状态（ ）信号被发射。

本机是事件驱动的，并保持自己的事件循环。活动通过张贴到机器[postEvent](qstatemachine.html#postEvent)（ ） 。请注意，这意味着它异步执行，并且它不会没有运行事件循环的进展。你通常不会有事件发布到本机直接作为Qt的转换，例如，[QEventTransition](qeventtransition.html)和它的子类，处理这个问题。但对于由事件触发的自定义转换，[postEvent](qstatemachine.html#postEvent)（）是有用的。

状态机处理事件，并采取转换，直至顶层的最终状态进入，状态机，然后放出[finished](qstate.html#finished)（）信号。您也可以[stop](qstatemachine.html#stop)（ ）显式状态机。该[stopped](qstatemachine.html#stopped)（）信号在这种情况下被发射。

下面的代码片断显示了一个状态机单击按钮时，将完成：

```
 [QPushButton](qpushbutton.html) button;

 QStateMachine machine;
 [QState](qstate.html) *s1 = new [QState](qstate.html)();
 s1->assignProperty(&button, "text", "Click me");

 [QFinalState](qfinalstate.html) *s2 = new [QFinalState](qfinalstate.html)();
 s1->addTransition(&button, SIGNAL(clicked()), s2);

 machine.addState(s1);
 machine.addState(s2);
 machine.setInitialState(s1);
 machine.start();

```

此代码示例使用[QState](qstate.html)，它继承[QAbstractState](qabstractstate.html)。该[QState](qstate.html)类提供了可用于设置属性和调用方法上的状态[QObject](qobject.html)当国家进入或退出秒。它还包含用于添加转场，例如方便的功能，[QSignalTransition](qsignaltransition.html)S作为在这个例子。请参阅[QState](qstate.html)类描述进一步的细节。

如果遇到错误，机器会寻找一个[error state](qstate.html#errorState-prop)，并且如果有，它会进入这种状态。可能发生的错误的类型由所述[Error](qstatemachine.html#Error-enum)枚举。进入错误状态后，错误的类型，可以检索与[error](qstatemachine.html#error)（ ） 。当进入错误状态的状态图的执行不会停止。如果没有错误状态适用于在错误状态时，机器将停止执行和错误信息会被打印到控制台。

* * *

## Type Documentation

```
QStateMachine.Error
```

该枚举类型定义了可以在运行时发生的状态机错误。当状态机在运行时遇到不可恢复的错误，它会设置返回的错误代码[error](qstatemachine.html#error)（ ） ，返回的错误信息[errorString](qstatemachine.html#errorString-prop)（） ，并输入基于错误的情况下的错误状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QStateMachine.NoError` | `0` | 没有发生错误。 |
| `QStateMachine.NoInitialStateError` | `1` | 本机已进入[QState](qstate.html)儿童不具有初始状态集。这个错误的上下文是一个缺少初始状态的状态。 |
| `QStateMachine.NoDefaultStateInHistoryStateError` | `2` | 本机已进入[QHistoryState](qhistorystate.html)它不具有默认状态设置。这个错误的上下文是[QHistoryState](qhistorystate.html)一个缺少默认状态。 |
| `QStateMachine.NoCommonAncestorForTransitionError` | `3` | 机器已经选择了一个过渡，其源和目标是不一样的状态的树的一部分，并且因此是不一样的状态机的一部分。一般情况下，这可能意味着国家之一没有得到父母或添加到任何机器。这个错误的上下文是过渡的源状态。 |

**See also** [setErrorState](qstate.html#errorState-prop)（ ） 。

```
QStateMachine.EventPriority
```

该枚举类型指定使用发布到状态机的事件的优先级[postEvent](qstatemachine.html#postEvent)（ ） 。

高优先级的活动正常优先级的事件之前处理。

| Constant | Value | Description |
| --- | --- | --- |
| `QStateMachine.NormalPriority` | `0` | 该事件具有正常的优先级。 |
| `QStateMachine.HighPriority` | `1` | 该事件具有高优先级。 |

```
QStateMachine.RestorePolicy
```

这个枚举变量指定的恢复策略类型。恢复策略生效时，机器进入其中设置一个或多个属性的状态。如果恢复策略设置为RestoreProperties ，状态机将保存属性的原始值新值被设置之前。

后来，当机器或者进入不设置为给定的属性的值的状态下，该属性将被自动恢复到其初始值。

只有一个初始值将被保存为任何给定的属性。如果某个属性的值已经储存的状态机，它不会被复盖，直到该物业已成功恢复。

| Constant | Value | Description |
| --- | --- | --- |
| `QStateMachine.DontRestoreProperties` | `0` | 状态机应该不保存属性的初始值，并在以后恢复它们。 |
| `QStateMachine.RestoreProperties` | `1` | 状态机应该保存属性的初始值，并在以后恢复它们。 |

**See also** [QStateMachine.globalRestorePolicy](qstatemachine.html#globalRestorePolicy-prop)和[QState.assignProperty](qstate.html#assignProperty)（ ） 。

* * *

## Method Documentation

```
QStateMachine.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的状态机具有给定_parent_。

```
QStateMachine.addDefaultAnimation (self, QAbstractAnimation animation)
```

添加一个默认_animation_应考虑的任何过渡。

```
QStateMachine.addState (self, QAbstractState state)
```

该_state_说法有它的所有权转移给Qt的。

将给定_state_这个状态机。国家变成了顶级的状态。

如果国家已经在不同的机器上，它首先会从旧机器中取出，然后加入到本机。

**See also** [removeState](qstatemachine.html#removeState)（）和[setInitialState](qstate.html#initialState-prop)（ ） 。

```
bool QStateMachine.cancelDelayedEvent (self, int id)
```

取消确定了在给定的延迟事件_id_。 ID应该是通过调用返回的值[postDelayedEvent](qstatemachine.html#postDelayedEvent)（ ） 。返回True如果该事件被成功取消，否则返回False 。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [postDelayedEvent](qstatemachine.html#postDelayedEvent)（ ） 。

```
QStateMachine.clearError (self)
```

清除状态机的错误字符串和错误代码。

```
list-of-QAbstractState QStateMachine.configuration (self)
```

返回极大一致集的状态（包括并行和最终状态）的，这个状态机是目前。如果一个国家`s`在配置中，它总是的情况下的父`s`也是在C 。然而，请注意，机器本身不是配置的显式成员。

```
list-of-QAbstractAnimation QStateMachine.defaultAnimations (self)
```

返回默认的动画，将被视为对任何过渡的列表。

```
Error QStateMachine.error (self)
```

[

返回发生在状态机的最后一个错误的错误代码。

```
QString QStateMachine.errorString (self)
```

```
bool QStateMachine.event (self, QEvent e)
```

](qstatemachine.html#Error-enum)

[从重新实现](qstatemachine.html#Error-enum)[QObject.event](qobject.html#event)（ ） 。

```
bool QStateMachine.eventFilter (self, QObject watched, QEvent event)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
RestorePolicy QStateMachine.globalRestorePolicy (self)
```

[

```
bool QStateMachine.isAnimated (self)
```

```
bool QStateMachine.isRunning (self)
```

返回是否该状态机正在运行。

](qstatemachine.html#RestorePolicy-enum)

[](qstatemachine.html#RestorePolicy-enum)[start](qstatemachine.html#start)（ ）[stop](qstatemachine.html#stop)（ ）

```
QStateMachine.onEntry (self, QEvent event)
```

从重新实现[QAbstractState.onEntry](qabstractstate.html#onEntry)（ ） 。

这个函数会调用[start](qstatemachine.html#start)（ ）来启动状态机。

```
QStateMachine.onExit (self, QEvent event)
```

从重新实现[QAbstractState.onExit](qabstractstate.html#onExit)（ ） 。

这个函数会调用[stop](qstatemachine.html#stop)（）停止状态机，并随后放出[stopped](qstatemachine.html#stopped)（）信号。

```
int QStateMachine.postDelayedEvent (self, QEvent event, int delay)
```

该_event_说法有它的所有权转移给Qt的。

帖子给定的_event_用于处理由该状态机中，用给定的_delay_以毫秒为单位。返回与延迟事件相关联的标识符，或-1，如果事件无法公布。

此函数立即返回。当延迟已过期，该事件将被添加到状态机的事件队列进行处理。状态机取事件的所有权，并删除它，一旦它已被处理。

您只能在状态机运行时发布事件。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [cancelDelayedEvent](qstatemachine.html#cancelDelayedEvent)（）和[postEvent](qstatemachine.html#postEvent)（ ） 。

```
QStateMachine.postEvent (self, QEvent event, EventPriority priority = QStateMachine.NormalPriority)
```

该_event_说法有它的所有权转移给Qt的。

帖子给定的_event_的给定_priority_处理这个状态机。

此函数立即返回。该事件被添加到状态机的事件队列中。事件在张贴的顺序处理。状态机取事件的所有权，并删除它，一旦它已被处理。

您只能在状态机运行时发布事件。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [postDelayedEvent](qstatemachine.html#postDelayedEvent)（ ） 。

```
QStateMachine.removeDefaultAnimation (self, QAbstractAnimation animation)
```

移除_animation_从预设的动画列表中。

```
QStateMachine.removeState (self, QAbstractState state)
```

该_state_争论

删除给定的_state_从这个状态机。状态的状态机版本的所有权。

**See also** [addState](qstatemachine.html#addState)（ ） 。

```
QStateMachine.setAnimated (self, bool enabled)
```

```
QStateMachine.setGlobalRestorePolicy (self, RestorePolicy restorePolicy)
```

```
QStateMachine.start (self)
```

这种方法也是一个Qt槽与C + +的签名`void start()`。

启动这个状态机。机器将重置它的配置和过渡到初始状态。当最后的顶级状态（[QFinalState](qfinalstate.html)）输入时，机器会发出的[finished](qstate.html#finished)（）信号。

**Note:**状态机将不无运行事件循环，如主应用程序事件循环运行开始[QCoreApplication.exec](qcoreapplication.html#exec)（）或[QApplication.exec](qapplication.html#exec)（ ） 。

**See also** [started](qstatemachine.html#started)（ ）[finished](qstate.html#finished)（ ）[stop](qstatemachine.html#stop)（）和[initialState](qstate.html#initialState-prop)（ ） 。

```
QStateMachine.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

停止该状态机。状态机将停止处理事件，然后放出[stopped](qstatemachine.html#stopped)（）信号。

**See also** [stopped](qstatemachine.html#stopped)（）和[start](qstatemachine.html#start)（ ） 。

* * *

## Qt Signal Documentation

```
void started ()
```

这是该信号的默认超载。

当状态机进入初始状态（这个信号被发射[QStateMachine.initialState](qstate.html#initialState-prop)） 。

**See also** [QStateMachine.finished](qstate.html#finished)（）和[QStateMachine.start](qstatemachine.html#start)（ ） 。

```
void stopped ()
```

这是该信号的默认超载。

这个信号被发射时，状态机已经停止。

**See also** [QStateMachine.stop](qstatemachine.html#stop)（）和[QStateMachine.finished](qstate.html#finished)（ ） 。