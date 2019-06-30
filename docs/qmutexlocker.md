# QMutexLocker Class Reference

## [[QtCore](index.htm) module]

该QMutexLocker类是简化了锁定和解锁互斥一个方便的类。[More...](#details)

### Methods

*   `__init__ (self, QMutex m)`
*   `QMutex mutex (self)`
*   `relock (self)`
*   `unlock (self)`

### Special Methods

*   `object __enter__ (self)`
*   `__exit__ (self, object type, object value, object traceback)`

* * *

## Detailed Description

该QMutexLocker类是简化了锁定和解锁互斥一个方便的类。

锁定和解锁[QMutex](qmutex.html)在复杂的函数和语句或异常处理代码很容易出错，难以调试。 QMutexLocker可以在这样的情况下使用，以确保始终良好定义的互斥的状态。

QMutexLocker应该在一个函数中创建一个地方[QMutex](qmutex.html)需要被锁定。创建QMutexLocker当互斥被锁定。你可以解锁和重新锁定互斥与`unlock()`和`relock()`。如果被锁定，当QMutexLocker被销毁互斥将被解锁。

例如，这种复杂的功能可以锁定一个[QMutex](qmutex.html)在进入功能和解锁互斥量在所有的出口点：

```
 int complexFunction(int flag)
 {
     mutex.lock();

     int retVal = 0;

     switch (flag) {
     case 0:
     case 1:
         retVal = moreComplexFunction(flag);
         break;
     case 2:
         {
             int status = anotherFunction();
             if (status < 0) {
                 mutex.unlock();
                 return -2;
             }
             retVal = status + flag;
         }
         break;
     default:
         if (flag > 10) {
             mutex.unlock();
             return -1;
         }
         break;
     }

     mutex.unlock();
     return retVal;
 }

```

这个例子功能将变得更加复杂，因为它是发展，从而增加将发生错误的可能性。

使用QMutexLocker大大简化了代码，并使其更具可读性：

```
 int complexFunction(int flag)
 {
     QMutexLocker locker(&mutex);

     int retVal = 0;

     switch (flag) {
     case 0:
     case 1:
         return moreComplexFunction(flag);
     case 2:
         {
             int status = anotherFunction();
             if (status < 0)
                 return -2;
             retVal = status + flag;
         }
         break;
     default:
         if (flag > 10)
             return -1;
         break;
     }

     return retVal;
 }

```

现在，互斥总是会在QMutexLocker对象被销毁（因为当函数返回解锁`locker`是一个自动变量） 。

同样的原则也适用于抛出和捕获异常的代码。未陷入已锁定互斥锁功能异常有没有办法解锁互斥前异常堆栈向上传递到调用函数的。

QMutexLocker还提供了一个`mutex()`成员函数，返回在其上QMutexLocker运行互斥。这对于需要访问互斥的代码很有用，比如[QWaitCondition.wait](qwaitcondition.html#wait)（ ） 。例如：

```
 class SignalWaiter
 {
 private:
     QMutexLocker locker;

 public:
     SignalWaiter([QMutex](qmutex.html) *mutex)
         : locker(mutex)
     {
     }

     void waitForSignal()
     {
         ...
         while (!signalled)
             waitCondition.wait(locker.mutex());
         ...
     }
 };

```

* * *

## Method Documentation

```
QMutexLocker.__init__ (self, QMutex m)
```

构造一个[QMutexLocker](qmutexlocker.html)和锁_mutex_。互斥锁将被解锁时，[QMutexLocker](qmutexlocker.html)被破坏。如果_mutex_是零，[QMutexLocker](qmutexlocker.html)什么都不做。

**See also** [QMutex.lock](qmutex.html#lock)（ ） 。

```
QMutex QMutexLocker.mutex (self)
```

[

返回一个指针，指向被锁在构造函数中的互斥体。

```
QMutexLocker.relock (self)
```

重新锁定未锁定互斥锁储物柜。

](qmutex.html)

[**See also**](qmutex.html) [unlock](qmutexlocker.html#unlock)（ ） 。

```
QMutexLocker.unlock (self)
```

这个解锁互斥锁固剂。您可以使用`relock()`再次锁定。它并不需要被破坏时被锁定。

**See also** [relock](qmutexlocker.html#relock)（ ） 。

```
object QMutexLocker.__enter__ (self)
```

```
QMutexLocker.__exit__ (self, object type, object value, object traceback)
```