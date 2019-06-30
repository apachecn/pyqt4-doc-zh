# QTimer Class Reference

## [[QtCore](index.htm) module]

该QTimer的类提供了重复和单触发定时器。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int interval (self)`
*   `bool isActive (self)`
*   `bool isSingleShot (self)`
*   `setInterval (self, int msec)`
*   `setSingleShot (self, bool asingleShot)`
*   `start (self, int msec)`
*   `start (self)`
*   `stop (self)`
*   `timerEvent (self, QTimerEvent)`
*   `int timerId (self)`

### Static Methods

*   `singleShot (int msec, QObject receiver, SLOT()SLOT() member)`
*   `singleShot (int msec, callable receiver)`

### Qt Signals

*   `void timeout ()`

* * *

## Detailed Description

该QTimer的类提供了重复和单触发定时器。

该QTimer的类提供了一个高层次的编程接口，用于定时器。要使用它，创建一个QTimer的，其连接[timeout](qtimer.html#timeout)（ ）信号到相应的插槽，和呼叫[start](qtimer.html#start)（ ） 。从那时起，它将发出[timeout](qtimer.html#timeout)（）信号以恒定的间隔。

例如对于一个一秒钟（ 1000毫秒）计时器（从[Analog Clock](index.htm)为例）：

```
     QTimer *timer = new QTimer(this);
     connect(timer, SIGNAL(timeout()), this, SLOT(update()));
     timer->start(1000);

```

从这时起，在`update()`槽被调用每一秒。

你可以通过调用setSingleShot （真）设置一个计时器超时只有一次。您也可以使用静态[QTimer.singleShot](qtimer.html#singleShot)（ ）函数在指定的时间间隔后调用一个槽：

```
     QTimer.singleShot(200, this, SLOT(updateCaption()));

```

在多线程应用程序中，您可以在具有一个事件循环的任何线程使用QTimer的。要开始从非GUI线程，使用一个事件循环[QThread.exec](qthread.html#exec)（ ） 。 Qt使用定时器的[thread affinity](qobject.html#thread)以确定哪个线程会放出[timeout()](qtimer.html#timeout)信号。正因为如此，你必须启动和停止在其线程计时器，它是不可能的，开始从另一个线程的计时器。

作为一个特例，为0的超时QTimer的将超时只要在窗口系统的事件队列中的所有事件都被处理。这可以用来做繁重的工作，同时提供迅速的用户界面：

```
     QTimer *timer = new QTimer(this);
     connect(timer, SIGNAL(timeout()), this, SLOT(processOneThing()));
     timer->start();

```

`processOneThing()`将从此被重复调用。它应该写在这样一种方式，它总是很快返回（通常在处理一个数据项之后），这样Qt可以把事件传送给窗口部件，一旦它已经完成了它的一切工作停止计时器。这是实现GUI应用程序中繁重的工作的传统方式，多线程，现在越来越多的平台变得可用，而我们预期的零毫秒QTimers将逐渐被取代[QThread](qthread.html)秒。

### Accuracy and Timer Resolution

定时器永不超时早于指定超时值，他们不能保证超时在指定的精确值。在许多情况下，它们可能会超时迟到了一段时间，它取决于该系统定时器的精度。

定时器的精度取决于底层操作系统和硬件。大多数平台支持1毫秒的分辨率，虽然计时器的精度不会在许多实际情况下等于该决议。

如果Qt是不能传送定时器触发的请求数量，它会悄悄地丢弃一些。

### Alternatives to QTimer

另一种使用QTimer的方法是调用[QObject.startTimer](qobject.html#startTimer)（ ）为对象，并重新实现[QObject.timerEvent](qobject.html#timerEvent)在你的类（）事件处理程序（它必须继承[QObject](qobject.html)） 。其缺点是[timerEvent](qtimer.html#timerEvent)（ ）不支持这种高层次的特点单触发定时器或信号。

另一个替代使用QTimer的方法是使用[QBasicTimer](qbasictimer.html)。它通常比使用较不笨重[QObject.startTimer](qobject.html#startTimer)（ ）直接。看[Timers](index.htm)对于所有三种方法的概述。

某些操作系统会限制定时器，可用于数; Qt会试着解决这些限制。

* * *

## Method Documentation

```
QTimer.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个定时器与给定_parent_。

```
int QTimer.interval (self)
```

```
bool QTimer.isActive (self)
```

```
bool QTimer.isSingleShot (self)
```

```
QTimer.setInterval (self, int msec)
```

```
QTimer.setSingleShot (self, bool asingleShot)
```

```
QTimer.singleShot (int msec, QObject receiver, SLOT()SLOT() member)
```

一个给定的时间间隔后这个静态函数调用一个插槽。

这是非常方便的使用此功能，因为您不需要打扰了[timerEvent](qobject.html#timerEvent)或者创建本地[QTimer](qtimer.html)对象。

例如：

```
 #include <QApplication>
 #include <QTimer>

 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);
     [QTimer](qtimer.html).singleShot(600000, &app, SLOT(quit()));
     ...
     return app.exec();
 }

```

此示例程序10分钟（ 600,000毫秒）后自动终止。

该_receiver_为接收对象和_member_是槽。的时间间隔是_msec_毫秒。

**Note:**这个功能是[reentrant](index.htm#reentrant)。

**See also** [setSingleShot](qtimer.html#singleShot-prop)（）和[start](qtimer.html#start)（ ） 。

```
QTimer.singleShot (int msec, callable receiver)
```

```
QTimer.start (self, int msec)
```

这种方法也是一个Qt槽与C + +的签名`void start(int)`。

开始或重新开始的超时间隔定时器_msec_毫秒。

如果计时器已经在运行，这将是[stopped](qtimer.html#stop)并重新启动。

If [singleShot](qtimer.html#singleShot-prop)诚然，定时器将只能激活一次。

```
QTimer.start (self)
```

这种方法也是一个Qt槽与C + +的签名`void start()`。

这个函数的重载[start](qtimer.html#start)（ ） 。

启动或重新启动在指定的超时定时器[interval](qtimer.html#interval-prop)。

如果计时器已经在运行，这将是[stopped](qtimer.html#stop)并重新启动。

If [singleShot](qtimer.html#singleShot-prop)诚然，定时器将只能激活一次。

```
QTimer.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

停止计时器。

**See also** [start](qtimer.html#start)（ ） 。

```
QTimer.timerEvent (self, QTimerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
int QTimer.timerId (self)
```

返回如果计时器正在运行的定时器的ID ，否则返回-1 。

* * *

## Qt Signal Documentation

```
void timeout ()
```

这是该信号的默认超载。

这个信号被发射时，定时器超时。

**See also** [interval](qtimer.html#interval-prop)，[start](qtimer.html#start)（）和[stop](qtimer.html#stop)（ ） 。