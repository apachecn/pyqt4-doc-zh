# QSignalTransition Class Reference

## [[QtCore](index.htm) module]

The QSignalTransition class provides a transition based on a Qt signal. [More...](#details)

Inherits [QAbstractTransition](qabstracttransition.html).

### Methods

*   `__init__ (self, QState sourceState = None)`
*   `__init__ (self, QObject sender, SIGNAL() signal, QState sourceState = None)`
*   `__init__ (self, signal signal, QState sourceState = None)`
*   `bool event (self, QEvent e)`
*   `bool eventTest (self, QEvent event)`
*   `onTransition (self, QEvent event)`
*   `QObject senderObject (self)`
*   `setSenderObject (self, QObject sender)`
*   `setSignal (self, QByteArray signal)`
*   `QByteArray signal (self)`

* * *

## Detailed Description

The QSignalTransition class provides a transition based on a Qt signal.

通常，您将使用的过载[QState.addTransition](qstate.html#addTransition)（）采用一个发送器和信号作为参数，而不是创建QSignalTransition直接对象。 QSignalTransition是一部分[The State Machine Framework](index.htm)。

你可以继承QSignalTransition和重新实现[eventTest](qsignaltransition.html#eventTest)（ ）方法使一个信号转换条件;传递给事件对象[eventTest](qsignaltransition.html#eventTest)（）将一个[QStateMachine.SignalEvent](index.htm)对象。例如：

```
 class CheckedTransition : public QSignalTransition
 {
 public:
     CheckedTransition([QCheckBox](qcheckbox.html) *check)
         : QSignalTransition(check, SIGNAL(stateChanged(int))) {}
 protected:
     bool eventTest([QEvent](qevent.html) *e) {
         if (!QSignalTransition.eventTest(e))
             return false;
         [QStateMachine](qstatemachine.html).SignalEvent *se = static_cast<[QStateMachine](qstatemachine.html).SignalEvent*>(e);
         return (se->arguments().at(0).toInt() == [Qt](qt.html).Checked);
     }
 };

 ...

 [QCheckBox](qcheckbox.html) *check = new [QCheckBox](qcheckbox.html)();
 check->setTristate(true);

 [QState](qstate.html) *s1 = new [QState](qstate.html)();
 [QState](qstate.html) *s2 = new [QState](qstate.html)();
 CheckedTransition *t1 = new CheckedTransition(check);
 t1->setTargetState(s2);
 s1->addTransition(t1);

```

* * *

## Method Documentation

```
QSignalTransition.__init__ (self, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造具有给定一个新的信号转换_sourceState_。

```
QSignalTransition.__init__ (self, QObject sender, SIGNAL() signal, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造具有给定关联的一个新的信号转换_signal_的给定_sender_，并用给定的_sourceState_。

```
QSignalTransition.__init__ (self, signal signal, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
bool QSignalTransition.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QSignalTransition.eventTest (self, QEvent event)
```

从重新实现[QAbstractTransition.eventTest](qabstracttransition.html#eventTest)（ ） 。

默认实现返回True，如果_event_是[QStateMachine.SignalEvent](index.htm)对象和事件的发送者和信号索引匹配这个过渡，否则返回False 。

```
QSignalTransition.onTransition (self, QEvent event)
```

从重新实现[QAbstractTransition.onTransition](qabstracttransition.html#onTransition)（ ） 。

```
QObject QSignalTransition.senderObject (self)
```

[

```
QSignalTransition.setSenderObject (self, QObject sender)
```

```
QSignalTransition.setSignal (self, QByteArray signal)
```

](qobject.html)

```
QByteArray QSignalTransition.signal (self)
```

[](qbytearray.html)