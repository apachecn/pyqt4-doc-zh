# QAbstractEventDispatcher Class Reference

## [[QtCore](index.htm) module]

该QAbstractEventDispatcher类提供了一个接口来管理Qt的事件队列中。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `closingDown (self)`
*   `bool filterEvent (self, sip.voidptr message)`
*   `flush (self)`
*   `bool hasPendingEvents (self)`
*   `interrupt (self)`
*   `bool processEvents (self, QEventLoop.ProcessEventsFlags flags)`
*   `list-of-tuple-of-int-int registeredTimers (self, QObject object)`
*   `registerSocketNotifier (self, QSocketNotifier notifier)`
*   `int registerTimer (self, int interval, QObject object)`
*   `registerTimer (self, int timerId, int interval, QObject object)`
*   `callable setEventFilter (self, callable filter)`
*   `startingUp (self)`
*   `unregisterSocketNotifier (self, QSocketNotifier notifier)`
*   `bool unregisterTimer (self, int timerId)`
*   `bool unregisterTimers (self, QObject object)`
*   `wakeUp (self)`

### Static Methods

*   `QAbstractEventDispatcher instance (QThread thread = None)`

### Qt Signals

*   `void aboutToBlock ()`
*   `void awake ()`

* * *

## Detailed Description

该QAbstractEventDispatcher类提供了一个接口来管理Qt的事件队列中。

事件调度器接收来自窗口系统和其他来源的事件。它然后将它们发送到[QCoreApplication](qcoreapplication.html) or [QApplication](qapplication.html)例如用于处理和传递。 QAbstractEventDispatcher提供细粒度的控制权事件传递。

