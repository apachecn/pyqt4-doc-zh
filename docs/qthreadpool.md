# QThreadPool Class Reference

## [[QtCore](index.htm) module]

该QThreadPool类管理QThreads的集合。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int activeThreadCount (self)`
*   `int expiryTimeout (self)`
*   `int maxThreadCount (self)`
*   `releaseThread (self)`
*   `reserveThread (self)`
*   `setExpiryTimeout (self, int expiryTimeout)`
*   `setMaxThreadCount (self, int maxThreadCount)`
*   `start (self, QRunnable runnable, int priority = 0)`
*   `bool tryStart (self, QRunnable runnable)`
*   `waitForDone (self)`
*   `bool waitForDone (self, int msecs)`

### Static Methods

*   `QThreadPool globalInstance ()`

* * *

## Detailed Description

该QThreadPool类管理QThreads的集合。

QThreadPool管理及recyles个人[QThread](qthread.html)对象以帮助减少在使用线程的程序线程的创建成本。每个Qt的应用程序有一个全局QThreadPool对象，它可以通过调用访问[globalInstance](qthreadpool.html#globalInstance)（ ） 。

要使用一个QThreadPool线程，子类[QRunnable](qrunnable.html)并实现run （ ）虚函数。然后创建类的一个对象，并把它传递给[QThreadPool.start](qthreadpool.html#start)（ ） 。

```
 class HelloWorldTask : public [QRunnable](qrunnable.html)
 {
     void run()
     {
         qDebug() << "Hello world from thread" << [QThread](qthread.html).currentThread();
     }
 }

 HelloWorldTask *hello = new HelloWorldTask();
 // QThreadPool takes ownership and deletes 'hello' automatically
 QThreadPool.globalInstance()->start(hello);

```

QThreadPool删除[QRunnable](qrunnable.html)自动默认。使用[QRunnable.setAutoDelete](qrunnable.html#setAutoDelete)（）来更改自动删除标志。

QThreadPool支持执行相同[QRunnable](qrunnable.html)不止一次被从内部调用tryStart （本）[QRunnable.run](qrunnable.html#run)（ ） 。如果autoDelete启用[QRunnable](qrunnable.html)当最后一个线程退出运行功能将被删除。调用[start](qthreadpool.html#start)（）多次使用相同的[QRunnable](qrunnable.html)当autoDelete启用创造竞争条件，因此不推荐。

线程是未使用一定量的时间会过期。默认的到期超时为30000毫秒（ 30秒） 。这可以使用被改变[setExpiryTimeout](qthreadpool.html#expiryTimeout-prop)（ ） 。设置一个负的到期超时禁用届满机制。

Call [maxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ）来查询所使用的最大线程数。如果需要，你可以更改该限制[setMaxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ） 。默认[maxThreadCount](qthreadpool.html#maxThreadCount-prop)（）是[QThread.idealThreadCount](qthread.html#idealThreadCount)（ ） 。该[activeThreadCount](qthreadpool.html#activeThreadCount-prop)（ ）函数返回目前正在做的工作线程数。

该[reserveThread](qthreadpool.html#reserveThread)（ ）函数保留一个线程外用。使用[releaseThread](qthreadpool.html#releaseThread)（）时，你正在与线程完成的，以便它可以被重新使用。从本质上讲，这些功能暂时增加或减少活动线程数和执行耗时的操作是不可见的QThreadPool时是有用的。

注意， QThreadPool是用于管理线程一个低级别的类，见[QtConcurrent.run](index.htm#run)（）或其他[Qt Concurrent](index.htm)API进行更高层次的替代品。

* * *

## Method Documentation

```
QThreadPool.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个线程池与给定_parent_。

```
int QThreadPool.activeThreadCount (self)
```

```
int QThreadPool.expiryTimeout (self)
```

```
QThreadPool QThreadPool.globalInstance ()
```

[](qthreadpool.html)

[返回全局](qthreadpool.html)[QThreadPool](qthreadpool.html)实例。

```
int QThreadPool.maxThreadCount (self)
```

```
QThreadPool.releaseThread (self)
```

发布一个线程以前通过调用保留[reserveThread](qthreadpool.html#reserveThread)（ ） 。

**Note:**调用此函数之前没有预留一个线程暂时增加[maxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ） 。当一个线程进入睡眠状态，等待更多的工作，让其他线程继续，这是很有用的。一定要调用[reserveThread](qthreadpool.html#reserveThread)（ ）进行等待，从而使线程池可以维持正确的时[activeThreadCount](qthreadpool.html#activeThreadCount-prop)（ ） 。

**See also** [reserveThread](qthreadpool.html#reserveThread)（ ） 。

```
QThreadPool.reserveThread (self)
```

准备一个线程，无视[activeThreadCount](qthreadpool.html#activeThreadCount-prop)（）和[maxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ） 。

一旦你与线程，调用来完成[releaseThread](qthreadpool.html#releaseThread)（）以允许它被重复使用。

**Note:**此功能将随时增加活动线程的数量。这意味着，通过使用此功能，可以为[activeThreadCount](qthreadpool.html#activeThreadCount-prop)（ ）返回的值大于[maxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ） 。

**See also** [releaseThread](qthreadpool.html#releaseThread)（ ） 。

```
QThreadPool.setExpiryTimeout (self, int expiryTimeout)
```

```
QThreadPool.setMaxThreadCount (self, int maxThreadCount)
```

```
QThreadPool.start (self, QRunnable runnable, int priority = 0)
```

保留一个线程，并使用它来运行_runnable_，除非这个线程将会使当前线程数超过[maxThreadCount](qthreadpool.html#maxThreadCount-prop)（ ） 。在这种情况下，_runnable_被添加到一个运行队列来代替。该_priority_参数可以用来控制执行的运行队列的顺序。

需要注意的是线程池需要的所有权_runnable_如果[runnable-&gt;autoDelete()](qrunnable.html#autoDelete)返回True ，而_runnable_会后，由线程池自动删除[runnable-&gt;run()](qrunnable.html#run)回报。如果[runnable-&gt;autoDelete()](qrunnable.html#autoDelete)返回False，所有权_runnable_保持与来电者。注意，改变在自动删除_runnable_调用此函数后，会导致不确定的行为。

```
bool QThreadPool.tryStart (self, QRunnable runnable)
```

尝试保留一个线程来运行_runnable_。

如果没有可用的线程在调用的时候，那么这个函数不执行任何操作并返回False 。否则，_runnable_立即运行使用一个可用的线程，这个函数返回True。

需要注意的是线程池需要的所有权_runnable_如果[runnable-&gt;autoDelete()](qrunnable.html#autoDelete)返回True ，而_runnable_会后，由线程池自动删除[runnable-&gt;run()](qrunnable.html#run)回报。如果[runnable-&gt;autoDelete()](qrunnable.html#autoDelete)返回False，所有权_runnable_保持与来电者。注意，改变在自动删除_runnable_调用此函数后会导致不确定的行为。

```
QThreadPool.waitForDone (self)
```

等待每一个线程退出并删除所有线程的线程池。

```
bool QThreadPool.waitForDone (self, int msecs)
```

这个函数的重载[waitForDone](qthreadpool.html#waitForDone)（ ） 。

最多等待_msecs_毫秒所有线程退出并删除所有线程的线程池。返回True如果被拆除的所有线程，否则返回False 。

此功能被引入Qt的4.8 。