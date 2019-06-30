# QHistoryState Class Reference

## [[QtCore](index.htm) module]

该QHistoryState类提供​​返回到一个以前的活动子状态的手段。[More...](#details)

继承[QAbstractState](qabstractstate.html)。

### Types

*   `enum HistoryType { ShallowHistory, DeepHistory }`

### Methods

*   `__init__ (self, QState parent = None)`
*   `__init__ (self, HistoryType type, QState parent = None)`
*   `QAbstractState defaultState (self)`
*   `bool event (self, QEvent e)`
*   `HistoryType historyType (self)`
*   `onEntry (self, QEvent event)`
*   `onExit (self, QEvent event)`
*   `setDefaultState (self, QAbstractState state)`
*   `setHistoryType (self, HistoryType type)`

* * *

## Detailed Description

该QHistoryState类提供​​返回到一个以前的活动子状态的手段。

史状态是一个伪状态，代表该子状态的父状态是在最后时刻父状态中退出。与历史状态为目标的过渡实际上是在父状态的其他子状态的一个过渡。 QHistoryState是一部分[The State Machine Framework](index.htm)。

使用[setDefaultState](qhistorystate.html#defaultState-prop)（ ）函数来设置，如果父状态从来没有进入应该进入状态。例如：

```
 [QStateMachine](qstatemachine.html) machine;

 [QState](qstate.html) *s1 = new [QState](qstate.html)();
 [QState](qstate.html) *s11 = new [QState](qstate.html)(s1);
 [QState](qstate.html) *s12 = new [QState](qstate.html)(s1);

 QHistoryState *s1h = new QHistoryState(s1);
 s1h->setDefaultState(s11);

 machine.addState(s1);

 [QState](qstate.html) *s2 = new [QState](qstate.html)();
 machine.addState(s2);

 [QPushButton](qpushbutton.html) *button = new [QPushButton](qpushbutton.html)();
 // Clicking the button will cause the state machine to enter the child state
 // that s1 was in the last time s1 was exited, or the history state's default
 // state if s1 has never been entered.
 s1->addTransition(button, SIGNAL(clicked()), s1h);

```

默认情况下，历史状态很浅，这意味着它不会记得嵌套状态。这可以通过配置[historyType](qhistorystate.html#historyType-prop)属性。

* * *

## Type Documentation

```
QHistoryState.HistoryType
```

此枚举指定的历史类型，一个[QHistoryState](qhistorystate.html)记录。

| Constant | Value | Description |
| --- | --- | --- |
| `QHistoryState.ShallowHistory` | `0` | 只有父状态的直接子状态被记录下来。在这种情况下，与历史状态为目标的过渡最终会在父是在上一次被退出的直接子状态。这是默认的。 |
| `QHistoryState.DeepHistory` | `1` | 嵌套状态被记录下来。在这种情况下，与历史状态为目标的过渡将结束在最深层的后代状态母公司是在上次被退出。 |

* * *

## Method Documentation

```
QHistoryState.__init__ (self, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的浅历史状态与给定_parent_状态。

```
QHistoryState.__init__ (self, HistoryType type, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造的赋予了新的历史状态_type_用给定的_parent_状态。

```
QAbstractState QHistoryState.defaultState (self)
```

[

```
bool QHistoryState.event (self, QEvent e)
```

](qabstractstate.html)

[从重新实现](qabstractstate.html)[QObject.event](qobject.html#event)（ ） 。

```
HistoryType QHistoryState.historyType (self)
```

[

```
QHistoryState.onEntry (self, QEvent event)
```

](qhistorystate.html#HistoryType-enum)

[从重新实现](qhistorystate.html#HistoryType-enum)[QAbstractState.onEntry](qabstractstate.html#onEntry)（ ） 。

```
QHistoryState.onExit (self, QEvent event)
```

从重新实现[QAbstractState.onExit](qabstractstate.html#onExit)（ ） 。

```
QHistoryState.setDefaultState (self, QAbstractState state)
```

```
QHistoryState.setHistoryType (self, HistoryType type)
```