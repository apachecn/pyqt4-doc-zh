# QFinalState Class Reference

## [[QtCore](index.htm) module]

该QFinalState类提供了一个最终状态。[More...](#details)

继承[QAbstractState](qabstractstate.html)。

### Methods

*   `__init__ (self, QState parent = None)`
*   `bool event (self, QEvent e)`
*   `onEntry (self, QEvent event)`
*   `onExit (self, QEvent event)`

* * *

## Detailed Description

该QFinalState类提供了一个最终状态。

最终状态是用来沟通的（部分）一[QStateMachine](qstatemachine.html)已完成其工作。当进入最后的顶级状态，状态机的[finished](qstate.html#finished)（）信号被发射。的一个在一般情况下，当最后的子状态（子[QState](qstate.html)）输入，父状态的[finished](qstate.html#finished)（）信号被发射。 QFinalState是一部分[The State Machine Framework](index.htm)。

要使用一个最终状态，您可以创建一个QFinalState对象，并添加从另一个状态过渡到它。例如：

```
 [QPushButton](qpushbutton.html) button;

 [QStateMachine](qstatemachine.html) machine;
 [QState](qstate.html) *s1 = new [QState](qstate.html)();
 QFinalState *s2 = new QFinalState();
 s1->addTransition(&button, SIGNAL(clicked()), s2);
 machine.addState(s1);
 machine.addState(s2);

 [QObject](qobject.html).connect(&machine, SIGNAL(finished()), [QApplication](qapplication.html).instance(), SLOT(quit()));
 machine.setInitialState(s1);
 machine.start();

```

* * *

## Method Documentation

```
QFinalState.__init__ (self, QState parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QFinalState](qfinalstate.html)与给定对象_parent_状态。

```
bool QFinalState.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QFinalState.onEntry (self, QEvent event)
```

从重新实现[QAbstractState.onEntry](qabstractstate.html#onEntry)（ ） 。

```
QFinalState.onExit (self, QEvent event)
```

从重新实现[QAbstractState.onExit](qabstractstate.html#onExit)（ ） 。