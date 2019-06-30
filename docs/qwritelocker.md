# QWriteLocker Class Reference

## [[QtCore](index.htm) module]

该QWriteLocker类是简化了锁定和解锁读写锁进行写访问一个方便的类。[More...](#details)

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

该QWriteLocker类是简化了锁定和解锁读写锁进行写访问一个方便的类。

QWriteLocker的目的（和[QReadLocker](qreadlocker.html)是为了简化[QReadWriteLock](qreadwritelock.html)锁定和解锁。锁定和解锁语句或异常处理代码很容易出错，难以调试。 QWriteLocker可以在这样的情况下使用，以确保始终良好定义的锁的状态。

下面是一个使用QWriteLocker锁定和解除锁定读写锁用于写一个例子：

```
 [QReadWriteLock](qreadwritelock.html) lock;

 void writeData(const [QByteArray](qbytearray.html) &data)
 {
     QWriteLocker locker(&lock);
     ...
 }

```

它等价于下面的代码：

```
 [QReadWriteLock](qreadwritelock.html) lock;

 void writeData(const [QByteArray](qbytearray.html) &data)
 {
     lock.lockForWrite();
     ...
     lock.unlock();
 }

```

该[QMutexLocker](qmutexlocker.html)文档显示的例子里使用的储物柜对象大大简化了编程。

* * *

## Method Documentation

```
QWriteLocker.__init__ (self, QReadWriteLock areadWriteLock)
```

构造一个[QWriteLocker](qwritelocker.html)和锁_lock_写作。锁定将被解除时，[QWriteLocker](qwritelocker.html)被破坏。如果`lock`是零，[QWriteLocker](qwritelocker.html)什么都不做。

**See also** [QReadWriteLock.lockForWrite](qreadwritelock.html#lockForWrite)（ ） 。

```
QReadWriteLock QWriteLocker.readWriteLock (self)
```

[

返回一个指针被传递给构造函数的读写锁。

```
QWriteLocker.relock (self)
```

重新锁定未锁定的锁定。

](qreadwritelock.html)

[**See also**](qreadwritelock.html) [unlock](qwritelocker.html#unlock)（ ） 。

```
QWriteLocker.unlock (self)
```

解锁与此相关的更衣柜锁。

**See also** [QReadWriteLock.unlock](qreadwritelock.html#unlock)（ ） 。

```
object QWriteLocker.__enter__ (self)
```

```
QWriteLocker.__exit__ (self, object type, object value, object traceback)
```