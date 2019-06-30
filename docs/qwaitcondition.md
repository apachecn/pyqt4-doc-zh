# QWaitCondition Class Reference

## [[QtCore](index.htm) module]

该QWaitCondition类提供了线程同步的条件变量。[More...](#details)

### Methods

*   `__init__ (self)`
*   `bool wait (self, QMutex mutex, int msecs = ULONG_MAX)`
*   `bool wait (self, QReadWriteLock readWriteLock, int msecs = ULONG_MAX)`
*   `wakeAll (self)`
*   `wakeOne (self)`

* * *

## Detailed Description

该QWaitCondition类提供了线程同步的条件变量。

QWaitCondition允许一个线程告诉某种条件已经满足其他线程。一个或多个线程可以阻塞等待QWaitCondition设置的条件与[wakeOne](qwaitcondition.html#wakeOne)（）或[wakeAll](qwaitcondition.html#wakeAll)（ ） 。使用[wakeOne](qwaitcondition.html#wakeOne)（ ）来唤醒中随机选择的条件或[wakeAll](qwaitcondition.html#wakeAll)（ ）来唤醒他们。

例如，让我们假设我们有每当用户按下一个键应该执行三项任务。每个任务可以被分成一个线程，每一个都具有一[run()](qthread.html#run)身体是这样的：

```
 forever {
     mutex.lock();
     keyPressed.wait(&mutex);
     do_something();
     mutex.unlock();
 }

```

这里，本`keyPressed`变量的类型QWaitCondition的全局变量。

第四个线程将读取按键和每收到一个，比如这个时候唤醒其它三个线程了：

```
 forever {
     getchar();
     keyPressed.wakeAll();
 }

```

其中三个线程被唤醒的顺序是不确定的。此外，如果某些线程仍在`do_something()`当按键被按下时，他们不会被唤醒（因为他们没有等待条件变量） ，所以该任务将不会为该按键来执行。这个问题可以用一个计数器和一个可以解决[QMutex](qmutex.html)守护它。例如，这里的工作线程新的代码：

```
 forever {
     mutex.lock();
     keyPressed.wait(&mutex);
     ++count;
     mutex.unlock();

     do_something();

     mutex.lock();
     --count;
     mutex.unlock();
 }

```

下面是第四个线程的代码：

```
 forever {
     getchar();

     mutex.lock();
     // Sleep until there are no busy worker threads
     while (count > 0) {
         mutex.unlock();
         sleep(1);
         mutex.lock();
     }
     keyPressed.wakeAll();
     mutex.unlock();
 }

```

互斥锁是必要的，因为两个线程试图改变同一个变量的值的结果同时是不可预知的。

等待条件是一个强大的线程同步原语。该[Wait Conditions](index.htm)示例显示了如何使用QWaitCondition作为替代[QSemaphore](qsemaphore.html)用于控制访问环形缓冲器由一个生产者线程和消费者线程共享。

* * *

## Method Documentation

```
QWaitCondition.__init__ (self)
```

构造一个新的等待条件的对象。

```
bool QWaitCondition.wait (self, QMutex mutex, int msecs = ULONG_MAX)
```

释放锁定_mutex_并等待在等待条件。该_mutex_必须首先锁定调用线程。如果_mutex_是不是在锁定状态，该函数将立即返回。如果_mutex_是一个递归互斥体，该函数立即返回。该_mutex_将被解锁，并且调用线程将被阻塞，直到下列任一条件满足：

*   Another thread signals it using [wakeOne](qwaitcondition.html#wakeOne)() or [wakeAll](qwaitcondition.html#wakeAll)(). This function will return true in this case.
*   _time_ milliseconds has elapsed. If _time_ is `ULONG_MAX` (the default), then the wait will never timeout (the event must be signalled). This function will return false if the wait timed out.

互斥将被返回到相同的锁定状态。这个功能被提供，以允许从锁定状态到等待状态的原子跃迁。

**See also** [wakeOne](qwaitcondition.html#wakeOne)（）和[wakeAll](qwaitcondition.html#wakeAll)（ ） 。

```
bool QWaitCondition.wait (self, QReadWriteLock readWriteLock, int msecs = ULONG_MAX)
```

释放锁定_readWriteLock_并等待在等待条件。该_readWriteLock_必须首先锁定调用线程。如果_readWriteLock_是不是在锁定状态，该函数将立即返回。该_readWriteLock_不能被递归锁定，否则此功能将无法正常释放该锁。该_readWriteLock_将被解锁，并且调用线程将被阻塞，直到下列任一条件满足：

*   Another thread signals it using [wakeOne](qwaitcondition.html#wakeOne)() or [wakeAll](qwaitcondition.html#wakeAll)(). This function will return true in this case.
*   _time_ milliseconds has elapsed. If _time_ is `ULONG_MAX` (the default), then the wait will never timeout (the event must be signalled). This function will return false if the wait timed out.

该_readWriteLock_将返回到相同的锁定状态。这个功能被提供，以允许从锁定状态到等待状态的原子跃迁。

此功能被引入Qt的4.4 。

**See also** [wakeOne](qwaitcondition.html#wakeOne)（）和[wakeAll](qwaitcondition.html#wakeAll)（ ） 。

```
QWaitCondition.wakeAll (self)
```

唤醒等待等待条件的所有线程。在该线程被唤醒的顺序依赖于操作系统的调度策略，并不能被控制或预测。

**See also** [wakeOne](qwaitcondition.html#wakeOne)（ ） 。

```
QWaitCondition.wakeOne (self)
```

唤醒等待的一个线程等待条件。该被唤醒的线程依赖于操作系统的调度策略，并且不能被控制或预测。

如果你想唤醒一个特定的线程，该解决方案通常使用不同的等待状态，并有不同的线程在等待不同的条件。

**See also** [wakeAll](qwaitcondition.html#wakeAll)（ ） 。