# QBasicTimer Class Reference

## [[QtCore](index.htm) module]

该QBasicTimer类提供了定时器事件的对象。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QBasicTimer)`
*   `bool isActive (self)`
*   `start (self, int msec, QObject obj)`
*   `stop (self)`
*   `int timerId (self)`

* * *

## Detailed Description

该QBasicTimer类提供了定时器事件的对象。

这是由内部的Qt快速，重量轻，低层次的类。我们建议使用更高级别[QTimer](qtimer.html)如果您要使用计时器在你的应用程序类，而不是这个类。请注意，这个定时器是一个重复的计时器，将发送后续的定时器事件，除非[stop](qbasictimer.html#stop)（ ）函数被调用。

要使用这个类，创建一个QBasicTimer ，并调用它的[start](qbasictimer.html#start)（ ）与一个超时间隔和一个指针指向一个函数[QObject](qobject.html)子类。当定时器超时，它会发送一个计时器事件到[QObject](qobject.html)子类。计时器可以在任何时候停止使用[stop](qbasictimer.html#stop)（ ） 。[isActive](qbasictimer.html#isActive)（）对正在运行的定时器返回True ，即它已经开始，还没有达到超时时间，一直没有停止。定时器的ID可以用检索[timerId](qbasictimer.html#timerId)（ ） 。

该[Wiggly](index.htm)示例使用QBasicTimer重绘窗口小部件定期。

* * *

## Method Documentation

```
QBasicTimer.__init__ (self)
```

Contructs一个基本定时器。

**See also** [start](qbasictimer.html#start)（ ） 。

```
QBasicTimer.__init__ (self, QBasicTimer)
```

```
bool QBasicTimer.isActive (self)
```

如果计时器正在运行，并且尚未停止，则返回True ，否则返回False 。

**See also** [start](qbasictimer.html#start)（）和[stop](qbasictimer.html#stop)（ ） 。

```
QBasicTimer.start (self, int msec, QObject obj)
```

启动（或重启）与计时器_msec_毫秒超时。

给定_object_将接收计时器事件。

**See also** [stop](qbasictimer.html#stop)（ ）[isActive](qbasictimer.html#isActive)（）和[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QBasicTimer.stop (self)
```

停止计时器。

**See also** [start](qbasictimer.html#start)（）和[isActive](qbasictimer.html#isActive)（ ） 。

```
int QBasicTimer.timerId (self)
```

返回定时器的ID 。

**See also** [QTimerEvent.timerId](qtimerevent.html#timerId)（ ） 。