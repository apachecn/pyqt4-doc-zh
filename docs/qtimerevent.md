# QTimerEvent Class Reference

## [[QtCore](index.htm) module]

该QTimerEvent类包含描述一个计时器事件参数。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, int timerId)`
*   `__init__ (self, QTimerEvent)`
*   `int timerId (self)`

* * *

## Detailed Description

该QTimerEvent类包含描述一个计时器事件参数。

计时器事件被定期发送到已经开始的一个或多个定时器对象。每个定时器都有一个唯一的标识符。将定时器开始[QObject.startTimer](qobject.html#startTimer)（ ） 。

该[QTimer](qtimer.html)类提供了一个使用信号，而不是事件的高层次的编程接口。它还提供单触发定时器。

该事件处理程序[QObject.timerEvent](qobject.html#timerEvent)（ ）接收计时器事件。

* * *

## Method Documentation

```
QTimerEvent.__init__ (self, int timerId)
```

构造一个计时器事件对象的定时器标识符设置为_timerId_。

```
QTimerEvent.__init__ (self, QTimerEvent)
```

```
int QTimerEvent.timerId (self)
```

返回计时器独特的标识符，它是相同的标识符作为从返回[QObject.startTimer](qobject.html#startTimer)（ ） 。