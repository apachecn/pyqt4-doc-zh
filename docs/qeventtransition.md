# QEventTransition Class Reference

## [[QtCore](index.htm) module]

该QEventTransition类提供了一个[QObject](qobject.html)特定于Qt的事件过渡。[More...](#details)

继承[QAbstractTransition](qabstracttransition.html)。

通过继承[QKeyEventTransition](qkeyeventtransition.html)和[QMouseEventTransition](qmouseeventtransition.html)。

### Methods

*   `__init__ (self, QState sourceState = None)`
*   `__init__ (self, QObject object, QEvent.Type type, QState sourceState = None)`
*   `bool event (self, QEvent e)`
*   `QObject eventSource (self)`
*   `bool eventTest (self, QEvent event)`
*   `QEvent.Type eventType (self)`
*   `onTransition (self, QEvent event)`
*   `setEventSource (self, QObject object)`
*   `setEventType (self, QEvent.Type type)`

* * *

## Detailed Description

该QEventTransition类提供了一个[QObject](qobject.html)特定于Qt的事件过渡。

一个QEventTransition对象的事件绑定到一个特定的[QObject](qobject.html)。 QEventTransition是一部分[The State Machine Framework](index.htm)。

例如：

```
 [QPushButton](qpushbutton.html) *button = ...;
 [QState](qstate.html) *s1 = ...;
 [QState](qstate.html) *s2 = ...;
 // If in s1 and the button receives an Enter event, transition to s2
 QEventTransition *enterTransition = new QEventTransition(button, [QEvent](qevent.html).Enter);
 enterTransition->setTargetState(s2);
 s1->addTransition(enterTransition);
 // If in s2 and the button receives an Exit event, transition back to s1
 QEventTransition *leaveTransition = new QEventTransition(button, [QEvent](qevent.html).Leave);
 leaveTransition->setTargetState(s1);
 s2->addTransition(leaveTransition);

```

### Subclassing

当重新实现[eventTest](qeventtransition.html#eventTest)（ ）函数，你应该先调用基实现，以验证该事件是[QStateMachine.WrappedEvent](index.htm)为正确的对象和事件类型。然后，您可投的情况下，以一[QStateMachine.WrappedEvent](index.htm)并通过调用得到的原始事件[QStateMachine.WrappedEvent.event](index.htm#event)（ ） ，并执行该对象上的额外检查。

* * *

## Method Documentation

```
QEventTransition.__init__ (self, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QEventTransition](qeventtransition.html)与给定对象_sourceState_。

```
QEventTransition.__init__ (self, QObject object, QEvent.Type type, QState sourceState = None)
```

该_sourceState_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QEventTransition](qeventtransition.html)与给定的事件相关联的对象_type_对于给定的_object_，并用给定的_sourceState_。

```
bool QEventTransition.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QObject QEventTransition.eventSource (self)
```

[

```
bool QEventTransition.eventTest (self, QEvent event)
```

](qobject.html)

[从重新实现](qobject.html)[QAbstractTransition.eventTest](qabstracttransition.html#eventTest)（ ） 。

```
QEvent.Type QEventTransition.eventType (self)
```

[

```
QEventTransition.onTransition (self, QEvent event)
```

](qevent.html#Type-enum)

[从重新实现](qevent.html#Type-enum)[QAbstractTransition.onTransition](qabstracttransition.html#onTransition)（ ） 。

```
QEventTransition.setEventSource (self, QObject object)
```

```
QEventTransition.setEventType (self, QEvent.Type type)
```