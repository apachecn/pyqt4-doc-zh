# QSharedMemory Class Reference

## [[QtCore](index.htm) module]

该QSharedMemory类提供了访问一个共享内存段。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum AccessMode { ReadOnly, ReadWrite }`
*   `enum SharedMemoryError { NoError, PermissionDenied, InvalidSize, KeyError, ..., UnknownError }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString key, QObject parent = None)`
*   `bool attach (self, AccessMode mode = QSharedMemory.ReadWrite)`
*   `sip.voidptr constData (self)`
*   `bool create (self, int size, AccessMode mode = QSharedMemory.ReadWrite)`
*   `sip.voidptr data (self)`
*   `bool detach (self)`
*   `SharedMemoryError error (self)`
*   `QString errorString (self)`
*   `bool isAttached (self)`
*   `QString key (self)`
*   `bool lock (self)`
*   `QString nativeKey (self)`
*   `setKey (self, QString key)`
*   `setNativeKey (self, QString key)`
*   `int size (self)`
*   `bool unlock (self)`

* * *

## Detailed Description

该QSharedMemory类提供了访问一个共享内存段。

QSharedMemory提供了多个线程和进程访问共享内存段。它还提供了一种用于单个线程或进程锁定的内存进行独占访问。

当使用这个类时，请注意以下平台的差异：

*   Windows: QSharedMemory does not "own" the shared memory segment. When all threads or processes that have an instance of QSharedMemory attached to a particular shared memory segment have either destroyed their instance of QSharedMemory or exited, the Windows kernel releases the shared memory segment automatically.
*   Unix: QSharedMemory "owns" the shared memory segment. When the last thread or process that has an instance of QSharedMemory attached to a particular shared memory segment detaches from the segment by destroying its instance of QSharedMemory, the Unix kernel release the shared memory segment. But if that last thread or process crashes without running the QSharedMemory destructor, the shared memory segment survives the crash.
*   QNX: Due to possible race conditions in the POSIX IPC implementation, [create](qsharedmemory.html#create)() should be called prior to any [attach](qsharedmemory.html#attach)() calls (even across multiple threads).
*   HP-UX: Only one attach to a shared memory segment is allowed per process. This means that QSharedMemory should not be used across multiple threads in the same process in HP-UX.
*   Symbian: QSharedMemory does not "own" the shared memory segment. When all threads or processes that have an instance of QSharedMemory attached to a particular shared memory segment have either destroyed their instance of QSharedMemory or exited, the Symbian kernel releases the shared memory segment automatically. Also, access to a shared memory segment cannot be limited to read-only in Symbian.

记住用锁定共享内存[lock](qsharedmemory.html#lock)（ ）读取或写入共享内存，并且前记得要与解除锁定[unlock](qsharedmemory.html#unlock)（ ）请在完成后。

不像 [QtSharedMemory](http://qt.digia.com/products/add-on-products/catalog/4/Utilities/qtsharedmemory/)， QSharedMemory自动销毁共享内存段时QSharedMemory的最后一个实例被从段分离，并给段的引用仍然存在。不要混合使用 [QtSharedMemory](http://qt.digia.com/products/add-on-products/catalog/4/Utilities/qtsharedmemory/)和QSharedMemory 。端口一切QSharedMemory 。

**Warning:**QSharedMemory变化的关键在一个Qt特定的方式，除非另有规定。互操作与非Qt应用程序是通过首先创建一个默认的共享内存实现[QSharedMemory](qsharedmemory.html#QSharedMemory)（ ） ，然后设置与本机键[setNativeKey](qsharedmemory.html#setNativeKey)（ ） 。当使用本机键，共享内存是不受保护就可以了多个访问（如无法[lock](qsharedmemory.html#lock)（））和用户定义的机制，用于实现这种保护。

* * *

## Type Documentation

```
QSharedMemory.AccessMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QSharedMemory.ReadOnly` | `0` | 共享内存段是只读的。写入共享内存段是不允许的。写与只读创建一个共享内存段的尝试导致程序中止。 |
| `QSharedMemory.ReadWrite` | `1` | 读取和写入共享内存段都是允许的。 |

```
QSharedMemory.SharedMemoryError
```

| Constant | Value | Description |
| --- | --- | --- |
| `QSharedMemory.NoError` | `0` | 未发生错误。 |
| `QSharedMemory.PermissionDenied` | `1` | 操作失败，因为调用方没有所需的权限。 |
| `QSharedMemory.InvalidSize` | `2` | 创建操作失败，因为请求的大小是无效的。 |
| `QSharedMemory.KeyError` | `3` | 操作失败，因为一个无效的关键。 |
| `QSharedMemory.AlreadyExists` | `4` | A [create](qsharedmemory.html#create)（ ）操作失败，因为具有指定键的共享内存段已经存在。 |
| `QSharedMemory.NotFound` | `5` | 一个[attach](qsharedmemory.html#attach)（ ）失败，因为具有指定键的共享内存段不能被发现。 |
| `QSharedMemory.LockError` | `6` | 企图[lock](qsharedmemory.html#lock)（ ）的共享内存段失败的原因[create](qsharedmemory.html#create)（）或[attach](qsharedmemory.html#attach)（ ）失败，返回False ，或者是因为在发生系统错误[QSystemSemaphore.acquire](qsystemsemaphore.html#acquire)（ ） 。 |
| `QSharedMemory.OutOfResources` | `7` | A [create](qsharedmemory.html#create)（ ）操作失败，因为没有足够的可用内存来满足该请求。 |
| `QSharedMemory.UnknownError` | `8` | 别的事情发生了，这是不好的。 |

* * *

## Method Documentation

```
QSharedMemory.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个共享内存对象与给定_parent_并与将其键值设为_key_。由于其键设置，其[create](qsharedmemory.html#create)（）和[attach](qsharedmemory.html#attach)（ ）函数可以调用。

**See also** [setKey](qsharedmemory.html#setKey)（ ）[create](qsharedmemory.html#create)（）和[attach](qsharedmemory.html#attach)（ ） 。

```
QSharedMemory.__init__ (self, QString key, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这个函数的重载[QSharedMemory](qsharedmemory.html#QSharedMemory)（ ） 。

构造一个共享内存对象与给定_parent_。共享内存对象的关键不是由构造函数中设置，因此共享内存对象没有一个基本的共享内存段连接。该密钥必须与设置[setKey](qsharedmemory.html#setKey)（）或[setNativeKey](qsharedmemory.html#setNativeKey)（ ）前[create](qsharedmemory.html#create)（）或[attach](qsharedmemory.html#attach)（）都可以使用。

**See also** [setKey](qsharedmemory.html#setKey)（ ） 。

```
bool QSharedMemory.attach (self, AccessMode mode = QSharedMemory.ReadWrite)
```

试图连接的过程中确定被传递给构造函数或调用该密钥的共享内存段[setKey](qsharedmemory.html#setKey)（）或[setNativeKey](qsharedmemory.html#setNativeKey)（ ） 。访问_mode_ is [ReadWrite](qsharedmemory.html#AccessMode-enum)在默认情况下。它也可以是[ReadOnly](qsharedmemory.html#AccessMode-enum)。返回True如果连接操作是成功的。如果返回False ，调用[error](qsharedmemory.html#error)（）来判断发生错误。附加共享内存段后，一个指向共享内存可以通过调用获得[data](qsharedmemory.html#data)（ ） 。

**See also** [isAttached](qsharedmemory.html#isAttached)（ ）[detach](qsharedmemory.html#detach)（）和[create](qsharedmemory.html#create)（ ） 。

```
sip.voidptr QSharedMemory.constData (self)
```

返回一个const指针，指向共享内存段的内容，如果已连接。否则返回null 。记住用锁定共享内存[lock](qsharedmemory.html#lock)（ ）读取或写入共享内存，并且前记得要与解除锁定[unlock](qsharedmemory.html#unlock)（ ）请在完成后。

**See also** [attach](qsharedmemory.html#attach)（）和[create](qsharedmemory.html#create)（ ） 。

```
bool QSharedMemory.create (self, int size, AccessMode mode = QSharedMemory.ReadWrite)
```

创建一个共享内存段_size_与传递给构造函数的关键，设置字节[setKey](qsharedmemory.html#setKey)（）或设置[setNativeKey](qsharedmemory.html#setNativeKey)（ ） ，然后附加到给定的接入新的共享内存段_mode_并返回`true`。如果指定了密钥的共享内存段已经存在，则不执行和附加操作`false`返回。当返回值是`false`，调用[error](qsharedmemory.html#error)（）来判断发生错误。

**See also** [error](qsharedmemory.html#error)（ ） 。

```
sip.voidptr QSharedMemory.data (self)
```

返回一个指向共享内存段的内容，如果已连接。否则返回null 。记住用锁定共享内存[lock](qsharedmemory.html#lock)（ ）读取或写入共享内存，并且前记得要与解除锁定[unlock](qsharedmemory.html#unlock)（ ）请在完成后。

**See also** [attach](qsharedmemory.html#attach)（ ） 。

```
bool QSharedMemory.detach (self)
```

从共享内存段分离的过程。如果这是附加到共享内存段的最后一个进程，那么共享内存段被释放系统，即内容被破坏。如果分离的共享内存段的函数返回True 。如果它返回False ，这通常意味着要么没有安装，或者它是由其他进程锁定的段。

**See also** [attach](qsharedmemory.html#attach)（）和[isAttached](qsharedmemory.html#isAttached)（ ） 。

```
SharedMemoryError QSharedMemory.error (self)
```

[

返回一个值，指示是否发生了错误，并且，如果是这样，这是其中的错误。

](qsharedmemory.html#SharedMemoryError-enum)

[**See also**](qsharedmemory.html#SharedMemoryError-enum) [errorString](qsharedmemory.html#errorString)（ ） 。

```
QString QSharedMemory.errorString (self)
```

返回上次发生错误的文本说明。如果[error](qsharedmemory.html#error)（ ）返回一个[error value](qsharedmemory.html#SharedMemoryError-enum)，调用这个函数来获取描述错误的文本字符串。

**See also** [error](qsharedmemory.html#error)（ ） 。

```
bool QSharedMemory.isAttached (self)
```

如果这个过程被附加到共享内存段，则返回True 。

**See also** [attach](qsharedmemory.html#attach)（）和[detach](qsharedmemory.html#detach)（ ） 。

```
QString QSharedMemory.key (self)
```

返回指定的键[setKey](qsharedmemory.html#setKey)（ ）这个共享内存，或null键，如果没有密钥已经被分配，或者如果该段被使用[nativeKey](qsharedmemory.html#nativeKey)（ ） 。关键是使用Qt的应用程序，以确定共享内存段的标识。

你可以找到本地的，特定的平台，重点使用的操作系统通过调用[nativeKey](qsharedmemory.html#nativeKey)（ ） 。

**See also** [setKey](qsharedmemory.html#setKey)（）和[setNativeKey](qsharedmemory.html#setNativeKey)（ ） 。

```
bool QSharedMemory.lock (self)
```

这是一个信号，通过这个进程锁定访问共享内存段并返回True 。如果另一个进程已锁定该段，该功能块，直到该锁被释放。然后，它获得锁并返回True 。如果这个函数返回False ，这意味着你已经忽略了从虚假申报[create](qsharedmemory.html#create)（）或[attach](qsharedmemory.html#attach)（ ） ，您所设定的关键[setNativeKey](qsharedmemory.html#setNativeKey)（ ），或[QSystemSemaphore.acquire](qsystemsemaphore.html#acquire)（ ）失败，原因是未知的系统错误。

**See also** [unlock](qsharedmemory.html#unlock)（ ）[data](qsharedmemory.html#data)（）和[QSystemSemaphore.acquire](qsystemsemaphore.html#acquire)（ ） 。

```
QString QSharedMemory.nativeKey (self)
```

返回本地，特定的平台，关键这个共享内存对象。本机关键是所使用的操作系统，以确定共享内存段的标识。

您可以使用本机键访问还没有被创建了Qt的共享内存段，或授予非Qt应用程序共享内存的访问。

此功能被引入Qt的4.8 。

**See also** [setKey](qsharedmemory.html#setKey)（）和[setNativeKey](qsharedmemory.html#setNativeKey)（ ） 。

```
QSharedMemory.setKey (self, QString key)
```

设置独立于平台_key_这个共享内存对象。如果_key_相同的电流键，则函数返回而不做任何事情。

您可以致电[key](qsharedmemory.html#key)（ ）来检索平台无关的关键。在内部，[QSharedMemory](qsharedmemory.html)此键转换成特定于平台的关键。如果改为调用[nativeKey](qsharedmemory.html#nativeKey)（ ） ，你会得到特定于平台的，转换的关键。

如果共享内存对象附加到底层的共享内存段，它会[detach](qsharedmemory.html#detach)从它设置新键之前。此功能不会做一个[attach](qsharedmemory.html#attach)（ ） 。

**See also** [key](qsharedmemory.html#key)（ ）[nativeKey](qsharedmemory.html#nativeKey)（）和[isAttached](qsharedmemory.html#isAttached)（ ） 。

```
QSharedMemory.setNativeKey (self, QString key)
```

设置本机，特定于平台的，_key_这个共享内存对象。如果_key_是与当前本地密钥，没有做任何函数返回。如果你想要的是分配一个关键段，你应该调用[setKey](qsharedmemory.html#setKey)（ ）来代替。

您可以致电[nativeKey](qsharedmemory.html#nativeKey)（ ）来检索本地密钥。如果本机键已被分配，调用[key](qsharedmemory.html#key)（ ）将返回一个空字符串。

如果共享内存对象附加到底层的共享内存段，它会[detach](qsharedmemory.html#detach)从它设置新键之前。此功能不会做一个[attach](qsharedmemory.html#attach)（ ） 。

如果设置了本机键的应用程序将不能移植。

此功能被引入Qt的4.8 。

**See also** [nativeKey](qsharedmemory.html#nativeKey)（ ）[key](qsharedmemory.html#key)（）和[isAttached](qsharedmemory.html#isAttached)（ ） 。

```
int QSharedMemory.size (self)
```

返回连接的共享内存段的大小。如果没有共享内存段连接，则返回0 。

**See also** [create](qsharedmemory.html#create)（）和[attach](qsharedmemory.html#attach)（ ） 。

```
bool QSharedMemory.unlock (self)
```

发布在共享内存段锁并返回True ，如果锁被该进程持有。如果该段没有被锁定，或者如果锁被另一个进程持有的，没有任何反应并返回False 。

**See also** [lock](qsharedmemory.html#lock)（ ） 。