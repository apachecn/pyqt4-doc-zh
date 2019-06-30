# QRunnable Class Reference

## [[QtCore](index.htm) module]

该QRunnable类是可运行的所有对象的基类。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QRunnable)`
*   `bool autoDelete (self)`
*   `run (self)`
*   `setAutoDelete (self, bool _autoDelete)`

* * *

## Detailed Description

该QRunnable类是可运行的所有对象的基类。

该QRunnable类是用于表示一个任务或一段代码需要被执行，您的代表重新实现一个接口[run](qrunnable.html#run)（）函数。

您可以使用[QThreadPool](qthreadpool.html)执行你的代码在一个单独的线程。[QThreadPool](qthreadpool.html)自动删除QRunnable如果[autoDelete](qrunnable.html#autoDelete)（ ）返回True （默认值） 。使用[setAutoDelete](qrunnable.html#setAutoDelete)（）来更改自动删除标志。

[QThreadPool](qthreadpool.html)支持执行相同QRunnable不止一次通过从内主叫QThreadPool.tryStart （本）[run](qrunnable.html#run)（）函数。如果autoDelete时启用的最后一个线程退出运行功能的QRunnable将被删除。调用[QThreadPool.start](qthreadpool.html#start)（ ）多次使用时autoDelete启用相同的QRunnable创造竞争条件，因此不推荐。

* * *

## Method Documentation

```
QRunnable.__init__ (self)
```

构造一个[QRunnable](qrunnable.html)。自动删除默认情况下启用。

**See also** [autoDelete](qrunnable.html#autoDelete)（）和[setAutoDelete](qrunnable.html#setAutoDelete)（ ） 。

```
QRunnable.__init__ (self, QRunnable)
```

```
bool QRunnable.autoDelete (self)
```

返回True为自动删除被启用，否则为False 。

如果自动删除已启用，[QThreadPool](qthreadpool.html)在调用后自动删除此可运行[run](qrunnable.html#run)（ ），否则，所有权仍属于该应用程序的程序员。

**See also** [setAutoDelete](qrunnable.html#setAutoDelete)（）和[QThreadPool](qthreadpool.html)。

```
QRunnable.run (self)
```

这种方法是抽象的，应在任何子类中重新实现。

在子类实现这个纯虚函数。

```
QRunnable.setAutoDelete (self, bool _autoDelete)
```

启用自动删除，如果_autoDelete_为True，否则自动删除被禁用。

如果自动删除已启用，[QThreadPool](qthreadpool.html)在调用后自动删除此可运行[run](qrunnable.html#run)（ ），否则，所有权仍属于该应用程序的程序员。

请注意，此标志必须在调用之前设置[QThreadPool.start](qthreadpool.html#start)（ ） 。后调用此函数[QThreadPool.start](qthreadpool.html#start)（ ）产生不确定的行为。

**See also** [autoDelete](qrunnable.html#autoDelete)（）和[QThreadPool](qthreadpool.html)。