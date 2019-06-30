# QReadWriteLock Class Reference

## [[QtCore](index.htm) module]

该QReadWriteLock类提供的读写锁。[More...](#details)

### Types

*   `enum RecursionMode { NonRecursive, Recursive }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, RecursionMode recursionMode)`
*   `lockForRead (self)`
*   `lockForWrite (self)`
*   `bool tryLockForRead (self)`
*   `bool tryLockForRead (self, int timeout)`
*   `bool tryLockForWrite (self)`
*   `bool tryLockForWrite (self, int timeout)`
*   `unlock (self)`

* * *

## Detailed Description

该QReadWriteLock类提供的读写锁。

读写锁是一个同步工具，用于保护可用于读取和写入访问的资源。如果你想允许多个线程同时有只读访问这个类型的锁是有用的，但只要有一个线程要写入的资源，所有其它线程必须被阻止，直到写入完成。

在许多情况下， QReadWriteLock是一个直接竞争者[QMutex](qmutex.html)。 QReadWriteLock是一个不错的选择，如果有许多并发读取和写入发生很少。

例如：

```
 QReadWriteLock lock;

 void ReaderThread.run()
 {
     ...
     lock.lockForRead();
     read_file();
     lock.unlock();
     ...
 }

 void WriterThread.run()
 {
     ...
     lock.lockForWrite();
     write_file();
     lock.unlock();
     ...
 }

```

以确保作家不是由读者永远阻塞，读者试图获取锁不会如果有阻塞作家等待访问，即使锁定目前仅由其它读者访问成功。此外，如果该锁由一个作家访问和另一位作家进来，那笔者将优先于该也可能会等待任何读者。

喜欢[QMutex](qmutex.html)，一个QReadWriteLock可以在构建时被递归锁定由同一个线程[QReadWriteLock.RecursionMode](qreadwritelock.html#RecursionMode-enum)。在这种情况下，[unlock](qreadwritelock.html#unlock)（ ）必须被调用的次数相同[lockForWrite](qreadwritelock.html#lockForWrite)（）或[lockForRead](qreadwritelock.html#lockForRead)（ ）被调用。需要注意的是试图以递归方式锁定，也就是说，它是不可能的读锁，在已经锁定写（反之亦然）一个线程，当锁定类型不能改变。

* * *

## Type Documentation

```
QReadWriteLock.RecursionMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QReadWriteLock.Recursive` | `1` | 在这种模式下，一个线程可以锁定同一[QReadWriteLock](qreadwritelock.html)多次与互斥不会被解锁，直到相应数量的[unlock](qreadwritelock.html#unlock)（ ）的调用而制定的。 |
| `QReadWriteLock.NonRecursive` | `0` | 在这种模式下，一个线程可能仅锁定[QReadWriteLock](qreadwritelock.html)一次。 |

这个枚举被引入或修改的Qt 4.4 。

**See also** [QReadWriteLock](qreadwritelock.html#QReadWriteLock)（ ） 。

* * *

## Method Documentation

```
QReadWriteLock.__init__ (self)
```

构造一个[QReadWriteLock](qreadwritelock.html)在对象[NonRecursive](qreadwritelock.html#RecursionMode-enum)模式。

**See also** [lockForRead](qreadwritelock.html#lockForRead)（）和[lockForWrite](qreadwritelock.html#lockForWrite)（ ） 。

```
QReadWriteLock.__init__ (self, RecursionMode recursionMode)
```

构造一个[QReadWriteLock](qreadwritelock.html)在给定的对象_recursionMode_。

此功能被引入Qt的4.4 。

**See also** [lockForRead](qreadwritelock.html#lockForRead)（ ）[lockForWrite](qreadwritelock.html#lockForWrite)（）和[RecursionMode](qreadwritelock.html#RecursionMode-enum)。

```
QReadWriteLock.lockForRead (self)
```

锁读锁。此函数将阻塞当前线程，如果任何线程（包括当前）已锁定用于写入。

**See also** [unlock](qreadwritelock.html#unlock)（ ）[lockForWrite](qreadwritelock.html#lockForWrite)（）和[tryLockForRead](qreadwritelock.html#tryLockForRead)（ ） 。

```
QReadWriteLock.lockForWrite (self)
```

锁写锁。此函数将阻塞当前线程，如果另一个线程已锁定读取或写入。

**See also** [unlock](qreadwritelock.html#unlock)（ ）[lockForRead](qreadwritelock.html#lockForRead)（）和[tryLockForWrite](qreadwritelock.html#tryLockForWrite)（ ） 。

```
bool QReadWriteLock.tryLockForRead (self)
```

尝试读锁。如果获得了锁，这个函数返回True ，否则返回，而不是等待该锁虚假变得可用，也就是说，它不会阻塞。

如果另一个线程已锁定用于写入的锁定尝试将会失败。

如果获得了锁，该锁必须被解锁[unlock](qreadwritelock.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

**See also** [unlock](qreadwritelock.html#unlock)（）和[lockForRead](qreadwritelock.html#lockForRead)（ ） 。

```
bool QReadWriteLock.tryLockForRead (self, int timeout)
```

这是一个重载函数。

尝试读锁。如果获得了锁这个函数返回True，否则返回False 。如果另一个线程已锁定的文笔，这个函数将等待最多_timeout_毫秒为锁变得可用。

注意：传递一个负数作为_timeout_相当于调用[lockForRead](qreadwritelock.html#lockForRead)（ ） ，即该函数将一直等待，直到锁可以锁定读数时_timeout_是负的。

如果获得了锁，该锁必须被解锁[unlock](qreadwritelock.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

**See also** [unlock](qreadwritelock.html#unlock)（）和[lockForRead](qreadwritelock.html#lockForRead)（ ） 。

```
bool QReadWriteLock.tryLockForWrite (self)
```

尝试写锁。如果获得了锁，则该函数返回True，否则，它会立即返回False 。

如果另一个线程已锁定用于读取或写入锁定的尝试将会失败。

如果获得了锁，该锁必须被解锁[unlock](qreadwritelock.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

**See also** [unlock](qreadwritelock.html#unlock)（）和[lockForWrite](qreadwritelock.html#lockForWrite)（ ） 。

```
bool QReadWriteLock.tryLockForWrite (self, int timeout)
```

这是一个重载函数。

尝试写锁。如果获得了锁这个函数返回True，否则返回False 。如果另一个线程已锁定用于读取或写入时，此功能会等待最多_timeout_毫秒为锁变得可用。

注意：传递一个负数作为_timeout_相当于调用[lockForWrite](qreadwritelock.html#lockForWrite)（ ） ，即该函数将一直等待，直到锁可以锁定写入时_timeout_是负的。

如果获得了锁，该锁必须被解锁[unlock](qreadwritelock.html#unlock)（ ）之前，另一个线程可以成功地将其锁定。

**See also** [unlock](qreadwritelock.html#unlock)（）和[lockForWrite](qreadwritelock.html#lockForWrite)（ ） 。

```
QReadWriteLock.unlock (self)
```

解除锁定。

试图解锁未锁定的锁是一个错误，将导致程序终止。

**See also** [lockForRead](qreadwritelock.html#lockForRead)（ ）[lockForWrite](qreadwritelock.html#lockForWrite)（ ）[tryLockForRead](qreadwritelock.html#tryLockForRead)（）和[tryLockForWrite](qreadwritelock.html#tryLockForWrite)（ ） 。