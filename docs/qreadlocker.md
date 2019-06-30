# QReadLocker Class Reference

## [[QtCore](index.htm) module]

该QReadLocker类是简化了锁定和解锁读写锁进行读访问一个方便的类。[More...](#details)

### Methods

*   `__init__ (self, QReadWriteLock areadWriteLock)`
*   `QReadWriteLock readWriteLock (self)`
*   `relock (self)`
*   `unlock (self)`

### Special Methods

*   `object __enter__ (self)`
*   `__exit__ (self, object type, object value, object traceback)`

* * *

## Detailed Description

该QReadLocker类是简化了锁定和解锁读写锁进行读访问一个方便的类。

QReadLocker的目的（和[QWriteLocker](qwritelocker.html)）是简化[QReadWriteLock](qreadwritelock.html)锁定和解锁。锁定和解锁语句或异常处理代码很容易出错，难以调试。 QReadLocker可以在这样的情况下使用，以确保始终良好定义的锁的状态。

下面是一个使用QReadLocker锁定和解除锁定读写锁来读取一个例子：

```
 [QReadWriteLock](qreadwritelock.html) lock;

 [QByteArray](qbytearray.html) readData()
 {
     QReadLocker locker(&lock);
     ...
     return data;
 }

```

它等价于下面的代码：

```
 [QReadWriteLock](qreadwritelock.html) lock;

 [QByteArray](qbytearray.html) readData()
 {
     lock.lockForRead();
     ...
     lock.unlock();
     return data;
 }

```

该[QMutexLocker](qmutexlocker.html)文档显示的例子里使用的储物柜对象大大简化了编程。

* * *

## Method Documentation

```
QReadLocker.__init__ (self, QReadWriteLock areadWriteLock)
```

构造一个[QReadLocker](qreadlocker.html)和锁_lock_阅读。锁定将被解除时，[QReadLocker](qreadlocker.html)被破坏。如果`lock`是零，[QReadLocker](qreadlocker.html)什么都不做。

**See also** [QReadWriteLock.lockForRead](qreadwritelock.html#lockForRead)（ ） 。

```
QReadWriteLock QReadLocker.readWriteLock (self)
```

[

返回一个指针被传递给构造函数的读写锁。

```
QReadLocker.relock (self)
```

重新锁定未锁定的锁定。

](qreadwritelock.html)

[**See also**](qreadwritelock.html) [unlock](qreadlocker.html#unlock)（ ） 。

```
QReadLocker.unlock (self)
```

解锁与此相关的更衣柜锁。

**See also** [QReadWriteLock.unlock](qreadwritelock.html#unlock)（ ） 。

```
object QReadLocker.__enter__ (self)
```

```
QReadLocker.__exit__ (self, object type, object value, object traceback)
```