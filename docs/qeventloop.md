# QEventLoop Class Reference

## [[QtCore](index.htm) module]

该QEventLoop类提供进入和离开事件循环的方法。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum ProcessEventsFlag { AllEvents, ExcludeUserInputEvents, ExcludeSocketNotifiers, WaitForMoreEvents, X11ExcludeTimers, DeferredDeletion }`
*   `class **[ProcessEventsFlags](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int exec_ (self, ProcessEventsFlags flags = QEventLoop.AllEvents)`
*   `exit (self, int returnCode = 0)`
*   `bool isRunning (self)`
*   `bool processEvents (self, ProcessEventsFlags flags = QEventLoop.AllEvents)`
*   `processEvents (self, ProcessEventsFlags flags, int maximumTime)`
*   `quit (self)`
*   `wakeUp (self)`

* * *

## Detailed Description

该QEventLoop类提供进入和离开事件循环的方法。

在任何时候，你可以创建一个QEventLoop对象，并调用[exec_](qeventloop.html#exec)（ ）就可以启动一个本地事件循环。从事件循环中，调用[exit](qeventloop.html#exit)（ ）将强制[exec_](qeventloop.html#exec)（ ）返回。

* * *

## Type Documentation

```
QEventLoop.ProcessEventsFlag
```

该枚举控制由处理的事件类型[processEvents](qeventloop.html#processEvents)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QEventLoop.AllEvents` | `0x00` | 所有事件。需要注意的是[DeferredDelete](qevent.html#Type-enum)事件经过特殊加工。看[QObject.deleteLater](qobject.html#deleteLater)（ ）的更多细节。 |
| `QEventLoop.ExcludeUserInputEvents` | `0x01` | 不处理用户输入事件，如ButtonPress和按键。请注意，该事件不会被丢弃，它们会在下一次交付[processEvents](qeventloop.html#processEvents)（）被调用，而不ExcludeUserInputEvents标志。 |
| `QEventLoop.ExcludeSocketNotifiers` | `0x02` | 不处理套接字通知事件。请注意，该事件不会被丢弃，它们会在下一次交付[processEvents](qeventloop.html#processEvents)（）被调用，而不ExcludeSocketNotifiers标志。 |
| `QEventLoop.WaitForMoreEvents` | `0x04` | 等待事件，如果没有未处理的事件都可用。 |
| `QEventLoop.DeferredDeletion` | `0x10` | 过时 - 不要使用。 |

该ProcessEventsFlags类型是一个typedef为[QFlags](index.htm)\u003cProcessEventsFlag\u003e 。它存储ProcessEventsFlag值的或组合。

**See also** [processEvents](qeventloop.html#processEvents)（ ） 。

* * *

## Method Documentation

```
QEventLoop.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个事件循环对象与给定_parent_。

```
int QEventLoop.exec_ (self, ProcessEventsFlags flags = QEventLoop.AllEvents)
```

进入主事件循环并等待，直到[exit](qeventloop.html#exit)（）被调用。返回传递给该值[exit](qeventloop.html#exit)（ ） 。

If _flags_被指定，由所允许的类型的唯一事件_flags_将被处理。

有必要调用这个函数来启动事件处理。主事件循环接收事件从窗口系统并调度这些应用程序的部件。

一般来说，没有用户交互可以调用exec （ ）之前发生。作为一种特殊的情况下，模式对话框喜欢[QMessageBox](qmessagebox.html)调用exec （之前可以使用） ，因为模式对话框使用自己的本地事件循环。

为了使您的应用程序执行閒置处理（即执行一个特殊的功能，每当有没有挂起的事件） ，请使用[QTimer](qtimer.html)与0超时。更复杂的空閒处理方案可以用来实现[processEvents](qeventloop.html#processEvents)（ ） 。

**See also** [QApplication.quit](qcoreapplication.html#quit)（ ）[exit](qeventloop.html#exit)（）和[processEvents](qeventloop.html#processEvents)（ ） 。

```
QEventLoop.exit (self, int returnCode = 0)
```

讲述了事件循环退出，并返回代码。

在此之后函数被调用时，事件循环从调用返回[exec_](qeventloop.html#exec)（ ） 。该[exec_](qeventloop.html#exec)（ ）函数返回_returnCode_。

按照惯例，_returnCode_0意味着成功，而任何非零值表示错误。

请注意，与同名的C库函数，这个函数_does_返回给调用者 - 它是事件处理，停止。

**See also** [QCoreApplication.quit](qcoreapplication.html#quit)（ ）[quit](qeventloop.html#quit)（）和[exec_](qeventloop.html#exec)（ ） 。

```
bool QEventLoop.isRunning (self)
```

如果事件循环运行，则返回True ，否则返回False 。事件循环被认为是从时间上运行时[exec_](qeventloop.html#exec)（ ）被调用，直到[exit](qeventloop.html#exit)（）被调用。

**See also** [exec_](qeventloop.html#exec)（）和[exit](qeventloop.html#exit)（ ） 。

```
bool QEventLoop.processEvents (self, ProcessEventsFlags flags = QEventLoop.AllEvents)
```

进程挂起的匹配事件_flags_直到有没有更多的事件来处理。如果返回已处理挂起的事件则为True，否则返回False 。

如果你有一个长期运行的操作，要显示其进展，而不允许用户输入，此功能特别有用，即通过使用[ExcludeUserInputEvents](qeventloop.html#ProcessEventsFlag-enum)标志。

这个函数是一个简单的包装器[QAbstractEventDispatcher.processEvents](qabstracteventdispatcher.html#processEvents)（ ） 。查看该功能的详细信息的文档。

```
QEventLoop.processEvents (self, ProcessEventsFlags flags, int maximumTime)
```

匹配过程中挂起的事件_flags_最多_maxTime_毫秒，或直到没有更多的事件来处理，以较短者为准。如果你有一个长期运行的操作，要显示其进展，而不允许用户输入，此功能特别有用，即通过使用[ExcludeUserInputEvents](qeventloop.html#ProcessEventsFlag-enum)标志。

**Notes:**

*   This function does not process events continuously; it returns after all available events are processed.
*   Specifying the [WaitForMoreEvents](qeventloop.html#ProcessEventsFlag-enum) flag makes no sense and will be ignored.

```
QEventLoop.quit (self)
```

这种方法也是一个Qt槽与C + +的签名`void quit()`。

讲述了事件循环正常退出。

同出口（0）。

**See also** [QCoreApplication.quit](qcoreapplication.html#quit)（）和[exit](qeventloop.html#exit)（ ） 。

```
QEventLoop.wakeUp (self)
```

唤醒事件循环。

**See also** [QAbstractEventDispatcher.wakeUp](qabstracteventdispatcher.html#wakeUp)（ ） 。