对于事件的处理使用简单的控制[QCoreApplication.processEvents](qcoreapplication.html#processEvents)（ ） 。

对于应用程序的事件循环的精细控制，呼叫[instance](qabstracteventdispatcher.html#instance)（ ）并调用函数返回的QAbstractEventDispatcher对象。如果你想用你自己的QAbstractEventDispatcher的QAbstractEventDispatcher子类或实例，您必须创建您的实例_before_创建[QApplication](qapplication.html)对象。

主事件循环是通过调用启动[QCoreApplication.exec](qcoreapplication.html#exec)（ ） ，并停止通过调用[QCoreApplication.exit](qcoreapplication.html#exit)（ ） 。这样建立的本地事件循环[QEventLoop](qeventloop.html)。

执行长时间操作的程序可以调用[processEvents](qabstracteventdispatcher.html#processEvents)（ ）用按位或各种组合[QEventLoop.ProcessEventsFlag](qeventloop.html#ProcessEventsFlag-enum)值来控制哪些事件应交付。

QAbstractEventDispatcher还允许一个外部事件循环的Qt的事件循环的集成。例如， Motif的扩展包括QAbstractEventDispatcher的重新实现，合并Qt和Motif的事件一起。

* * *

## Method Documentation

```
QAbstractEventDispatcher.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的事件调度给定的_parent_。

```
QAbstractEventDispatcher.closingDown (self)
```

```
bool QAbstractEventDispatcher.filterEvent (self, sip.voidptr message)
```

发送_message_通过被设置的事件过滤器[setEventFilter](qabstracteventdispatcher.html#setEventFilter)（ ） 。如果没有事件过滤器被设置，这个函数返回False ，否则，这个函数返回的事件过滤器函数的结果。

的子类[QAbstractEventDispatcher](qabstracteventdispatcher.html) _must_调用此函数为_all_从系统收到的信息，以确保与可在应用中使用的任何扩展兼容性。

注意，类型_message_依赖于平台。看[QAbstractEventDispatcher.EventFilter](qabstracteventdispatcher.html#EventFilter-typedef)了解详情。

**See also** [setEventFilter](qabstracteventdispatcher.html#setEventFilter)（ ） 。

```
QAbstractEventDispatcher.flush (self)
```

这种方法是抽象的，应在任何子类中重新实现。

刷新事件队列。这通常几乎立即返回。不执行任何操作平台上比X11等。

```
bool QAbstractEventDispatcher.hasPendingEvents (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果有一个事件的等待，否则返回False 。

```
QAbstractEventDispatcher QAbstractEventDispatcher.instance (QThread thread = None)
```

[

返回一个指向事件调度对象指定_thread_。如果_thread_为零时，当前线程被使用。如果没有事件调度器存在指定的线程，这个函数返回0 。

**Note:**如果Qt的内置，无需线程的支持，_thread_参数将被忽略。

```
QAbstractEventDispatcher.interrupt (self)
```

这种方法是抽象的，应在任何子类中重新实现。

](qabstracteventdispatcher.html)

[中断事件的调度，即事件调度将返回从](qabstracteventdispatcher.html)[processEvents](qabstracteventdispatcher.html#processEvents)（）尽快。

```
bool QAbstractEventDispatcher.processEvents (self, QEventLoop.ProcessEventsFlags flags)
```

这种方法是抽象的，应在任何子类中重新实现。

进程挂起的匹配事件_flags_直到有没有更多的事件来处理。返回True如果一个事件被处理，否则返回False 。

如果你有一个长期运行的操作，要显示其进展，而不允许用户输入，此功能特别有用，即通过使用[QEventLoop.ExcludeUserInputEvents](qeventloop.html#ProcessEventsFlag-enum)标志。

如果[QEventLoop.WaitForMoreEvents](qeventloop.html#ProcessEventsFlag-enum)标志被设置在_flags_，这个函数的行为如下：

*   If events are available, this function returns after processing them.
*   If no events are available, this function will wait until more are available and return after processing newly available events.

如果[QEventLoop.WaitForMoreEvents](qeventloop.html#ProcessEventsFlag-enum)标志没有被设置在_flags_，并没有事件的情况下，这个函数会立即返回。

**Note:**此函数不连续处理事件，它返回后，所有可用的事件被处理。

**See also** [hasPendingEvents](qabstracteventdispatcher.html#hasPendingEvents)（ ） 。

```
list-of-tuple-of-int-int QAbstractEventDispatcher.registeredTimers (self, QObject object)
```

这种方法是抽象的，应在任何子类中重新实现。

返回注册定时器的清单_object_。计时器ID是每对中的第一个成员;的间隔是第二。

```
QAbstractEventDispatcher.registerSocketNotifier (self, QSocketNotifier notifier)
```

这种方法是抽象的，应在任何子类中重新实现。

Registers _notifier_与事件循环。子类必须实现此方法，以配合一个套接字通知到另一个事件循环。

```
int QAbstractEventDispatcher.registerTimer (self, int interval, QObject object)
```

注册一个定时器指定_interval_对于给定的_object_。

```
QAbstractEventDispatcher.registerTimer (self, int timerId, int interval, QObject object)
```

这种方法是抽象的，应在任何子类中重新实现。

注册一个定时器指定_timerId_和_interval_对于给定的_object_。

```
callable QAbstractEventDispatcher.setEventFilter (self, callable filter)
```

该_filter_参数也可能没有。

取代了事件过滤功能，这[QAbstractEventDispatcher](qabstracteventdispatcher.html)同_filter_并返回被替换的事件过滤功能。只有当前事件过滤器函数被调用。如果你想使用这两个过滤功能，节省更换[EventFilter](qabstracteventdispatcher.html#EventFilter-typedef)在一个地方，你可以调用它。

这里设置的事件过滤器函数被调用，用于从事件之前的系统事件循环采取的所有消息被分派到各自的目标，包括并不意味着Qt的对象的消息。

事件过滤器函数应该返回True，如果要过滤的信息， （即停止） 。它应该返回False ，以便处理消息继续。

缺省情况下，事件过滤功能设定（即，这个函数返回一个空[EventFilter](qabstracteventdispatcher.html#EventFilter-typedef)它第一次被调用） 。

```
QAbstractEventDispatcher.startingUp (self)
```

```
QAbstractEventDispatcher.unregisterSocketNotifier (self, QSocketNotifier notifier)
```

这种方法是抽象的，应在任何子类中重新实现。

取消注册_notifier_从事件调度。子类必须重写此方法，以配合一个套接字通知到另一个事件循环。重新实现必须调用基实现。

```
bool QAbstractEventDispatcher.unregisterTimer (self, int timerId)
```

这种方法是抽象的，应在任何子类中重新实现。

注销定时器与给定_timerId_。成功返回True ，否则返回False 。

**See also** [registerTimer](qabstracteventdispatcher.html#registerTimer)（）和[unregisterTimers](qabstracteventdispatcher.html#unregisterTimers)（ ） 。

```
bool QAbstractEventDispatcher.unregisterTimers (self, QObject object)
```

这种方法是抽象的，应在任何子类中重新实现。

取消注册所有与给定的相关联的定时器_object_。返回True如果所有的计时器都成功删除，否则返回False 。

**See also** [unregisterTimer](qabstracteventdispatcher.html#unregisterTimer)（）和[registeredTimers](qabstracteventdispatcher.html#registeredTimers)（ ） 。

```
QAbstractEventDispatcher.wakeUp (self)
```

这种方法是抽象的，应在任何子类中重新实现。

唤醒事件循环。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [awake](qabstracteventdispatcher.html#awake)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToBlock ()
```

这是该信号的默认超载。

事件循环调用，可以阻止一个函数之前，这个信号被发射。

**See also** [awake](qabstracteventdispatcher.html#awake)（ ） 。

```
void awake ()
```

这是该信号的默认超载。

从可以阻止一个函数的事件循环返回后这个信号被发射。

**See also** [wakeUp](qabstracteventdispatcher.html#wakeUp)（）和[aboutToBlock](qabstracteventdispatcher.html#aboutToBlock)（ ） 。