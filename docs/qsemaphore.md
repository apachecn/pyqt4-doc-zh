# QSemaphore Class Reference

## [[QtCore](index.htm) module]

该QSemaphore类提供了一个通用的计数信号量。[More...](#details)

### Methods

*   `__init__ (self, int n = 0)`
*   `acquire (self, int n = 1)`
*   `int available (self)`
*   `release (self, int n = 1)`
*   `bool tryAcquire (self, int n = 1)`
*   `bool tryAcquire (self, int n, int timeout)`

* * *

## Detailed Description

该QSemaphore类提供了一个通用的计数信号量。

信号量是互斥的推广。当一个互斥只能被锁定一次，有可能获得一个信号量多次。信号量是通常用于保护一定数量的相同的资源。

信号量支持两种基本操作，[acquire](qsemaphore.html#acquire)（）和[release](qsemaphore.html#release)（）：

*   acquire(_n_) tries to acquire _n_ resources. If there aren't that many resources available, the call will block until this is the case.
*   release(_n_) releases _n_ resources.

还有一个[tryAcquire](qsemaphore.html#tryAcquire)（ ）函数立即返回，如果它不能获得资源，以及[available](qsemaphore.html#available)（）函数，返回可用资源的数量在任何时间。

例如：

```
 QSemaphore sem(5);      // sem.available() == 5

 sem.acquire(3);         // sem.available() == 2
 sem.acquire(2);         // sem.available() == 0
 sem.release(5);         // sem.available() == 5
 sem.release(5);         // sem.available() == 10

 sem.tryAcquire(1);      // sem.available() == 9, returns true
 sem.tryAcquire(250);    // sem.available() == 9, returns false

```

信号量的一个典型应用是用于控制访问环形缓冲器由一个生产者线程和消费者线程共享。该[Semaphores](index.htm)示例显示了如何使用QSemaphore来解决这个问题。

信号量的非计算例子是在餐厅用餐。信号量与椅子在餐厅数初始化。当人们到达时，他们想要一个座位。由于座位填满，[available](qsemaphore.html#available)（ ）递减。随着人们离开，[available](qsemaphore.html#available)（ ）递增，让更多的人进入。如果10人一方想坐下，但只有9个座位，这10人将等待，但4人一党会坐下（以可用座位5 ，使得10人的派对等待更长的时间） 。

* * *

## Method Documentation

```
QSemaphore.__init__ (self, int n = 0)
```

创建一个新的信号量并初始化它扼守资源的数量_n_（默认为0 ） 。

**See also** [release](qsemaphore.html#release)（）和[available](qsemaphore.html#available)（ ） 。

```
QSemaphore.acquire (self, int n = 1)
```

试图获取`n`资源的信号量把守。如果_n_\u003e[available](qsemaphore.html#available)（ ） ，这个调用将阻塞直到有足够的资源可用。

**See also** [release](qsemaphore.html#release)（ ）[available](qsemaphore.html#available)（）和[tryAcquire](qsemaphore.html#tryAcquire)（ ） 。

```
int QSemaphore.available (self)
```

返回资源的当前可用的信号的数目。这个号码永远不能否定的。

**See also** [acquire](qsemaphore.html#acquire)（）和[release](qsemaphore.html#release)（ ） 。

```
QSemaphore.release (self, int n = 1)
```

发布_n_资源的信号量把守。

此功能可用于“创造”的资源也是如此。例如：

```
 [QSemaphore](qsemaphore.html) sem(5);      // a semaphore that guards 5 resources
 sem.acquire(5);         // acquire all 5 resources
 sem.release(5);         // release the 5 resources
 sem.release(10);        // "create" 10 new resources

```

**See also** [acquire](qsemaphore.html#acquire)（）和[available](qsemaphore.html#available)（ ） 。

```
bool QSemaphore.tryAcquire (self, int n = 1)
```

试图获取`n`资源把守的信号，并成功返回True 。如果[available](qsemaphore.html#available)（）\u003c_n_，这个调用会立即返回False不获取任何资源。

例如：

```
 [QSemaphore](qsemaphore.html) sem(5);      // sem.available() == 5
 sem.tryAcquire(250);    // sem.available() == 5, returns false
 sem.tryAcquire(3);      // sem.available() == 2, returns true

```

**See also** [acquire](qsemaphore.html#acquire)（ ） 。

```
bool QSemaphore.tryAcquire (self, int n, int timeout)
```

试图获取`n`资源把守的信号，并成功返回True 。如果[available](qsemaphore.html#available)（）\u003c_n_，这个调用会等待最多_timeout_毫秒资源变为可用。

注意：传递一个负数作为_timeout_相当于调用[acquire](qsemaphore.html#acquire)（ ） ，即该函数将一直等待资源变为可用，如果_timeout_是负的。

例如：

```
 [QSemaphore](qsemaphore.html) sem(5);            // sem.available() == 5
 sem.tryAcquire(250, 1000);    // sem.available() == 5, waits 1000 milliseconds and returns false
 sem.tryAcquire(3, 30000);     // sem.available() == 2, returns true without waiting

```

**See also** [acquire](qsemaphore.html#acquire)（ ） 。