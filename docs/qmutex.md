# QMutex Class Reference

## [[QtCore](index.htm) module]

该QMutex类提供线程之间的访问串行化。[More...](#details)

### Types

*   `enum RecursionMode { NonRecursive, Recursive }`

### Methods

*   `__init__ (self, RecursionMode mode = QMutex.NonRecursive)`
*   `lock (self)`
*   `bool tryLock (self)`
*   `bool tryLock (self, int timeout)`
*   `unlock (self)`

* * *

## Detailed Description

该QMutex类提供线程之间的访问串行化。

一个QMutex的目的是保护的对象，数据结构或代码部分，以便只有一个线程可以在同一时间访问它（这类似于Java`synchronized`关键字）。它通常是最好使用一个互斥与[QMutexLocker](qmutexlocker.html)因为这可以很容易地确保锁定和解锁一贯执行。

例如，假设有一个打印一条消息，两行用户的方法：

```
 int number = 6;

 void method1()
 {
     number *= 5;
     number /= 4;
 }

 void method2()
 {
     number *= 3;
     number /= 2;
 }

```

如果这两种方法称为连续，会发生以下情况：

```
 // method1()
 number *= 5;        // number is now 30
 number /= 4;        // number is now 7

 // method2()
 number *= 3;        // number is now 21
 number /= 2;        // number is now 10

```

如果这两种方法都从两个线程同时调用然后按下列顺序会导致：

```
 // Thread 1 calls method1()
 number *= 5;        // number is now 30

 // Thread 2 calls method2().
 //
 // Most likely Thread 1 has been put to sleep by the operating
 // system to allow Thread 2 to run.
 number *= 3;        // number is now 90
 number /= 2;        // number is now 45

 // Thread 1 finishes executing.
 number /= 4;        // number is now 11, instead of 10

```

如果我们添加了一个互斥体，我们应该得到我们想要的结果：

```
 QMutex mutex;
 int number = 6;

 void method1()
 {
     mutex.lock();
     number *= 5;
     number /= 4;
     mutex.unlock();
 }

 void method2()
 {
     mutex.lock();
     number *= 3;
     number /= 2;
     mutex.unlock();
 }

```

那么只有一个线程可以修改`number`在任何给定的时间，其结果是正确的。这是一个简单的例子，当然，但适用于任何其他情况下的事情需要发生在一个特定的顺序。

当你调用[lock](qmutex.html#lock)（ ）在一个线程，其它试图调用线程[lock](qmutex.html#lock)（ ）在同一个地方会阻塞，直到获得该锁调用的线程[unlock](qmutex.html#unlock)（ ） 。非阻塞的替代品[lock](qmutex.html#lock)（）是[tryLock](qmutex.html#tryLock)（ ） 。

* * *

## Type Documentation

```
QMutex.RecursionMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QMutex.Recursive` | `1` | 在这种模式下，一个线程可以锁定同一互斥多次和互斥不会被解锁，直到相应数量的[unlock](qmutex.html#unlock)（ ）的调用而制定的。 |
| `QMutex.NonRecursive` | `0` | 在这种模式下，一个线程可能只锁定一个互斥体一次。 |

**See also** [QMutex](qmutex.html#QMutex)（ ） 。

* * *

## Method Documentation

```
QMutex.__init__ (self, RecursionMode mode = QMutex.NonRecursive)
```

构造一个新的互斥体。互斥锁处于未锁定状态下创建。

If _mode_ is [QMutex.Recursive](qmutex.html#RecursionMode-enum)，一个线程可以锁定同一互斥多次和互斥不会被解锁，直到相应数量的[unlock](qmutex.html#unlock)（ ）的调用而制定的。默认值是[QMutex.NonRecursive](qmutex.html#RecursionMode-enum)。

**See also** [lock](qmutex.html#lock)（）和[unlock](qmutex.html#unlock)（ ） 。

```
QMutex.lock (self)
```

锁定互斥锁。如果另一个线程已锁定互斥锁，则该调用将被阻塞，直到该线程已经解锁了。

调用此函数从同一个线程相同的互斥体多次是允许的，如果这个互斥体是一个[recursive mutex](qmutex.html#RecursionMode-enum)。如果这个互斥体是一个[non-recursive mutex](qmutex.html#RecursionMode-enum)，此功能将_dead-lock_当互斥锁递归锁定。

**See also** [unlock](qmutex.html#unlock)（ ） 。

```
bool QMutex.tryLock (self)
```

试图锁定互斥。如果获得了锁，这个函数返回True。如果另一个线程已锁定互斥锁，则该函数立即返回False 。

如果获得了锁，互斥锁必须被解锁[unlock](qmutex.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

调用此函数从同一个线程相同的互斥体多次是允许的，如果这个互斥体是一个[recursive mutex](qmutex.html#RecursionMode-enum)。如果这个互斥体是一个[non-recursive mutex](qmutex.html#RecursionMode-enum)，此功能将_always_尝试以递归方式锁定互斥时返回False 。

**See also** [lock](qmutex.html#lock)（）和[unlock](qmutex.html#unlock)（ ） 。

```
bool QMutex.tryLock (self, int timeout)
```

这是一个重载函数。

试图锁定互斥。如果获得了锁这个函数返回True，否则返回False 。如果另一个线程已锁定互斥锁，则此功能将等待最多_timeout_毫秒互斥体变得可用。

注意：传递一个负数作为_timeout_相当于调用[lock](qmutex.html#lock)（ ） ，即该函数将一直等待，直到互斥量能，如果被锁定_timeout_是负的。

如果获得了锁，互斥锁必须被解锁[unlock](qmutex.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

调用此函数从同一个线程相同的互斥体多次是允许的，如果这个互斥体是一个[recursive mutex](qmutex.html#RecursionMode-enum)。如果这个互斥体是一个[non-recursive mutex](qmutex.html#RecursionMode-enum)，此功能将_always_尝试以递归方式锁定互斥时返回False 。

**See also** [lock](qmutex.html#lock)（）和[unlock](qmutex.html#unlock)（ ） 。

```
QMutex.unlock (self)
```

解锁互斥量。尝试在不同的线程在一个锁定它会导致一个错误解除锁定互斥锁。解锁未在不确定的行为锁定的互斥锁。

**See also** [lock](qmutex.html#lock)（ ） 。