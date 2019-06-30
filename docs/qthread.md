# QThread Class Reference

## [[QtCore](index.htm) module]

在QThread中的类提供了一个平台无关的方式来管理线程。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Priority { IdlePriority, LowestPriority, LowPriority, NormalPriority, ..., InheritPriority }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int exec_ (self)`
*   `exit (self, int returnCode = 0)`
*   `bool isFinished (self)`
*   `bool isRunning (self)`
*   `Priority priority (self)`
*   `quit (self)`
*   `run (self)`
*   `setPriority (self, Priority priority)`
*   `setStackSize (self, int stackSize)`
*   `int stackSize (self)`
*   `start (self, Priority priority = QThread.InheritPriority)`
*   `terminate (self)`
*   `bool wait (self, int msecs = ULONG_MAX)`

### Static Methods

*   `QThread currentThread ()`
*   `int currentThreadId ()`
*   `int idealThreadCount ()`
*   `msleep (int)`
*   `setTerminationEnabled (bool enabled = True)`
*   `sleep (int)`
*   `usleep (int)`
*   `yieldCurrentThread ()`

### Qt Signals

*   `void finished ()`
*   `void started ()`
*   `void terminated ()`

* * *

## Detailed Description

在QThread中的类提供了一个平台无关的方式来管理线程。

一个QThread中对象管理程序中控制一个线程。 QThreads开始执行的[run](qthread.html#run)（ ） 。默认情况下，[run](qthread.html#run)（ ）通过调用启动事件循环[exec_](qthread.html#exec)（ ）并运行里面的线程Qt的事件循环。

您可以使用它们移动到线程使用工作对象[QObject.moveToThread](qobject.html#moveToThread)（ ） 。

```
 class Worker : public [QObject](qobject.html)
 {
     Q_OBJECT
     QThread workerThread;

 public slots:
     void doWork(const [QString](qstring.html) &parameter) {
         // ...
         emit resultReady(result);
     }

 signals:
     void resultReady(const [QString](qstring.html) &result);
 };

 class Controller : public [QObject](qobject.html)
 {
     Q_OBJECT
     QThread workerThread;
 public:
     Controller() {
         Worker *worker = new Worker;
         worker->moveToThread(&workerThread);
         connect(workerThread, SIGNAL(finished()), worker, SLOT(deleteLater()));
         connect(this, SIGNAL(operate([QString](qstring.html))), worker, SLOT(doWork([QString](qstring.html))));
         connect(worker, SIGNAL(resultReady([QString](qstring.html))), this, SLOT(handleResults([QString](qstring.html))));
         workerThread.start();
     }
     ~Controller() {
         workerThread.quit();
         workerThread.wait();
     }
 public slots:
     void handleResults(const [QString](qstring.html) &);
 signals:
     void operate(const [QString](qstring.html) &);
 };

