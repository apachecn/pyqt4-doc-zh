# QSystemSemaphore Class Reference

## [[QtCore](index.htm) module]

该QSystemSemaphore类提供了一个通用的计数系统信号量。[More...](#details)

### Types

*   `enum AccessMode { Open, Create }`
*   `enum SystemSemaphoreError { NoError, PermissionDenied, KeyError, AlreadyExists, ..., UnknownError }`

### Methods

*   `__init__ (self, QString key, int initialValue = 0, AccessMode mode = QSystemSemaphore.Open)`
*   `bool acquire (self)`
*   `SystemSemaphoreError error (self)`
*   `QString errorString (self)`
*   `QString key (self)`
*   `bool release (self, int n = 1)`
*   `setKey (self, QString key, int initialValue = 0, AccessMode mode = QSystemSemaphore.Open)`

* * *

## Detailed Description

该QSystemSemaphore类提供了一个通用的计数系统信号量。

信号量是互斥的推广。当一个互斥可以锁定只有一次，一个信号可以被收购多次。通常情况下，一个信号是用来保护一定数量的相同的资源。

像它的对手更轻[QSemaphore](qsemaphore.html)，一个QSystemSemaphore可以从多个被访问[threads](qthread.html)。不像[QSemaphore](qsemaphore.html)，一个QSystemSemaphore可以从多个也可以访问[processes](qprocess.html)。这意味着QSystemSemaphore是一个更重的类，所以如果你的应用程序并不需要访问多个进程的信号量，你可能会想使用[QSemaphore](qsemaphore.html)。

信号量支持两种基本操作，[acquire](qsystemsemaphore.html#acquire)（）和[release](qsystemsemaphore.html#release)（）：

[acquire](qsystemsemaphore.html#acquire)（ ）试图获取一个资源。如果没有资源可用，呼叫阻塞，直到一个资源变为可用。然后，资源获取和调用返回。

[release](qsystemsemaphore.html#release)（ ）释放一个资源，因此它可以被其他进程获得。该功能也可以被称为具有参数n \u003e 1时，它释放N个资源。

系统信号与一个字符串键创建其他进程可以使用使用相同的信号。

例如：创建一个系统信号量

```
 QSystemSemaphore sem("market", 3, QSystemSemaphore.Create);
                              // resources available == 3
 sem.acquire();               // resources available == 2
 sem.acquire();               // resources available == 1
 sem.acquire();               // resources available == 0
 sem.release();               // resources available == 1
 sem.release(2);              // resources available == 3

```

系统的信号量的一个典型应用是用于控制访问环形缓冲器由一个生产者进程共享和消费者的过程。

### Platform-Specific Behavior

当使用这个类时，请注意以下平台的差异：

**Windows:**QSystemSemaphore并不拥有其底层的系统semaphore 。窗口拥有它。这意味着，当QSystemSemaphore针对特定键的所有实例都被摧毁，要么有自己的析构函数被调用，或者因为一个或多个进程崩溃时，Windows将删除底层的系统semaphore 。

**Unix:**

*   QSystemSemaphore owns the underlying system semaphore in Unix systems. This means that the last process having an instance of QSystemSemaphore for a particular key must remove the underlying system semaphore in its destructor. If the last process crashes without running the QSystemSemaphore destructor, Unix does not automatically remove the underlying system semaphore, and the semaphore survives the crash. A subsequent process that constructs a QSystemSemaphore with the same key will then be given the existing system semaphore. In that case, if the QSystemSemaphore constructor has specified its [access mode](qsystemsemaphore.html#AccessMode-enum) as [Open](qsystemsemaphore.html#AccessMode-enum), its initial resource count will not be reset to the one provided but remain set to the value it received in the crashed process. To protect against this, the first process to create a semaphore for a particular key (usually a server), must pass its [access mode](qsystemsemaphore.html#AccessMode-enum) as [Create](qsystemsemaphore.html#AccessMode-enum), which will force Unix to reset the resource count in the underlying system semaphore.
*   When a process using QSystemSemaphore terminates for any reason, Unix automatically reverses the effect of all acquire operations that were not released. Thus if the process acquires a resource and then exits without releasing it, Unix will release that resource.
*   Symbian: QSystemSemaphore behaves the same as Windows semaphores. In other words, the operating system owns the semaphore and ignores [QSystemSemaphore.AccessMode](qsystemsemaphore.html#AccessMode-enum).

* * *

## Type Documentation

```
QSystemSemaphore.AccessMode
```

此枚举所使用的构造函数和[setKey](qsystemsemaphore.html#setKey)（ ） 。其目的是使处理问题在崩溃的生存信号量的Unix实现。在Unix中，当信号量生存崩溃，我们需要一种方法来迫使它重新设置它的资源数，当系统重新使用信号量。在Windows和Symbian的，其中信号量不能崩溃生存，此枚举有没有效果。

| Constant | Value | Description |
| --- | --- | --- |
| `QSystemSemaphore.Open` | `0` | 如果信号量已经存在，它的初始资源计数不复位。如果信号量不存在，则创建它和它的初始资源计数设置。 |
| `QSystemSemaphore.Create` | `1` | [QSystemSemaphore](qsystemsemaphore.html)采用信号量的所有权，并将其资源数量为请求值，不管信号是否已经存在了有倖存崩溃。此值应传递给构造函数，当第一个信号为一个特定的键构造，你知道，如果信号量已经存在，它只能是因为撞车。在Windows和Symbian的，其中一个信号量不能崩溃生存，创建并打开具有相同的行为。 |

```
QSystemSemaphore.SystemSemaphoreError
```

| Constant | Value | Description |
| --- | --- | --- |
| `QSystemSemaphore.NoError` | `0` | 未发生错误。 |
| `QSystemSemaphore.PermissionDenied` | `1` | 操作失败，因为调用方没有所需的权限。 |
| `QSystemSemaphore.KeyError` | `2` | 操作失败，因为一个无效的关键。 |
| `QSystemSemaphore.AlreadyExists` | `3` | 操作失败，因为具有指定键的系统信号量已经存在。 |
| `QSystemSemaphore.NotFound` | `4` | 操作失败，因为具有指定键的系统信号量不能被发现。 |
| `QSystemSemaphore.OutOfResources` | `5` | 操作失败，因为没有足够的可用内存来满足该请求。 |
| `QSystemSemaphore.UnknownError` | `6` | 别的事情发生了，这是不好的。 |

* * *

## Method Documentation

```
QSystemSemaphore.__init__ (self, QString key, int initialValue = 0, AccessMode mode = QSystemSemaphore.Open)
```

请求系统信号灯指定_key_。参数_initialValue_和_mode_根据下面的规则，这是依赖于系统的使用。

在Unix中，如果_mode_ is [Open](qsystemsemaphore.html#AccessMode-enum)并且系统已经由一个信号量_key_，该信号被使用，并且信号量的资源计数不改变，即_initialValue_被忽略。但如果系统中还没有确定的一个信号_key_，它会为重点的新信号量，并设置其资源计数_initialValue_。

在Unix中，如果_mode_ is [Create](qsystemsemaphore.html#AccessMode-enum)并且系统已经由一个信号量_key_，该信号被使用，并且其资源计数设置为_initialValue_。如果系统中还没有确定的一个信号_key_，它会为重点的新信号量，并设置其资源计数_initialValue_。

在QNX ，如果_mode_ is [Create](qsystemsemaphore.html#AccessMode-enum)并且系统已经由一个信号量_key_，该信号量将被删除，新的人会与资源计数设置为密钥创建_initialValue_。

在Windows和Symbian的，_mode_被忽略，系统总是试图创建一个信号量指定_key_。如果系统中还没有确定为一个信号_key_，它创建了信号量，并设置其资源计数_initialValue_。但是，如果系统中已经有确定的信号_key_它使用信号量，而忽略_initialValue_。

该[mode](qsystemsemaphore.html#AccessMode-enum)参数只适用于Unix系统，以处理一个信号量生存进程崩溃的情况。在这种情况下，下一个进程分配一个信号具有相同的_key_将获得生还的信号，除非_mode_ is [Create](qsystemsemaphore.html#AccessMode-enum)，资源计数不会被重置_initialValue_但将保留它已由坠毁过程中给出的初始值。

**See also** [acquire](qsystemsemaphore.html#acquire)（）和[key](qsystemsemaphore.html#key)（ ） 。

```
bool QSystemSemaphore.acquire (self)
```

获取通过这个信号量把守的资源之一，如果有一个可用的，则返回True 。如果把这个信号量把守的资源已被收购，呼叫阻塞，直到其中一人被释放由另一个进程或具有相同的密钥信号量的线程。

如果返回False ，表示发生了系统错误。通话[error](qsystemsemaphore.html#error)（）来得到一个值[QSystemSemaphore.SystemSemaphoreError](qsystemsemaphore.html#SystemSemaphoreError-enum)指示发生错误。

**See also** [release](qsystemsemaphore.html#release)（ ） 。

```
SystemSemaphoreError QSystemSemaphore.error (self)
```

[

返回一个值，指示是否发生了错误，并且，如果是这样，这是其中的错误。

](qsystemsemaphore.html#SystemSemaphoreError-enum)

[**See also**](qsystemsemaphore.html#SystemSemaphoreError-enum) [errorString](qsystemsemaphore.html#errorString)（ ） 。

```
QString QSystemSemaphore.errorString (self)
```

返回上次发生错误的文本说明。如果[error](qsystemsemaphore.html#error)（ ）返回一个[error value](qsystemsemaphore.html#SystemSemaphoreError-enum)，调用这个函数来获取描述错误的文本字符串。

**See also** [error](qsystemsemaphore.html#error)（ ） 。

```
QString QSystemSemaphore.key (self)
```

返回分配给本系统信号量的关键。最关键的是通过它的信号可以从其他进程访问的名称。

**See also** [setKey](qsystemsemaphore.html#setKey)（ ） 。

```
bool QSystemSemaphore.release (self, int n = 1)
```

发布_n_资源的信号量把守。返回True除非有一个系统错误。

例如：创建有五个资源的系统信号量，获取所有这些，然后释放它们。

```
 [QSystemSemaphore](qsystemsemaphore.html) sem("market", 5, [QSystemSemaphore](qsystemsemaphore.html).Create);
 sem.acquire(5);           // acquire all 5 resources
 sem.release(5);           // release the 5 resources

```

此功能还可以“创造”的资源。例如，马上上述声明的顺序如下，假设我们添加语句：

```
 sem.release(10);          // "create" 10 new resources

```

十大新的资源现在由信号量把守，除了已经存在的五个。你通常不会使用这个函数来创建更多的资源。

**See also** [acquire](qsystemsemaphore.html#acquire)（ ） 。

```
QSystemSemaphore.setKey (self, QString key, int initialValue = 0, AccessMode mode = QSystemSemaphore.Open)
```

此功能的工作方式相同的构造。它这个重构[QSystemSemaphore](qsystemsemaphore.html)对象。如果新的_key_是从旧的密钥不同，调用这个函数就像调用与旧的密钥信号的析构函数，然后调用构造函数来创建一个新的信号量与新_key_。该_initialValue_和_mode_参数的定义与构造。

**See also** [QSystemSemaphore](qsystemsemaphore.html#QSystemSemaphore)（）和[key](qsystemsemaphore.html#key)（ ） 。