```

那么工人的插槽内的代码将在一个单独的线程中执行。但是，你可以自由的工人插槽连接到任何信号，任何物体，在任何线程。它是安全的连接在不同的线程信号和槽，这要归功于一个叫机制[queued connections](qt.html#ConnectionType-enum)。

另一种方法，使代码运行在一个单独的线程，是子类化QThread中，并重新实现[run](qthread.html#run)（ ） 。例如：

在这个例子中，该线程将退出运行函数返回之后。不会有任何事件循环运行的线程，除非你调用[exec_](qthread.html#exec)（ ） 。

重要的是要记住，一个QThread中的对象通常生活在它被创建的线程，而不是在它管理的线程是很重要的。这经常被忽视的细节是指一个QThread中的插槽将在其家乡线程的上下文中执行，而不是在它管理的线程的上下文中。出于这个原因，在QThread中的子类实现新的插槽是容易出错和气馁。

**Note:**如果你与对象交互，使用任何比排队的信号/插槽连接（例如直接函数调用）等技术，那么就需要平时多线程的预防措施才能作出。

**Note:**这是不可能改变GUI对象的线程关联，它们必须保持在主线程中。

### Managing threads

QThread中会通过当线程是一个信号notifiy你[started](qthread.html#started)（ ）[finished](qthread.html#finished)（）和[terminated](qthread.html#terminated)（ ） ，也可以使用[isFinished](qthread.html#isFinished)（）和[isRunning](qthread.html#isRunning)（ ）来查询线程的状态。

你可以通过调用停止线程[exit](qthread.html#exit)（）或[quit](qthread.html#quit)（ ） 。在极端情况下，你可能要强行[terminate](qthread.html#terminate)（ ）正在执行的线程。但是，这样做是危险的，气馁。请阅读文档[terminate](qthread.html#terminate)（）和[setTerminationEnabled](qthread.html#setTerminationEnabled)（ ）的详细信息。

在Qt 4.8起，它可以释放生活在刚刚结束的线程对象，通过连接[finished](qthread.html#finished)（）信号来[QObject.deleteLater](qobject.html#deleteLater)（ ） 。

使用[wait](qthread.html#wait)（）来阻塞调用线程，直到其他线程执行完毕（或者直到指定的时间已经过去了） 。

静态函数[currentThreadId](qthread.html#currentThreadId)（）和[currentThread](qthread.html#currentThread)（ ）返回标识当前正在执行的线程。前者返回该线程的平台特定的ID ，后者返回一个QThread中的指针。

要选择你的线程将给予（如确定该命令的名称`ps -L`在Linux上，例如） ，你可以调用[setObjectName()](qobject.html#objectName-prop)前启动线程。如果你不打电话[setObjectName()](qobject.html#objectName-prop)，给你的线程的名称将是你的线程对象的运行时类型（例如类名，`"RenderThread"`在的情况下[Mandelbrot Example](index.htm)，因为这是QThread中的子类的名称） 。请注意，这是目前不可用发布版本的Windows 。

QThread中还提供了静态的，平台独立的睡眠功能：[sleep](qthread.html#sleep)（ ）[msleep](qthread.html#msleep)（）和[usleep](qthread.html#usleep)（ ）允许完整秒，毫秒和微秒分辨率分别。

**Note:** [wait](qthread.html#wait)（ ）和[sleep](qthread.html#sleep)（）函数应该是不必要的，一般的，因为Qt是事件驱动型的框架。而不是[wait](qthread.html#wait)（ ） ，考虑侦听[finished](qthread.html#finished)（）信号。取而代之的是[sleep](qthread.html#sleep)（ ）函数，可以考虑使用[QTimer](qtimer.html)。

* * *

## Type Documentation

```
QThread.Priority
```

该枚举类型表示操作系统应该如何安排新创建的线程。

| Constant | Value | Description |
| --- | --- | --- |
| `QThread.IdlePriority` | `0` | 定没有其他线程正在运行时才能使用。 |
| `QThread.LowestPriority` | `1` | 定频率低于LowPriority 。 |
| `QThread.LowPriority` | `2` | 定频率低于NormalPriority 。 |
| `QThread.NormalPriority` | `3` | 操作系统的默认优先级。 |
| `QThread.HighPriority` | `4` | 预计往往比NormalPriority 。 |
| `QThread.HighestPriority` | `5` | 预计往往高优先。 |
| `QThread.TimeCriticalPriority` | `6` | 尽可能多地如期举行。 |
| `QThread.InheritPriority` | `7` | 使用相同的优先级创建线程。这是默认的。 |

* * *

## Method Documentation

```
QThread.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QThread](qthread.html)管理一个新的线程。该_parent_采取所有权[QThread](qthread.html)。该线程不会开始执行，直到[start](qthread.html#start)（）被调用。

**See also** [start](qthread.html#start)（ ） 。

```
QThread QThread.currentThread ()
```

[](qthread.html)

[返回一个指针，指向一个](qthread.html)[QThread](qthread.html)该公司管理当前执行的线程。

```
int QThread.currentThreadId ()
```

返回当前正在执行的线程的线程句柄。

**Warning:**此函数返回的句柄用于内部目的，不应在任何应用程序代码不能使用。

**Warning:**在Windows中，返回值是一个伪句柄为当前线程。它不能被用来进行数值比较。也就是说，这个函数返回由Win32函数getCurrentThread （ ）返回的Win32函数getCurrentThreadId返回的DWORD （ Windows的线程ID ） （ ） ，而不是句柄（ Windows的线程句柄） 。

```
int QThread.exec_ (self)
```

进入事件循环并等待直到[exit](qthread.html#exit)（）被调用，返回传递给该值[exit](qthread.html#exit)（ ） 。返回的值是0，如果[exit](qthread.html#exit)（ ）通过调用[quit](qthread.html#quit)（ ） 。

有必要调用这个函数来启动事件处理。

**See also** [quit](qthread.html#quit)（）和[exit](qthread.html#exit)（ ） 。

```
QThread.exit (self, int returnCode = 0)
```

讲述了线程的事件循环退出与返回代码。

调用该函数后，线程离开事件循环，并从调用返回[QEventLoop.exec](qeventloop.html#exec)（ ） 。该[QEventLoop.exec](qeventloop.html#exec)（ ）函数返回_returnCode_。

按照惯例，_returnCode_0表示成功，非零值表示错误。

请注意，与同名的C库函数，这个函数_does_返回给调用者 - 它是事件处理，停止。

没有QEventLoops将不再启动该线程，直到[QThread.exec](qthread.html#exec)（ ）再次被调用。如果在事件循环[QThread.exec](qthread.html#exec)（ ）是不是下次调用运行，那么[QThread.exec](qthread.html#exec)（ ）也将立即返回。

**See also** [quit](qthread.html#quit)（）和[QEventLoop](qeventloop.html)。

```
int QThread.idealThreadCount ()
```

返回可在系统上运行的线程数理想。这样做是查询处理器内核的数量，实际和逻辑，在系统中。该函数返回-1，如果无法检测到处理器内核的数量。

```
bool QThread.isFinished (self)
```

返回True如果线程完成，否则返回False 。

**See also** [isRunning](qthread.html#isRunning)（ ） 。

```
bool QThread.isRunning (self)
```

返回如果线程正在运行，则为True，否则返回False。

**See also** [isFinished](qthread.html#isFinished)（ ） 。

```
QThread.msleep (int)
```

强制当前线程睡眠_msecs_毫秒。

**See also** [sleep](qthread.html#sleep)（）和[usleep](qthread.html#usleep)（ ） 。

```
Priority QThread.priority (self)
```

[

返回的优先级为一个正在运行的线程。如果线程没有运行，这个函数返回`InheritPriority`。

这个函数是Qt 4.1中引入。

](qthread.html#Priority-enum)

[**See also**](qthread.html#Priority-enum) [Priority](qthread.html#Priority-enum)，[setPriority](qthread.html#setPriority)（）和[start](qthread.html#start)（ ） 。

```
QThread.quit (self)
```

这种方法也是一个Qt槽与C + +的签名`void quit()`。

讲述了线程的事件循环退出，返回代码为0（成功） 。等效于调用QThread.exit （ 0 ） 。

这个函数不执行任何操作，如果线程没有一个事件循环。

**See also** [exit](qthread.html#exit)（）和[QEventLoop](qeventloop.html)。

```
QThread.run (self)
```

的起点的线。后调用[start](qthread.html#start)（ ） ，新创建的线程调用该函数。默认实现调用[exec_](qthread.html#exec)（ ） 。

您可以重新实现这个功能，方便先进的线程管理。从该方法返回将结束线程的执行。

**See also** [start](qthread.html#start)（）和[wait](qthread.html#wait)（ ） 。

```
QThread.setPriority (self, Priority priority)
```

该函数设置_priority_对于一个正在运行的线程。如果线程没有运行，这个函数不执行任何操作并立即返回。使用[start](qthread.html#start)（）开始一个特定的优先级的线程。

该_priority_参数可以在任何值`QThread.Priority`枚举除`InheritPriorty`。

的效果_priority_参数是依赖于操作系统的调度策略。特别是，本_priority_在不支持线程的优先级（如在Linux上，看到http://linux.die.net/man/2/sched_setscheduler更多的细节）系统将被忽略。

这个函数是Qt 4.1中引入。

**See also** [Priority](qthread.html#Priority-enum)，[priority](qthread.html#priority)（）和[start](qthread.html#start)（ ） 。

```
QThread.setStackSize (self, int stackSize)
```

设置为线程的最大堆栈大小_stackSize_。如果_stackSize_大于零，最大的堆栈大小设置为_stackSize_字节，否则的最大堆栈大小是自动由操作系统决定的。

**Warning:**大多数操作系统都放在线程堆栈尺寸最小和最大限制。该线程将无法启动，如果堆栈大小是超出这些限制。

**See also** [stackSize](qthread.html#stackSize)（ ） 。

```
QThread.setTerminationEnabled (bool enabled = True)
```

启用或禁用的基础上，终止当前线程的_enabled_参数。线程必须已经启动了[QThread](qthread.html)。

When _enabled_是假的，终止被禁用。未来的呼叫[QThread.terminate](qthread.html#terminate)（ ）会立即返回而不影响。相反，终止被推迟到终端已启用。

When _enabled_诚然，终端已启用。未来的呼叫[QThread.terminate](qthread.html#terminate)（ ）通常会终止线程。如果终止已推迟（即[QThread.terminate](qthread.html#terminate)（ ）被调用终止禁用） ，这个函数将终止调用线程_immediately_。注意，该函数不会在这种情况下返回。

**See also** [terminate](qthread.html#terminate)（ ） 。

```
QThread.sleep (int)
```

强制当前线程睡眠_secs_秒。

**See also** [msleep](qthread.html#msleep)（）和[usleep](qthread.html#usleep)（ ） 。

```
int QThread.stackSize (self)
```

返回线程的最大堆栈大小（如果设置有[setStackSize](qthread.html#setStackSize)（ ） ） ;否则返回零。

**See also** [setStackSize](qthread.html#setStackSize)（ ） 。

```
QThread.start (self, Priority priority = QThread.InheritPriority)
```

这种方法也是一个Qt槽与C + +的签名`void start(QThread::Priority = QThread.InheritPriority)`。

通过调用开始执行线程[run](qthread.html#run)（ ） 。该操作系统将根据安排线程_priority_参数。如果线程已经在运行，这个函数不执行任何操作。

的效果_priority_参数是依赖于操作系统的调度策略。特别是，本_priority_在不支持线程的优先级（如在Linux上，看到http://linux.die.net/man/2/sched_setscheduler更多的细节）系统将被忽略。

**See also** [run](qthread.html#run)（）和[terminate](qthread.html#terminate)（ ） 。

```
QThread.terminate (self)
```

这种方法也是一个Qt槽与C + +的签名`void terminate()`。

终止线程的执行。该线程可能会或可能不会被立即终止，取决于操作系统的调度策略。监听[terminated](qthread.html#terminated)（）信号，或使用[QThread.wait](qthread.html#wait)（ ）后终止（ ） ，以确保万无一失。

当线程终止时，等待完成线程的所有线程将被唤醒。

**Warning:**这个函数是危险的，它的使用是气馁。该线程可以在它的代码路径中的任何一点被终止。线程可以同时修改数据被终止。没有机会的线程后自行清理，解锁任何持有的互斥锁，等等，总之，使用此功能只有在绝对必要的。

终端可以明确地启用或禁用通过调用[QThread.setTerminationEnabled](qthread.html#setTerminationEnabled)（ ） 。调用此函数，而终止在终止伤残结果被推迟，直到重新启用终止。看到的文档[QThread.setTerminationEnabled](qthread.html#setTerminationEnabled)（ ）获取更多信息。

**See also** [setTerminationEnabled](qthread.html#setTerminationEnabled)（ ） 。

```
QThread.usleep (int)
```

强制当前线程睡眠_usecs_微秒。

**See also** [sleep](qthread.html#sleep)（）和[msleep](qthread.html#msleep)（ ） 。

```
bool QThread.wait (self, int msecs = ULONG_MAX)
```

块的线程，直到下列任一条件满足：

*   The thread associated with this [QThread](qthread.html) object has finished execution (i.e. when it returns from [run](qthread.html#run)()). This function will return true if the thread has finished. It also returns true if the thread has not been started yet.
*   _time_ milliseconds has elapsed. If _time_ is ULONG_MAX (the default), then the wait will never timeout (the thread must return from [run](qthread.html#run)()). This function will return false if the wait timed out.

这提供了类似的功能在POSIX`pthread_join()`功能。

**See also** [sleep](qthread.html#sleep)（）和[terminate](qthread.html#terminate)（ ） 。

```
QThread.yieldCurrentThread ()
```

收益率执行当前线程到另一个线程可运行的，如果有的话。注意，操作系统决定哪个线程切换。

* * *

## Qt Signal Documentation

```
void finished ()
```

这是该信号的默认超载。

当线程执行完这个信号被发射。

**See also** [started](qthread.html#started)（）和[terminated](qthread.html#terminated)（ ） 。

```
void started ()
```

这是该信号的默认超载。

当线程开始执行这个信号被发射。

**See also** [finished](qthread.html#finished)（）和[terminated](qthread.html#terminated)（ ） 。

```
void terminated ()
```

这是该信号的默认超载。

当线程被终止这个信号被发射。

**See also** [started](qthread.html#started)（）和[finished](qthread.html#finished)（ ） 。